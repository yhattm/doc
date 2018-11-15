http://www.statmethods.net/

https://www.tutorialspoint.com/r/index.htm

https://www.rstudio.com/products/rstudio/download-server/
http://serverip:8787

https://aws.amazon.com/tw/blogs/big-data/crunching-statistics-at-scale-with-sparkr-on-amazon-emr/

<pre>
par(mfrow=c(3,1))
X=seq(0:5:0.01)
plot(x)



X <- array(1:24, dim=c(3,4,2))
X <- array(0, dim=c(3,4,2))

matrix(data=NA, nrow=1, ncol=1, byrow=FALSE, dimnames=NULL)
X<-maxtrix(1:24, nrow=4, ncol=6, byrow=TRUE)

X1 <- c(1,2,3)
X2 <- c(4,5,6)
X3 <- c(7,8.9)
X <- cbind(X1,X2,X3)
Y=t(X)
X[,1]
X[2,]
eigen(Y)
Z <- Y%*%Y

id <- c(1,2,3)
age <- c(25,30,35)
X.dataframe  <- data.frame(id, age)
X.dataframe[2]
edit(X.dataframe)

Sex <- factor(c("M","F","F","M"))

Paul.Family <- list(name="Paul", wife="Iris", no.kids=3, kids.age=c(25,28,30), Sex, X.dataframe)
Paul.Family$kids.age
Paul.Family[[4]]

A <- c(1,2,3)
X <- a+2
{a <- c(1,2,3); x=a+2}

if (x>5) y=2 else y=4

X <- 1
switch(X, 5, sum(1:10))
Y <- "juice"
switch(Y, juice="Apple", meat="Pork")

X <- 0
for(i in 1:5) X <- X+I

While (I <= 10) (sum <- sum + I; I <- I + 1)


X <- array(1:24, dim = c(4,6))
apply(X, 1, sum)
apply(X, 2, sum)

X <- list(a=1:10, b=exp(-1:1))
lapply(X, sum)
sapply(X, sum)


setwd("c:/")
X <- read.table("X.csv", sep=",", header=TRUE)
write.table(X, "C:/X_File.csv", row.names=FALSE, col.names=FALSE, sep=",")
data()
data(iris)
str(iris)
summary(iris)


myfun <- function(X=1) { Y <- X+2; return (Y) }
X <- 1
myfun <- function(X) { X << -2;  print(X) }  # <<-改變外部物件的值

plot(y)
plot(x, y)
points(x, y)
lines(x, y)

par()


if (nchar(Sys.getenv("SPARK_HOME")) < 1) {
  Sys.setenv(SPARK_HOME = "/usr/lib/spark")
}
library(SparkR, lib.loc = c(file.path(Sys.getenv("SPARK_HOME"), "R", "lib")))
sparkR.session(master = "local[*]", sparkConfig = list(spark.driver.memory = "2g"))
s3df <- read.df("s3://infaniai/1.csv", "csv")

head(s3df)
names(s3df)
colnames(s3df)
row.names(s3df)
Rownames(s3df)
summary(s3df)

write.df()

</pre>