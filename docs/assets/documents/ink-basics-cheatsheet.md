# Ink Cheatsheet for Narrative Design Fall '24

## Official Ink documentation
Most of what follows is selectively derived from the official documentation. There's s much more to learn! Here are the two main documents:
- [Ink Basics Tutorial](https://www.inklestudios.com/ink/web-tutorial/)
- [Ink Writer's Manual](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md)

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

### Divert position affects Output
The position of a divert will affect the Output text. For example:
```
== my_name ==
Sam
```

`My name is ->my_name `

produces the Output

`My name is Sam`

while the following 
```
My name is
-> Sam
```

produces

```
My name is

Sam
```


### END knot
The END knot indicates the end of your content. You do not create content for END, you just send the You always want to make sure that your knots divert to an end like this:

`-> END`

## Choices

Choices are the type of input offered to players via Ink. There are two types of [choices](https://github.com/inkle/ink/blob/master/Documentation/WritingWithInk.md#2-choices) in Ink.

The standard way of creating a non-repeating choice is to use a `*` .

The other way, which allows you to reuse a choice is with a `+` . This is called a _sticky choice_ and is helpful, for instance, if you want to send a player back to a knot and have all choices available and repeatable.

A non-repeating choice looks like this:

`* Say hello. -> name_of_knot`

and a sticky choice looks like this:

`+ Say hello. -> name_of_knot`

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

which results in

```
CHOICE:
"I'm fine."

OUTPUT:
"I'm fine," I responded.

"Oh, that's nice", he replied.
```

### Default choices
It's possible to use a divert without text to create a default choice if no other non-repeating choice remains. For example:

```
== default_choice_example ==
* One -> default_choice_example
* Two -> default_choice_example
* -> END
```

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


### Reusing the same knot but incrementing the visited count
Surprisingly, if a divert leads to the current knot, the count will not go up! You need to leave a knot and then return to keep counting, like this:

```
== loop ==
// Print the count
{loop}

+ Choice 
    -> return_to_loop

== return_to_loop ==
-> loop
```


#### Comparison Operators
You can compare a this count to a number using an operator, such as >, <, ==, or !=

Examples:
```
// If the knot count is equal to 1
{loop == 0}

// If knot count is greater than 1
{loop > 0}

// If knot count is less than 1
{loop < 1}

// If knot count is not equal to 1
{loop != 0}

```



### Creating variations of text with alternatives
The | character is used to create different text variations.

#### Variation 1: Sequence
Sequences provide alternatives in order and stops on the last option:

```
The cat is {sleepy|tired|lazy}.
```
Which produces these variations:
```
The cat is sleepy.
The cat is tired.
The cat is lazy.
The cat is lazy.
```

#### Variation 2: Cycle (&)
Cycles provide alternatives in order and loop when finished:

```
The cat is {&sleepy|tired|lazy}.
```
Which produces these variations:
```
The cat is sleepy.
The cat is tired.
The cat is lazy.
The cat is sleepy.
```

#### Variation 3: Do Once (!)
Do Once provides alternatives in order and only displays text once:

```
The cat is {!sleepy|tired|lazy}.
```
Which produces these variations:
```
The cat is sleepy.
The cat is tired.
The cat is lazy.
The cat is .
```

#### Variation 4: Shuffle (~)
```
The cat is {~sleepy|tired|lazy}.
```

Which produces variations like this:
```
The cat is tired.
The cat is sleepy.
The cat is sleepy.
The cat is lazy.
The cat is tired.
```

#### Variations can be combined
Here is an example of variations which are shuffled and displayed only once
```
The cat is {~!sleepy|tired|lazy}.
```

#### Variations can include diverts!

```
The cat is {!sleepy|tired -> nap|lazy ->END}.
```

### Shuffling
There are additional ways to shuffle alternative text.

#### Shuffle and display each only once
```
{shuffle once:
    - yes
    - no
}
```

#### Shuffle and stop on last choice
```
{shuffle stopping:
    - yes
    - no
}
```
