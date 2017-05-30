# The Crux Collapse

_The crux has always been a troubled child, let us analyse how it may be superfluous and confising in this latest vision of what the io model could be_

##The name says all
When an object in a structure begins to take on a placeholder or made up term that is when we might stop to think, "is that something that should really exist". Crux was really on the line, a crux is kind of like the crossing point, it certainly fit with what it was, but is obscure to a suspicious degree.

What is a crux
    - Terminal component of a membrane held under a named role.
    - bears a label that it is to be designated with.
    - has an inversion function that currently just pairs strings. 
    - holds a contact object for each role it can fill, that it constructs.
    - remembers the membranes that hold it.

What could it become.
    - a two sided entity, like a medium that has an appearance profile on either side.
    - a way to create injectors for its contact groups.
    
    
Why is it up for chop?
    - It seems to introduce and unneccessary layer for these systems. Why cant membranes contain the contacts directly?
    - It's treatment of contacts as strings, is now becoming seen as higly restrictive to having extensible io channels that would involve the creation of new contacts.
    
what would replace it?
     - Contacts which now implement real inversion and bridging and injection, the inverses would reference each other directly.
     
what cant contacts do? 
    - contacts cant be groups of contacts of different types
    - before we could create pairs of contacts that are not inversions. This would promise to be a means of converting between different kinds of contact over a membrane. 
    - contacts were well isolated so that they could be exposed as per need to the wild without leaking to the meta level, however a recent development has seen that contacts should only be available to state through hooks.

how will those be addressed?
- although contacts cannot be grouped, this is of little consequence, designative grouping should be restricted to membranes and visors. Functional grouping should just be done by creating complex contact types, which is totally possible now yay. 

- contacts come in many varieties, so therefore do their inversions, they might not have inversions or their inversions might be the same type(probable for symmetric systems). Although this does not restrict us to 1:1 as per cruxes, but just means that the special will have a more generic inverse. The type of inverse can also be different, so long as it will play ball. 

- a contact will have a level of access to context dictated by its constructor and injection prototype methods. This enables the creation of new hook methods which provides closure access to the data channel. 

what are the implications for media?
- before media were expecting dumb contacts with a certain interface because they happen to be called something. This is arduous, discussed below

## nominal schlominal
Roles, an interface and a key, the key appearing as value of roleA/B of a medium and in the roles property of crux to an interface fitting object and used to actually get the correct crux from the medium, just so that the link has the interface the same as the crux.roles.key(contact) object. What a mess!

Now heres how it should work. 

A medium has one or two constructors to check the instance of the contacts. There is now only one type for each label, but we dont know what it is when it appears in the mesh, so. In the mesh the medium with the strongest claim to the contact should have the opportunity to create the link. 

### The Strongest Link
The positive conflict problem rears it's head again, now taking the current model of  each medium having a list of rules. the issue is that a contact may be referrable by two or more designators, in such a case we have a loss of commutativity on the addition of media. Which if we are declarative, is an error. 

This problem did exist before but it has been exacerbated by widening the criteria for designation and restricting the ability to implicitly filter. Actually our implicit filter is now just potentially able to capture all contacts. 

is there a possibility for commutative resolution of conflict, that is regardless of who appeared first? 
- Specificity: The most specific wins. Allowing subtype linking to kick supertype links(hence invalidiating their rules) off.
- Power/Authority: a form level may beat a construct for instance. 
- rule specificity: a rule using a wildcard can be defeated by a specific value.

Really, the solution is to have runtime errors for irresponsible overlapping of rules in different media, perhaps in time there can be other possibilities, and even a static check for overlap. 

  




