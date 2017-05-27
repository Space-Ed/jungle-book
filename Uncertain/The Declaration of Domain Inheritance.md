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

### Possibility 1 : alignment of domain with structure\(Implicit Domain use\).

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
Such double management would be quite unfavourable

### Possibility 2: Locator meta-construct property.

this model requires the parent to create a middle layer, to expicitly say the location of the new cell

```js
sandwich:{
    fancy:{locator:'fancy', patch:['Bread', 'Spread']}
}
```

That will give the fancy array constructor the fancy domain of the parent.

### Possibility 3 : Locator key modifier

This model requires extra parsing of the key to divulge the desired domain infliction.

```js
sandwich:{
    "myfancysandwich of fancy":["Bread", "Spread"]
}
```

the syntax could be different than "&lt;key&gt; of &lt;domain&gt; "

### Possibility 4: explicit Domain patch

```js
sandwich:{
    fancy:Cell({
        crown:["Bread", "Spread"]
        domain:{
          Bread:"fancy:Bread",
          Spread:"fancy:Spread"  
        }
    })
}

or

sandwich:{
    fancy:Cell({
        crown:["Bread", "Spread"]
        domain:"fancy"
    })
}
```

## Domain Selection

In this section we make a fancy sandwich in the same domain but select the components we will use.

### Possibility 1: not possible.

The structural similarity of inflicting subdomains and specified selection is too similar to be harmonious and not confising. and selection does not allow for the kinds of encapsulation we are trying to implement.

### Possibility 2:  Basis designation.

In this access methodology we are using a similar syntax to membranes in order to designate patterns in the structure

```js
sandwich:{
    fancy:["fancy:Bread", "fancy:Spread"],
    
}


```



