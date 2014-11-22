Assignment-2
============
cacheSolve <- function(x, ...) {
  
  ## Return a matrix that is the inverse of 'x'
  m <- x$getInverse()
  
  ## return the inverse if its already set
  if( !is.null(m) ) {
    message("getting cached data")
    return(m)
  }
  
  ## Get the matrix 
  data <- x$get()
  
  ## Calculate the inverse 
  m <- solve(data) %*% data
  
  ## Set the inverse to the object
  x$setInverse(m)
  
  m
}
