# Build-a-Telegram-AI-Bot-with-OpenClaw-Anthropic-API
Build a Telegram AI bot with OpenClaw. Local setup, Claude AI, cron jobs, allowlist security.


# Build a Telegram AI Bot with OpenClaw

**Project Link:** [View Project](http://learn.nextwork.org/projects/ai-openclaw-setup)
<img width="2752" height="1536" alt="Deploying_an_AI_Agent" src="https://github.com/user-attachments/assets/1e01fb95-ed62-4df5-be2d-c9cad47ca506" />

---

![Image](http://learn.nextwork.org/radiant_blue_innocent_pawpaw/uploads/ai-openclaw-setup_k3m8n2q5)

---

## Introducing Today's Project

In this project, I am setting up a free, open-source AI agent called OpenClaw on my local machine, connecting it to the Anthropic API and a Telegram bot so I can message it from my phone, locking it down with an allowlist so only I can use it, running the OpenClaw Gateway as the central hub to handle all my messages, and completing a secret mission to automate a check every 10 minutes for proactive tasks.

### Key tools and concepts

The key tools I used include Node.js v22+, OpenClaw (the open-source AI assistant platform), the Anthropic API with Claude Sonnet 4.5, Telegram and BotFather for creating a bot, the OpenClaw Gateway (a background service running on port 18789), the Control UI (a web-based chat interface), the allowlist (via the allowFrom configuration field), and cron jobs for automated scheduling. Key concepts I learned include how a local Gateway acts as an always-on hub between my messages and the AI, why personal-by-default security mode differs from multi-user lockdown, how bot tokens work as authentication, what tokens are for API billing, and how proactive automation (cron jobs) transforms a reactive chatbot into an autonomous agent.

### Challenges and wins

This project took me approximately 45 to 60 minutes from start to finish, including the secret mission cron job setup. The most challenging part was navigating the Onboarding Wizard prompts because some options required pressing spacebar to select before hitting Enter, and I had to carefully skip the right screens while making sure my API key was pasted correctly without extra spaces.

### Project Reflection

I did this project today to learn how to deploy my own always-on, locally-run AI assistant that I can message from my phone and that can proactively reach out to me on a schedule. Another skill I want to learn is how to connect OpenClaw to additional tools like Google Calendar, email, or home automation systems so my assistant can actually execute tasks on my behalf beyond just sending messages.



---

## Installing OpenClaw and Running the Gateway

I am installing or verifying Node.js v22+, installing OpenClaw on my machine, answering the installer prompt, and verifying that the Gateway is running so my assistant stays alive in the background ready to respond whenever I message it.

![Image](http://learn.nextwork.org/radiant_blue_innocent_pawpaw/uploads/ai-openclaw-setup_w4x9c2d7)

### Verifying the Gateway

I installed OpenClaw by running curl -fsSL https://openclaw.ai/install.sh | bash in my terminal, which launched the Onboarding Wizard where I confirmed the security prompt, selected QuickStart, chose Anthropic as my AI provider, pasted my Anthropic API key, selected Claude Sonnet 4.5, skipped through the remaining prompts, and then I verified the Gateway was running by executing openclaw gateway status and confirming that the status showed as active and healthy.



---

## My First Conversation with an AI Assistant

In this step, I am opening the built-in Control UI in my browser, having my first conversation with my OpenClaw assistant to see what it can do, and checking my usage and costs with the /status command.



![Image](http://learn.nextwork.org/radiant_blue_innocent_pawpaw/uploads/ai-openclaw-setup_g8h3k6n1)

### Testing the assistant

I asked my assistant "Hello! Can you introduce yourself and tell me what you can do?" and it responded with an introduction about itself and a list of its available tools and capabilities, confirming that my local Gateway on port 18789 is successfully connected to the Anthropic API and my assistant is working properly.

---

## Connecting Telegram for Mobile Access

In this step, I am creating a Telegram bot using BotFather, adding the bot token to my OpenClaw configuration, and testing that my assistant responds to me through Telegram so I can message it from anywhere at any time.

### Configuring the Telegram channel

I connected Telegram to my OpenClaw assistant by using @BotFather in Telegram to create a new bot named MyNextWorkClaw with the username mynextworkclaw_bot, copying the bot token that @BotFather gave me, then going to the Control UI and asking my assistant "Here is my bot token: [YOUR_TOKEN]. Please add it to my OpenClaw configuration as a Telegram channel," followed by restarting the Gateway with openclaw gateway restart, and finally testing the connection by searching for my bot in Telegram, sending /start to get a pairing code, asking my assistant to approve the pairing with that code, and then sending a test message to confirm my assistant responds through Telegram.

---

## Securing the Assistant with Allowlists

In this step, I'm going to find my Telegram user ID and configure an allowlist so that only I can talk to my OpenClaw assistant, because allowlists are important to prevent unauthorized users from discovering my bot, draining my Anthropic API credits, or accessing my assistant's capabilities

![Image](http://learn.nextwork.org/radiant_blue_innocent_pawpaw/uploads/ai-openclaw-setup_j5l9n3p7)

### Implementing security controls

I secured my OpenClaw assistant by finding my Telegram user ID (either from the pairing response or by asking my bot "What is my Telegram user ID?"), then messaging my bot in Telegram with the command "Add my Telegram user ID [my_number] to the allowlist in my OpenClaw configuration so only I can message you," followed by restarting the Gateway with openclaw gateway restart, and the allowFrom field in my config now restricts access so that only messages from my numeric Telegram user ID are processed while everyone else is blocked

---

## Automating with Cron Jobs

![Image](http://learn.nextwork.org/radiant_blue_innocent_pawpaw/uploads/ai-openclaw-setup_d4f8h2k6)

### Building proactive automation

In this project extension, I set up a cron job that sends me a motivational quote and a fun fact every 10 minutes, and it runs at intervals defined by the cron schedule (*/10 * * * ), which I created by simply messaging my Telegram bot "Set up a cron job: every 10 minutes, send me a motivational quote and a fun fact," then I verified it with openclaw cron list, and I customized it by asking my assistant to update the check to also include a random piece of trivia, turning my assistant from a reactive chatbot into a proactive agent that reaches out to me automatically.

---

---
