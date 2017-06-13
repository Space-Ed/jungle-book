The prospect here is to understand how a functional approach to the jungle state model could have legs. The key idea is that all changes to state are actually the application of a composition function that produces new state by mixing with the old. That means if you grab an object it will not change but if you get the same one again, it could have been updated. such a system requires that changes at the most granular level will percolate out and become updates at the root level, access is now charged with the detection of a change, and whether to return the unchanged value or a new one.


This is all quite difficult to pull off in an environment that is quite intrinsically modifiable. 
# Primary Function Categories

## reduce:
A function for taking a value and joining it to another.

## map
function for transforming a value

## compose:
A function for creation of complex value from simple values? Simple objects are

## negate:
return the opposite of a value. 

## terminate:
return whether the item is treated as a terminal, or complex

# Complex functions

The operations on complex objects are meld, mask, invert.

## meld:

- union keys
- reduce commonalities, 
- include differences 
- default reduce is take latest

## mask: 
- intersection of keys
- reduce commonalaties
- drop differences
- default reduce to take identical values.

## Invert
- reversal of existing values.
- terminal inversion function defaults to deletion.
- could turn positive numbers to negative or invert OT


# Mondadification
by having a revolving state object we introduce prospects for a revolving stack of function application that models a stateful system. The below operations can be updates or projections of the state. All of these 'given values' are preceded by a map applications of input values.

## blend:
take a given value and meld it into the existing on

## subtract:
take a given value and use it to hide a selection of values in the output. internally inverts the given value and melds it. 

## diff:
take a given value and provide the change by which to reach it from the existing. Technically inverts the exitsing and melds the new into it.

## screen
take a given value and use it to mask with the existing, thereby only showing values that appear in both

## dump
express the existing value, creating a replication. 

# Advanced Features.

## Accessibility / Proxification

taking the existing value of the above model and exposing it to be modifiable and readable from an external context, the modifications all being therefore turned into blend operations and reads into dumps

## Asynchronisation
This development feature allows the operations aforementioned to take place over some time, therefore when they are relied upon by other processes they must be exposed as promises.

## Hierarchicalization
this has been achieved through the blender to date, it is also recursibility of the structure, now what we will see is the internalisation of a structure that may have object operations applied to an arbitrary depth, and allow each layer to have distinct functional form. The form selected may even be contingnet on the value. 

There are perhaps two ways of dealing with this. One is what blender does that is maintains a crown and a form, that must therefore cast everything into a blender to be part of the structure. This seems to break our shallow functional behaviour. 

The alternative could be to have terminators that specifically check for complex object, and reducers that have a special treatment of other blender structures. In ths way we can perform an operation on one, with the other(which could be a blender dump). That way seems sensible. But how are complex but plain objects treated? Must they be cooerced? Perhaps not, so long as we can retain the functional operation essence, then we would apply the appropriate binary operation. 

The interplay this has with the subcomponent structure is immense, we must take the above step one further in two ways. 
a) Potentially the access point is actually a proxy value
b) potentially the cell provides its own blend strategy

## Lazification
Extend upon accessibility and provide a lazified access that only fulfills operations once they are relied upon to complete.

## Historification
Hold onto the history of all updates and allow operations upon it, following is an arbitrary set of operations enabled by the system. 

- tagging: identifying stages that can be referred to 
- reset: ability to go to tagged version 
- branching : ability to have different forward paths 
- roll back: undo/turn back time. 

when updates occur actually they are applied, but once in history no updates will change those things and the changes accumulated will operate on a replication in a monadic way.


now we must internalise the links of flow through the structure so that scanning is possible. the scanning could be undertaken by a designator language. Like with our monadic operations they can both be expressive or updating, updating it essentially setting the head of the structure, that would be the target for access. operations like roll back are just special cases, an undo/redo system follows from tagging every undoable change.



## Synchronization
