## How fast is your code?

After I got my Ph.D., I started a consulting business with some
friends. One of my first gig had to do with processing geophysical
signals. At the time, my client would fly over the ground and collect
a whole disk (a CD-ROM) per hour. Though the data volumes would
now be modest, it was enormous at the time. I had written a small
program that could process small bits of data quickly, but the engineers
in charge of the project would not consider my work because it was 
unable to process entire disks in a reasonable time. What I had done
did solve their problem, but convincing anyone to wait for hours to
see results that may or may not be correct was hard. I did eventually
reengineer my code so that it was sufficiently fast. And I did get
paid... but I learned a valuable lesson: performance matters.


On some level, it is easy to tell how fast your program is: 
just run it and see how quickly it terminates.
If it is fast enough, the story ends there.

But what if your code is not fast enough? Then you need reason
about the speed of your program.

During another consulting gig, I was tasked with designing a new
compressed image format. As as I can tell, this format is still used 
for some medical applications. It was even implemented in hardware. 
By that time, I had learned a lot about producing good software, so
I had tests to make sure that code was sane. The code used a lot of
memory for the era, but I'm told it had better speed than competitive
commercial alternatives.

One day my client emails me to report a bug. He writes that when
processing large images, the program becomes absurdly slow.
I asked for a copy of the image and I run my own tests. As it 
turns out, my client had used images where twice the resolution
(both vertical and horizontal) so that there were four times as many
pixels. I benchmark my code and it ran almost exactly four times slower
on the larger images.

So I wrote back to my client:

> Yes, if you process an image that has four times as many pixels, it is going to take four times longer, at least: it is not a bug.

What followed was a long discussion that made me realized that such a simple 
point was entirely nontrivial. My client had never considered that the
processing speed could depend on the size of the input.

And that simple observation is a key teaching moment in computer science.
There is a whole field in computer science dedicated to this observation:
complexity theory. Despite its name, complexity theory is somewhat simple
at its core. It is even maybe simplistic.

Given an algorithm, you should try to characterize its speed as a function
of the size of the input. But computer scientists do not want their results
to depend on the specifities of one system. And, in any case, they often
don't want (or can't) implement their ideas in software. Thus, they use
"cost models". For example, you can prove that it possible to sort
an array using "n log n" comparisons.

(explain why this is so in a concise way)

Computer scientists like to assume that the model predicts accurately the running speed of
the program implementing the algorithm. I should warn you that most models fail at 
this goal, but it rarely concerns computer scientists. In any case, 
the naive computer scientist expects a curve representing the running time of the 
program versus the size of the input to look like a plot of the function f(n) = n log n.
But what of the units? Does it take n log n seconds or n log n minutes to sort
an array containing n elements? And what if my program always needs a given fraction
of a second when it starts, irrespective of the value of n?

So we are going to ignore these details and be happy if the running time 
goes like K n log n  when n is very large and for some constant K that depends
on your system and chosen unit.

That would be beautifully simple, but real-world programs often have speeds
that depend on the input. Suppose that you are benchmarking the time it takes 


Then we get another problem. Some programs have speeds that depend on the input.
Suppose that your program seeks the first instance of a given value in an array.
An algorithm that visits all elements one by one, stopping whenever the target
value is found, might require up to n comparisons when the array has size n, but
possibly far less.

Thus, we say that an algorithm has a cost in O(n log n) or O(n) if, when n
is large, the cost can be bounded by a function K n log n or K n for some constant
K.


- n is often not large, certainly not infinitely large, all computers have finite memory, no program can run with ever larger inputs
- Cost models are usually counting the wrong things, so they are bad at predicting real-world performance. In fact, computer scientists do not even pretend that their model predicts real-world performance (they never check). Even if you did check, the statement " the running time can be bounded by a function K n log n" when n is large is not testable, falsifiable. It is a mathematical statement, not a scientific one.
- when n grows, in practice, we often use different programs, different algorithms
- many algorithsm with favorable cost models can be impractical, e.g., linked list
- performance problems are not always due to large inputs: you can have massive performance problems due to tasks over small inputs if they are common enough.
- constants do matter, we are often willing to pay twice as much for a computer that runs 20% faster. Certainly, it would be easy to sell a computer that runs twice as fast at twice the cost, if everything else (e.g., power usage) remains the same.


- predictable performance matters

- data access (disk, network, memory, cache) is often the bottleneck

- then, only then, execution
- execution is superscalar

- JIT
- effect of the programming language
- Can you write fast code in a slow language
- Can you write slow programs in a fast language


prediction about performance are almost always wrong

Performance is data specicific: scanning a sorted array for a value is probably faster than scanning a randomized array

putting a rarely used branch into a separate code location helps with instruction cache buffering
  
  10x cache ratio, less memory better speed
  
  row-wise column-wise, random-wise
  
  adding/squaring vs temporaries
  
  data dependencies
  
  unrolling: Why are unrolled loops faster?
https://lemire.me/blog/2019/04/12/why-are-unrolled-loops-faster/


Performance speed limits
https://travisdowns.github.io/blog/2019/06/11/speed-limits.html

How fast is getline in C++?
https://lemire.me/blog/2019/06/18/how-fast-is-getline-in-c/


Nice quotes:
Complexity theory itself is a gross estimation on reality and performance. Complexity theory tells you nothing about how fast (or slow) an algorithm is in practice: quicksort typically is faster than merge sort, despite both being O(n * log(n)).
Heck, quicksort can be faster than radix sort in many cases. Another case: Bitonic sort is asymptotically slower at O(n * log^2(n)), but Bitonic sort lends itself to parallelism very well, so its "faster" in practice (even if its not work-efficient). So why do people use complexity analysis at all? Its completely irrelevant to determining quicksort vs mergesort vs bitonic sort! Well, simple: because its relatively easy to calculate, and relatively easy to understand. Polynomial time, and Nondeterministic Polynomial time (aka NP-complete) are both "easy" to describe and understand (for a... somewhat interesting definition of easy). At least, in the greater scope of mathematics they're concise and "simple" definitions.

A great number of algorithms in Knuth's "The Art of Computer Programming" are calculated out to the precise number of assembly-language statements executed... including the constant. No "big-O" estimates involved. This deeper analysis is great to read once or twice, but read enough of it and you realize how much harder it is to think about. Complexity theory is far faster to analyze and apply to algorithms, even if its an incomplete picture. As such, emphasis should be on "ease of use" and "convenience" as opposed to any real amounts of practical rigor.

The other issue: is that NP vs P is the great unsolved mathematical problem of our lifetime. So a huge amount of professors introduce the concept of NP vs P so that their students can be ready for a major mathematical debate relevant to the field.

EDIT: In practical optimization, I think most people care about "Linear", "Sublinear", and "Superlinear". For example, the Painter's Algorithm for GPUs is superlinear: O(n * log(n)). But a depth-test based approach to GPU scene painting is linear: O(n). Linear is "good enough" so optimization basically stops there.

