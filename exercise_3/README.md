# Exercise 3


## Solving simple one-off jobs

LLMs can be very helpful in solving day-to-day problems that you would usually solve manually or by writing some one-off script. With the possibility to use natural language to describe what you want, you can often boost your productivity by simply handing off the implementation in code to an LLM. It often requires less effort for you and you can get solutions for less.


This isn't really an exercise in any prompting technique, so you're not learning anything new compared to exercise 1 & 2. 

Just try all of these prompts and see what you get. The idea is to inspire you to use LLMs for all kinds of small daily tasks. Choose one of bash/zsh/python whichever scripting language you're most comfortable with.

`write a [bash|zsh|python] program to`:

- rename all files in this directory from snake case to camelcase
- cut a mp3 file into 10 second chunks
- convert all images in the current directory to png in greyscale color
- find all lines from file1 that are not in file2 and vice versa
- find missing records in text files. I have two files with json records separated by newlines. The records have the format '{"name": "John Doe", "email": "john.doe@example.com" }'. Find all names that are present in file1 but not in file2 and vice versa. Do the same diff for emails.
- monitor a folder for changes and log the changes
- download all images from a given URL

the list could go on forever but you get the idea. ChatGPT also has a very powerful data analysis mode which lets you upload directly into the context, as well as execute python code on it. Bing Chat however currently does not. It is worth mentioning however as some of these tasks can be done without even leaving the LLM environment, by instead uploading the data you need to work on.

## Bootstrap code

GPT-4 can generate a rough draft of an entire program if you do not know how to start, or how the template of a specific solution using a specific type of tech would look like. Simply ask it to generate a piece of code involving tech xyz to solve abc and it can be a useful starting point.

for example:

```
create a CRUD interface in react 
with complete code for a Customer that involves
firstname, lastname, email address and shoe size
```


## How do I ...?

Instead of Googling, just try using an LLM for research topics. Please keep in mind that LLMs have a knowledge cutoff date (at time of writing ChatGPT had its cutoff date moved to April 2023). An LLM however still has bias towards samples that are very common in the training data, and recency is not weighted in the same way has Google manages its index. Therefore, searching for very fresh knowledge will not give good results. If you need a programming answer that is based on an API that has changed over time, you can often get code answers which are correct but based on an earlier version of the library/sdk you are working on.

Example prompts below, but try some research topics of your own you recently googled for.

- write a rust program that integrates between opentelemetry and a logger framework so that trace_id and span_id is put in the logs
- how do I center a div
- write a python function which subscribes to all updates/inserts of a postgres table called svt_ids
- ...


## Incrementally building something

Instead of making a correct prompt, you can easily use ChatGPT/Bing chat as a programming assistant where you just iteratively add instructions, refining the output you see. For example you start off with a simple instruction, like building a small game in HTML/javascript.

For example you start off with the prompt

```
write a small game in html/javascript. Start with an empty screen with brown background and a character that is rendered using an airplane emoji
```

and then you continue in the same session with

```
add a moving enemy helicopter which is automatically flying around on the screen.
```

and you continue iterating like this. you get the idea.


## GPT-4 bag o' tricks

#### continue

If a response is too long, it is sometimes cut off. Simply typing `continue` as a follow-up prompt can sometimes help and makes the LLM continue.

#### summarize text

GPT-4 can condense text, providing summaries of longer documents

#### simplify

ask GPT-4 to translate complex concepts into simpler language 

