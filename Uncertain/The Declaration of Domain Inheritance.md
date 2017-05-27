### The many confusing possibilities of where patterns are made and shared.

A Composite\(A\) is constructing another Construct within it\(B\).

A says  
  I have been given a domain  
  B will be recovered from a pattern in this domain  
  I would like to decide what domain B is given.

B says  
  I am being constructed in a domain  
  I would like to choose which subdomain I am constructed with

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

### Possibility 1 : alignment of domain with structure.

in this model the parent decides what it's children will have access to by defining an entry of it's own domain that is the domain to pass on, which could be overiding, inheriting or isolated.

```js
sandwich:{
    fancy:['Bread', 'Spread'],
    normal:['Bread', 'Spread'],
}
```

In this example our scanning of the sandwich property finds two children, one has a key that is within the domain, that is 'fancy' so when the fancy array is scanned, it will be given that subdomain 

### Possibility 2: Locator meta-construct property.

this model requires the parent to create a middle layer, to expicitly say the location of the new cell

```js
sandwich:{
    fancy:[{locator:'fancy',basis:'Bread'},{locator:'fancy', basis:'Bread'}]
    fancy:[{locator:'fancy',basis:'Bread'},{locator:'fancy', basis:'Bread'}]
}
```



