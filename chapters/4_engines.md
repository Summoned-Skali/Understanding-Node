# JavaScript engines

In the previous chapter we spoke mostly of `Node`, it's `C++` core, and how this enables the extension of `JavaScripts` functionality. We know that `Node` uses the `V8` engine, and we know that there are many `JavaScript` engines, but what exactly is an engine? well, much like everything else, `JavaScript` engines are simply programs whose responsibility is to execute `JavaScript` code, the most popular `JavaScript` engine being the `V8` engine. We know that this particular engine powers not only server-side applications outside of the browser via and embedded version of it within `Node`, but also in the `chrome` browser. But... what if you didn't use `chrome`? currently, the most popular browsers on the market are `chrome`, `brave`, `safari`, `edge`, and `firefox`, do all of these run the `v8` engine? the short answer is no.

| Engine | Description |
| --- | --- |
| V8 | Open-source Engine used by Chrome and Node |
| SpiderMonkey | Engine powering Firefox |
| JavaScriptCore | Open-source Engine developed by Apple for Safari |
| Rhino | Open-source Engine for Firefox |
| Chakra | Engine for Microsoft Edge |
| JerryScript | Engine for IoT |

We have multiple engines, remember `JavaScript` is not understandable by the computer directly, it needs to be converted into a computer-understandable language, each engine handles this conversion. These engines differ slightly in how they conduct this task, but effectively solve the same problem.

### V8

V8 has an edge on other engines, there is a reason it became so popular. Not only can V8 run both on the browser and on a machine using `Node`, but as we learned previously, we have control over extending functionality ourselves due to it's open-source nature. It can also be embedded into any `C++` application we may write. `v8` also allows for `JavaScript` code to run much faster, which improves the end user experience, paves the way for the development of web applications (and SPAs), and allows smaller teams of devs specialising in `JavaScript` to operate across the entire stack.

Using it's proprietary parser, it generates an abstract syntax tree. Then ignition generates bytecode from this tree using the internal `v8` bytecode format. Bytecode is then compiled into machine code by TurboFan which also handle the memory allocation for objects. Garbage collection collects the objects which are no longer needed. It also utilises optimisation techniques such as elision (the art of omitting unnecessary objects from a copy) of expensive runtime properties, and inline caching. The garbage collector is a generational incremental collector (a collector which does not collect all unreachable objects during a cycle, all generational garbage collectors are incremental, an incremental GC does not necessarily employ a generation scheme to decide which unreachable objects to collect or not, A generational collector divides the unreachable objects into different sets, roughly according to their age. The basic theory here is that the objects most recently created will become unreachable quickly, so the set of 'young' objects are collected at an early stage. An incremental collector may be implemented with this scheme, or another alternative method, which may decide which group of objects should be sweeped in a different manner [see Wiki](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)#Generational_GC_.28ephemeral_GC.29)).


___

<div align="right">

[<< prev](./3_nodecore.md) | [next >>]()