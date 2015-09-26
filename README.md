# Getting-and-Cleaning--Project
G&amp;D Project work
RR_subject_dataset <- function() {
  
subject_test <- read.table("C:/Users/Radha/Desktop/UCI HAR Dataset/test/subject_test.txt")
subject_train <- read.table("C:/Users/Radha/Desktop/UCI HAR Dataset/train/subject_train.txt")
subject_merged <- rbind(subject_train, subject_test)
names(subject_merged) <- "subject"
subject_merged
}

head(subject_test)
head(subject_train)  
head(subject_merged)

RR_X_dataset <- function() {
X_test <- read.table("C:/Users/Radha/Desktop/UCI HAR Dataset/test/X_test.txt")
X_train <- read.table("C:/Users/Radha/Desktop/UCI HAR Dataset/train/X_train.txt")
X_merged  <- rbind(X_train, X_test)
}

head(X_merged)
RR_y_dataset <- function() {
y_test <- read.table("C:/Users/Radha/Desktop/UCI HAR Dataset/test/y_test.txt")
y_train <- read.table("C:/Users/Radha/Desktop/UCI HAR Dataset/train/y_train.txt")
y_merged  <- rbind(y_train, y_test)
}



RR_selected_measurements <- function() {
features <- read.table("C:/Users/Radha/Desktop/UCI HAR Dataset/features.txt", header=FALSE, col.names=c("id", "name"))
  
feature_selected <- grep("mean\\(\\)|std\\(\\)", features$name)
filtered_dataset <- X_dataset[, feature_selected]
names(filtered_dataset) <- features[features$id %in% feature_selected, 2]
filtered_dataset
}

X_filtered_dataset <- RR_selected_measurements()

activity_labels <- read.table("C:/Users/Radha/Desktop/UCI HAR Dataset/activity_labels.txt", header=FALSE, col.names=c("id", "name"))

y_dataset[, 1] = activity_labels[y_dataset[, 1], 2]
names(y_dataset) <- "activity"


full_dataset <- cbind(subject_dataset, y_dataset, X_filtered_dataset)
write.csv(full_dataset, "full_activity_with_names.csv")

head(full_dataset)

measurements <- full_dataset[,3:dim(full_dataset)[2]]
ty_dataset <- aggregate(measurements, list(full_dataset$subject, full_dataset$activity), mean)
names(ty_dataset)[1:2] <- c("subject", "activity")
head(ty_dataset)
write.csv(ty_dataset, "fn_ty_dataset.csv")
write.table(ty_dataset, "fn_ty_dataset.txt")

