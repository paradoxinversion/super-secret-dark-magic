Stack
last in, first out
used in browsers such as when navigating back to previous sites
functions: push (add to the top fo the stack), pop (remove from the top of the stack), peek (display top element), length (return the amount of elements)

Using stacks to solve palindromes:

```javascript
var letters = []; // this is the stack
var word = "racecar";
var reverseWorde = "";

// put the letters of the word into the stack
for (var i = 0; i < word.length; i++) {
  letters.push(word[i]); // pushing onto the top of the array-as-stack
}

// pop off the stack in reverse order
for (var i = 0; i < word.length; i++) {
  rword += letters.pop(); // popping from the array-as-stack
}

if (reverseWord === word) {
  console.log("Yes");
} else {
  console.log("no");
}
```

Stack implementation in js (but you can use arrays as stacks, so )

```js
var Stack = function () {
  this.count = 0;
  this.storage = {};

  // Adds a value to the end of the stack
  this.push = function (value) {
    this.storage[this.count] = value;
    this.count++;
  };

  // Removes and Returns the value at the end of the stack
  this.pop = function () {
    if (this.count === 0) {
      return undefined;
    }

    this.count--;
    var result = this.storage[this.count];
    delete this.storage[this.count];
    return result;
  };

  // Returns the value at the end of the stack, but does not remove it
  this.peek = function()[
    return this.storage[this.count-1]; // make sure to use -1 to get the last item.
  ]
  this.size = function () {
    return this.count;
  };

  // also contains? takes an object, but does modify the stack
};
```

Use as

```js
var myStack = new Stack();
mystack.push(1);
mystack.peek();
``;
etc;
```

Access: O(n) (biggest stack drawback)
Search: O(n)
Insert: O(1)
Delete: O(1)

stacks are the backbone of recursion.
also back-paging and undo/redo.
