
In biology a membrane is the outer wall of a cell, it is one of the fundamental parts of a cell, in fact it was the formation of a division between the inside and the outside that made it possible for processes to become distinct, for competition. In the domain of software we don't have a lipid bilayer and various intervening portal molecules, instead we have what are usually called interfaces or port hosts, or stdio, API's. They exist in various forms and levels from physical cables and network protocols through to virtualised interfaces of a virtual machine or device driver and type interfaces in statically typed languages. It isnt just to avoid overloading the term that we choose to use "Membrane" instead because Jungle seeks to rise above some of the fundamental assumptions of interfaces, and creates a very distinctive model.

In most kinds of software and hardware the nature of interfaces is that they are built to have a certain form for the entire lifespan of their use, they cannot be extended at either end. 

This is for very good reason, in most software we have a situation where either side of our interface is relying on the other to be a certain way, the definition of an interface, must precede the definition of either implementation. In other words there is a contract between these parties that dicates the possible kinds of interaction and must be signed by both before it is considered safe to interact, if those parties want to change the way they interact they must create and sign a new contract, in software this usually means creating changes affecting multiple hosts across many source files, and restarting parts or the entirety of a system.

Membranes and the other Jungle IO constructs provide a way of creating dynamic interfaces that can change over time, without requiring recompilation, pushing to repositories, restarting the program, even without reconstructing the cell. 

##Structure
```json
{
	contacts:{
		contact-type: {
			label: Crux
		}
	subranes:{
		sublabel: Membrane
	}
}	
```

## contact type separation
	see [Contact] (contact.md)

ownership

designation

sub-membranes(subranes)
