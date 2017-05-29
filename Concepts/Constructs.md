# Construct.

constructs are a class of object which are central to the Jungle Architecture.

Almost everything is a construct, and this is what enables the core features of Jungle to be distributed through every component. 

a construct implements a certain interface and meets some operational requirements.


## Spec
A construct is always instantiated with a single object, that will contain all configuration and information required for construction. This object should be considered to be immutable. It contains some properties that have special keyword meaning.
###basis
The identifier with which to designate the base implementation of the construct from the domain of the parent.

###domain
1. (string) The identifier with which to designate the domain of operation based of the parent domain.
2. (Domain) the actual domain to use
3. (undefined) the default is to inherit the parent domain.

