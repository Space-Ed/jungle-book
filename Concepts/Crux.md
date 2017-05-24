A Crux represents a bridging from one side of a membrane to another, usually from the inside of a cell to the outside. Therefore a crux will typically exist on two membranes. The purpose for this structure is to genericise the commonalities between different kinds of bridge. Other names for a crux could include bridge, port, passage, tunnel, oraface.. the essence is a permeable connection between two surfaces. 

In terms of implementation Crux is an abstract class from which 

A crux is usually created as a result of the construction form of a cell.

the essential information to this process is
1. What will the crux be referred to as
2. What role(contact-type) will the crux expose
3. What membrane will the crux be exposed on

the first should be the key of the form item that is reponsible for creating this crux, second is derived by using unambiguous prepositional statements

The contacts presented by a crux are produced in the construction of the specific type of crux. 

### Constraints 

### Invertability 
Every contact-type that is present within a crux should be invertable, that is given the string for one label type it will return the other. 


Jungle has a few builtin crux types and also presents the possibility of extending the framework to create  more fundamentally different cruxes.

- CallCrux: 
	this class provides the standard mechanism for interaction between cells, it is implemented to generically capture several models of interaction, including:
	- push mode(events):
		Here we are just making a call to some external subscribers with some data, not caring about any return values or whether the target state changes. In Jungle subscribers are the outgoing links of a caller contact. 
	- pull mode(requests):
		Here we are calling an external resource to fetch something, sometimes with a query argument. The response could be either asynchronous or synchronous.
	- tracable:
		In order for system debugging to make sense, we need to be able to follow chains of causation, not just know the stack trace. In asynchronous environments especially, the callers that gave bad data can be lost. 
	- multiplicity/blocking:
		In an asynchronous environment, our means of 
	-
push and pull mode, many to many, one to one, tracable, 

- AccessCrux: 

- 