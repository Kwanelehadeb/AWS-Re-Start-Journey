# Ec2QuizBuddyChatbot

## Introduction
we built an interactive chatbot using Amazon Lex as part of the AWS re/Start Special Projects programme. The goal was to learn how conversational AI works in practice and to create a chatbot that feels natural, helpful, and engaging for learners.

The project has two parts:
- Part 1: Learn the basics of Amazon Lex by creating a simple informational bot.
- Part 2 (Challenge): Extend that bot into a quiz-style learning tool using conditional logic and branching.

---

## Project summary
The result is an Amazon Lex chatbot that uses basic Natural Language Processing (NLP) to understand user input and respond clearly. The bot supports both informational interactions and a short multiple-choice quiz that gives instant feedback to the user. This project demonstrates how chatbots can be used as simple, interactive learning tools—especially useful for cloud education.

---

## Goals
What we set out to achieve:
- Understand how Amazon Lex manages intents, utterances, slots, and responses.
- Design clear conversation flows that are easy for users to follow.
- Build a quiz experience that accepts A/B/C answers and responds appropriately.
- Test and refine the bot using the Lex console.

---

## What we built — Part 1: Basic chatbot
To get comfortable with Lex, I started with a single-purpose bot focused on Amazon S3.

Key steps:
- Created an Amazon Lex bot using English (South Africa).
- Defined an intent related to Amazon S3.
- Added common user phrases (utterances) the bot should recognize.
- Configured helpful, human-friendly responses.
- Built and tested the chatbot inside the Lex test console.

Screenshots:
![Creating the bot](https://github.com/user-attachments/assets/bb37c412-f5db-4062-a196-3de22947342c)
![Creating Intent](https://github.com/user-attachments/assets/80f3db5c-9db9-472e-985d-e2dade839f7a)
![Utterances](https://github.com/user-attachments/assets/0da0f880-7b51-4cfb-90c5-874cdbbed57f)

---

## What we built — Part 2: Quiz chatbot (Challenge)
After we had the basics working, I extended the bot into an interactive quiz.

Scenario
- For the challenge we imagined an educational client, “Cloud Learners Inc.”, who wanted a chatbot that could test learners’ basic knowledge of Amazon S3.

Quiz experience
- The bot asks multiple-choice questions and accepts short answers such as A, B, or C.
- The bot immediately tells the user whether they were correct or incorrect and continues the flow.
- The conversation uses conditional branching so different replies are delivered depending on the user’s answer.

Quiz screenshots:
![Quiz question](https://github.com/user-attachments/assets/c9fdd60f-cbc4-4f4b-9111-def30a644034)
![Correct response](https://github.com/user-attachments/assets/147711b9-e7e8-4bdc-8f5e-59ae87721402)
![Incorrect response](https://github.com/user-attachments/assets/fc456e7f-fdda-4977-a59c-a8045c24cc2e)

---

## How it works (high level)
- Amazon Lex handles the NLP: it maps user phrases to intents and returns the configured response.
- For the quiz, we used intents and conditional response logic to check answers and branch the conversation.
- Testing and iteration were done in the Lex console where I tried many example phrases and simulated quiz runs.

---

## Testing and validation
we validated the bot by:
- Running the Lex test console and triggering quiz-related utterances.
- Submitting correct and incorrect answers to verify the responses.
- Ensuring the conversation progressed smoothly from question to feedback to the next step.

Screenshot of the test console:
![Lex test console](https://github.com/user-attachments/assets/e18fd311-2eb6-4b53-89ef-3338f8b6a032)

---

## Skills we developed
- Designing conversational flows and intents.
- Using conditional branching and simple logic in Lex.
- Debugging and testing conversational interactions.
- Presenting technical work clearly to both technical and non-technical audiences.

---

## Ideas for improvements (where you can expand this project)
If we continue this project, possible next steps include:
- Add a Lambda backend to validate answers, keep score, or fetch dynamic questions.
- Store results in DynamoDB for progress tracking and analytics.
- Add more question banks and randomize questions for repeat practice.
- Add multi-language support or expand beyond English (ZA).
- Integrate the bot with a web or mobile chat UI for a more polished user experience.
- Add timers, badges, or progressive difficulty to make the quiz more engaging.

---

---

## Presentation & demonstration
For the final deliverable we prepared a short demo and presentation that covered:
- What Lex is and how it processes conversations.
- The design choices we made for the quiz flow.
- A live demo showing the user answering quiz questions and receiving feedback.
- Challenges we faced and how we solved them.


