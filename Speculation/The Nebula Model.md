This version has arisen out of some difficulties in harmonising the IO model with the construction model, there were some assumptions from legacy versions that have pervaded which now must be rooted out to allow the kind of extensibility we crave. 

## Status
Hexamatic IO has been implemented and a cell has been implemented with one kind of hook construct to exhibit the way the interaction occurs, there is a draft of how contextual injection could work using a bridging visor

## Motivations

Simplification of IO components,
Ability to integrate with state, 
compatibility with visors.

## Actions

Dissolve the Crux
- most importantly in the membrane, methods must be replaced

Dissolve Contact type strings
- everywhere the word 'role' is is probably affected

Implement contact based system
- Contact Class

Medium must now use instanceof in its suppose check 

Genericise Designation and have membrane inherit from it.
- Groups and Terminals. Complex and simple. 
- Implement visors
- 

## Effects

- contacts are extensible.
- no more contact types.
- designation can be used by other systems.
- injection is genericised, not requiring specific contacts. 
- inner and outer inversions must be fate bound to the original.


### watchers and visors of designation spaces

Watchers were previously exclusively the host of the membrane or the parent membrane, now with the advent of a visor, the watcher for a certain event could be somewhere else. 

It makes one wonder, was it ever neccessary to have exactly one watcher, exactly two just seems weird. What if there were any number of watchers? and any number of visors.

The watcher would be a layer, that remembers what the membrane is being viewed as.

All watchers are watchers of the primary sector, visors that appear could have the ability to remove contacts from the primary sector. That seems odd, it makes one think that there should be visors only when they exist from the beginning of the membrane's lifetime. 

The exclusive watcher is the way that a contact is known only by one possible designation at each level.

Watchers.
- The mesh is a watcher that is concerned with following rules of connnection.
- a cell may watch it's own shell to know the interactions that are being forced upon it.
- In a perceptible space there could be many watchers of a situation, primarly the watching of state, but what of the watching of other actors?




