# Design notebook entry

## Last week's critique

**TODO:** Fill in this part with a summary and reflection on the critique you received for
last week's work. Answer questions such as:  How, specifically, did the feedback help
improve the project? Did the feedback point out or offer something you hadn't considered?
Did it help you make a design decision? Was it helpful in addressing the most pressing
issues in your project? How will you incorporate the feedback into your work? Will you
change something about the design, implementation, or evaluation as a result?

Honestly some of the best feedback I got this week was encouragement to keep working on my project. I was 
feeling pretty defeated after last week, and I was feeling like maybe starting over in a different language 
was the way to go. However, discussing my project trajectory with Adam and some Scala features that I could 
use to smooth things out a bit with Prof Ben really helped. While I no longer think Scala was the right choice 
for this project, I'm excited to use Traits in future Scala endeavors. Discussing languages that might be 
better fits for the project, like Python, also made me interested in functional dynamic languages, so I spent 
a bit of time researching Clojure and Groovy, which might be good alternatives.

## Description

**TODO:** Fill in this part with information about your work this week:
important design decisions, changes to previous decisions, open questions,
exciting milestones, preliminary results, etc. Feel free to include images
(e.g., a sketch of the design or a screenshot of a running program), links to
code, and any other resources that you think will help clearly convey your
design process.

At the end of class on Wednesday, I realized that the dynamic library wasn't quite working how I expected; it 
allows new class members to be added to an existing class at runtime, but it doesn't add these automatically 
when a subclass object is stored in a superclass variable. This meant that although each ```HeartsPlayer``` in 
a ```List[Player]``` should be able to call scoreStack, it wasn't able to. This meant I had to go back to the 
drawing board on implementation, so I tried two things. First, I tried using extension methods; this didn't 
work, and it made the syntax utterly unreadable and full of awful (but necessary) kludges. I then figured out 
a way to use ```this.``` to assign new superclass members within a subclass initializer. This works ok, 
although the way that these member variables are stored, in a ```Map[String,Any]``` means that we can't call 
any functions on these variables. By judiciously working around these limitations, I was, at long last, able 
to create a working version of the game Hearts in my DSL; it's horrifically ugly, some of my implemented 
functions are only usable for specific use-cases, and its significantly longer than my original python code, 
but it works. I'm pretty sure my implementation in Scala is as good as it's going to get; I've spent a lot of 
time exploring various alternatives to the Dynamic library, but, without fundamentally limiting my language in 
some way, there is no neater way to implement what I've already done.

## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

To be honest, my DSL kind of feels like a mediocre Scala library right now. It honestly might be best if I just
start over, maybe in Python, Clojure, or Groovy, since these languages have Dynamic types. While that's out of 
scope for this class (I only have so much time in the week), I've been pondering how I could implement this 
language as an external DSL. I spent some time commenting my code this week, but a README explaining how to 
write in the language and run programs would be really helpful; hopefully I'll have time to add that.

**What questions do you have for your critique partners? How can they best help
you?**

I think I need someone to read over the Hearts program (without looking at boardGame.scala) and tell me if 
they can understand what it does. One of my original design goals was readability, which I don't think I am at 
all meeting in general, but if another CS major can understand what's going on, I'll be pretty happy.

**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**

About 6 hours, outside of class.

**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**

This week, I think I finally cemented the fact that Scala was not the right host language for my design, and 
an internal DSL was also not the choice. I do feel a lot more skilled with Scala, since a lot of this week was 
spent testing things out in separate files and reading documentation, and I understand a lot better the 
tradeoffs of a static vs. a dynamic language. While I'm sad that my DSL didn't turn out at all how I wanted, I 
am proud that I have a working implementation of a game in my language.
