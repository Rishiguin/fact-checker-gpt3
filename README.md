# fact checking with prompt chaining


- you ask your desired LLM a question
- the LLM generates an initial answer to the question
- the LLM self-interrogates what the assumptions were that went into that answer
- the LLM sequentially determines if each of these assumptions are true
- the LLM generates a new answer to the question, incorporating the new information

## to run

1. Make sure you have langchain installed (`pip install langchain`). 

2. Add your api key in `fact_checker.py` Get it from https://platform.openai.com/account/api-keys

Then run

3. `python3 fact_checker.py "insert question here"`

*Be sure to wrap your question in quotes if you're passing it as a command line argument.*

## example

Question: *"What type of mammal lays the biggest eggs?"*


**Initial answer:**
The biggest eggs laid by any mammal belong to the elephant.

**Assumptions made:**
- The elephant is a mammal 
- Mammals lay eggs 
- Eggs come in different sizes 
- Elephants lay bigger eggs than other mammals

**Verification of assumptions:**
- The elephant is a mammal: TRUE 
- Mammals lay eggs: FALSE - Most mammals give birth to live young.
- Eggs come in different sizes: TRUE 
- Elephants lay bigger eggs than other mammals: FALSE - Elephants do not lay eggs.

**New answer:**
This question cannot be answered because elephants do not lay eggs and most mammals give birth to live young.
