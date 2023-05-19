# SOLID Principles

There are plenty of literature of SOLID principles. A lot of them explain it better than I ever will.

Stating the SOLID principles here because


## Single responsibility principle
It's straight forward, one class should do one thing. I comply to this principle in the nesting chapter and the naming chapter.
 In my ideal world, we can produce readable code without comments. The class name and method names should be ample to explain what your method does. It's like twitter, where there is a word limit for the explaination; you are limited to using the method names. It ties back to Single responsiblitity principle, becaue if you can't explain what a class does in a few short words, probably it is doing too much. The "Getting rid of Nesting" chapter is a different approach. If your code contains a lot of nesting, same as branches, it might also be doing too much, violating the SRP. In those chapters I will explain how I refactor the code or do the naming.
 
## Open closed principle
This one states "software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification." in practice I feel this principle draws a lot of confusion. Should we never fix bugs? Should we never update existing code?

Right now I tend to use this principle on interface design, rather than the code implementation. In the bug fix argument, the expectation of the code does not change, although the behavior changes. For example, if List.getFirst() returns the second element instead of the first, it's not doing what it says. By doing a bug fix, we are changing the behavior, but honoring the contract we setup through the interface. 

Emphasis on this is a "design phase" principle. I try to design the methods in the interface as essential as possible. Of course we cannot see the future, and requirements may change. But it is nice to identify the basic operations that we always need, designing interfaces to provide these operations would prevent modification in the future.

Another anti-pattern of OCP is the adding of boolean flags. One day a engineer finds an existing method that is similar to what they need, so they add a boolean flag to change the behavior. This is modification to the code. Although it doesn't break clients often, it makes the number of code paths grow by 2^n, back to violating SRP.

I probably don't respect existing contract currently. Too young too simple. And break clients a lot in work.

## Liskov substitution principle
