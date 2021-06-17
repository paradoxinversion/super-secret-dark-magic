Queues are another data holding structure like stacks, but differ a bit. Stacks are Last in First Out (LIFO) and Queue are First in First Out (FIFO). A queue can be implemented with a js array

tail: back
head: front
access: 0(n)
search: O(n)
insert& delete: O(n)

common uses: job scheduling, pritner queuing

```js
function Queue() {
  collection = [];
  this.print = function () {
    console.log(collection);
  };

  // add an element to the tail of the queue (el length-1)
  this.enqueue = function (element) {
    collection.push(element);
  };
  // remove element from the head (el 0)
  this.dequeue = function () {
    return collection.shift();
  };

  this.front = function () {
    return collection[0];
  };

  this.size = function () {
    return collection.length;
  };

  this.isEmpty = function () {
    return collection.length === 0;
  };
}
```

Priority queues take a priority value into account, where higher priority items are earlier in the queue

```js
function PriorityQueue() {
  var collection = [];
  this.printCollection = function () {
    console.log(collection);
  };
  this.enqueue = function (element) {
    if (this.isEmpty()) {
      collection.push(element);
    } else {
      var added = false;
      for (var i = 0; i < collection.length; i++) {
        // priority check here
        if (element[1] < collection[i][1]) {
          collection.splice(i, 0, element);
          added = true;
          break;
        }
      }
      if (!added) {
        collection.push(element);
      }
    }
  };

  this.dequeue = function () {
    // just return the value without the priority (index 0)
    var value = collection.shift();
    return value[0];
  };

  this.front = function () {
    return collection[0];
  };

  this.size = function () {
    return collection.length;
  };

  this.isEmpty = function () {
    return collection.length === 0;
  };
}

var pq = new PriorityQueue();

// note the two element array passed in
pq.enqueue(["Item 1", 2]);
pq.enqueue(["Item 2", 1]);
```
