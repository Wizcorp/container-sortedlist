# container-sortedlist
SortedList implementation in Javascript

To manage a sorted list of elements. Best use case: elements are frequently removed from the list or the property on which they are sorted can slightly change.
Complexity in O(1) for removal.

Note: Benchmarks seem to show that iteration seem as fast as array iteration.

To **instanciate** a new list:
``` javascript
// In this example, myList will hold elements sorted by zIndex
function myComparisonFunction(a, b) {
	return a.zIndex - b.zIndex;
}

var myList = new SortedList(myComparisonFunction);
```

To **add** an element:
``` javascript
var myObjectReference = myList.add(myObject);
```

To **remove** an element:
``` javascript
myList.removeByReference(myObjectReference); // O(1)
// or
myList.remove(myObject); // O(n)
```

To **reposition an element**:
``` javascript
myList.reposition(myObjectReference);
```

To **move an element to the beginning of the list**:
``` javascript
myList.moveToTheBeginning(myObjectReference);
```

To **move an element to the end of the list**:
``` javascript
myList.moveToTheEnd(myObjectReference);
```

To **iterate** through the elements:
``` javascript
for (var node = myList.first; node !== null; node = node.next) {
	node.object += 1;
}
```

To **apply a treatment** on all the elements in sorted ordered:
``` javascript
myList.forEach(function (object) {
	console.log(object);
});
```

To **apply a treatment** on all the elements in opposite sorted ordered:
``` javascript
myList.forEachReverse(function (object) {
	console.log(object);
});
```

To **convert into an array**:
``` javascript
var myArray = myList.toArray();
```