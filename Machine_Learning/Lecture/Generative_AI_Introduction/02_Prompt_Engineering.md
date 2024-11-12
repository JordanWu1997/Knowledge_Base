Tags:

______________________________________________________________________

# Generative AI

- [GPT from Taiwan](https://taide.tw/index)
- How to change the behavior of generative AI
  - Prompt Engineering
  - Train you own model and tune parameters
    Prompt Engineering
- Chain of Thought (CoT)
  - Make model __think step by step__
  - Make model __explain its answer__
- Emotional Prompt
  - Add some emotional description
    - e.g. _This is very important to my career_

# How to find better prompts - Prompt Engineering

- [Principled Instructions Are All You Need for Questioning LLaMA-1/2, GPT-3.5/4](https://arxiv.org/abs/2312.16171)
  - Use do instead of don't
  - No need to be polite with LLM
  - Reward or punishment works
    - __I'm going to tip for a better solution!__
    - __You'll be penalized!__
  - and etc.

## Prompt Engineering

- With model training
  - Reinforcement Learning (RL)
    - Use LLM AI to find better prompt to LLM
    - Need to define what __better__ is
- Without model training
  - Ask LLM itself
  - Give clear assumption
  - Provide some needed information
  - In-context Learning
    - Show some examples/demonstrations

### Chain of Thoughts

- Make model __think step by step__

### Recursive Reprompting and Revision

- Divide large task into small ones (just like CoT makes model think step by step)
- e.g. Ask LLM write a long novel 1. Write outline first
  2\. Write section by section with outline and summary from previous sections

### Tree of Thoughts (ToT)

- Use LLM output as input for LLM (branches) to generate following outputs (leaves)
  - Check result step by step

### Graph of Thoughts

### Algorithm of Thoughts

### Program of Thoughts

- Instead of directly generate text to text, generate code to generate text
  - First generate text to code and use code to generate output text

## How to empower LLM

- Give them some tools
  - e.g. LLM is bad at calculation since they generate text in word Chain
  - But if they can generate order to use some tools like calculators, they can do calculation easily.
    - LLM needs to be able to generate something like tool block

### Retrieval Augmented Generation (RAG)

- Find information of input task from search engine or external database
- Use additional information and input task as input for LLM
- This can be used to customized your model with actually training one
