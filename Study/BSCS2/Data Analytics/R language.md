# R Syntax Reference

## Basic Operations
### Assignment
```r
x <- 5     # Preferred method
y = 10     # Alternative assignment
15 -> z    # Rightward assignment
```

### Comments
```r
# Single-line comment

# For multi-line comments,
# use multiple # symbols
```

## Data Types
### Atomic Vectors
```r
num <- 3.14            # Numeric
int <- 5L              # Integer
char <- "hello"        # Character
bool <- TRUE           # Logical (must be uppercase)
```

### Special Values
```r
NA    # Missing value
NULL  # Null object
NaN   # Not a Number
Inf   # Infinity
```

## Data Structures
### Vectors
```r
v1 <- c(1, 2, 3)                 # Combine
v2 <- 1:5                        # Sequence
v3 <- seq(1, 10, by = 2)         # Custom sequence
v4 <- rep(c(1,2), times = 3)     # Replicate
```

### Matrices
```r
mat <- matrix(1:6, 
            nrow = 2, 
            ncol = 3)
```

### Lists
```r
my_list <- list(
  name = "Alice",
  age = 30,
  scores = c(95, 89, 92)
)
```

### Data Frames
```r
df <- data.frame(
  name = c("Alice", "Bob"),
  age = c(25, 30),
  score = c(95, 88)
)
```

### Factors
```r
factor_var <- factor(c("low", "medium", "high"))
```

## Control Flow
### Conditional
```r
if (x > 10) {
  print("Large")
} else if (x > 5) {
  print("Medium")
} else {
  print("Small")
}
```

### Loops
```r
# For loop
for (i in 1:5) {
  print(i)
}

# While loop
while (x < 10) {
  x <- x + 1
}
```

## Functions
### Basic Function
```r
add <- function(a, b) {
  return(a + b)
}
```

### Anonymous Function
```r
squared <- function(x) x^2
```

## Subsetting
### Vectors
```r
v[3]            # Third element
v[-2]           # All except second
v[v > 3]        # Logical subsetting
```

### Data Frames
```r
df[1, ]         # First row
df[, "age"]     # Age column
df$score        # Score column
df[df$age > 25, ]  # Filter rows
```

## Common Operations
### Arithmetic
```r
5 + 3
10 / 2
2^3
```

### Logical
```r
TRUE & FALSE   # AND
TRUE | FALSE   # OR
!TRUE          # NOT
```

## Input/Output
### Working Directory
```r
getwd()
setwd("/path/to/directory")
```

### Reading Data
```r
read.csv("data.csv")
read.table("data.txt")
```

## Packages
```r
install.packages("dplyr")  # Install
library(dplyr)             # Load
require(ggplot2)           # Alternative load
```

## Help System
```r
?mean         # Help for function
help("sum")   # Alternative help
example(plot) # See examples
```

## Basic Statistics
```r
mean(v)
median(v)
sd(v)
summary(df)
```

## Common Functions
```r
length(v)
names(df)
str(df)
head(df)
tail(df)
```

## Basic Plotting
```r
plot(x, y)
hist(v)
boxplot(v)
barplot(table_data)
```


> [!info] see also [[Data Analytics]]