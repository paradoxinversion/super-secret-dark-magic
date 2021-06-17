big o uses 4 criteria

the most common functions in ds: access, search, insert, delete

A time complexity equation works by inserting the size of the data set as an integer `n`, and returning the number of operations that need to be conducted by the computert before the function can finish.

we always use the worst case scenario

our n is going to have adverse effects on how many operations it takes

0(1): task will be completed in a single instruction, no matter the size of the data. the best and most unlikely in the wild time. Simple returning true from a function is an example of this.
0(log(N)): it's fast, and gets more efficient as N increases. It uses logarithmic algorithms, making it great for data operations that might be HUGE in terms of N. Binarty search is one example of this.
O(n): It's still in the 'okay' range. It's linear. For each increase in data, the instructions needed to act on that data increase by the same amount. A data set of 10 would take 10 instructions, and so forth. Anything above O(n) is getting into bad territory.
O(n log n): relative bad.
O(n^2) : polynomial
O(2^n): exponential

getting time complexity:
```
function sumUp(n){
  let result = 0; // runs 1
  for (let i = 1; i <= n; i++){ // runs 1
    result += i; // runs n
  }
  return result; // runs 1
}
```

T = 1 + 1 + n + 1 = 3 + n = 3 + 1 * n
1*n + 3 can be written as 1 * n + 3
now make it T=a*n+b

find the fastes growing term (a*n here)

remove the coefficient (a)
