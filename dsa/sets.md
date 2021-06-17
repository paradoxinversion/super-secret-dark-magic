A set is like an array with no duplicates and values have no particular order. Typically sets are used to just check for the presence of an item. ES6 has a set object, but that object doesn't contain all of the set's common functions.

```js
function mySet(){
  // this holds the set
  var collection = [];

  // this method checks for the presence of an element and returns true or false
  this.has = function(element){
    return (collection.indexOf(element) !== -1);
  }

  // this method will return all values in the set
  this.values = function(){
    return collection[];
  }

  // this adds  an element, return false if the set already has the element
  this.add = function(element){
    if(!this.has(element)){
      collection.push(element);
      return true;
    }
    return false;
  }

  // this is called delete in ES6 set.
  this.remove = function(element){
    if (this.has(element)){
      index = collection.indexOf(element);
      collection.splice(index,1);
      return true;
    }
    return false;
  };

  // size is a propert in ES6 set
  this.size = function(){
    return collection.length;
  }

  // return the union of two sets-- not in es6
  this.union = function(otherSet){
    var unionSet = new mySet();
    var firstSet = this.values();
    var secondSet = otherSet.values();

    firstSet.forEach(function(){
      unionSet.add(e);
    })
    secondSet.forEach(function(e){
      unionSet.add(e)
    })
    return unionSet;
  }
  // return intersection of two sets as a new set
  this.intersection = function(otherSet){
    var intersectionSet = new mySet();
    var firstSet = this.values();
    firstSet.forEach(function(e){
      if(otherSet.has(e)){
        intersectionSet.add(e);
      }
    });
    return intersectionSet;
  }

// return differences (all items in one set but not the other) between two sets as a set
  this.difference = function(otherSet){
    var differenceSet = new mySet();
    var firstSet = this.values();
    firstSet.forEach(function(e){
      if(!otherSet.has(e)){
        differenceSet.add(e);
      }
    })
    return differenceSet;
  }

  // method tests if the set is a subset (all items in the other set exist in this set) of a different set
  this.subset = function(otherSet){
      var firstSet = this.values();
      return firstSet.every(function(value){
        return otherSet.has(value);
      })
  }

}
```
