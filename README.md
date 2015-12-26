# programming_assignemt_2


## Makecahematrix function creates an special object matrix and calculates the inverse 
## of this matrix;storing it in the cache memory, making it available for a further call.

x<-matrix(x = matrix())


makeCacheMatrix <- function(x = matrix()) {
  inv <- NULL
  set <- function(y) {
    x <<- y
    inv <<- NULL
  }
  get <- function() x
  setinverse<- function(solve) inv<<-solve
  getinverse <- function() inv
  list(set = set, get = get,
       setinverse = setinverse,
       getinverse = getinverse)
}



## THis function creates a "special object" aiming to acquire the inverse matrix of 
## a given matrix. If not it computes to calculate the inverse matrix instead.

cacheSolve <- function(x, ...){
  inv <-solve(x)
  if (!is.null(inv)) {
    message("getting cached matrix")
    return(inv)
  } 
  data<-x$get()
  inv<-solve(data)
  solve (inv)
  inv
}
