# programmingishard

## Message to random visitors :

Ultimately, I plan for this GitHub repository to turn into a "book".
Somewhat accidentally, I made the repository public, and some people
took notice. 

I have since decided to leave the repository public.

Yet, this project not nearly ready for public consumption. It is a mess.
It is naive. It is boring.


## Preface

I learned to program when I was barely twelve years old. Like most kids,
I started out trying to program my own video games. And I largely failed.
The projects would start out well, but then I would often encounter surprising
problems. 

For example, I recall learning how to draw a strawman, pixel by 
pixel (at the time, in the 1980s, we had few pixels). It worked beautifully.
So I figured that animating the strawman would be easy. Just draw the strawman,
clear the screen, and redraw the strawman. On paper, it is a flawless plan.
In practice, the result was horrible. It kept my processor fully occupied
while the screen was flashing.

In a later project, I decided to stick with moving a "tank" made of only
a couple of pixels. This worked much better. One of the pixel would flash
annoyingly, but I decided it was a feature. Then I decided that my tank should
fire bullets. After a time, I managed to have the "tank" fire a single
bullet (made of a single pixel). It worked beautifully... with the bullet
flying through the screen. At first, the bullet would mave at the same speed
as the tank, so one pixel at a time. But that was a problem because the tank
could litterally keep up with its bullet. So I doubled the speed of the bullet,
so it could move two pixels with each time increment. This was better, but not
fast enough. I think I ended up making the bullet move four pixels at a time.
Much better. Then I added walls to the environment. My walls were one pixel 
thick, naturally. I did not have to redraw them when the tank moved, but I wanted
both the tank and the bullets to be stopped by the walls.  Because the walls
had a different color, I found it easy to prevent the tank from moving into a wall:
just check whether the color pixel. With the bullets, it was something else:
they moved four pixels at a time... so they could materialize beyond a wall,
and checking the color of one pixel was no longer sufficient. I kept going and
fixed many problems. When a friend of mine came over, I invited him to play.
He quickly found many vexing problems. For example, by moving in diagonal, it
was somehow possible to move the tank through a wall. My friend also noticed
that my tank could only fire one bullet at a time. At that point in time,
my code was getting a bit large. I could not identify the bugs. I tried
changing the code in various ways, but nothing did it. Furthermore, I had
no idea how allow the tank to shot an unlimited number of bullets, though I did
find a way to fire up to two bullets.

Over time, I got a lot better. As a seniors in high school, we had a 
computer science class and I could run circles around most (but not all)
of my peers. I wrote an adventure game with minimalist natural language
processing. I wrote an Othello board game.

I then took my first serious programming class, at a local community 
college. I learned to program in Pascal. I discovered IDE (integrated
development environments), debugers, structured programming and so forth.
I believe that the class I took was commonly taken by students who were
pursuing technical studies. Though it was an introductory course,
I was impressed by how little I knew starting in the course.

I never took another programming course. In fact, I never took any 
computer science course. While in college, I audited an introductory 
course, but it was taught by  lowly graduate students with minimal 
supervision from a bored professor.

So, as a programmer, I am largely self-taught. But I expect that it is
quite common. In the best of cases, college programs have a small handful
of programming classes. And they are most often in an introductory setting,
a stepping stone to get students to move on to the more important things like 
artificial intelligence, software engineering or theoretical computer science.

It is maybe for the best. I don't think we learn to program by watching
someone talk in front of a classroom. I think it is a bit ridiculous to
expect students to "program" with pencil and paper, as if they were Ada
Lovelace. It is also hard to teach what you do not know, or do not love,
and, evidently, to many computer scientists, programming is a lowly task.

Still, people learn to program. And, collectively, we get better at it. The
"trade" of programming has become much more sophisticated since the days I 
first wrote my naive tank game.

As for myself, I learned a lot from both my mistakes and my successes. Here
are a few of my early experiences:

- I was tasked by a Physics professor to program a "galaxy" simulator in Pascal.
  One simply had to spray a few stars, give them a nudge, and see how gravity 
  made them move. My simulator was initially quite buggy, but it eventually 
  did display the stars. At each time increment, I had to account for each star
  "pulling" on each other star. Alas I quickly realized that my program did not scale.
  I could simulate two or three stars, but no matter what I did, I could not make
  hundreds of stars flying over the screen. Quite simply, as the number of stars
  increase, the number of interactions between stars increase much faster (quadratically).
  Thus I learned a valuable lesson: though my computer is fast, it cannot solve
  all problems quickly.
- In college, my friends like to play a "solitaire" game where one starts with a board
  where all cells but one is occupied. You can move the pieces like in a Checker game,
  jumping over another piece. The piece that gets jumped over is discarded. The goal
  is to empty the board so that a single piece is left. My friends learned all sorts
  of clever ways to solve this game, and they challenged me. I was annoyed and I did
  not want to bother learning to play well. So I went to my room, and within an hour
  or so, I wrote a program that could generate as many solutions as one wanted. My 
  algorithm was super simple: it simply started each new game with a random allowable
  move. It would keep playing randomly. When no more move was possible, it would check
  the number of pieces left. If a single piece was left, it would print out the result.
  This simple randomized algorithm turned out to be very fast. My program was very simple.
  My friends quickly stopped playing afterward.
- When Microsoft released Windows 3.1, I was in love. My PC had this beautiful interface.
  What could I do with it? I decided that I would write a talking clock. It was easy
  enough. Since we did not have voice synthesizers, I simply recorded my own voice.
  My talking clock was beautiful! The only problem was that it was large and used almost
  all the memory in my PC!

One experience after another, I learned to program. It was difficult.

Using as credentials my Ph.D. in Mathematics, I became a professor in Mathematics,
then a government researcher in "information technology", and later a professor
in computer science. I became a professor somewhat by accident. It is likely
that had there been other paths open to me, I might have become a programmer.

Nevertheless, I kept being surprised at how little the people I met knew about
programming. You'd think that computer scientists would show some interest
in the art of programming, but, as a matter of pride, computer scientists would
insist that all the programming in their research projects was done by students.

The implication is clear: programming a low-status activity.
It is not uncommon for programmers to work for non-programmers 
who assume that programming is easy. Many sentences
start with "you just have to..." and finish with a task that is far
beyond the abilities of most people. "No, you cannot just convert these
scanned pages into your favorite word processor format without introducing
errors."

Educators have tried for years to make programming sound easy. You
have great projects like Scratch. Many business leaders promote software
programming as a career.

You would think that I would be pleased at such development, and in some
way I am. 

I used to think that important programming projects
required large teams with much funding, or few exceptional people.
I no longer think so. Advanced programming skills can be acquired,
they can even be acquired quickly. That's because programmers are
an ingenious bunch. More than maybe any other professional community,
they have built tools and made available their know-how, all of it
packaged in a particularly accessible way, if only you know where to look.

But I fear that part of these initiatives are contributing to
the myth that programming is a shallow skill. I don't think it is true. 
Programming is hard in the same way that writing, machining, dansing,
or baseball is hard.

We used to think that most people could never learn to read and write.
We now know that most people can learn to read and write. However, few
people can write for the New York Times. Almost nobody can become a famous
novelist. Writing well is hard.






## random plan


beyond naive theory:
  - models lie: constant-time are not constant time, focus on the data size you have
  - hash tables can fail you
  - maps and sets : hash tables are not O(1), often not even close

memory is hard 
  - throughput and latency
 - locality matters 
  - objects consume memory: fewer objects, less memory

memory is parallel, so even harder
 - little’s law
  - memory access is parallel, and this is limited by instruction windows, batching is good
  - extra core/parallel code can be necessary to achieve best throughput


Your processor can do many things *per* cycle
  - Your processor can see in the future
  - Unpredictable branches are bad
  - this interacts either favorably or unfavorably with memory: linked list is bad  

numbers are hard
  - most calculators can't do 10000000000000000 + 1 = 10000000000000001
  - floating point are difficult a*b  - a * b is not always zero, often not even close
  - subnormal 
  - NaN
  - associativity
  - two's complement: how are negative values represented?

strings are hard
  - Unicode, UTF-8, UTF-16, what is a "character", how many "characters" in your string? How do  you represent an emoticon?
  - Sorting, hashing

randomness is hard
- generating good random numbers can be hard
- useful algorithms: Bloom filters, reservoir sampling, Knuth's shuffle.



