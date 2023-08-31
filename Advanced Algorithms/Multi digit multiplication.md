#### Lattice Multiplication Algo
```
multiply(X[0 ... m - 1], Y[0 ... n - 1]) {
//create a new array Z[0 ... ... m + n - 1] with 0's as initial values of the array
	for i ranging from 0 to m-1 {
		carry = 0
		for j ranging from 0 to n-1{
			Z[i+j] = Z[i+j] + carry + X[i] * Y[j]
		}
	}
}
```
