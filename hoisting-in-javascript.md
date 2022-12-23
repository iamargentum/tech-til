# hoisting

reference - https://developer.mozilla.org/en-US/docs/Glossary/Hoisting

hoisting is very nicely explained in the mdn docs

\*as per my understanding

hoisting is the act of bringing variable, function or class declarations to the top of the code before execution (probably in global context? -> need to read about this)

this prevents getting reference errors if the defined variabels or functions are used before declaration (who would want to do that? -> again, need to find this out)

now, only the entities defined using var, function function\* async function, async function\* are the ones that are hoisted
(what is function\* and async function\*? -> why do i not know this?)

actually let and const are also hoisted, but their hoisting does not bring anything to the table, i guess, i mean that is what is written in mdn

let and const don't act as hoisted entities because the temporal dead zones forbid the usage of any variables before their declaration, so this might only not work when a variable is defined with the const or let keyword outside of the TDZ and also inside of it? (come on! this is so confusing!)


some good insights from the document -
```
    {
        var x = 1
    }

    console.log("x is ", x) // output: x is 1
```

the above example is not a form of hoisting as the var declaration is not scoped to the TDZ

a lot needs to be added to this document, but this seems to be it for now
