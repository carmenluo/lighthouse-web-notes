## Strongly typed VS weakly typed
Strongly typed: will check variable's type before excution whereas weakly typed doesn't.
Strongly typed: will need to explicitely cast variable whereas weakly typed doesn't

## Dynamically typed VS Statically typed
Statically typed: Every name is bound to a type at compile time and an object
Dynamiclly typed: Every name is bound to an object
```
employeeName = 9
employeeName = "Steve Ferg"
```
The above code is illegle in statically type
Dynamically typed and weakly typed language can provide flexibility for developer, but for strongly typed and statically we 
are expected to check the type at compile time so that it can have better performance
Ruby is strongly typed, so "4.0" / 2 is illeagal. we need to convert it to int first with "4.0".to_i

