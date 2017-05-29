
The topic is how those values that are particular to a subclass of entity and have a certain role within their behaviour that make them special, and are not treated as generic subconstructs. 


The Zero-Sum game here is a balance between **Added Complexity** and **Name Collision Risk**

The properites that are set to be special in the core model are as follows.

Entity
+ basis
+ domain

Cell
+ prime
+ dispose

Synth
+ resolve
+ carry

Weave
+ medium names

configurations
    - meta membrane/property
        - existance
        - exposure (mesh/shell)
        - reach (domain visor)
        - limitation (methods filter)
    - synchronization.
    - crux infliction/self infliction.
    - offering state(outer, child, nominalized)


#### Mitigate Added complexity

If we prioritise the reduction of complexity we would throw all properties in the single spec object, that would in turn mean that more keywords for the specification need to be reserved.


The keywords would be defined as a semistatic property of the extending classes, that is a set of keywords that are going to be treated differently so should not be used as constructs. 

The problem would be the potential for misuse of those properties, "Why the hell isn't that construct working!" where it is not feasible to distinguish an accidental value from a deliberate one.  

### Mitigate Keyword Sprawl

Because extending the core class is likely, it is hard to expect the extent of the proplem that could exist, the way to genericise configuration values is to reserve only one special keyword that is "form", which is then matched to a method of the class. 

This method would be called at construction, rather than prime, so that it preempts the creation of all other cruxes.

A corresponding extract and diposal method would be needed to manage the creation of the item. 

a possibility is to actually require every kind of composite to have a form constructor method that creates a construct, this construct is assigned to it's own property and is then bound to be the first primed and last disposed, and extracted as 'form'. In short it is conformant to other constructs, but it's basis constructor is fixed to the class by a method instead of determined by the basis. This means the form can be turned into a cell, create properties in the parent, and populate the structure given from constructor, with the contents of the form cache.

This is seen as a preferable option and reduces the likeliness of having to create complex policy objects. And even from a configuration syntax perspective it helps keep the code structured apart from the generic entries. 

Moreover because the form object could be cellularised, it's modification through the membrane or injection into context are both left as implementations of the induct method.

