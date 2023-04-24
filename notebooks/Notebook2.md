# Design notebook entry

## Last week's critique

**TODO:** Fill in this part with a summary and reflection on the critique you received for
last week's work. Answer questions such as:  How, specifically, did the feedback help
improve the project? Did the feedback point out or offer something you hadn't considered?
Did it help you make a design decision? Was it helpful in addressing the most pressing
issues in your project? How will you incorporate the feedback into your work? Will you
change something about the design, implementation, or evaluation as a result?

Both the feedback I received from Prof Wiedermann and from Adam helped me fully commit to
pivoting my goals: changing my intended user base away from total newbies has allowed me to
focus on creating a more feature-rich DSL. I also took Adam's advice in implementing a play
function, which runs the actual game. This serves as a wrapper for the whole Round-Turn
structure. Speaking of the Round-Turn structure, I'm still working out exactly how Actions
will fit in, but I was able to pin down a general implementation of round(), and am getting
close to figuring out how a specific implementation of turn() might look. I've also been
focusing on filling out the features of each class much more (although certain of them
have been quite difficult). I've also been taking a look at trait usage, and I have some ideas 
of how I might want it to work; I definitely need to do some more research about OOP in Scala
in general, as I've been running into some weird subtyping problems that I don't quite 
understand.

## Description

**TODO:** Fill in this part with information about your work this week:
important design decisions, changes to previous decisions, open questions,
exciting milestones, preliminary results, etc. Feel free to include images
(e.g., a sketch of the design or a screenshot of a running program), links to
code, and any other resources that you think will help clearly convey your
design process.

I spent a good chunk of this week adapting my Python code into Scala, adding
some richness to it that takes advantage of Scala's DSL-building features. I
got pretty stuck while trying to implement a "do for all players" function that
has a more readable syntax than just using a for loop. The problem is that it's
very difficult to have the iterator variable accessible in the body of the loop,
without having an onerous amount of syntax for the user to write.

## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

I need to finish implementing Hearts using my new syntax, and see where the
continuing sticking points in my code are. My Scala code is not currently more
*efficient* than my Python code, in terms of lines written, but it's already
significantly more readable. I'm really happy with where my interrupts are going,
but I need to work out the prompt and eachPlayer functions. In class, I need to
ask Prof Wiedermann why my deal function is requiring parentheses, and how I
should lay out my classes- should they all have separate files?

**What questions do you have for your critique partners? How can they best help
you?**

I'd love to get some advice about implementing prompt and eachPlayer, but I think
I'll have to ask my critique partners and Prof Wiedermann about them in class, as
just code reviewing might not necessarily be that helpful. I also want some advice
about how to lay the classes out in different files, and maybe just pick my partners'
brains for some more functions that would make sense for my various classes. I also
definitely need help with some parentheses-free syntax implementation, but again
I think I'll just have to ask about it in class.

**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**

Outside of class, and not including this reflection, I spent around 6-7 hours this week
working on this project.

**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**

I think I made it much more progress on design than I expected to, but much less
progress on implementation than I meant to. I think that's ok, as I expect my
implementation process to speed up a bit now that I'm more practiced writing Scala
and in my DSL. I still feel like I'm on track to get to a good place by the end of
the class, but it's still been a bit slower going than I was expecting.
