# n8n AI News Telegram Bot

An automated AI news monitoring workflow built with **n8n**. It collects articles from multiple RSS feeds, filters for relevant AI-related keywords, keeps only recent news, prepares a concise message, and publishes the results to a Telegram channel.

## Overview

This workflow runs once per day and processes AI news from multiple RSS sources.

Current sources:

- OpenAI
- TechCrunch AI
- n8n Blog

The workflow:

1. Runs automatically on a daily schedule.
2. Reads articles from multiple RSS feeds.
3. Merges all articles into one stream.
4. Filters titles using AI-related keywords.
5. Keeps only articles published in the last 24 hours.
6. Extracts the title, link, publication date, and available RSS summary/description.
7. Formats the article into a readable Telegram message.
8. Publishes the selected news to a Telegram channel.

## Workflow

```text
Daily Schedule
   ├── RSS OpenAI
   ├── RSS TechCrunch AI
   └── RSS n8n
          ↓
       Merge News
          ↓
    Filter Keywords
          ↓
 Filter Last 24 Hours
          ↓
  Prepare News Message
          ↓
 Publish to Telegram
```

## Features

- Automated daily execution
- Multiple RSS feed aggregation
- Keyword-based filtering
- 24-hour publication-date filtering
- RSS summary/description extraction
- Telegram channel publishing
- No paid AI API required
- Built with free/public RSS feeds

## Example Keywords

The workflow can keep articles whose titles contain terms such as:

```text
AI
agent
automation
OpenAI
LLM
```

The keyword conditions are combined with **OR**, so an article only needs to match one of them.

## Recent News Filter

A second filter keeps only articles published within the previous 24 hours.

Conceptually:

```text
Article publication date
is after
current time - 24 hours
```

This keeps the daily Telegram feed focused on recent news.

## Message Format

Example Telegram message:

```text
🧠 AI News Update

📰 Article title

📝 Summary:
Short description from the RSS feed...

🔗 https://example.com/article
```

> Note: The current version uses the summary/description supplied by the RSS feed. It does not use a paid LLM API for AI-generated summarization.

## Tools Used

- n8n
- Telegram Bot API
- RSS
- OpenAI News RSS
- TechCrunch AI RSS
- n8n Blog RSS

## What I Learned

This project helped me practice:

- Scheduled workflows
- RSS feed processing
- Working with multiple data sources
- Merge nodes
- Filtering multiple items
- OR conditions
- Date and time filtering
- n8n expressions
- Data mapping
- Telegram Bot integration
- Publishing automated content to a Telegram channel
- End-to-end automation testing

## Possible Improvements

Future improvements could include:

- Duplicate article detection using the article URL
- AI-generated summaries using a local or free-tier model
- Source labels for each article
- Error handling and retry logic
- Article scoring or prioritization
- Sending one daily digest instead of separate messages
- Storing an archive of published articles
- Adding more reliable AI news sources

## Project Status

✅ Working prototype completed

The workflow has been tested for:

- Reading multiple RSS feeds
- Merging feed items
- Keyword filtering
- 24-hour date filtering
- Telegram bot authentication
- Publishing messages to a public Telegram channel

## Repository Files

This repository can also include:

```text
README.md
workflow.json
workflow.png
```

- `workflow.json` — exported n8n workflow for importing into another n8n instance
- `workflow.png` — screenshot of the complete workflow
