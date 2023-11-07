# Exercise 2

## Prompt engineering


Different prompts can make an LLM spit out really different stuff. Asking the same thing in a new way can change the game. So, prompt engineering is all about crafting your words just right to steer the LLM.

Unfortunately, prompt engineering is more of an art than a science, which often requires experience and intution. But lets practice some common techniques to get you started!

### Prompting techniques

### Few-shot learning

Few-shot learning is a machine learning technique that enables models to learn new concepts with only a few examples. This technique is particularly useful for programming. The idea is to include to include example input and output in your prompt which also gives you the opportunity to teach new concepts within the prompt.

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
 
Reflection is a prompting technique where you ask the model to reflect on its previous answer, which research has shown can improve quality. One version of this trick to do this in a single prompt, is to ask it act as different personas. One persona that provides a solution and another that provides criticism.
Lastly, let the model synthesize the two answers. There are more nifty tricks like this for examplethe Reflexion paper which is more involved but this is a single prompt template you can try.

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
Answer as two different personas: Solver which gives a solution with code 
and Critic which criticizes what solver said. 
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

Chain of thought (CoT) prompting is a trick where you either break down a problem into smaller steps and show the model how to solve the problem with broken down steps. Or alternatively, you get the model to spit out its thought process step by step. CoT helps models perform better on trickier problems which involve multi step reasoning. Using pseudo code to describe a solution is a form of CoT. A last trick is to just add the phrase "lets think step by step" at the end.

A chain of thought prompt also guides the exact solution you want. 

A simple prompt would be:

Write a python program that calculates the odds at winning in blackjack (american rules) when using basic strategy.

An example of a chain of thought prompt would be to outline the entire solution in pseudo code:

```
Give me a basic full implementation of the following simulation in python

1. Play blackjack with the following strategy:

	- Stand if you have 12-16 and the dealer has 2-6; hit if the dealer has 7-Ace.
	- Always split Aces and 8s.
	- Never split 10s and 5s; always split 2s and 3s against the dealer's 4-7.
	- Double down on 11 if the dealer has 2-10; hit if the dealer has an Ace.
	- Double down on 10 if the dealer has 2-9.
	- Double down on 9 if the dealer has 3-6.
	- Stand on 17 and up.
	- Hit until you have at least 17 if the dealer has a 7 or higher.
	- Use Surrender when you have 16 and the dealer has a 9, 10, or Ace, and when you 	have 15 and the dealer has a 10, if available.

2. Set up a simulation environment that mimics the game of blackjack. This includes deck composition, dealer rules, and player actions.

3. Begin the simulation by dealing out cards randomly to the player and dealer, following the rules of the game.

4. Play out a large number of blackjack hands using the defined strategy. For each hand, random events (like the next card drawn) need to be simulated based on the probabilities in a real game.

5. After each simulated hand, record whether it was a win, loss, or tie.

6. Repeat: Repeat the process for a large number of hands to get a statistically significant sample size. The more hands you simulate, the more accurate your estimate of the odds will be.

7. Analyze Data: Analyze the recorded results to calculate the proportion of hands won, lost, and tied.

8. Calculate Odds: The odds of winning are the number of hands won divided by the total number of hands played.
```

Using this style of prompting, ask bing chat to implement a black simulator with and without CoT


##### Let's think step by step

Another variation of chain of thought prompting is to force the model to show its reasoning itself. For example by adding "explain your reasoning step by step" or "let's think step by step". Experiment with some prompts and see how the answer changes!