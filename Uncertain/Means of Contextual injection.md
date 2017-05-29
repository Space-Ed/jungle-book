This problem is one of managing consistency across the existing rule designation interconnection infrastructure, while adding a feature that was essentially left out.

Originally it was though that the cell heart or 'nucleus' would be a cell itself and that it would only implement those cruxes that allow the injection into the synctree.

However this approach is now seen as fairly impractical, because it is really only pushing the problem away, why would there be a different set of cruxes available to that particular kind of cell. meanwhile having other stateful interactions of the host cell to being an access to that cell's core.

So to reduce this complexity we want the state to be a composite and proxy, that alway gives it's exposed object to the parent and provides the offerrings as cruxes to be added to appropriate membranes according to the state configuration portion of the form.

with this model in mind there is the matter of allowing the declarative injection of certain contacts. such that they may be interacted with in operations that involve the encapsulated state. This kind of interaction applies to all sorts of entity types, what we want for is a sort of 'hookification' of contacts. that can apply, quite regardless of the medium.

The way our inital hook implemenations have achieved this is by capping the contact and discerning an action upon the state and an action on the membrane.

Now we want the means to have a discernment of membrane, to cause the action upon state. This effectively takes it from the safe, construction time to a more uncertain mesh operation time.

Such a move calls into question exactly where those kinds of declaration's effects should be implemented, In the Crux, the contact, the medium or the mesh.

Contact inheritance seems to be inevitable, because we want to extract this notion of hookability. That is inescapable in a sense. But lets not throw the baby out with the bathwater and say that the whole mesh must be recreated. By default, media have 1 or 2 roles, now they should be more abstract contact types. But really this is only to achieve a single feature, instead of throwing away everything. lets just force hookability onto the contact interface. That means a crux declares it's hookability, and if so must also provide the implementation of hook method against a given \(contact, exposure\). Now we will skirt around the mesh and have a seperate, declaration space that is hooks. From a configuration perspective it will look quite similar to declaring rules in a medium.

```js
hooks:[
    "mebrane:crux >> path.to.alias"
]
```

the issue with this hooks object is that it is so similar to the mesh rules that it could be confused, having a distinctly aggressive state changing effect at any time in the cells life.

Also we want all kinds of contacts that are 'hookable' to be affected by this segment, but that means there is not the same assurance that a medium has to be dealing with one type on each side of the arrow.

that is then going to require us to specify the contact-type that should be hooked\(arduous\) or reintroduce those hooks to the media where the types are implicit \(colluded\). The third option is to make hooks a medium that deals with the abstract type of contact 'hookable', and then you would have conflicts when the types are not compatible.

Actually option zero is to expose the mesh to the state. thereby allowing designation of contacts

or exposing every crux that is not linked to anything\(that's actually totally crazy\)

another novel approach is to declare a visor which is exposed for the mesh primary membrane, that would prevent designation through the normal channel. it would be declarative, but there is still the step where we choose which contact types, so it becomes arduous. in fact all designations require the type to be specified it's just that a medium does this by having inherent types for A & B. 

Wherever you go it is arduous exposure of type names, against colluding with other kinds of rule.

what is really the downside to colluding? 

a:p -&gt; b:q is fundamentally different to a:p &gt;&gt; b.p as a position in the state.



The next option is to use a hook construct that targets a certain property or set of properties and generates. rather than creating the hook itself it must find some. these cruxes would need priority access to those cruxes appearing in the mesh. they preceed the rules of linking 

being constructs inducted to a cell with a key, they will be able to inject at that safely, in a sense the hookcall hook is one of these except that it creates it's own crux instead of having to find one. but the one created could be discovered through this system, there would be no need to specify. 

In a way we have gone full circle to having a hooks configuration, except now it is more verbose and arduous,

```js

{
    tostomach:{
        basis:'hook',
        visor:'stomach:oesophagus/called'
    }
}

this.tostomach('food'); 
```

Of course now there is a possible creation of many designated for one 

```js
{
    outmouth:{
        basis:'hook',
        visor:'*:{oesophagus, windpipe}/called'
    }
}

this.outmouth.lungs.windpipe('air')
this.outmouth.stomach.oesophagus('food')
```

now this has inserted lungs and stomach to not be ambiguous if they happened to have some of the same name. But it begs the question, why were they ommitted in the first case?

perhaps we can attempt collapse

```js
{
    outmouth:{
       basis:'hook',
       visor:'*:{oesophagus, windpipe}/called',
       collapse:true
    }
}

this.outmouth.windpipe('air');
this.outmouth.oesophagus('food');
```

Now because we have specified the collapse, we wont be surprised when an ambiguity causes a construction failure. 

you can take this one step further considering that a cell's configuration can deal with it's nucleus as it sees fit. 

```js

{
    outmouth:{
       basis:'hook',
       visor:'*:{oesophagus, windpipe}/called',
       collapse:true
    }
}

this.outmouth.windpipe('air');
this.outmouth.oesophagus('food');

```


