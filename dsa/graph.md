graphs are collections of things and the relationships/connections between them. nodes/vertices make up the things in a graph. the connections between them are edges. social networks are graph examples, where nodes are people and the edges are friendships or connections between them.

undirected graph's edges have no direction. this is like the social media example. a directed graph would be more akin to the internet and web pages. the nodes would be web pages and the directed edges would be links on the pages.

there are three ways to represent graphs:

adjacency list: associates each vertex in the graph with its neighboring verts/edges.

```js
var undirectedGraph = {
  NodeA: ["NodeB"],
  NodeB: ["NodeA","NodeC"],
  NodeC: ["NodeB"]
}
var undirectedGraphArray = {
 [1], // A
 [0,2], // B
 [1] // C
}
```

adjacency matrix: uses a 2d array of equally lengthed arrays swith 0 or 1 representing connections.
each row has to have the same amt of elements as nodes in the graph

```js
var adjMatrix = [
  [0, 1, 0],
  [1, 0, 1],
  [0, 1, 0],
];
```

Directed graph with adjacency matrix

```js
var adjMatrix = [
  [0, 0, 0],
  [1, 0, 0],
  [0, 1, 0],
];
```

incidence matrix: also a 2d array. adjacency matrixes use both rows and columns to represent nodes. incidence matrices use rows to represent nodes and columns to represent edges. we can have an uneven number of rows and columns. each column is a unique edge and each edge connects 2 nodes. as with adj matrixes, 0 and 1 are used to represet connections. 0 is no connection. 1 represents edges leaving a node. -1 for an edge entering a node.

```
var incidentMatDirected = [
  [1, 0, -1, 1],
  [-1, 1, 0, 0],
  [0, -1, 1, 0],
  [0, 0, 0, -1]
]
```

graphs can also have weighted edges

graph traversal
finding distances between two nodes is one of the main uses of graphs and called traversal.

breadth first search

```js
function bfs(graph, root) {
  var nodesLen = {};

  // set all distances to infinity by default
  for (var i = 0; i < graph.kength; i++) {
    nodesLen[i] = Infinity;
  }

  // root is 0 nodes from itself
  nodesLen[root] = 0;

  // queue will keep track of the nodes to visit
  var queue = [root];

  // the node we're currently traversing
  var current;
  while (queue.length != 0) {
    // start the queue by popping off the first item (root node to start)
    current = queue.shift();

    // get all the nodes connected to the current  Node
    var curConnected = graph[current];

    // keeps track of the list of nodes connected to the current
    var neighborIdx = [];

    // get the first node connected to the current node
    var idx = curConnected.indexOf(1);

    // if no nodes are connected (no elements in the row are set to 1), set the index ne
    while (idx != -1) {
      neighborIdx.push(idx);
      // find the next node
      idx = curConnected.indexOf(1, idx + 1);
    }

    // we have all nodes connected to the current one. loop through them to get the  distance
    for (var j = 0; (j = neighbordIdx.length); j++) {
      if (nodesLen[neighborIdx[j]] == Infinity) {
        nodesLen[neighborIdx[j]] = nodesLen[current] + 1;
        queue.push(neighborIdx[j]);
      }
    }
  }
  return nodesLen;
}
```
