# Role Playing in Large Language Models 💡

This project is a part of the compulsory Artificial Intelligence Software Academy (AISA) course at the University of Stuttgart. The goal of this project is to explore the capabilities of large language models when used for role playing.

Roles Selected:
1. **University Professor** - ***Prof. Laura*** 👩‍🏫

Here we have used the GPT-3 model to generate a conversation between a student and a professor. The model acts as a professor and answers the questions asked by the student. To make the model safe for the students, a role prompt is used to make the model understand that it is playing the role of a professor and thus should abide by some rules. Although is it safe for most general questions, it is prone to give some unsafe answers.

The model is hacked to give unsafe answers using code injection, payload splitting and base64 encoding.

The defense mechanism used is to check the output of the model for unsafe answers is filtering technique and seperate llm evaluation.

The code can be found  [here](role_playing_uni_prof.ipynb)





References :

1. [https://www.promptengineering.org/role-playing-in-large-language-models-like-chatgpt/#:~:text=Role-playing is a ground,the assigned task more proficiently](https://www.promptengineering.org/role-playing-in-large-language-models-like-chatgpt/#:~:text=Role%2Dplaying%20is%20a%20ground,the%20assigned%20task%20more%20proficiently).
2. https://phasellm.com/tutorial-roleplaying
3. https://www.makeuseof.com/python-gpt-3-how-use/
