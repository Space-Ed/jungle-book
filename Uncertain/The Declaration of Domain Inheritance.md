### The many confusing possibilities of where patterns are made and shared.

A Composite\(A\) is constructing another Construct within it\(B\).

A says  
  I have been given a domain  
  B will be recovered from a pattern in this domain  
  I would like to decide what domain B is given.

B says  
  I am being constructed in a domain  
  I would like to choose which subdomain I am constructed with

I would like to be constructed in my own domain.

### Example

```js
import Cell, Domain from 'junglejs'


Cell({
    domain:Domain({
        Bread:"Tip-top white bread"
        Spread:"Kraft peanut butter"
        fancy:Domain({
            Bread:"Wholewheat & Linseed sourdough"
            Spread:"Pic's Peanut Butter"
        })
    }),

    sandwich:['Bread', 'Spread']  
})
```

The question is, how can we make a fancy sandwich?

**Note: in this example the strings "Bread" and "Spread" are actually serial construct specifiers with bases of those names.**

## Domain infliction

### Possibility A1 : alignment of domain with structure\(Implicit Domain use\).

in this model the parent decides what it's children will have access to by defining an entry of it's own domain that is the domain to pass on, which could be overiding, inheriting or isolated.

```js
sandwich:{
    fancy:['Bread', 'Spread'],
    normal:['Bread', 'Spread'],
}
```

In this example our scanning of the sandwich property finds two children, one has a key that is within the domain, that is 'fancy' so when the fancy array is scanned, it will be given that subdomain. While elegant in expression The obvious problem is that you can have a 'gourmet' and 'classy' names both using the fancy domain. without also expressing these in the domain description.

```js
domain:{
    ..
    fancy:{..}
    gourmet:Domain('fancy'),
    classy:Domain('fancy')
}
    
```
Such double management would be quite unfavourable but this does perhaps show how domains may be based of an extention of a sibling domain

### Possibility A2: Locator meta-construct property.

this model requires the parent to create a middle layer, to expicitly say the location of the new cell

```js
sandwich:{
    fancy:{locator:'fancy', patch:['Bread', 'Spread']}
}
```

That will give the fancy array constructor the fancy domain of the parent. This mode gives some flexibility to the child, who could be bringing their own locator.

### Possibility A3 : Locator key modifier

This model requires extra parsing of the key to divulge the desired domain infliction.

```js
sandwich:{
    "myfancysandwich of fancy":["Bread", "Spread"]
}
```

the syntax could be different than "&lt;key&gt; of &lt;domain&gt; "

### Possibility A4: explicit Domain patch

```js
sandwich:{
    fancy:Cell({
        anon:["Bread", "Spread"]
        domain:{
          Bread:"fancy:Bread",
          Spread:"fancy:Spread"  
        }
    })
}

or

sandwich:{
    fancy:Cell({
        anon:["Bread", "Spread"] 
        domain:"fancy"
    })
}
```
see [Anonymous Values](The Treatment of Anonymous Values.md)

## Domain Selection

In this section we make a fancy sandwich in the same domain but select the components we will use.

### Possibility B1: not possible.

The structural similarity of inflicting subdomains and specified selection is too similar to be harmonious and not confising. and selection does not allow for the kinds of encapsulation we are trying to implement.

### Possibility B2:  Basis designation.

In this access methodology we are using a similar syntax to membranes in order to designate patterns in the structure

```js
sandwich:{
    fancy:["fancy:Bread", "fancy:Spread"],
    
}
```
### Possibility B3: name modifier.

Here we use some special expression as the key to designate the domain.

```js
sandwich:{
    gourmet:{
        fancy_0:"Bread",
        fancy_1:"Spread"
    }
}
```
we lose arrays

### Possibility  B4: explicit basis designation:

Actually this is the same as 2 but expanded so that it may include a locator 

```js
sandwich:{
    fancy:[{basis:"fancy:Bread", locator:"fancy"},{basis:"fancy:Spread", locator:"fancy"}],   
}
```

that's right 5 times we have written "fancy", first as the property name, then as selector, then as locator. This example highlights the confusion between the basis being based off the given location or of the parent. 

both of these cases are ambiguous

```js
sandwich:{
    fancy:[{basis:"Bread", locator:"fancy"},{basis:"Spread", locator:"fancy"}],   
}
```
A)Bread is made in the fancy domain.
B)Bread is made in the normal domain but from fancy ingredients.

```js
sandwich:{
    fancy:[{basis:"fancy:Bread"},{basis:"fancy:Spread"}],   
}
```
A)The Bread is given the parent domain.
b)The Bread is given the same domain as the place it was designated.






## Together

It is this last possibility that really presents the only sensible option, because it is directly object representation, the others can be considered to be syntactic sugar which convert into this. Perhaps in the case of constructing a special domain to give to a child this can be achieved by extending an existing pattern and feeding back under a name. Alternatively we could have the locator property accept a domain, or we could as in A4 create a domain patch 

### A2 & B4

```js
sandwich:{
    gourmet:{
        locator:"fancy",
        patch:[
            {basis:"Bread", locator:""},        
            {basis:"Spread", locator:"fancy"}
        ]
    }  
}

```

### Full Expression

Creates a sandwich of normal classy or gourmet variety 

```sh
> sandwich.normal
A tip-top white bread with Kraft peanut butter

> sandwich.classy  
A Wholewheat & Linseed Sourdough with Hummus and Sundried Tomatoes

> sandwich.gourmet
A Crusty Semolina with mushrooms fried in butter
```


```js

import Cell, Domain from 'junglejs'


sandwich = Cell({
    domain:Domain({
        Bread:"Tip-top white bread"
        Spread:"Kraft peanut butter"
        fancy:Domain({ //implicitly patch
            Bread:"Wholewheat & Linseed sourdough"
            Spread:"Pic's Peanut Butter"
            classy:Domain({
                Spread:"Hummus and Sundried Tomatoes"
            })
        })
    }),
    
    form:{..}, //format the selection to a sandwich description
    
    normal:["Bread", "Spread"], //implicit anonymous and patch and basis string values.  
        
    classy:Cell({ //implicit basis "cell"
        locator:'fancy',
        patch:["Bread", "classy:Spread"]              
     }), 
        
    gourmet:{ //implicit cell patch
        domain:Domain({ //explicit domain extention
          basis:"fancy", //domain basis
          patch:{
              Spread:"mushrooms fried in butter", //domain specific override
              glutenFree:Domain({
                  Bread:"Crusty semolina"
              })
          }
       }),        
        
        anon:[
            {basis:"glutenFree:Bread", locator:"", patch:undefined},//explicit spec
            {basis:"Spread", locator:"", patch:undefined}
        ]
       
    } 
})



```






























