## Domains

Like the domain names of the web and the namespace of various programming languages.

The idea with domains is that our domain is an object accessible from a cell that contains all valid instructions, now what it is doing is all things that could be included are encapsulated in these domains. 

It is this interesting space, a static space, but we do become curious, sparked by the discussion of construction in a dynamic scope,

the idea here would be that this scope has access to this domain for when it has this raw structure, this serialised format of a construct, it is able to create the real thing from this. Within the scope of 'this' we use a command to make something, in doing so we look within the domain we hold reference to, then we take a basis and a patch, and create a modification of the basis and inject it under a name\(or with an anonymous name\) into the context.

2 cases 

one where we produce a pattern and induct into the system

the other where we produce a primary construct and with modification inject or put back into a target domain. 

### Implementation

The domain is defined as an entry of a cell that has the ability to create constructs within itself, the implementation requires:

1.  the form parsing rule that 'domain' is a keyword which creates a domain from the value
2.  the domain is a contruct which will inject approprite methods into the context
   1. appropriate means that it will sometimes not expose the ability to use or extend the domain from the context.
3. the domain is handled first so that other constructs will have this available at 
4. The domain is by default the domain of the parent
5. If a child is to be restricted to a separate domain
   1. A subdomain of the constructing cell 
   2. A visor of this domain.
   3. An entirely new domain.
6. Seperate Domain must be determined at construction 

### Construction within

when an entity is constructed, it is recovered from a basis that maps to a domain in the context of the construction. 



### Inheritance

Domains are the mechanism by which a basis is modified to mean somthing different in various contexts.

