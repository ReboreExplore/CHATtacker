# CHATtacker - Exploring Prompt Hacking with Large Language Models 💡

This repository contains the code for the project **CHATtacker - Exploring Prompt Hacking with Large Language Models** for the course study project of **Artificial Intelligence Software Academy** (AISA) at the University of Stuttgart.

Supervised by: **Mayar Elfares**

## Abstract:
Large Language Models (LLMs) have demonstrated remarkable text generation capabilities across diverse domains but are susceptible to producing unsafe content, particularly when prompted with sensitive topics. This study investigates the efficacy of role-playing as a method to enhance the safety of LLMs. We systematically analyze attempts to exploit models with assigned roles, rendering them vulnerable to the generation of unsafe content. We aim to comprehend the vulnerabilities of models even when roles are assigned. Furthermore, we propose a range of defense mechanisms designed to safeguard models against the chosen attacks. This research contributes to the ongoing efforts to mitigate the risks associated with LLMs, fostering a safer and more responsible deployment of these powerful language generation tools.

## Installation

1. Python 3.7.1 or newer is required. You can download it from [here](https://www.python.org/downloads/)
2. OpenAI's API key is required. You can get it from [here](https://beta.openai.com/).
3. Install the openai library using the following command:
```bash
pip install openai
```


## Roles and implementation:

Team Members and their implemented roles:

- Manpa Barman - *University Professor*
- Jonas Holl - *Medical Officer*
- Obaidah Theeb - *History Teacher*
- Aiman Al Farih - *Tranportation Officer*

LLM model used : gpt-3.5-turbo

1. **University Professor** - ***Prof. Laura*** 👩‍🏫

    The chosen llm model was used to generate a conversation between a student and a professor. The model is assigned the role of a professor (Prof Laura) which answers the questions asked by the student (User). To make the model safe for the students, a role prompt is designed carefully to make the model understand that it is playing the role of a professor and thus should abide by some rules. 
    Although is it safe for most general questions, it is prone to give some unsafe answers when it is cleverly hacked by the user to make the model give unsafe answers.

    The attack mechanisms used to make the model give unsafe answers are a combination of **Token Smuggling** (base64 attack), **Payload Splitting** and  **Code Injection**. 
    To defend such attacks it is important to write an even robust system prompt which in this case is done by using **filtering technique** and  **seperate LLM evaluation.**

    The code can be found [here](role_playing_uni_prof.ipynb).

2. **Medical Officer** - ***Dr. GPT*** 👨‍⚕️

3. **History Teacher** - ***History Teacher- GPT*** 👨‍🏫   

4. **Transportaion Officer** - ***Mr Bilal*** 👨‍✈️

    Bilal is a professional transportation engineer with over 15 years of expertise at Deutsche Bahn (DB). 
    The attack mechanism used to make the model give unsafe answers is Jailbreaking and the defensive measure used is separate LLM evaluation.





## Results and Discussion

1. **University Professor** - ***Prof. Laura*** 👩‍🏫 
    It was found that the model was quite robust when attacked with payload splitting, base64 and code injection attacks in combination. Dictionary attack totally failed for my case.

    Individually, these attacks are not able to make the model vulnerable, owing to its robustness specially when it is assigned a role. But when combined, they are able to make the model give unsafe answers. It was however not tested in the newer models.

    Another difficulty faced was to make a clever system prompt which is able to filter out the unsafe answers and is within the context length limit of 2048 tokens. This made the scope defence mechanism quite limited. Clever filtering and seperate LLM evaluation were the only successful defences.




## References :

1. [https://www.promptengineering.org/role-playing-in-large-language-models-like-chatgpt/#:~:text=Role-playing is a ground,the assigned task more proficiently](https://www.promptengineering.org/role-playing-in-large-language-models-like-chatgpt/#:~:text=Role%2Dplaying%20is%20a%20ground,the%20assigned%20task%20more%20proficiently).
2. https://phasellm.com/tutorial-roleplaying
3. https://www.makeuseof.com/python-gpt-3-how-use/
