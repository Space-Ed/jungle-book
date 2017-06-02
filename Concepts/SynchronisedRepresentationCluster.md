# Synchronised Representation Cluster

This object is of a distributed nature, it is a system where many comonents share a common form but are of a different nature. Like the representation of a process as a visual interface with various components(view), and an abstract representation of the data contained within (model) in addition to the code itself(). The attempt to implement these kind of systems that require the alignment of sructure and information across many different contexts of repesentation is one of the core problems of writing software. Many existing frameworks will attempt to fix this problem by defining an architecture that only allows these synchronisations to occur in a constrained way that can be managed, this is especially true for MVC style applications operate.

But there is more to the world of possible programs than what this architecture can successfully model. by attempting to constrain our components into these boxes, it requires them to genericise and become more complex as features are added that should really belong to a different representation.

The aim of Jungle is not to contrain to a particular architecture but rather to make the high level synchronisation connections between architectural components first class within the framework. This means they are on the same level as inter-module messaging and state sharing.

These systems are:
- **Synchronised**: What happens to one happens to the others.
- **Representation**: How one looks is not how one is, representations are context sensitive expressions of form.
- **Cluster**: a group of peers, each aware of the others, no hierarchy, free to come, free to go. 

with this model it becomes possible to create entire architectures as repositionalble components with plug in parts, To add new representations of data without adding complexity to existing types, to synchronise and represent all or only part of a whole structure. 

The true power of this technology is truly unlocked when it is spanned over networks and is able to manage the synchronization between several endpoints on many hosts running various platform technology, thereby enabling distributed collaborative editing of arbitrary software systems. This technology will enable us to break free the shackles of the server-client web, and allow us to become connected to one another without the intemediaries watching over us.

of course there are significant challenges for the implementation of such a system.