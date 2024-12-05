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
<br>

## Design Patterns

#### <u>Definition and Examples</u>

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
By leveraging these design patterns, developers can avoid reinventing the wheel and create more robust and maintainable code. You can read more about these patterns <a href="https://www.geeksforgeeks.org/software-design-patterns/#types-of-software-design-patterns">here</a>
<br>
</p>
<br>

#### <u>Applications in ICS314</u>
<p>

At the time I am writing this essay, my ICS 314 final project group just met our 2nd milestone or key checkpoint, and at this checkpoint we were expected to connect some of our website pages to a database with reading and writing capabilities incorporated on our website. I was able to implement reading and writing functionality on my page, known as the "Edit Goals" page, which is only available to system admins and edits the goals users will be able to chose from to put under their profile, such as "Learn to play a new musical instrument." 
<br>
<br>
With context out of the way, I will now explain a couple of design patterns that are present in the code of just this singular file of code. 
<br>
<br>
</p>

<p><b>Container/Presentational Pattern</b></p>

<div style="width: 48%; float: left;">

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="cm">/* Container Component */</span>
<span class="kd">const</span> <span class="nx">EditGoalsForm</span> <span class="o">=</span> <span class="p">()</span> <span class="o">=&gt;</span> <span class="p">{</span>
  <span class="c1">// State and logic here</span>
  <span class="k">return</span> <span class="p">(</span>
    <span class="o">&lt;</span><span class="nx">Container</span><span class="o">&gt;</span>
      <span class="p">{</span><span class="cm">/* Presentational components */</span><span class="p">}</span>
    <span class="o">&lt;</span><span class="sr">/Container</span><span class="err">&gt;
</span>  <span class="p">);</span>
<span class="p">};</span>
</code></pre></div></div>

</div>
<div style="width: 48%; float: right;">
<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="cm">/* Presentational Component */</span>
<span class="kd">const</span> <span class="nx">GoalRow</span> <span class="o">=</span> <span class="p">({</span> <span class="nx">goal</span><span class="p">,</span> <span class="nx">onSave</span><span class="p">,</span> <span class="nx">onEdit</span> <span class="p">})</span> <span class="o">=&gt;</span> <span class="p">(</span>
  <span class="o">&lt;</span><span class="nx">tr</span><span class="o">&gt;</span>
    <span class="o">&lt;</span><span class="nx">td</span><span class="o">&gt;</span><span class="p">{</span><span class="nx">goal</span><span class="p">.</span><span class="nx">isEditing</span> <span class="p">?</span> <span class="o">&lt;</span><span class="nx">FormControl</span> <span class="p">...</span> <span class="o">/&gt;</span> <span class="p">:</span> <span class="nx">goal</span><span class="p">.</span><span class="nx">goal</span><span class="p">}</span><span class="o">&lt;</span><span class="sr">/td</span><span class="err">&gt;
</span>    <span class="o">&lt;</span><span class="nx">td</span><span class="o">&gt;</span>
      <span class="p">{</span><span class="nx">goal</span><span class="p">.</span><span class="nx">isEditing</span> <span class="p">?</span> <span class="p">(</span>
        <span class="o">&lt;</span><span class="nx">Button</span> <span class="nx">onClick</span><span class="o">=</span><span class="p">{()</span> <span class="o">=&gt;</span> <span class="nx">onSave</span><span class="p">(</span><span class="nx">goal</span><span class="p">)}</span><span class="o">&gt;</span><span class="nx">Save</span><span class="o">&lt;</span><span class="sr">/Button</span><span class="err">&gt;
</span>      <span class="p">)</span> <span class="p">:</span> <span class="p">(</span>
        <span class="o">&lt;</span><span class="nx">Button</span> <span class="nx">onClick</span><span class="o">=</span><span class="p">{()</span> <span class="o">=&gt;</span> <span class="nx">onEdit</span><span class="p">(</span><span class="nx">goal</span><span class="p">)}</span><span class="o">&gt;</span><span class="nx">Edit</span><span class="o">&lt;</span><span class="sr">/Button</span><span class="err">&gt;
</span>      <span class="p">)}</span>
    <span class="o">&lt;</span><span class="sr">/td</span><span class="err">&gt;
</span>  <span class="o">&lt;</span><span class="sr">/tr</span><span class="err">&gt;
</span><span class="p">);</span>
</code></pre></div></div>
</div>
<div style="clear: both;"></div>
<br>

<p>
The code snippets above depicts an example of a Container/Presentational design pattern in a next component designed by myself. The code for this same component will be used in following examples. This design pattern enforces a separation of concerns -- simplifying a programming problem -- by using separate components to display data to the user and how to display data to the user. 
<br>
<br>
The code for this next component has a return statement in the <i>Container Component</i> of the design pattern which is used to display information on the actual "Edit Goals" page mentioned before, that information being the contents of the return statement. In the <i>Presentational Component</i>, a different button (that being the data), will show depending on whether the goal is being edited or not. 
<br>
<br>
</p>
<p><b>Higher-Order Component (HOC) Pattern</b></p>
<br>
<div style="width: 48%; float: left;">

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="cm">/* 
 * HOC Component 
 * File Location: @/lib/dbActions.ts
 */</span>

<span class="k">export</span> <span class="k">async</span> <span class="kd">function</span> <span class="nx">editGoal</span><span class="p">(</span><span class="nx">goal</span><span class="p">:</span> <span class="p">{</span>
  <span class="nl">id</span><span class="p">:</span> <span class="nx">number</span><span class="p">;</span>
  <span class="nl">goal</span><span class="p">:</span> <span class="nx">string</span><span class="p">;</span>
  <span class="nl">isEditing</span><span class="p">:</span> <span class="nx">number</span><span class="p">;</span>
<span class="p">})</span> <span class="p">{</span>
  <span class="c1">// Update the database</span>
  <span class="k">await</span> <span class="nx">prisma</span><span class="p">.</span><span class="nx">goals</span><span class="p">.</span><span class="nx">update</span><span class="p">({</span>
    <span class="na">where</span><span class="p">:</span> <span class="p">{</span> <span class="na">id</span><span class="p">:</span> <span class="nx">goal</span><span class="p">.</span><span class="nx">id</span> <span class="p">},</span>
    <span class="na">data</span><span class="p">:</span> <span class="p">{</span>
      <span class="na">goal</span><span class="p">:</span> <span class="nx">goal</span><span class="p">.</span><span class="nx">goal</span><span class="p">,</span>
      <span class="na">isEditing</span><span class="p">:</span> <span class="nx">goal</span><span class="p">.</span><span class="nx">isEditing</span><span class="p">,</span>
    <span class="p">},</span>
  <span class="p">});</span>
<span class="p">}</span>
</code></pre></div></div>

</div>
<div style="width: 48%; float: right;">

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="cm">/* Edit Goals Component */</span>
<span class="dl">'</span><span class="s1">use client</span><span class="dl">'</span><span class="p">;</span>

<span class="k">import</span> <span class="p">{</span> <span class="nx">editGoal</span> <span class="p">}</span> <span class="k">from</span> <span class="dl">'</span><span class="s1">@/lib/dbActions</span><span class="dl">'</span><span class="p">;</span>
  <span class="p">.</span>
  <span class="p">.</span>
  <span class="p">.</span>
<span class="kd">const</span> <span class="nx">enableEdit</span> <span class="o">=</span> <span class="k">async</span> <span class="p">(</span><span class="nx">goal</span><span class="p">:</span> <span class="nx">Goals</span><span class="p">)</span> <span class="o">=&gt;</span> <span class="p">{</span>
  <span class="kd">const</span> <span class="nx">updatedGoal</span> <span class="o">=</span> <span class="p">{</span> <span class="p">...</span><span class="nx">goal</span><span class="p">,</span> <span class="na">isEditing</span><span class="p">:</span> <span class="mi">1</span> <span class="p">};</span>
  <span class="k">await</span> <span class="nx">editGoal</span><span class="p">(</span><span class="nx">updatedGoal</span><span class="p">);</span> <span class="c1">// Calls HOC</span>
  <span class="nb">window</span><span class="p">.</span><span class="nx">location</span><span class="p">.</span><span class="nx">reload</span><span class="p">();</span>
<span class="p">};</span>

<span class="kd">const</span> <span class="nx">saveGoal</span> <span class="o">=</span> <span class="k">async</span> <span class="p">(</span><span class="nx">goal</span><span class="p">:</span> <span class="nx">Goals</span><span class="p">)</span> <span class="o">=&gt;</span> <span class="p">{</span>
  <span class="kd">const</span> <span class="nx">updatedGoal</span> <span class="o">=</span> <span class="p">{</span> <span class="p">...</span><span class="nx">goal</span><span class="p">,</span> <span class="na">isEditing</span><span class="p">:</span> <span class="mi">0</span> <span class="p">};</span>
  <span class="k">await</span> <span class="nx">editGoal</span><span class="p">(</span><span class="nx">updatedGoal</span><span class="p">);</span> <span class="c1">// Calls HOC</span>
  <span class="nb">window</span><span class="p">.</span><span class="nx">location</span><span class="p">.</span><span class="nx">reload</span><span class="p">();</span>
<span class="p">};</span>
  <span class="p">.</span>
  <span class="p">.</span>
  <span class="p">.</span>
  <span class="o">&lt;</span><span class="nx">Button</span> <span class="nx">variant</span><span class="o">=</span><span class="dl">"</span><span class="s2">success</span><span class="dl">"</span> <span class="nx">className</span><span class="o">=</span><span class="dl">"</span><span class="s2">me-2</span><span class="dl">"</span> <span class="nx">onClick</span><span class="o">=</span><span class="p">{()</span> <span class="o">=&gt;</span> <span class="nx">saveGoal</span><span class="p">(</span><span class="nx">goal</span><span class="p">)}</span><span class="o">&gt;</span>
    <span class="nx">Save</span>
  <span class="o">&lt;</span><span class="sr">/Button</span><span class="err">&gt;
</span>  <span class="o">&lt;</span><span class="nx">Button</span> <span class="nx">variant</span><span class="o">=</span><span class="dl">"</span><span class="s2">primary</span><span class="dl">"</span> <span class="nx">className</span><span class="o">=</span><span class="dl">"</span><span class="s2">me-2</span><span class="dl">"</span> <span class="nx">onClick</span><span class="o">=</span><span class="p">{()</span> <span class="o">=&gt;</span> <span class="nx">enableEdit</span><span class="p">(</span><span class="nx">goal</span><span class="p">)}</span><span class="o">&gt;</span>
    <span class="nx">Edit</span>
  <span class="o">&lt;</span><span class="sr">/Button</span><span class="err">&gt;
</span></code></pre></div></div>

</div>
<div style="clear: both;"></div>
<br>

<p>
The code snippets above depicts an example of a Higher-Order Component (HOC) design pattern. This design pattern reduces redundancy -- allow multiple components to also use that logic without redefining the logic -- by defining said logic, the editGoal function, as a different component in another file. This also helps in making the code more readable by passing functions to child components which handle very specific tasks.
<br>
<br>
The <i>HOC Component </i> is defined in a separate file, alongside other functions that can edit database data, and is passed the goal object to be edited. In the next component code, the HOC is referenced and passed an updated goal parameter which contains the updated <i>isEditing</i> and <i>goal</i> values (the goal value being the text of the goal). In this implementation, all client sided changes are handled by the next component code and the database changes are handled by the HOC. This change was also necessary as prisma must run in an asynchronous environment, whereas the client-sided changes require a "use client" page, therefore that separation of functions was needed.
<br>
<br>
</p>

## Future Thoughts
<p>
Though design patterns were not something I consciously implemented into my coding environment, both of the examples in my code being that case, I think they are extremely valuable to follow. From the novice level, which is where I believe I am in most cases, I think design patterns can guide you to optimizing your programming by teaching you the best practices from the start while explaining the reasoning in a beginner-friendly manner. And at any level, I believe following design pattern will lead to improved coding efficiency and readability, as the patterns are what they advertise: standardized reusable solutions.
</p>