common structure where data is stored in nodes. each node has a reference to its element and the next node in the list.

arrays vs linked lists:
arrays are fixed size, linked lists are dynamic
arrays have ineffiecient insertions and deletions, LL's don't
arrays have random access (indexing), LL's don't
arrays might waste memory, lls don't
arrays store things in contiquous memory, so sequential search is faster. the opposite is true for LLs

Each ll has a head and a size

access: O(n)
search: O(n)
insert: O(n) or O(1)
delete: O(n) or O(1)

used for: backing of other data structures (stacks, queues, etc), playlists with data (titles, length, the song file, etc), photo galleries (where each photo points ot the next in the list). symbol table management in designing compilers. Uses in switching apps and programs in OS's using circular linked lists.

```js
function LinedList() {
  var length = 0;
  var head = null;

  var Node = function () {
    this.element = element;
    this.next = null;
  };

  this.size = function () {
    return length;
  };

  this.head = function () {
    return head;
  };

  this.add = function (element) {
    var node = new Node(element);
    if (head === null) {
      head = node;
    } else {
      var currentNode = head;
      while (currentNode.next) {
        currentNode = currentNode.next;
      }
      currentNode.next = node;
    }
    length++;
  };

  this.remove = function (element) {
    var currentNode = head;
    var previousNode;
    if (currentNode.element === element) {
      head = currentNode.next;
    } else {
      while (currentNode.element !== element) {
        previousNode = currentNode;
        currentNode = currentNode.next;
      }
      previousNode.next = currentNode.next;
    }
    length--;
  };

  this.isEmpty = function () {
    return length === 0;
  };

  this.indexOf = function () {
    var currentNode = head;
    var index = -1;

    while (currentNode) {
      index++;
      if (currentNode.element === element) {
        return index;
      }
      currentNode = currentNode.next;
    }
    return -1;
  };

  this.elementAt = function(index){
    var currentNode = head;
    var count = 0;
    while (count < index){
      count ++;
      currentNode = currentNode.next
    }
    return currentNode.element;
  }

  this.addAt(index, element){
    var node = new Node(element);
    var currentNode = head;
    var previousNode;
    var currentIndex = 0;

    if (index > length){
      return false;
    }
    if (index === 0){
      node.next = currentNode;
      head = node;
    }else {
      while (currentIndex < index){
        currentIndex++;
        previousNode = currentNode;
        currentNode = currentNode.next;
      }
      node.next = currentNode;
      previousNode.next = node;
    }
    length++;
  }

  this.removeAt(index){
    var currentNode = head;
    var previousNode;
    var currentIndex = 0;
    if (index < 0 || index >= length){
      return null;
    }
    if (index === 0){
      head = currentNode.next;
    }else {
      while(currentIndex < index){
        currentIndex++;
        previousNode = currentNode;
        currentNode = currentNode.next;
      }
      previousNode.next = currentNode.next;
    }
    length --;
    return currentNode.element
  }
}

var test = new LinkedList();
test.add("Uno");
test.add("Dos");
test.add("Tres")
```
Doubly linked lists can traverse both ways. DLL's have previous pointers as well as next pointers. 

Same Big O as linked lists.

Examples: browser caches, undo/redo in programs, open recent functionality