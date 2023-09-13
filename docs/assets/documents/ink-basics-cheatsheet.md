# Ink cheatsheet for Narrative Design Fall '23


## Knots
A story is comprised of multiple linked sections that are referred to as [knots](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#3-knots).

These are marked up sections of content with unique names.

These are the fundmental structural element of ink content.

A knot looks like this:

`== knot_name ==`

The name needs to contain no spaces. You also need at least 2 equal signs on at least the left hand side (both is easier to read).

## Diverts
The story can be moved from knot to knot using divert arrows ([diverts](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#4-diverts))

A divert looks like this:

`-> name_of_knot`

### END knot
The END knot indicates the end of your content. You do not create content for END, you just send the You always want to make sure that your knots divert to an end like this:

`-> END`

## Choices

Choices are the type of input offered to players via Ink. There are two types of [choices](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#2-choices) in Ink.

The standard way of creating a non-repeating choice is to use a `*` .

The other way, which allows you to reuse a choice is with a `+` . This is called a _sticky choice_ and is helpful, for instance, if you want to send a player back to a knot and have all choices available and repeatable.

A choice looks like this:

`* Say hello. -> name_of_knot`

### Suppressing choices
Normally, making a choice echoes the text from the choice before the content from the knot. To only display the text from the next knot you can [supress the choice text](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#suppressing-choice-text) with `[]`.

For example:

`[Say hello.] -> hello_knot`

You can also suppress text after choice text which will delay its output until the choice is made:

```
* I laughed[]! Uncontrollably!
```

results in

```
CHOICE:
I laughed

OUTPUT:
I laughed! Uncontrollably!
```

### Combining choice and output
This approach can be used to combine choices with output text, for example, when writing dialogue choices:

```
How are you?
*	"I'm fine[."]," I responded.
	"Oh, that's nice", he replied.
```

## Comments
If you want to leave comments for yourself, which will not appear to your players you can use either 

`// followed by the comment` for a single line or

```
/* 
 many 
 lines 
 of 
 comments
*/
 ```


# Week 3

## Stitches
Knots can include sub-sections called [stitches](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#6-includes-and-stitches) which are marked using a single equals sign `=`:

```
== welcome ==
= first_visit
...
= not_first_visit
```

To divert to a stitch you use _dot notation_ like this `knot_name.stitch_name`. For example:

```
+ [Enter the mysterious house] -> welcome.first_visit
* [Enter your home] -> welcome.not_first_visit
```

Also, the first choice is always the default, so the choices above could also be written like this:
```
+ [Enter the mysterious house] -> welcome
* [Enter your home] -> welcome.not_first_visit
```

### Local diverts
From inside a knot, you don't need to use the full address for a stitch:

```
== welcome ==
= first_visit
-> not_first_visit

= not_first_visit
...
```

## Weave
Ink provide additional markup for more complex branching structures, which it refers to as [weave](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#part-2-weave)

### Gather marks (-)
One of the new features of weave is the ability to [gather](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#1-gathers) your narrative back together without needing a knot or stitch. To do this use a `-` at the start of a line. For example:

```
* I'm tired.
* I'm sleepy.
- I had a restless night's sleep.
```

which results in:
```
CHOICES:
I'm tired.
I'm sleepy.

EXAMPLE OUTPUT:
I'm tired.
I had a restless night's sleep.
```

## Glue
By default, Ink inserts line-breaks before every new line of content. If you don't want this you can "[glue](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#glue)" text together with `<>`:

```
* Hello -> hello_world

== hello_world ==
<> World!
```

## Conditional Choices
You can also turn choices on and off based on [whether a player seen a particular piece of content](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#conditional-choices). This is done using curly brackets `{}`.

```
* [Go home to get your camera.] -> get_camera
* [Go to the park.] -> at_the_park

== get_camera ==
You go home to grab your camera and then head to the park.
-> at_the_park

== at_the_park ==
* {get_camera} You decide to take some photos.
* You decide to take a nap.
- ->END

```

You can combine conditional choices like this:
```
* {get_camera} {at_the_park} [You took a lot of pictures at the park]
```

You can check if a condition has NOT happened with `not`:

```
* {not get_camera} Too bad you forgot your camera!
```

### These conditional choices are actually numbers!
These conditional choices actually keep track how many times you visited a knot/stitch. You can check how many times you've visited something like this:

```
-> hub
== hub ==
* You found the egg! -> get_clue
* You found the key! -> get_clue

== get_clue ==

// you can use greater than or less than to compare. So below: if the get_clue count is less than 2
+ {get_clue < 2} [You've got a clue!] -> hub

// the == means equal to this number. So below: if get_clue count equals 2
* {get_clue == 2} [You found all the clues. What a mysterious place.]
- -> END
```

### Printing the count as text
It's sometimes helpful to show this count in your story. One possible reason would be to just check if the counts match your expectations. To do this:

```
{get_clue} seen. 
```