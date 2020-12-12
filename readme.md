# Tree Notation - the Book

This book aims to explain the core ideas of Tree Notation so that you can leverage these ideas to build useful, complex things using simple technology.

The book will be broken up into Sections.

The first Section will be written for people that want to build Tree Notation libraries in their favorite programming language(s).

Each Section will be broken up into Chapter.

Each Chapter will present a real life challenge and guide you through solving it with Tree Notation.

Tree Notation is still a very early idea. It is likely that while working with it you will come up with novel ideas, better terms, and useful tricks! It will be a journey for both the readers of this book and the author(s). Do please share pull requests to make this book better. And feel free to *own* these ideas. You are on the cutting edge. If you think the name "Tree Notation" is a misnomer, come up with something better. Tree Notation is *not* a trademark or a patent. Tree Notation is *not* a company. It is *not* a marketing ploy. It is an *idea*, in its earliest stages, and will only be useful if people like you improve it and make it so.


## Outline

Section 1: Building a Tree Notation Library in an Existing Language
 Chapter 1: Grid Notation and Basic Parsing
 Chapter 2: Adding Useful Read and Write Methods
 Chapter 3: Parsing to Types
 Chapter 4: Compiling to Other Languages
 Chapter 5: Grammers
 Chapter 6: Combining Grammars
 Chapter 7: Visual IDEs
Section 2: Tree Notation for Non-Programmers
 Chapter 1: Tree Notation with Just Pen and Paper
Section 3: Tree Notation and Hardware Implications
Section 4: Tree Notation and Connections with MathDSLs and the Physical Sciences

## Section 1: Building a Tree Notation Library in an Existing Language

So you are intrigued by Tree Notation, but you only program in the MonkeyBanana Programming Language and have a hard time grasping how this could be useful. This Section will walk you through creating your own general purpose library to read, write, parse, and compile a Tree Language.

In this Section we will role play as a software consultancy shop.

One day your favorite customer, Nursino's—("get the door, it's Nursino's!"), has come in and said "Help! We have a ton of web pages to manage but our nurses doesn't have time for complicated tech and we need a way to make it simpler for them. All our devices run MonkeyBanana, so whatever you build needs to work with that."

Your firm, a savvy group of expert MonkeyBanana Programmers, have a hunch that this "Tree Notation" thing you've seen get 5 or 6 upvotes on Reddit might be exactly what they need. The only problem is there is no way to work with Tree Notation in the MonkeyBanana Programming Language.

That is, until you come along. You know now is the time to make the MonkeyBanana Tree Notation library.

You know that Nurino's has a lot of web pages and their nurses are busy with non-tech things and need an easier way to manage them all. You also know that in the future they are going to have more and more web pages, and that this is a problem they are going to have for a long time, so it makes sense to not rush out a hacky solution but to think from first principles and do it right.

You take a look at one of the pages on Nursino's website:

`<title>Nurino's Services Offerered</title>
<p>Here is a list of home nursing services we offer</p>
<table>
 <thead>
 	<th>Service</th>
 	<th>Price</th>
 </thead>
 <tbody>
 	<tr>
 		<td>Blood Pressure Check</td>
 		<td>$10</td>
    </tr>
    <tr>
      <td>Temperature Check</td>
      <td>$5</td>
    </tr>
 </tbody>
<table>`

You have a hunch that a "simple design" is a "good design". You have this hunch because one time you visited the Egyptian Museum in Cairo, and noticed that the sandals the Pharoahs wore had the exact same simple design you were wearing on your feet 3,000 years later.

So you decide your strategy will be to start at the end—come up with the simplest representation of the page above in Tree Notation, and then build your MonkeyBanana to work with that.

Here is what you come up with:

`title Nurino's Services Offerered
paragraph Here is a list of home nursing services we offer
table
 Service Price
 BloodPressureCheck $10
 TemperatureCheck $5`

Now, we are ready to begin! In this section we will work exclusively with the document above. We will call it the `PriceListPage`. We will parse it and edit it with basic Tree Notation, and then we will create a Tree Language to parse it with types, compile it, and edit it with Visual IDEs.

### Chapter 1 - Grid Notation and Basic Parsing

In all of these chapters we expect you will be using the language of your choice. I will use the term "MonkeyBanana" to refer to language you are using (since I don't know what that language actually will be).

Most general purpose languages should be easy to work with (C, Ruby, Python, Java, Haskell, PHP, etc). However, languages that merely "encode data", aren't really the right tool for the job.

#### Exercises 1

Create a "TreeNotation" class in MonkeyBanana. The constructor should take a string.

Create a unit test file. In your unit tests, pass in the `PriceListPage` string above.

Then add methods to your `TreeNotation` class do the following:

1. Count the number of "nodes" in the string. In Tree Notation, one line === one node.

2. Count the number of "cells" in the string. In Tree Notation, one word === one node (unless a tab is used to separate cells, in which case one cell could contain multiple words)

3. Count the number of "nodes" in the "root tree". (Hint: it should be less than #2).

4. Write a method to return the string at node 1, cell 0.

5. Write a method to turn your TreeNotation instance back into a string and ensure that `TreeNotation(PriceListPage).toString()` === `PriceListPage`.

6. Export the document to a JSON object. (Notes: just export strings. Note: at this point there are multiple "correct" answers for how to export the `table` as JSON, since we don't have a higher level Tree Language yet that resolves ambiguities)

#### Exercise 1 Hints

Tree Notation defines 3 delimiters:
- Node delimiter symbol (usually new line)
- Cell delimiter symbol (usually a space, but often a tab instead)
- Edge symbol (usually a space, but often a tab instead)







