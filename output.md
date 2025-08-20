**OpenAI ChatGPT Integration Guide**

Complete Setup & Implementation Guide

This comprehensive guide will walk you through integrating OpenAI's
powerful AI capabilities directly into your alexa360 chatbots, enabling
intelligent, context-aware conversations with your users.

# Introduction & Key Concepts

The alexa360 integration with OpenAI Assistant allows you to leverage
the power of OpenAI directly within your chatbots. The OpenAI Assistant
is a virtual assistant trained on your specific business data, enabling
it to answer user inquiries effectively.

<figure id="fig:integration">
<p><img src="media/Screenshot 2025-08-20 100224.png" alt="OpenAI Integration Dashboard" />
<span id="fig:integration" data-label="fig:integration"></span></p>
</figure>

**Key Concepts**

- **OpenAI Assistant**: A virtual assistant trained on your uploaded
  business files, functioning like a searchable knowledge base.

- **Assistant ID**: A unique identifier for your OpenAI Assistant within
  alexa360.

- **Model**: The specific OpenAI model used by your assistant (e.g.,
  gpt-4 turbo).

- **Instructions**: Additional prompts or guidelines provided to the
  assistant for refining its responses.

- **File Uploads**: Business-related documents uploaded for the
  assistant's training.

# Setting Up the OpenAI Assistant

## Access the Integration

**Navigate to Integrations**

In your alexa360 dashboard, navigate to **Integrations → OpenAI**.

<figure id="fig:integration">
<p><img src="media/Screenshot 2025-08-20 101459.png" alt="API Key Configuration" />
<span id="fig:integration" data-label="fig:integration"></span></p>
</figure>

## API Key Configuration

**Generate OpenAI API Key**

Follow these steps to configure your API key:

1.  Generate your OpenAI API key at <https://platform.openai.com>

2.  Login with your credentials → Go to your profile (top-right corner)
    → **View API Keys**

3.  Copy your API key and paste it into alexa360 OpenAI settings

4.  Click **Save** to establish the connection

## Uploading Files

**Upload Business Documents**

- Under the **Files** tab, upload relevant business documents to train
  your assistant

- Files can be uploaded via button or file URL

- Recommended file size limit: 200 MB

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/1.png" alt="File Upload Interface" /> <span id="fig:integration"
data-label="fig:integration"></span></p>
</figure>

## Creating an Assistant

**Create New Assistant**

1.  Click **New Assistant**

2.  Enter **name**, **description**, and select a **model** (default:
    gpt-4 turbo)

3.  Provide **instructions** (tone, style, persona---up to 20,000
    characters)

4.  Attach previously uploaded files relevant to the assistant's
    function

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/assisstant.png" alt="Assistant Creation Interface" /> <span
id="fig:integration" data-label="fig:integration"></span></p>
</figure>

**Save & Sync**

- Click **Create** to generate the assistant

- The assistant will also sync with your OpenAI account

**✅ Success!** Your OpenAI Assistant is now ready to use in your
chatbot flows!

# Using the Assistant in Your Flow

## Building the Flow

**Create Flow**

Create a new flow in alexa360 to incorporate the assistant.

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/6.png" alt="Flow Creation Interface" /> <span id="fig:integration"
data-label="fig:integration"></span></p>
</figure>

## Question Block Configuration

**Add Question Block**

Add a question block prompting input, e.g., *\"What can I help you with
today?\"*

## OpenAI Assistant Integration

**Select Integration**

Under **Integrations**, select **OpenAI → Create Assistant Completion**.

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/4.png" alt="Integration Selection" /> <span id="fig:integration"
data-label="fig:integration"></span></p>
</figure>

## Configuration Options

**Configure Assistant Settings**

- **Remember History**: Choose whether the assistant should retain
  conversation history

- **Assistant ID**: Enter the ID of the assistant you created earlier

- **Model Override** (Optional): Override the assistant's default model

- **User Input**: Map the user's text input into the Content field

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/5.png" alt="Configuration Options" /> <span id="fig:integration"
data-label="fig:integration"></span></p>
</figure>

## Testing & Saving

**Test & Save**

1.  Try a sample query like *\"What is your offer?\"*

2.  Review the assistant's response

3.  Save the completion once satisfied

# Mapping the Assistant Response

**Run Test Request**

In the **Create Assistant Completion** block, run a **Test Request**.

**Access Sample Data**

Open the **Sample Data** section.

**Map Response Values**

1.  Click the **Map** icon → Select the assistant reply value

2.  Assign it to a custom field (e.g., `assistant_reply`)

3.  Save your mapping

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/Screenshot%202025-08-20%20104536.png" alt="Response Mapping" />
<span id="fig:integration" data-label="fig:integration"></span></p>
</figure>

**ℹ️ Note:** You can now reuse the assistant's replies in messages
throughout your flows.

# Intent Detection with OpenAI

alexa360 offers an intent detection system powered by OpenAI. This lets
you capture **parameters** from user queries, similar to Google
Dialogflow.

## Workflow Setup

**Enable Auto Intent Detection**

- Go to **Automations** → enable the **Auto Intent Detect** slider

- If you get an error, ensure OpenAI integration is configured correctly

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/Screenshot%202025-08-20%20104659.png" alt="Auto Intent Detection" />
<span id="fig:integration" data-label="fig:integration"></span></p>
</figure>

## Creating Intents

**Create New Intent**

1.  Click **+ New Intent**

2.  Define intent name, description, and sample training phrases

3.  Add **parameters** with value options (like location, date, product)

4.  Assign a subflow to trigger once all required parameters are filled

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/Screenshot%202025-08-20%20104744.png" alt="Intent Creation" />
<span id="fig:integration" data-label="fig:integration"></span></p>
</figure>

## Best Practices for Intents

**Intent Management**

- Clear stored parameters after intent completion to avoid using
  outdated data

- Save intent values in JSON custom fields and reset them at the end of
  each flow

- Remember the bot hierarchy: **Intents → Keywords → Default Reply**

**⚠️ Token Usage:** Token usage increases with the number of parameters
in an intent and higher confidence thresholds.

# Creating & Using Embeddings

Embeddings help match user inputs with business knowledge, allowing
highly relevant responses.

## Creating an Embedding

**Navigate to Embeddings**

Go to **Integrations → OpenAI → New Embedding**.

**Fill Required Fields**

- **Type**: Context category (optional, but recommended)

- **Heading**: Title/summary of the embedding

- **Text**: Main body (max 1000 characters)

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/1e.png" alt="Embedding Creation" /> <span id="fig:integration"
data-label="fig:integration"></span></p>
</figure>

## Importing Embeddings (Bulk)

- Use **Import CSV** to upload multiple embeddings at once

- CSV must include headers: `type, heading, text`

- Ensure headers are lowercase and not capitalized

## Embedding Match & Completion

- **Embedding Match**: Compares a user prompt to embeddings, returns the
  closest match with a **score**

- **Completion**: Uses the matched embedding as context for generating a
  response

- Recommended score threshold: ≥0.79 for accuracy (test for your use
  case)

# Vector Stores (Advanced)

Vector Stores allow you to store and retrieve information in a way that
is optimized for semantic search. Instead of matching keywords, vector
stores use embeddings (numerical representations of text) to find the
most relevant pieces of information based on meaning.

This feature is especially useful for building chatbots that can answer
domain-specific questions directly from large sets of business
documents, FAQs, or customer knowledge bases.

**Key Concepts**

- **Embedding**: A numerical vector representation of text. Two pieces
  of text with similar meaning will have embeddings that are close to
  each other.

- **Vector Store**: A structured storage system in alexa360 that holds
  embeddings for fast semantic search.

- **Match Score**: A similarity score (0 → 1.0) that shows how closely
  the user's query matches a stored embedding.

- **Context Retrieval**: Pulling the most relevant text from the vector
  store to use as context for the assistant's response.

## Creating a Vector Store

**Navigate to Vector Stores**

Navigate to **Integrations → OpenAI → Vector Stores** in your alexa360
dashboard.

**Create New Store**

1.  Click **New Vector Store**

2.  **Name**: A descriptive name (e.g., \"Product Catalog\", \"Support
    KB\")

3.  **Description**: Purpose of this store

4.  **Model for Embeddings**: Choose which OpenAI embedding model to use
    (e.g., `text-embedding-3-large`)

5.  Save the Vector Store

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/Screenshot%202025-08-20%20104942.png" alt="Vector Store Creation" />
<span id="fig:integration" data-label="fig:integration"></span></p>
</figure>

## Adding Data to a Vector Store

**Add Individual Embeddings**

1.  Open your Vector Store and click **Add Embedding**

2.  **Type** (optional): A category or context tag (e.g., \"Pricing\",
    \"Returns\")

3.  **Heading**: Title/summary of the entry

4.  **Text**: Full content (max 1000 characters)

**Bulk Import via CSV**

- Use **CSV upload** for bulk imports

- Ensure the file has lowercase headers (`type, heading, text`)

- Each row represents one embedding record

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/3v.png" alt="Bulk Import Interface" /> <span id="fig:integration"
data-label="fig:integration"></span></p>
</figure>

## Using Vector Stores in Flows

**Add Vector Store Search Block**

In your flow, add an **OpenAI → Vector Store Search** block.

**Configure Search Parameters**

1.  Map the **user input** as the query

2.  **Top N Results**: How many embeddings to return (e.g., 3)

3.  **Match Threshold**: Minimum similarity score required (e.g., ≥0.79)

4.  Map results into custom fields (e.g., `best_heading`, `best_text`,
    `best_score`)

<figure id="fig:integration">
<p><img src="https://raw.githubusercontent.com/MagedDevOps/alexa360-openai-guide/main/media/4v.png" alt="Search Parameters Configuration" /> <span id="fig:integration"
data-label="fig:integration"></span></p>
</figure>

## Example Flow: FAQ Knowledge Base

1.  **Trigger**: User asks → *\"Do you offer free trials?\"*

2.  **Vector Store Search**:

    - Input: user's query

    - Output: matched embedding → \"Free trial\" (score 0.90)

3.  **Assistant Completion**:

    - Prompt includes retrieved text: *\"Based on company policy:
      alexa360 offers a 14-day free trial with no credit card
      required.\"*

4.  **Response**: AI-generated reply grounded in the knowledge base

## Best Practices for Vector Stores

- Keep embeddings concise (≤1000 characters each). Split long docs into
  smaller sections.

- Use descriptive **headings** for faster troubleshooting and search.

- Test different **thresholds** (0.75--0.85) to balance accuracy and
  flexibility.

- Regularly update embeddings as your business information changes.

- Combine **vector search + assistant completion** for the best mix of
  retrieval + generative AI.

**✅ With Vector Stores,** your alexa360 chatbot moves from generic AI
to a knowledge-driven virtual assistant, capable of answering with
accuracy, grounded in your business data.

# Advanced Usage and Considerations

- **Multiple OpenAI Actions**: alexa360 provides various OpenAI actions
  (e.g., list assistant files, create assistant, embeddings).

- **Looping Conversations**: You can loop back to the assistant
  completion to create ongoing dialogue-like interactions.

- **Custom Fields**: Store assistant replies in custom fields for later
  use in flows or messages.

# Practical Use Cases

- **Website Widget Support**: AI-powered FAQs and live chat escalation.

- **E-commerce**: Order tracking, returns, personalized product
  recommendations.

- **Facebook & Instagram Comments**: Automatically reply with relevant
  answers instead of generic responses.

- **Knowledge Base Bots**: Use embeddings + assistant completions to
  answer questions from uploaded docs.

# Summary & Best Practices

By integrating OpenAI with alexa360, you can:

- Build assistants trained on your own data

- Use AI for FAQs, support, bookings, and sales

- Detect intents and capture structured data

- Match and generate responses using embeddings

- Implement advanced vector stores for semantic search

This empowers your chatbot to deliver **natural, context-aware, and
business-specific answers**---enhancing customer experience and reducing
manual workload.


**ℹ️ Additional Resources:**

- OpenAI API Documentation: <https://platform.openai.com/docs>

- alexa360 Support Center: Contact support for implementation assistance

- Best Practices Guide: Review advanced configuration options in your
  dashboard