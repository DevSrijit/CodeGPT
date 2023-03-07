# GPT-Powered Customer Support Bot for Discord
[<img src="https://open.autocode.com/static/images/open.svg?" width="192">](https://open.autocode.com/)

This is a GPT-powered customer or community support bot. It works by connecting
to a Google Sheet with three colums: `Question`, `Answer` and `Embedding`.
Every time a user asks a question to the bot, it will first categorize the
question as a general conversation or tech support question. If it think it's a
tech support question, it will then query Google Sheets to find the most
appropriate answer and respond accordingly.

The `Embedding` field is meant to cache Embedding data in Google Sheets so you
don't have to re-query OpenAI for general support questions every time. If you
add new questions and answers, **you do not need to populate this field**.

![Support bot](/readme/gallery/1-bot-example.png)

## Example data for Google Sheets

Your Google Sheet must contain data in the following format to work. **Note that
the Embedding field can be empty, your bot will populate this automatically.**

| Question | Answer | Embedding |
| --- | --- | --- |
| How do I update my credit card? | You can update your credit card at https://autocode.com/dashboard/-/account/payment-methods/ | |
| My Discord bot won't link, help! | Try linking it again in incognito mode or disabling popup blockers. | |
| When I run my code it says "test data". | Try changing your payload in the editor using real IDs, or talking to your endpoint directly from Discord. | |
| Why is my bot offline? | You've likely used your free credits. Visit https://autocode.com/dashboard/-/account/sub/ to activate your account. | |
| How do I learn to code? | The best place to start is our Discord bot guide at https://autocode.com/guides/how-to-build-a-discord-bot/ | | |

## Adding more Questions and Answers

Simply update your Google Sheet to give your bot a larger knowledge base. Note
that when using the default template without modificaiton the Q&A repository
will only be looked up when the bot believes it has encountered a tech support
question.

## Bot not working?

Make sure [Privileged Intents](https://autocode.com/discord/threads/what-are-discord-privileged-intents-and-how-do-i-enable-them-tutorial-0c3f9977/)
are enabled for your bot, specifically the **Message Content** intent.
This is required to respond to the `bot_mention` event.

## Happy hacking!

Interested in how this bot works? Want to better understand embedding vectors?
Check out the guide [How to build a GPT support Discord bot](http://autocode.com/guides/how-to-build-a-gpt-support-discord-bot/).