# Programming language styles

> The limits of language are the limits of your world. - Wittgenstein

There are many programming languages. Some become fashionable while others slowly die off. It is likely that if you have some programming experience, then you have acquired a taste for the styles and languages that you prefer.

Given some context, there are undeniably programming techniques that are more productive and others that are to be avoided.

For example, some people like to use "pure functional programming". In such a programming style, one designs "functions" which take inputs (that cannot be modified) and produces an output that depends only on the inputs you have provided, and they change nothing else. For example, if you write a function that takes a string of characters, then create a copy of this string of characters with one extra character added at the end, you have a pure function with no side-effects.

Though few people program in pure functional style, many programming languages have immutable objects (like strings in Java) that make reasoning about the execution of the program easier.

At the other extreme, there are still people who use GOTO instructions. A GOTO instruction tells the program to continue executing at a given location. For example, the following program would print the same string again and again:

```
  10. print "hello"
  20. GOTO 10
```


Though popular for a time, the use of GOTO instructions has now fallen out of favor among programmers simply because it can become too difficult to reason about the execution of the program. The net result is often when people call "spaghetti code". In the sense that programming is communication, the GOTO instruction falls too easily into obfuscation.

(give examples)



Some languages try harder to be safe than others. C and C++ have undefined behavior. It is not as bad as it sounds as ultimately, undefined behaviors are rather the norm. Software can always run out of memory and so forth. Strange things happen.




There are long and painful arguments about which programming style best. Invariably, these debates are tainted by the specific experience of the programmers, including what types of software they have written, and what programming style they last learned.

Almost universally, programmers fall into the pattern of "falling in love" with the latest new style or technique they have learned. Often, they rush to put it to good use.
Familiarity also biases people in favor of the programming languages they know best (which are often the latest ones that they have mastered).

(what objective guidance can we offer?)


- Programming is social. You may have your own preferences, and it is entirely possible that everyone shared then, everyone would be more productive. It is also possible that some natural language is more efficient than English at some tasks. Yet popularity often trumps the intrinsic qualities of a given programming language. If you can get more users, more developers, to use, improve and access your software, it is usually worth many times the modest productivity gains you might derive from another languages. The same is true of specific programming styles. For example, maybe you can program using GOTO statements without any difficult and the resultings code might be very efficient... but if it makes your code hard to understand for others, it might not be worth it. Of course, we can also reverse these statements. If you wish to only program with some elite class of programmers that match you own interests, you can choose a programming language that only this elite class will master. Nevertheless, everything else being equal, you should probably stick with popular programming languages, and use as few features and as few little known styles as you can. Making your code simple and accessible is probably always a net win.

- blabla
