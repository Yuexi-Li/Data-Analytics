# matrix math numpy
## datatypes 

- scaler 
  `s= np.array(5)` 
- vector 
  `v = np.array([1,2,3])` 
- matrix 
`m = np.array([[1,2,3], [4,5,6], [7,8,9]])`
- tensor 
`t = np.array([m,s,v])`
## shape
- shape 
  `v.shape`
- reshape 
  `v.reshape(1,4)`
  
## calculation 
### element wise operation 
- requied matrices to be same size  
- `np.multiple(m,n)` or `m * n`
### matrix product 
- required size`\((m,n) * (n, p)\)`
- `np.matmul(a, b)`
- if the matrices are two dimensional
  `dot` function  are the same 
  `np.dot(a,a)`
### matrix transpose 
- turn `(m,n)` to `(m,n)`
- `n.T`