# Ink cheatsheet for Narrative Design Fall '24


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

### Default choices
It's possible to use a divert without text to create a default choice if no other non-repeating choice remains. For example:

```
== default_choice_example ==
* One -> default_choice_example
* Two -> default_choice_example
* -> END
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
