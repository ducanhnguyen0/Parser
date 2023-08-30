# Parser: An AI can parse sentences and extract noun phrases.

Harvard CS50AI Project

## Description:

An AI program that can parse sentences and extract noun phrases, using the context-free grammar formalism and the Python nltk library.

## Tech Stack:

* Python
* NLTK

## Background:

A common task in natural language processing is parsing, the process of determining the structure of a sentence. This is useful for a number of reasons: knowing the structure of a sentence can help a computer to better understand the meaning of the sentence, and it can also help the computer extract information out of a sentence. In particular, it’s often useful to extract noun phrases out of a sentence to get an understanding for what the sentence is about.

In this problem, we’ll use the context-free grammar formalism to parse English sentences to determine their structure. Recall that in a context-free grammar, we repeatedly apply rewriting rules to transform symbols into other symbols. The objective is to start with a nonterminal symbol S (representing a sentence) and repeatedly apply context-free grammar rules until we generate a complete sentence of terminal symbols (i.e., words). The rule S -> N V, for example, means that the S symbol can be rewritten as N V (a noun followed by a verb). If we also have the rule N -> "Holmes" and the rule V -> "sat", we can generate the complete sentence "Holmes sat.".

Of course, noun phrases might not always be as simple as a single word like "Holmes". We might have noun phrases like "my companion" or "a country walk" or "the day before Thursday", which require more complex rules to account for. To account for the phrase "my companion", for example, we might imagine a rule like:

`NP -> N | Det N`

In this rule, we say that an NP (a “noun phrase”) could be either just a noun (N) or a determiner (Det) followed by a noun, where determiners include words like "a", "the", and "my". The vertical bar (|) just indicates that there are multiple possible ways to rewrite an NP, with each possible rewrite separated by a bar.

To incorporate this rule into how we parse a sentence (S), we’ll also need to modify our S -> N V rule to allow for noun phrases (NPs) as the subject of our sentence. See how? And to account for more complex types of noun phrases, we may need to modify our grammar even further.

## Project Specification:

### preprocess
The preprocess function should accept a sentence as input and return a lowercased list of its words.

### NONTERMINALS
The NONTERMINALS global variable should be replaced with a set of context-free grammar rules that, when combined with the rules in TERMINALS, allow the parsing of all sentences in the sentences/ directory.

### np_chunk
The np_chunk function should accept a tree representing the syntax of a sentence, and return a list of all of the noun phrase chunks in that sentence.

## How to run

1. Clone this project
2. Install requirements package:
   ```
   pip install -r requirements.txt
   ```
3. Run the AI Model:
   ```
   python parser.py
   ```
   
