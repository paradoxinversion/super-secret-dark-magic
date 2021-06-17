Creational patterns - 
Factory: Creates related objects without the need for a constructer, handling implementation (ie what to instantiate) under the hood
Builder - Allows a client to construct a complex object by specifying the type and content. Construction details are hidden from the client. 
Structural Patterns
Prototype - The Prototype Pattern creates new objects, but rather than creating non-initialized objects it returns objects that are initialized with values it copied from a prototype - or sample - object. The Prototype pattern is also referred to as the Properties pattern. 

Behavioral Patterns
Observer - Subscription based pattern where objects subscribe to an event and get notified when it occurs-- this is the backbone of event driven programming and js. Promotes OOD and loose coupling. Has a subject, which maintains a list of observers, implements an interface letter observers (un)subscribe, and sends notifications to observers when its state changes. Observvers have a function sig that can be invoked whe nSubject changes.

Command Pattern- The Command pattern encapsulates actions as objects. Command objects allow for loosely coupled systems by separating the objects that issue a request from the objects that actually process the request. These requests are called events and the code that processes the requests are called event handlers. Suppose you are building an application that supports the Cut, Copy, and Paste clipboard actions. These actions can be triggered in different ways throughout the app: by a menu system, a context menu (e.g. by right clicking on a textbox), or by a keyboard shortcut. Command objects allow you to centralize the processing of these actions, one for each operation. So, you need only one Command for processing all Cut requests, one for all Copy requests, and one for all Paste requests.  Because commands centralize all processing, they are also frequently involved in handling Undo functionality for the entire application. 
ALSO FOR JS:

composite pattern:  The Composite pattern allows the creation of objects with properties that are primitive items or a collection of objects. Each item in the collection can hold other collections themselves, creating deeply nested structures.

A tree control is a perfect example of a Composite pattern. The nodes of the tree either contain an individual object (leaf node) or a group of objects (a subtree of nodes).

All nodes in the Composite pattern share a common set of properties and methods which supports individual objects as well as object collections. This common interface greatly facilitates the design and construction of recursive algorithms that iterate over each object in the Composite collection. 
Constructor design pattern

Module design pattern (incapsulate code!), and allow public/private vars