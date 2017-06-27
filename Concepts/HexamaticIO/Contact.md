
A contact is an object that rests on the outer surface of the membrane, and is designable by a designation string from a . It represents a point of exposure that can be joined onto other things. It is one critical part of a channel essentially they are the  nodes of a directed graph where the edges are links formed in a medium, and the terminals are the cells where they are rooted.

A callback function is an example of a contact, that can be joined onto another kind of contact, that is a callable. The contact is only able to communicate it's occupied(capped) status, whether this link takes place and how it takes place are the roles of a [Mesh](Mesh.md) and [Medium](Medium.md) respectively.

A contact must provide two methods

Invert: from this contact create a partnering contact that represents the opposite side, to be inserted in  the opposite side of the membrane. Usually this creates a sympathetic pair of contacts that represent the directionality of the contact going a certain direction across the membrane. It is also possible that a contact inverts to itself, or it is uninvertable, the membrane does not care. To make a quick analogy a revolving door looks the same on both sides, and there is really nothing behind a screen, but a 

Inject: given an object and a key insert a property representation of the contact. This is the means by which the end points finally make contact with the [Nucleus]() of a cell. The context of injection is typically the nucleus, but it could be any of the exposed facets of the cell in the Anchor.

Additionally the contact provides generic capability to be hidden, this act informs its host membrane to not allow it to be designated, and if it becomes hidden it is effectively removed, and when unhidden it is effectively added again, triggering the respective events to the watchers of the membrane.

Besides being hidden the contacts store the state of exclusiveness to other parts of the io system, these exclusivity flags are: 
- plugged(link exclusive) : when a contact is only allowed one connection to it, the medium will register this on the contact when it creates that link, this means that when media try to make links to it that the whole mesh will go down. 

- claimed(medium exclusive): sometimes a medium requires exclusive access to a contact while allowing many links, a claim will create the error when a medium attempts to claim a contact already claimed

-  gloved(rule exclusive): created by using the bar in the link rule defined in the mesh, this allows you to ensure that a contact will only be used in a way you expect, it will prevent other rules from applying, but if another glove appears it is an error


### Generic Contact Types

- Call:
	the standard mechanism for transporting data an an asymetric way through a system, the parametrisation of a call contact creates the many different styles of endpoint integration and possible models of io. This includes

__push and pull__: a call expecting no return is a push, it integrates by reaction and depositing
	- deposit: when the push of some data reaches a cell the value is assigned to a property of the nucleus. That can then be retrieved. 
	- reaction: When the value of a property is set it causes a push to occur.

push is the model of publish subscribe and pull is the model of request response

	
__Async and sync__: pull calls can be synchronous whereby they will available to represent retrieval or provision of a value integrating as a getter or get in the nucleus. 

asynchronous pull is when the value we get is returning a promise of a value rather than an actual value. 

__hooked__: When a call contact is hooked it means that the end point is a function that operates within the context. An outgoing call is hooked by hook:true, this will make a function that makes the call available within the nucleus. an incoming calls is hooked by hook:function(value){..} that means you provide the function that will be called in the context of the nucleus. 


- Access:
the access contact represents a 

- CoResponsive
- Synchroniser

### Esoteric Contact Types

- Audio Bus
- Physical Collision
- 