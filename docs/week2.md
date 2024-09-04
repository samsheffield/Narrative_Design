# INTERACTIVE FICTION

## Discuss Interactive Fiction Selections
- Break into small groups (3-4 people) and discuss the 3 games you played for homework.
- Use your notes and open-ended questions to drive the discussion.
- Share out as a larger group. 

## Interactive Fiction
Interactive fiction (IF) is a category of games that communicate with the player through text. These are the type of video game storytelling, and they continue to be developed to this day.

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

## Infocom
Infocom was a successful software company from the 1980s which produced numerous classic works of interactive fiction. The company started as a collaborative project between MIT staff and students, many who had previously worked on a version of their flagship adventure title, Zork. Infocom was a highly successful company, dominating the early computer software marketplace (In 1983, the computer software distribution company, Softsel, listed all of the top 10 selling pieces of software in December as Infocom games). They remained independent software produces until 1986 when their business was acquired by Activision.

Infocom games were interactive text adventures in which players used short series of words to give commands such as "go north" or "turn on the microphone" the software. These fall under the category of Parser Interactive Fiction.  

These games were programmed using a language called ZIL (Zork Implementation Language) and run using a virtual machine called the Z-machine interpreter. This machine has been ported to various computer platforms and has resulted in the games still being playable today on modern computers. The use of a virtual machine also allowed their games to be run on computers that weren't intended for such use.

Infocom games were notable not only for their quality or popularity, but also for their clever marketing and use of included props and extras called "feelies". Feelies extended the fiction of the games into physical, tangible objects and also sometimes served a secondary purpose: anti-piracy protection.

## Choose Your Own Adventure Books
CYOA was one of the most popular series of children's books in the 1980s in the US, originally created by Edward Packard. The concept was created in 1975, but Packard was rejected by publishers for years leading to Packard shelving the idea for a period.

These books (called "gamebooks") allowed readers to participate in the stories by making choices. These choices would lead to multiple endings, thus allowing the reader to "choose their own adventure" on each read through.

This form of interactive fiction is reminiscent of the types of web-based games which became popular in the 2000s created using Twine.

##  Interactive Fiction Resources
- The Infocom Gallery ([link](http://infocom.elsewhere.org/gallery/))
- The Interactive Fiction Database ([ifdb.org](https://ifdb.org/search?searchfor=system:Inform+7))


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

Today, we'll be focusing on the basics:
- Knots
- Diverts
- Choices (and how to suppress them)
- Managing loops
- Combining choices with output

# Homework

## Read Plot. It's a Problem. by Emily Short
Read [this informative blog post](https://emshort.blog/2021/08/10/mailbag-plot-its-a-problem/) by Emily Short on the challenges and importance of good plotting in your narrative games. 

## One Room IF Exercise
Create a short (no longer than 5 minutes to play) Interactive Fiction game using Ink with the following simple premise:

_You are in a room that you want to leave._

### Design Considerations:
- There is only one way out of the room, so the choices given to the player must ultimately connect back to the same place. Avoid multiple endings.
- Use choices to establish the setting of your game and reveal details about who/where we are. Where are we and how do we know? What things do you need to expose to the player? What time of day is it? 
- Choose language which you feel effectively sets the tone for the experience. Avoid making it purely descriptive.
- This game will be very linear, with a focus on exploration and not on things which complicate our ability to achieve the goal (like puzzles). Give us something to _see_ and choices which encourage curiosity.

### What to turn in
- Please upload the .ink file to the class Canvas site.