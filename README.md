### Introduction

makeCacheMatrix <- function(x = matrix()) {
    zz <- NULL
  set <- function(y) {
          x <<- y
          zz <<- NULL
  }
  get <- function() x
  setinverse <- function(inverse) zz <<- inverse
  getinverse <- function() zz
  list(set = set,
       get = get,
       setinverse = setinverse,
       getinverse = getinverse)
}

cacheSolve <- function(x, ...) {
  zz <- x$getinverse()
  if (!is.null(zz)) {
          message("getting cached data")
          return(zz)
  }
  data <- x$get()
  zz <- solve(data, ...)
  x$setinverse(zz)
  zz
}


For this assignment, assume that the matrix supplied is always
invertible.

In order to complete this assignment, you must do the following:

1.  Fork the GitHub repository containing the stub R files at
    [https://github.com/rdpeng/ProgrammingAssignment2](https://github.com/rdpeng/ProgrammingAssignment2)
    to create a copy under your own account.
2.  Clone your forked GitHub repository to your computer so that you can
    edit the files locally on your own machine.
3.  Edit the R file contained in the git repository and place your
    solution in that file (please do not rename the file).
4.  Commit your completed R file into YOUR git repository and push your
    git branch to the GitHub repository under your account.
5.  Submit to Coursera the URL to your GitHub repository that contains
    the completed R code for the assignment.

### Grading

This assignment will be graded via peer assessment.
