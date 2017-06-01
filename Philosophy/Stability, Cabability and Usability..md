One of the most significant challenges in the writing of programs is to ensure that it is all of the above, to build programs that are safe from failure in the user's hands, are intuitive; not requiring a large number of steps, memorization or context shifting while achieving the function that should be as extensive as possible.

This seems at times to be a place where tradeoffs must occur, that you cannot have one without the other, but from other perspective it is the harmonization of these aims that is the very art of programming. Nevertheless it is worth investigating how these notions play against one another, so we can begin to gain an appreciation for how gains can be made in all areas and recognise and catch early when one is falling behind. I think everyone would agree that if any one corner fails there is a catastrophic collapse, and all efforts towards the other aims will be a waste. An unstable program will likely cause users to lose trust after some number of successive failures, a program with overt complexity will daunt the user to think it is too difficult to learn, and a program without offering features and capabilities that are pleasing will likely be supervened by other programs.

In the case of a software used in the construction of other software the same principles apply, but now the user is other developers, this is the case that is relevant to Jungle and is this analysis.

there are within the design of languages and api's a number of generic descisions that are made each having a certain effect on these measures. When achieving a given feature it may be possible to analyze the effects 

### Stability

When programs fail there are any number of outcomes, both noticible and unnoticable, it is any departure from the intended behaviour of the system, that does not mean unintended usage but indeed it is hard to know if something behaves as intended in a use case one did not consider. Managing stability involves a number of development techniques, most prominiently writing of tests, but also the use of Static types, linters and other failure mitigation strategies. The ideal of keeping all bases covered is usually unattainable, but often a few cases with an understanding of the internal mechanisms can prove operability to all other cases. This works in a similar way to a mathematical inductive proof, the problem with complex software is however there is a reality of computational resource to contend with, there is no infinite limit. Therefore it is not always sufficient to consider the basic case and incremental case, there is also the reasonable domain usage case, which is way more arbitrary and based of a fuzzy idea of how the software will be used. Often the only way to gauge is to have these systems out in the wild. 


### Capability
The features, or reach of a program, encompassing all capailities. What can it do? In the case of the jungle core, the answer is usually fairly abstract, often relating to the other aspects of capability and core principles.

#### Scalability
How much can it do? The number of elements that can be added, number of users, number of connections possible, verticies, concurrent processes..

#### Recombinability
Does it have parts that can be combined? This will enable an explosion of possibility that allows a program to mould to the user's need. This is the bread and butter of frameworks in particular but also modular synths, and visual coding systems. It lends itself to a certain domain of technical advancement. But can be distilled, even to a few elements that are obvious.

#### Integrations
Does it interact with other systems? 

#### Extensibility
Can it be 
