---
icon: flask-round-potion
---

# Usage calculation

This page explains how to calculate the * * conversational text count * * and the * * knowledge base capacity * * when the system is in use. Understanding how usage is calculated can help you plan the use of resources and design AI assistants more effectively.

## Conversation text count

### How General Text is Calculated

* For each round of conversation, * * user input * * and * * AI assistant responses * * are counted.
* One character counts as one word

Example: In the conversation history, the user input will be counted as 6 words, and the user input will be counted as 2 words, so the total is 8 words

```
使用者：Hello!
AI助理：您好
```

### How the image is calculated

* * 500 * * words per image

## Knowledge Base Capacity Calculation

The sum of the * * file sizes * * in the knowledge base upload page of all AI assistants under the organization is the capacity used by the knowledge base.

## Usage Statistics Page

See current usage in * * Organization Settings * *

<figure><img src="../.gitbook/assets/截圖 2025-03-27 上午8.05.41.png" alt=""><figcaption></figcaption></figure>

## よくある質問

* If the file is deleted, is the capacity calculated?
  * will not be calculated after deletion