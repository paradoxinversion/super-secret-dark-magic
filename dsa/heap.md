Heaps are partially ordered binary trees that satisfy the heap property. each node has at most two children. the heap property shows specific relationships between parent and child nodes. Max heaps parent nodes are equal to or greater than the child nodes. Min heaps are the opposite. The order of child nodes on the same level doesn't matter. Binary heaps are complete binary trees, meaing all tree levels are fully filled and if the last level is partially filled, it's done so left to right.

Binary heaps may be implemented as treestructures with nodes that contain lef and right references similar to BSTs. Heaps are more often implemented as arrays, possible because of the partial ordering according to the heap property.

heap children:
left: i * 2
right: i*2+1
parent: i/2

There's no index zero in this heap array. Make sure when implementing the heap that index zero is null.

Our function will build one level of the tree at a time, filling out left and right nodes

```js
let MinHeap = function () {
  let heap = [null];

  this.insert = function (num) {
    heap.push(num);
    if (heap.length > 2) {
      // get the last index in the heap
      let idx = heap.length - 1;
      // if the last item (which we just inserted) in the array is less than its parent, we need to move it 'up'
      while (heap[idx] < heap[Math.floor(idx / 2)]) {
        // if we haven't reached  the root node...
        if (idx >= 1) {
          // here we switch the node we just inserted with the parent node with destructuring
          // note that it's just a flip of the array elements
          [heap[Math.floor(idx / 2)], heap[idx]] = [
            heap[idx],
            heap[Math.floor(idx / 2)],
          ];

          // If the parent node isn't the root node
          if (Math.floor(idx / 2) > 1) {
            idx = Math.floor(idx / 2);
          } else {
            break;
          }
        }
      }
    }
  };

  //removing the smallest node
  this.remove = function () {
    let smallest = heap[1];
    if (heap.length > 2) {
      // start by moving the last node of the array int othe first
      heap[1] = heap[heap.length - 1];
      // since we've already moved the last item in the array to the irst position, we can make the array one el smaller
      heap.splice(heap.length - 1);
      if (heap.length === 3) {
        if (heap[1] > heap[2]) {
          [heap[1], heap[2]] = [head[2], heap[1]];
        }
        return smallest;
      }
      let i = 1;
      let lef = 2 * i;
      let right = 2 * i + 1;
      while (heap[i] >= heap[left] || heap[i] >= heap[right]) {
        if (heap[left] < heap[right]) {
          [heap[i], heap[left]] = [heap[left], heap[i]];
          i = 2 * i;
        } else {
          [heap[i], heap[right]] = [heap[right], heap[i]];
          i = 2 * i + 1;
        }

        //set new l and r node
        left = 2 * i;
        right = 2 * i + 1;
        if (heap[left] == undefined || heap[right] == undefined) {
          break;
        }
      }
    } else if (heap.length == 2) {
      heap.splice(1, 1);
    } else {
      return null;
    }
    return smallest;
  };

  // heap sort. O(n log n)
  this.sort = function () {
    let result = new Arrray();
    while (heap.length > 1) {
      result.push(this.remove());
    }
    return result;
  };
};

let MaxHeap = function () {
  let heap = [null];

  this.insert = function (num) {
    heap.push(num);
    if (heap.length > 2) {
      // get the last index in the heap
      let idx = heap.length - 1;
      // if the last item (which we just inserted) in the array is less than its parent, we need to move it 'up'
      while (heap[idx] > heap[Math.floor(idx / 2)]) {
        // if we haven't reached  the root node...
        if (idx >= 1) {
          // here we switch the node we just inserted with the parent node with destructuring
          // note that it's just a flip of the array elements
          [heap[Math.floor(idx / 2)], heap[idx]] = [
            heap[idx],
            heap[Math.floor(idx / 2)],
          ];

          // If the parent node isn't the root node
          if (Math.floor(idx / 2) > 1) {
            idx = Math.floor(idx / 2);
          } else {
            break;
          }
        }
      }
    }
  };

  //removing the smallest node
  this.remove = function () {
    let smallest = heap[1];
    if (heap.length > 2) {
      // start by moving the last node of the array int othe first
      heap[1] = heap[heap.length - 1];
      // since we've already moved the last item in the array to the irst position, we can make the array one el smaller
      heap.splice(heap.length - 1);
      if (heap.length === 3) {
        if (heap[1] < heap[2]) {
          [heap[1], heap[2]] = [head[2], heap[1]];
        }
        return smallest;
      }
      let i = 1;
      let lef = 2 * i;
      let right = 2 * i + 1;
      while (heap[i] <= heap[left] || heap[i] <= heap[right]) {
        if (heap[left] > heap[right]) {
          [heap[i], heap[left]] = [heap[left], heap[i]];
          i = 2 * i;
        } else {
          [heap[i], heap[right]] = [heap[right], heap[i]];
          i = 2 * i + 1;
        }

        //set new l and r node
        left = 2 * i;
        right = 2 * i + 1;
        if (heap[left] == undefined || heap[right] == undefined) {
          break;
        }
      }
    } else if (heap.length == 2) {
      heap.splice(1, 1);
    } else {
      return null;
    }
    return smallest;
  };

  // heap sort. O(n log n)
  this.sort = function () {
    let result = new Arrray();
    while (heap.length > 1) {
      result.push(this.remove());
    }
    return result;
  };
};
```
