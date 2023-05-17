There is a purpose of writing a book. There is also a purpose of the topic. 1 year ago I browsed though Ray Dalio's Principles. He compiled the set of rules he operates by. He stated that his principles might not appy to me, just as my principles might not apply to you. Either way, having principles are better than not having principles. Writing out my own principles helps me revise them. Smart people think about how they think. They also keep updating their internal algorithm.

A year ago I gave a code review that resulted in an additional 2 day change, but also made the code stage worse. But since it was a large change, we still recognised the effort and merged in the code. A few months later, we found the refactor was too hard to maintain and reverted the changes. The collegue who initiated the change had an argument with me. Saying that my principles had changed after the code review. It was I who made them make the big change, then later changed my mind to revert it.

Our principles might not be right. It may cause disasters. But when they happen, it's nice to trace back to what principle caused the error. I changed from feeling sorry to feeling grateful about the incident. It taught me to make better communications, and also update the way I write code.

# Tenets

Tenets was always a required section in design docs, when I worked in Amazon. The purpose of tenets was to help us make a design choice, such as "Favor low cost over scalability", "Favor auditability over performance", "Favor performance over correctness". After lying down the tenets, it would be easy to choose a single server or a distributed solution, database type, or the pub/sub system. 

The tenets are somewhat measureable, my principles are not. I can't give a number value to each principle I follow, but I may design these principles to optimize some other objective. It gives the principle some empirical grounds, not just doing by belief.

## First tenet - Code cleaness

There is no way to measure code cleaness. Robert C. Martian wrote in *The Clean Coder*, "The only way to measure code cleaness is WTFs per minute." Even so, my WTFs/m maybe different from yours. Since everyone writes code differently. The definition cleanness also changes overtime. Reading the unix `ls` source code now would be a total annoyance. But the code was probably state of its art at the time. with 26,447 commits and still in good shape.

I think I can still define code cleaness. Reading others code, sometimes I get the feeling of "Wow, this is exactly how I would write it.". Certain naming conventions, certain choices of structuring code, gives me an feeling of the author follows the same principles as I am. It's natural for me to define code cleaness as people following the same principles would find each other's code clean. If we don't follow the same principles, you can still find my code dirty.

Another measure is if I would understand the code in 3 weeks. Controversially, I feel there are 2 extremes of engineers. One type  tries to understand the whole code base, the more you understand the higher level you are. The principle engineer can tell you an which service decision is made, how the decision flow passes through one service then another, while a junior engineer knows a function they are modifying. The other extreme is to not remember anything at all, but rather be able to understand my code later when I read it. Following my code, I should also be able to find my focus points in log(n), size of the code base time. As the code also servers as way points of where the stuff is. In practical, most people are a mix between the two, but I want to push myself to the latter. After all, my little brain will never catch up to the million lines of code written by humanity. I'd like to preserve it for music, literature, and art instead.

Glorify cleaness as the first tenet. Anything I write later can be ignored, if you have a cleaness argument.

### Cleaness over performance
Why aren't we writing assembly?
C, maybe
C++.

Not telling you to writing bubble sort, because it is easier to understand than quick sort. 
### Concise ness
Is shorter code better?

## Second tenet - Unit test coverage
We are still lacking a measureable this point. Unit test coverage is one of the measureables. There are tool that give you a 0-100% number after you build your code. The later principles aim to push the coverage as close to 100% as possiple.

Searching online for "what is a good test coverage", the answer varies from 60% - 90%. These claims don't include on how coverage optimizes code quality. For example correlating test coverage to another measureable. A service with 10 dependencies would have an higher error rate than a service than 1. There could be a service running for 10 years without unit tests, but has been tested by time and now stable. I double if we graph the 2 numbers, the error rate would have an minimun between 60-90%.

The target might be different from the manager view point. They balence between delivery speed and quality. If is valid to say 80% is good enough, let's push this out. 

My reasoning for pushing 100% is not because well tested code causes less errors.
My reasoning is because well written code should be easy to test. Structuring the code correctly enables us to mock dependencies easy. Following single responsibility makes the tests shorter. If you struggle to write tests that can reach every line, there is probably something wrong in the source code.

Pushing for 100% gives me confidence that the code is well written.
