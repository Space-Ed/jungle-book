Ideally the creation of user interfaces will be standardised into a Jungle domain that can be imported as needed and extended upon in the jungle fashion without too much difficulty.

At first we must consider only the web platform as a serious possibility.

There are broadly two approaches to building a gui toolkit.

1) target a specific existing library like JQueryUI or bootstrap to provide all outward functionality and just create bindings for these specific libraries.

2) get as close to the base level DOM API as possible and only use that to create the kit.

While it would be practical to focus on leveraging other technology, in terms of embracing a specific kind of jungle flavour it will be neccessary to fall to basic principles. For instance the relationships between  components might be modelled as contacts, and it could be unwieldy to use these if the underlying library has its own meand. Those libraries are intended for use from an application, not as a mapping onto a wrapper library

3) Another possibility is to modify an existing open source gui library to 

	a) gain better insight to the nuances required to create such a library and 
	b) save some labour while adapting to the specific needs of jungle

It would need to be a very cogently crafted library to be worth the effort to understand it. 


At the heart of a UI library is the nestable component. 

In HTML the element is such an entity. Ideally as we create wrappers to these components the relationships they share are also encapsulated. That is the relation to the parent that constrains its size and relation to the model they represent, any events that may take place, and the data that passes through them.

The creation of elements could be done on a server by creating an id from a serial uuid that the wrapper uses to recover it and attach. That saves some time while the content is loaded. The 