---
layout: essay
type: essay
title: "Optimizing Your Development"
# All dates must be YYYY-MM-DD format!
date: 2024-12-04
published: true
labels:
  - React
  - TypeScript
  - Developer Tool Kit
---

## Introduction
<p>

In software development, creating efficient, scalable, and maintainable code is a constant challenge, no matter where you are in your software developer career. Many of the habits taught to and maintained by ourselves will serve as reusable solutions to common software design problems, which nearly all programming problems can be simplified down to with the proper approach.
<br>
<br>
What may come to surprise developing software engineers are that many of the techniques they frequently employ by practice are commonly used by many software engineers and are recognized as <b>design patterns</b>. By adopting design patterns, individual and teams of developers can standardize their approach, improve communication, and streamline the development process. And numerous design patterns are not bound by programming languages, making them a versatile tool in any developer's kit.
<br>
<br>
Even for myself, I had not recognized how many design patterns I had picked up during my programming WOD's (Workout of the Day) and implemented into a final project for ICS 314 -- a culmination of all the concepts learned during that class. Even more general design approaches I had picked up in learning C, C++, and Java in the years before and seamlessly applied to JavaScript and TypeScript; I did not expect those techniques, deviating from the standardized design patterns slightly as I had picked them up naturally, to also be a part of my tool set.
</p>

## Design Patterns

#### <u><b>History and Examples</b></u>

<p>
Design patterns are standardized reusable solutions to common problems in software design. Design patterns encapsulate the best practices and provide a template for solving routine software development challenges in a way that is effective while curating to a wide audience of developers from newbies to professionals, allowing any software developer to implement those techniques. Utilizing design patterns will result in the swift development of code that is easily comprehensible, for both the original and additional developers, that can be applied to many different problems, reducing redundancy.
<br>
<br>
<b>Design patterns can classified into three main categories:</b>
<br>
<b>Creational Patterns</b> – Focuses on object creation mechanisms, where functionality of code is independent of how its objects are created, composed, or represented. This approach focuses on designing objects for the specific problem while reducing complexity or redundancy.
<br>
<b>Structural Patterns</b> – Deals with the composition of classes or objects, with the aims of utilizing inheritance and interfaces (between classes and/or objects) to form a larger structure for the entire system which is efficient and flexible.
<br>
<b>Behavioral Patterns</b> – Addresses communication between objects, relating to how to design a collaborative system handler that distributes responsibilities between objects to support and manage more complex systems.
<br>
</p>

<p align="center">
<img src="../img/design-patterns/design-patterns.png" height="300px">
<br>
By leveraging these design patterns, developers can avoid reinventing the wheel and create more robust and maintainable code.
<br>
</p>



#### <u><b>Applications in ICS314</b></u>
<p>

Though bootstrap does bring ease of use for those simpler website designs, when it came to recreating a website of <u>my choice</u>, without any help from the professor as with the two previously mentioned web designs, I found those same features of bootstrap to be limiting when it came to finer or higher-level details. A prime example of this is one of the dropdown menus of the navigation menu for bitwarden (at https://bitwarden.com/).
<br>
<br>
The real website had a horizontal dropdown menu that overall just looked fancy and heavily customized, as shown on the first image below. I tried my best to abstract the menu so I could implement it using just bootstrap: the menu goes until the margins at the sides of the page, there are three columns each with a header, a paragraph, and containers which contain text and redirect the user on click, and underneath all that a footer with more links. This may have just been due to my lack of knowledge of bootstrap, but I was not able to find a way to widen the dropdown menu element of bootstrap to the specifications of the real site or even widen it much it all, making the columns I defined way to crammed with overlapping text, could not figure out how to add those containers with lighter backgrounds at the bottom of each column. My final website design is shown after the image of the original website.
<br>
</p>

<p>
Overall, it seems <b>the component that bootstrap had implemented to simplify my design workflow was actually inhibiting it</b> and I ended opting out of making the columned-dropdown-menu and just listed the different sections vertically in my replication. As I mentioned before, there may have been a way to implement the original menu design using bootstrap that I simply did not know of, but the benefits of bootstrap that I pointed out before cater towards quickly developing and learning how to develop websites.
<br>
<br>
Though I was able to replicate the rest of the bitwarden website with relative ease, as there was little nesting of bootstrap components or other kind of element depth, my failure to implement that one dropdown menu is what stuck with me of that exercise. And that left me to believe that while bootstrap was helpful for simple formatting and prototyping of a website, when it comes to a website design that requires more depth and customizability than bootstrap provides by default, it is most likely better to learn to implement said design elements using css styling with html.
</p>

## Future Thoughts
So, going back to the time-in pay-out perspective I mentioned at the beginning of this essay, I think it isn't worth it to put all your time into mastering a UI Framework such as bootstrap. Do I think it's a helpful tool that one can use in the path of mastering some other skill like html or React <i>(foreshadowing...)</i>. Definitely! Though I may be learning frontend development because the curriculum of my class says to and not because it's something I'm deeply interested in, it is inevitably something I will have to suck up and learn, just like many other skills and languages my future work will require of me, since I'm also not sure of what field I want to work in. Being able to evaluate and reflect on these skills, while not being masters of them, will be a valuable skill in itself that I learned of to effectively divide my time towards developing my skillset in the future.