# Design notebook entry

## Last week's critique

**TODO:** Fill in this part with a summary and reflection on the critique you received for
last week's work. Answer questions such as:  How, specifically, did the feedback help
improve the project? Did the feedback point out or offer something you hadn't considered?
Did it help you make a design decision? Was it helpful in addressing the most pressing
issues in your project? How will you incorporate the feedback into your work? Will you
change something about the design, implementation, or evaluation as a result?

The critiques I received in class last week helped me better pin down what the goals of my project are.
First and foremost, I want a versatile language that is able to describe a large variety of games. This means that making my language overly restrictive in any way will fundamentally limit the types of games that can be created; thus, the language should still allow for many general-purpose programming language concepts. While this might mean that the language errs close to the border of DSL and library, it is critical that the language remains as flexible as possible.
Secondly, the language should be easy to read; Adam and I are both working on languages that will likely be read, if not necessarily written, by people without a significant CS background. Thus, it should be somewhat prosaic in form.
Finally, it would be nice if the language was easy to write; much like the above point, the accessibility of the language is important, although not quite as crucial.
This has shaped how I've approached the entire project, and I think it will significantly speed up my development process.

## Description

**TODO:** Fill in this part with information about your work this week:
important design decisions, changes to previous decisions, open questions,
exciting milestones, preliminary results, etc. Feel free to include images
(e.g., a sketch of the design or a screenshot of a running program), links to
code, and any other resources that you think will help clearly convey your
design process.

This week has been a very interesting, design-wise. For the flexibility criterion I discussed above, I decided very quickly that my project should be an internal DSL. That way, in case there is some way in which the language is incomplete, a seasoned programmer could add some host language code as a stopgap until the DSL can be updated. This realization was difficult- I spent a few hours programming an object-oriented framework for board games, then extended it to 52-card-deck card games, then used that framework to program the game Hearts. The process of programming exposed a lot of the "sticking points" where a DSL could be useful. For example, many games have a set round structure, in which each player takes a turn; each of these turns is a specific sequence of steps, each of which are made of one or more actions. These actions are in turn composed of atomic moves, like moving a card from one location to another, or rolling dice. The below document outlines the current OOP structure of game objects, but but the Round-Turn-Action-Move relationship is currently eluding me.

I implemented everything this week in Python, as it was quick and simple to get my ideas down, which let me find the places where a DSL could really fill in the gaps. However, I'm still confident that I want to implement the actual DSL in Scala, as I think the features it offers, both in terms of customizability and OOP in general, will allow for a better-constructed language. This is a bit of a tradeoff, however. Having a DSL hosted in Scala rather than in Python means that a prospective programmer will have a larger barrier to entry. As I alluded to in my first section, though, this will likely mean that the language is easier to read, but harder to write (at least, for someone with little CS experience). Since I consider the functionality and readability of the language to be more important than its writeability, I think this is a tradeoff worth making. While I'm a bit disappointed that the language will not be as easy to use as I had originally intended, I think this is in the language's best interest. With many more weeks of development, I feel confident that a GUI could be devised, perhaps Scratch-style, that would make development in this DSL as easy as I want it to be, without sacrificing its flexibility or readability.

https://docs.google.com/document/d/1yPfdPlC9sN5qvzx74-tXSt-7NBsu8DFBAY_Z_-y3AB8/edit?usp=sharing

I have actually implemented all of the features on the first page of this document in Python (which I used to construct the Hearts program), but the features on the second page are the ones currently giving me trouble.

## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

Far and away the most pressing issue for my project is the Round-Turn-Action-Move sequence. I feel confident that the Round implementation won't be terrible, and most of this week was spent getting Move to be as ironed out as possible. I'm just not totally certain that Scala has the right tools to make the Turn and Action sequences quite as crisp as I want them to be, but I think I'll be able to find something good enough; I just suspect it's going to take a lot of time. On the bright side, I think I've found a pretty good design loop, which I was using this week: I wrote a full program in my temporary Python DSL, then added features to that DSL to reduce the size of my program, shrinking it quite considerably (and making it much more readable). This seems like a good way to evaluate the strength of my DSL in general, although writing programs in it that serve as functional test cases is quite daunting at times, and may take up the bulk of my time in one of the later weeks.

**What questions do you have for your critique partners? How can they best help
you?**

First, I want to know if my goal realignment makes sense for the language; is it really better that my language should be more fully-featured at the expense of its readability?
Second, I have a design conundrum: I'm not sure whether to have a few classes with a lot of functionality, all of which will not necessarily be used in every program, or many classes with more specific functionality. I'm leaning towards the former, as it feels more intuitive: someone programming in the language is more likely to understand a Card class, rather than a CardWithTextAndFlavor class and a CardWithPowerAndToughness class. If they need more specific options, or need additional features, the language will still support subclassing and inheritance.

**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**

Not totally sure, but somewhere between 7 and 9 hours, probably around 8 (not including the time I spent working on this notebook).

**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**

I feel like I'm on track for where I wanted to be with the project, but the design phase has been far tougher than I expected it to be. To be honest, I hadn't really appreciated how difficult rules enforcement was going to be, which is something that I figured was going to be fairly easy. Honestly, I still haven't fully decided how deeply rules enforcement is going to be embedded in this version of the DSL; it's extremely finicky, and I'm worried its slowing down the project. However, for this to be viable for a computer to play, it needs to have rules enforcement: a computer playing chess that didn't understand the rules of chess, but knew how to win, would try to take the King on the first move every time; that makes the main goal of my project largely null and void.
I'm not sure whether the project will be at all close to the point where I want it to be at the end of these four weeks; however, I do feel like I am putting in good work (and a lot of time), and learning some difficult lessons about language design. I think I'm still on-track for an A on the project, and I have the distinct feeling I'll be putting some work in on it over the summer- it's been a blast to work on so far, despite the difficulties I've been having. Hopefully, critique groups will clear up my uncertainty a bit, and I'm excited to jump back into Scala.
