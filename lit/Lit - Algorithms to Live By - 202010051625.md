# Algorithms to Live By
> @book{Christian_Griffiths_2016, place={New York}, edition={First U.S. Edition}, title={Algorithms to live by: The computer science of human decisions}, ISBN={9781627790369}, publisher={Henry Holt and Company}, author={Christian, Brian and Griffiths, Tom}, year={2016} }



## Scheduling 
When it comes to humans with a giant pile of tasks, computer science concepts really come into their own. Looking at the tasks by themselves, order doesn't necessarily matter from the start - it's only when other pieces of metadata such as due date that optimal work comes into play. 

> Not all unfinished business is created equal.

As more variables get introduced, so do the number of metrics that measure what success looks like in your given context. In particular, two key strategies are:
1. **Earliest Due Date**: Complete tasks due the earliest first. This minimizes waiting time for others and lifts deadline stress the fastest. 
2. **Shortest Processing Time**: Get as many things done as quickly as possible. If a task doesn't take super long, do it before longer tasks. 

The sum amount of weight each task has is, funnily enough, its "weight." The closest thing to a swiss army knife when it comes to an optimal scheduling strategy is combining this concept of weight with Shortest Processing Time - Its "Density."

$$\frac{\text{Task Weight}}{\text{Task Completion Time}}$$

This measure turns out to be super optimal for handling uncertainty. If an unexpected task has a higher "density," slot it in appropriately. 

Of course, this is not always optimal. Consider a case where two heavy buckets need to be moved to the same place, although one is closer to the goal than the other. If you move the farther one, drop it off, then move the other one, this is not as efficient as dropping off the first one, *switching* to the second, and walking back. 

This leads to the importance of **context switching**. A computer's form of multitasking ("threading") is effectively switching incredibly quickly (in the realm of fractions of milliseconds) That said, context switching is dangerous, as the metawork time needed to switch is useless to tasks. 

Not all context switching is created equal. High mental intensity work such as writing and coding take a long time to start up (let alone finding a flow state). 

It can be incredibly easy to become paralyzed by tasks because of context switching, where that's all you are doing. This is called **thrashing**. To prevent this, saying no to tasks is good but unfeasible. Instead, establish a minimum amount of time before context switching can even happen. Computers have this down to a science - if threading time is high, we'd notice. The trick is to work faster than our brains can see/observe. 

> The moral is that you should try to stay on a single task as long as possible without decreasing your responsiveness below the minimum acceptable limit.**Decide how responsive you need to be - and then, if you want to get things done, be no more responsive than that**. 