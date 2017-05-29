
This problem is one of managing consistency across the existing rule designation interconnection infrastructure, while adding a feature that was essentially left out.

Originally it was though that the cell heart or 'nucleus' would be a cell itself and that it would only implement those cruxes that allow the injection into the synctree.

However this approach is now seen as fairly impractical, because it is really only pushing the problem away, why would there be a different set of cruxes available to that particular kind of cell. meanwhile having other stateful interactions of the host cell to being an access to that cell's core.

So to reduce this complexity we want the state to be a composite and proxy, that alway gives it's exposed object to the parent and provides the offerrings as cruxes to be added to appropriate membranes according to the state configuration portion of the form.


with this model in mind there is the matter of allowing the declarative injection of certain contacts. such that they may be interacted with in operations that involve the encapsulated state. This kind of interaction applies to all sorts of entity types, what we want for is a sort of 'hookification' of contacts. that can apply, quite regardless of the medium. 

The way our inital hook implemenations have achieved this is by capping the contact and discerning an action upon the state and an action on the membrane. 

Now we want the means to have a discernment of membrane, to cause the action upon state. This effectively takes it from the safe, construction time to a more uncertain mesh operation time.

Such a move calls into question exactly where those kinds of declaration's effects should be implemented, In the Crux, the contact, the medium or the mesh. 

Contact inheritance seems to be inevitable, because we want to extract this notion of hookability. That is inescapable in a sense. But lets not throw the baby out with the bathwater and say that the whole mesh must be recreated. By default, media have 1 or 2 roles, now they should be more abstract contact types. But really this is only to achieve a single feature, instead of throwing away everything. lets just force hookability onto the contact interface. That means a crux declares it's hookability, and if so must also provide the implementation of hook method against a given (contact, exposure). Now we will skirt around the mesh and have a seperate, declaration space that is hooks. From a configuration perspective it will look quite similar to declaring rules in a medium.

hooks:[
	"<designator> "
]





