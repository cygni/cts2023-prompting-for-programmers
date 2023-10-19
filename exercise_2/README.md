# Exercise 2

## Prompt engineering


Different prompts can make an LLM spit out really different stuff. 
Asking the same thing in a new way can change the game. 
So, prompt engineering is all about crafting your words just right to steer the LLM.

### Prompting techniques

### Few-shot learning

Few-shot learning is a machine learning technique that enables models to learn new concepts with only a few examples.
This technique is particularly useful for programming. 

Let's try to solve a few-shot learning problem using bing chat.

Here is a slightly adjusted number system 

#### Symbols

🍀 = 1
🌟 = 5
🚀 = 10
🌕 = 50
🌈 = 100
⚡ = 500
🌍 = 1000

#### Rules

Repeating a symbol represents addition:

- 🍀🍀🍀 = 3
- 🚀🚀🚀 = 30

Placing a smaller symbol before a larger symbol means subtraction:

- 🍀🌟 = 4
- 🍀🚀 = 9

Placing a smaller symbol after a larger symbol means addition:

- 🌟🍀 = 6
- 🌈🌕 = 150

Only subtract one number from another:

🚀🌈 = 90 (not 🍀🌍🍀🌍)

Don't repeat a symbol more than three times:

🚀🌕 = 40 (not 🚀🚀🚀🚀)

Larger symbols precede smaller ones when writing larger numbers:

🌍🌍🚀🚀🍀🍀🍀 = 2023

Using bing chat, prompt the model to learn the number system and create some python code that coverts a number to decimal. 
Ask it to provide test code for all examples.

### Reflection
 
A prompting technique where you ask the model to reflect on its previous answer, which research has shown can improve quality. 
One version of this trick to do this in a single prompt, is to ask it act as different personas. One persona that provides a solution and another that provides criticism.
Then let the model synthesize the two answers. There are more nifty tricks like this for example
the Reflexion paper which is more involved but this is a single prompt template you can try.

#### Programming problem

Given two strings, both strings consist of open
parentheses '(' or close parentheses ')' only.
Your job is to check if it is possible to concatenate the two strings in
some order, that the resulting string will be good. Output the concatenated string if it is possible, 
otherwise output "impossible".

A string S is considered to be good if and only if all parentheses in S
are balanced. For example: the string '(())()' is good, while the string
'())' is not.


1. Prompt bing chat to generate python code that solves the problem without any reflection.
2. Prompt bing chat to solve the problem with reflection.

For example with the following prompt template: 

```
I want you to generate python code that solves X. 
```

and then add

```
Answer as two different personas: Solver which gives a solution with code and Critic which criticizes what solver. 
Finally conclude with a synthesis of Solver and Critic with updated code.
```

#### Research problem

We have a system that is based on microservices deployed in the cloud. We are having performance issues. 
Use bing chat to come up with ideas on how to make the system more performant.

1. Prompt bing chat to generate an answer without any reflection.
2. Prompt bing chat to solve the problem with reflection.

#### Research problem 2

We have a big legacy system written using old tech like JSP. We want to migrate to a single-page application (SPA). What is a good approach?

1. Prompt bing chat to generate an answer without any reflection.
2. Prompt bing chat to solve the problem with reflection.


#### Chain of thought

First try to solve the problem with a straight-forward prompt.

Then use chain of thought to improve the prompt.

```
I want to do X, lets think step by step.
```