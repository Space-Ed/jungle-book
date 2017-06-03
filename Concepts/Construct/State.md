State is the devil and the saint, let us for a moment consider each way

The bad: 
	- Side effects
	- Multiple influences
	- Nullable
	- Order of operation
	- Untracability
	- Global variable
	- repeated in many places and unreliably updated
	- Asynchronously resolved value

The good:
	- Extended Memory
	- Contextualization
	- appropriate cohesion of function
	- Scope
	- Change/Dynamic
	- customization
	- synchronously available
	- reliably mirrored
	

Jungle is, rather than being an attempt to seperate the problematic area of state to a sideline area, that is generally going to mean that components are not able to be recontextualised. Instead it creates a layer of indirection between the external modifiers and the internal state of a component.

Much like in statically typed languages that are able to declare properties as public, in Jungle the core state is only exposed through access/offer contacts, but going one step further it requires the explicit creation of links that will create the connection that allows anything to access anything else. That is the same for property access as it is for calling as it is for full blown synchronization. This strategy, although creating a more arduous path to getting at state from outside, does help to mitigate some of the downsides of state.

This can be made very powerful by using patterns of interconnection(rules) that actually reflect the way that components are connected, rather than leaving it to the components themselves. That reduces the work in creating the connections of dependency to O(1) while the number of connections becomes O(Nˆ2) all the while 


Tracability.

If a component chooses to make an aspect of its being variable to some context by exposing an offering contact, it can then upon its failure report not just it's final state but also who could be responsible by following those links to culprits. Furthermore state can be naturally converted into reactive processes, that means that it creates a situation where a call in can drop off or pick up values and a call out can be created upon the change to or request of a value. Interaction of this kind can be traced as it flows through a network, even as it is combined and transformed.

Order Of Operations
A large source of error within computer programs. Sometimes depending on the state, a different set of actions are valid, and it is actions drive these differences. This means the actions are not always permutable. It is no actions fault that a failure occurs, a bug can only be fixed by finding the correct permution of actions, that is in the worst case, a factorial explosion of possibilities. In Jungle we use objects to configure the entire structure, and furthermore the interactions are declarative, this means that additions after the fact do not have different. Jungle also provides facility for modes.


  


