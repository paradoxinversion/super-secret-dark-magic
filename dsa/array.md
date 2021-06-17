arrays: store values of the same type
items in arrays are caleld elements
arrays are stored in coniguous memory
arrays have
name
type
size - fixed upon creation and represents the total number of elements that can be stored. cannot be changed.

parallel arrays are 2 or more arrays with the same number of elements and corresponding values in their indexes. especially useful for storing different types of data about the same entity.

Access: O(1)
Insert: 0(n)
Delete: O(n)
search: 0(n) (most of the time)

insert and delete are O(n) because you have to shift every element after the index you want to insert the value at to the right one space

prost: good for similar data, O(1) access, very basic
cons: size is fixed, insert & delete are inneficient, can waste space
