# slices and arrays in go
---

i've recently started [learning go](https://gobyexample.com) and got confused between slices and arrays
so i searched up their differences \([reference](https://www.developer.com/languages/arrays-slices-golang/)\)

the basic difference that i could find is that arrays are not flexible and are not meant to be associated with dynamic memory allocation
slices are actually built on the top of arrays and they provide us with functionality that makes arrays more flexible

so, slices are just arrays under the hood, but with added capabilities like append, copy and stuff

one important thing to notice (not related to difference between slices and arrays) is that arrays are of value type in go, unlike c or c++ where arrays are of pointer type

also, we can copy one array into another by simply using the assignment operator

ex. array1 = array0

in the above example, array0 gets copied into array1
and array1 is a distinct copy of array0, no strings attached, so if we make changes to array1, array0 stays unaffected (cries in javascript XDXDXD)

there are a lot of other differences/peculiarities of slices and arrays, but this seems to be enough for now
