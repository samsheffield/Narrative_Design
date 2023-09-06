# PARSER GAMES & INTERACTIVE FICTION

## Interactive Fiction
Interactive fiction (IF) is a category of games that communicate with the player through text. There are different types of Interactive Fiction, such as Parser IF like the games we played for homework.

### What is a Parser IF game?
Parser games are Interactive Fiction games played by typing in a set of limited commands through a natural language interpreter console. These are the earliest types of Interactive Fiction. They typically rely heavily on puzzles to complicate the unfolding of the story.

## Colossal Cave Adventure (1976)
Widely considered the first Interactive Fiction game, created by William Crowther in 1976. It is a simulation of the Mammoth and Flint Ridge cave systems in Kentucky with magical elements.

Crowther said this about the game's origin:

"I had been involved in a non-computer role-playing game called Dungeons and Dragons at the time, and also I had been actively exploring in caves — Mammoth Cave in Kentucky in particular.
"Suddenly, I got involved in a divorce, and that left me a bit pulled apart in various ways. In particular I was missing my kids.

Also the caving had stopped, because that had become awkward, so I decided I would fool around and write a program that was a re-creation in fantasy of my caving, and also would be a game for the kids, and perhaps some aspects of the Dungeons and Dragons that I had been playing.

My idea was that it would be a computer game that would not be intimidating to non-computer people, and that was one of the reasons why I made it so that the player directs the game with natural language input, instead of more standardized commands. My kids thought it was a lot of fun."

### Legacy
Colossal Cave Adventure directly inspired the creation of numerous early commercial computer games such Infocom's [Zork](https://en.wikipedia.org/wiki/Zork) (1977), [Adventureland](https://en.wikipedia.org/wiki/Adventureland_%28video_game%29) (1978), [Rogue](https://en.wikipedia.org/wiki/Rogue_(video_game)) (1980), and Atari's [Adventure](https://en.wikipedia.org/wiki/Adventure_(1980_video_game)) (1980) which collectively formed the foundation of interactive fiction, adventure, rogue-like genres of computer games.

# Contemporary Parser Games
- The Interactive Fiction Database ([ifdb.org](https://ifdb.org/search?searchfor=system:Inform+7))

## Discussion Groups: CCA and Emily Short selections
- Break into small groups to discuss the game you played for homework
- Use the discussion question that you came up with for homework as starting points
- Share highlights of your discussion out with the class

## IF tools
This is not an exhaustive list, but these are popular tools for creating Interactive Fiction today.

### Inform7
[Inform](https://ganelson.github.io/inform-website/) is a powerful programming language that uses natural language syntax for creating parser Interactive Fiction.

### Twine
[Twine](https://twinery.org/) is a popular open-source tool for creating interactive, nonlinear stories created by Chris Klimas. It is an excellent tool which is used primarily for creating online IF in the vein of [Choose Your Own Adventure](https://en.wikipedia.org/wiki/Choose_Your_Own_Adventure) books from the 1980s.

### Ink
This markup language was developed by Inkle Studios as an in-house tool and released as an open source project. It has gained popularity in recent years due to its lightweight syntax, advanced feature set, and ability to be integrated into game engines.


## Ink Introduction
Today we're going to focus on the basics of using Ink and Inky.

### What is Ink? 
Ink is a narrative scripting language for games. It is a _markup_ language, not a programming language, so it has a gentle learning curve and can be implemented really quickly. Unlike other excellent narrative tools such as [Twine](https://twinery.org/), it was designed by Inkle Studios' to integrate into a game engine. It is also able to easily create web-based interactive fiction.

### What is Inky? 

Inky is an interactive editor for Ink files that allows you to easily play through your game as you write it. The editor is very simple but does feature some nice quality of life things like the ability to offer suggestions and highlight errors. In addition to autoring .ink files, it can export to web (for online interactive fiction) or to JSON (for integration into things like dialogue systems).

### Cheatsheet for Ink
Here is a [cheatsheet](./assets/documents/ink-basics-cheatsheet.md) which will be updated to include all things Ink that we cover in this class. The [Ink Manual](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md) is also great and I would highly recommend getting comfortable with it to find examples of advanced Ink usage.

Today, we'll be focusing on the absolute basics:
- Knots
- Diverts
- Choices (and how to suppress them)
- Combining choices with output

## Narrative Design: Plotting & Outlining
Finishing this kind of game is sometimes the most challenging part without making a plan. As with other kinds of writing, and outline is an effective tool for creating the underlying structure of your game.

### What's a plot?
A plot in a story is the series of events which unfold from start to finish ( a beginning, middle, and end). It expresses not only what happens but also how one event leads to another.

_The man woke up in the morning and experienced a number of unfortunate events which led him to arrive in the Emergency Room instead of class as planned._

This is very similar to a classic definition of a game:

_An easily achievable goal complicated with interesting obstacles._

### Outlining the plot
Creating an outline of significant moments in your game and how a player moves from one to another is an important early step that can help you actually finish your game.

It's important not to become too obsessed with the details of each moment at this point. Just provide enough information about the moment and then figure out how it connects to the next one(s).

You can do this on paper, or directly in a tool like Ink. I'd recommend the former and then transcribing it to the latter to avoid worrying about Ink's markup while coming up with your idea.

Two important things about this:
1. Focus on the through-line first.
2. Have an ending (or endings).

### Focus on the through-line first
The through-line of your game is the direct path through it from beginning to the end which contains the significant turning points of the plot. Choices in games are exciting! But they can complicate your ability to focus on the story you want to tell.

Once you have the through-line in place, you can consider what you like and dislike about the structure and complicate the game little by little.

This approach is also nice because you start out with something that actually works and just becomes more interesting with iteration.

### Have an ending
When outlining your plot, have an ending. One of the biggest traps is to _figure it out later._ You might not. And it will be more challenging for you to figure out where to go if you don't have an idea where you are going!

You might even start writing near the ending, or backwards from the ending until you have a sense of the sequence of events leading to it.

Keep in mind with branching narratives (like with the first project) you will have multiple endings to contend with. How do you get to each one?

### Story Beats
Beats are emotional moments in a story. Every scene has at least one emotional beat.

These beats are typically related to a character's ability to achieve internal or external goals. For example:

An external character goal (concrete in nature) might include:
- Finding treasure
- Rescuing a sibling
- Climbing to the top of a mountain

An internal character goal (emotional in nature) might include:
- Feeling financially secure
- Gaining approval from a sibling
- Being the first in the world to achieve something

As emotional moments, beats can either be _up beats_ (giving hope that a character will achieve their goals) or _down beats_ (making us fear they will not achieve their goals).

#### Types of beats
There are many types of beats. Here are some derived from Robin Law's Hamlet's Hit Points ([link](./assets/documents/beat-types.md))

## In-class Exercise
Create a small interactive story using a shared pool of words (actors, actions, objects, and locations) that we create. You can choose the kind of story, but don’t spend too much time thinking about your concept. This is just practice!

We'll use this simple skeleton for our plot:

_[actor] does/did [action] with [object] in the [location] to  [goal]_

### Do this on paper first
You can write this down in the form of a flowchart or use scraps of paper to represent the key moments or emotional beats in your story:

- Write down the ending (you can only have one ending for this exercise).
- Create the through-line to your story (straightest line from beginning, middle, to end). _Keep this very short (under 12 steps from start to finish)_
- Create one meaningful choice for a player that adds interest or complication to reaching the end.

### Transcribe to Ink
Once you have the outline of your story on paper, transcribe the story to ink in a sequence of knots connected with diverts.

### Share
We'll share our stories with one another. No need to share files, just allow others to use your laptop.


## Text Game (Due 09/20)

### Project Description
For this project, you will create a text-only short game with Ink that takes 10-15 minutes to play at most. Your game should have at least three significant endings, but subject matter is up to you to decide. 

### Goals
The goals for this project are to...
1. Get familiar with Ink.
2. Gain experience in charting out the story of a game.

Don’t spend too much time thinking about the perfect concept (masterpiece syndrome). Experimenting with structure and trying things out are more important than the originality of your premise.

# Homework

## Read Plot. It's a Problem. by Emily Short
Read [this informative blog post](https://emshort.blog/2021/08/10/mailbag-plot-its-a-problem/) by Emily Short on the challenges and importance of good plotting in your narrative games. 

## Create an online folder for the Text Game project
Please create an online folder to collect your work on this project (including the outline from this week) and submit the link to me via email before the start of class next week.

Name the folder like this:

`yourname_textgame_narrative_design`


## Begin Text Game: Create an outline
Assignment details can be found [here](./assets/documents/text-game-outline.md)
