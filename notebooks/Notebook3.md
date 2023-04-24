# Design notebook entry

## Last week's critique

**TODO:** Fill in this part with a summary and reflection on the critique you received for
last week's work. Answer questions such as:  How, specifically, did the feedback help
improve the project? Did the feedback point out or offer something you hadn't considered?
Did it help you make a design decision? Was it helpful in addressing the most pressing
issues in your project? How will you incorporate the feedback into your work? Will you
change something about the design, implementation, or evaluation as a result?

The critiques I received last week set me on the right track with some of the design issues I was having,
especially my stylistic issues. Adam has been keeping me on track with not getting bogged down in the style of 
my language and focusing on functionality over form for the time being. Checking out the rules of Magic: The 
Gathering has also been good, as it's been making me think about how game designers think about timing windows 
during games, and how blocks of code might be reused, e.g. since MTG "Main Phases" happen twice per turn. Our 
discussion of parentheses-less and infix functions in class was also super helpful, but I anticipate I'll end 
up thinking about that more when I finish the main functionality.

## Description

**TODO:** Fill in this part with information about your work this week:
important design decisions, changes to previous decisions, open questions,
exciting milestones, preliminary results, etc. Feel free to include images
(e.g., a sketch of the design or a screenshot of a running program), links to
code, and any other resources that you think will help clearly convey your
design process.

This week I "completed" a draft program in my DSL, the card game Hearts, when I realized that there was 
something severely wrong with my entire design. I had completely forgotten that Scala is not a 
dynamically-typed language, and thus, I couldn't use classes in place of their subclasses, like I had in my 
Python implementation of the language. The majority of the week was spent testing out different methods for 
making my existing design work: the Dynamic trait, generic types, and even switching host languages. At the 
very end of my work this week, I think I found an acceptable solution, which involves a HashMap of variables 
and constants, plus liberal use of the class extension functionality of Scala, but I definitely want to talk 
to other people in class about other ways I might go about tackling the problem. It definitely was 
disappointing to go from feeling like my language was at a really good place to having such a severe setback, 
but perhaps it will be for the best; the way I'm planning on doing things now won't require the user to have 
to understand OOP, which would be really nice.

## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

Honestly, I just have to get these type issues ironed out and I should have something that, while ugly, 
actually does work the way I intend it to.

**What questions do you have for your critique partners? How can they best help
you?**

I just want to run the various options I discussed above by my partners and talk about the pros and cons. I'll 
also definitely need to chat with Prof Ben about if there are any Scala features I might be missing or other 
ways to tackle the problem that I haven't thought of yet.

**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**

I spent a significant amount of time on the project this week, probably close to 8 or 9 hours, not including 
class time and this reflection.

**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**

This week was pretty horrendous. I felt like I was digging myself out of a hole the entire time; however, I 
feel like I learned a lot more about Scala (reading a bunch of documentation always helps), and I have some 
great ideas about how I would want to implement future problems in Scala. I also definitely feel like I'm 
figuring out some of the tradeoffs of an internal vs. an external DSL (and now kind of wishing I had done an 
external one), but I'm glad that I now have a good idea about what internal vs. external implementations look 
like (I did the latter in PLs with the Raskell final project).
