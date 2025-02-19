# Master Teacher BOT

## Overview

Master Teacher BOT is a Telegram bot designed to help users prepare for exams or reinforce knowledge in a specific subject. The bot presents users with 10 questions per session and prompts them to either continue with additional questions or review and analyze their answers.

## Features

- **Interactive Exam Preparation**: Engage in a question-and-answer session with 10 questions per round.
- **Session Analysis**: Option to review your answers after each session.
- **Serverless Architecture**: Built using AWS Lambda for scalability.
- **Secure Answer Storage**: Uses AWS S3 to securely store user responses.
- **Written in Rust**: The entire codebase is developed in Rust for performance and safety.

## Technologies

- **AWS Lambda**: For hosting and running the bot's backend logic.
- **AWS S3**: To store user answers and session data.
- **Telegram Bot API**: For interfacing with users on Telegram.
- **Gemini 2.0**: For LLM-generated answers.

## Configuration
* **AWS Lambda Deployment**: Configure your AWS Lambda function to use the compiled binary. You can use AWS SAM or the AWS CLI to deploy the function.
* **S3 Bucket Setup**: Make sure the S3 bucket specified in S3_BUCKET_NAME exists and the Lambda function has permissions to read and write to it.
* **Telegram Bot Webhook**: Set your Telegram bot webhook to point to your AWS API Gateway endpoint that triggers the Lambda function.

## Usage
* Start a conversation with your Master Teacher BOT on Telegram, indicating the topics or disciplines you wish to discuss.
* The bot will send 10 exam preparation questions.
* After the session, choose to either:
  * Continue with another set of questions, or
  * Analyze your answers from the previous session.

To run the program it is necessary to define the following variables in **AWS Lambda** *Configuration/Environment variables*:

* **BUCKET_NAME**: This is the name of the AWS S3 bucket where the users' answers will be stored.
* **GEMINI_API_KEY**: This is the access key to use the Gemini 2.0 service, which is responsible for the intelligent generation of questions and the analysis of answers.
* **TELEGRAM_BOT_TOKEN**: This is the token that authenticates and allows the bot to connect to the Telegram API.

## Contributing
Contributions are welcome! Please follow these steps:

* Fork the repository.
* Create a new branch for your feature or bug fix.
* Commit your changes with clear messages.
* Open a pull request detailing your changes.

## License
This project is licensed under the **MIT License**. See the **LICENSE** file for details.

