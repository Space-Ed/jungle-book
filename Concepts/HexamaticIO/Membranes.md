In biology a membrane is the outer wall of a cell, it is one of the fundamental parts of a cell, in fact it was the formation of a division between the inside and the outside that made it possible for processes to become distinct from their environment, for the repliction race between these distinct processes. In the domain of software we don't have a lipid bilayer and various intervening portal molecules, instead we have what are usually called interfaces or port hosts, or standard io streams. They exist in various forms and levels from physical cables and network protocols through to virtualised interfaces of a platform, and type interfaces in statically typed languages. We choose to use "Membrane" instead of this generic term not just to avoid overloading, but because Jungle seeks to rise above some of the fundamental assumptions of interfaces, and creates a very distinctive model.

In most kinds of software and hardware the nature of interfaces is that they are built to have a certain form for the entire lifespan of their use, they cannot be extended at either end.

This is for very good reason, in most software we have a situation where either side of our interface is relying on the other to be a certain way, the definition of an interface, must precede the definition of either implementation. In other words there is a contract between these parties that dicates the possible kinds of interaction and must be signed by both before it is considered safe to interact, if those parties want to change the way they interact they must create and sign a new contract, in software this usually means creating changes affecting multiple hosts across many source files, and restarting parts or the entirety of a system.

Membranes and the other Jungle IO constructs provide a way of creating dynamic interfaces that can change over time, without requiring recompilation, pushing to repositories, restarting the program, even without reconstructing the cell it envelops.

## Structure

```js
{
    contacts:{
        contact-type: {
            label: Crux //every crux is stored acording to the contact it exposes on the membrane and its label
        }
    subranes:{
        sublabel: Membrane //a membrane is a recursive object, it can contain other membranes under a label
    },
    host:MembraneHost,
}
```

## ownership & notification
a membrane has a single owner called a membrane host, that is notified of changes upon the membrane and also defines the policy about what changes are possible. This is how a membrane is able to grow within a system because the host will be capable of reacting to the changes. For example the host could be a [Mesh](Mesh.md) that reacts to an addition by creating a link

## sub-membranes\(subranes\)

A membrane can contain other membranes, this provides a natural way of grouping cruxes and moving them to new points of exposure in a wholesale way. Membranes always form a tree structure, so a membrane cannot be a subrane of many membranes, and they may not form feedback loops. A membrane containing others will be notified about changes occurring in any subrane including the addition and removal of subranes.

## designation

primarily a membrane is a container for [Cruxes](Crux.md), once a crux has been added to a membrane it can be discovered and grouped using a special designation language.This looks something like:

```
    membrane.designate("a.b:c",'type')
    //where a and b are subranes\(dot seperated\) and c is the crux \(after the colon\)
 ```

furthermore it is possible to use wildcards similar to file globbing, to select multiple cruxes at once.

```"*.b:*"``` means: from the submembrane called 'b' of all submembranes select 

usually these designations are part of the link rules that dictate what get connected to what.

## inversion

A membrane can have two sides, the inner face caled the shell and the outer face called the the lining. These are in fact two distinct membranes, each being the others inverse, they both have the same cruxes but as opposite contact-types. That means that cruxes must be invertable to appear on both sides. You can think of the membrane being two circles where the cruxes are lines between them like the gills of a mushroom, or spokes of a wheel.

## contact type separation

```
see [Contact] (contact.md)
contacts are organised by type, therefore contacts of distinct type but similar name may coexist, this means that patterns of interconnectedness can be repeated accross different contact types.
```


