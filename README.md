# Memory Lane

Memory Lane is a Jupyter Notebook designed to summarize your long iMessage conversations, letting you reminisce about meaningful exchanges without the need to manually scroll through years of messages. Using advanced natural language processing techniques, it provides concise summaries of your chats, enabling a nostalgic experience.

## Features

The notebook offers the following capabilities:

1. **Data Extraction**: Connects to the iMessage database stored locally on your macOS device and extracts relevant conversation data using Python's SQLite library.

2. **Data Formatting**: Decodes attributed body messages and filters messages by specific contacts or numbers.

3. **Text Splitting**: Utilizes LangChain's `RecursiveCharacterTextSplitter` to split long conversations into smaller, manageable chunks while maintaining context.

4. **Vector Embedding**: Converts conversation segments into embeddings using OpenAI's `OpenAIEmbeddings` for use in large language models.

5. **Clustering**: Organizes conversation chunks using FAISS for efficient similarity searches.

6. **Summarization**: Feeds relevant conversation chunks into OpenAI's GPT-4 for generating high-quality summaries of topics and themes.

7. **Querying**: Allows querying specific topics or themes from the conversation for targeted insights.

## How It Works

### Process Overview

1. **Extracting iMessage Data**:

   - Reads your local iMessage database (`chat.db`) for message content, sender information, and timestamps.
   - Filters messages to include only those relevant to the specified contact(s).

2. **Text Splitting and Embedding**:

   - Splits long conversations into overlapping chunks of approximately 3000 characters.
   - Converts each chunk into a numerical vector representation for efficient processing.

3. **Summarization**:

   - Uses FAISS to cluster and retrieve the most relevant conversation chunks.
   - Summarizes the chunks using GPT-4, combining them into a cohesive narrative.

4. **Interactive Querying**:

   - Enables users to pose specific questions (e.g., "What were the most common topics?") and receive tailored summaries.

## Setup and Usage

### Prerequisites

- macOS device with iMessage database access (`chat.db`).
- Python 3.10 or higher.
- OpenAI API key for accessing GPT-4.
- Required Python libraries: `sqlite3`, `LangChain`, `FAISS`, `OpenAIEmbeddings`, and `TypedStreamReader`.

## Example Use Case

After setting up the notebook, you can:

- Generate a summary of the most frequent conversation topics.
- Retrieve meaningful quotes or discussions on specific themes.
- Export summaries for nostalgic keepsakes or analysis.

## Additional Resources

For a detailed explanation of a similar implementation, check out the accompanying Medium post: [Using LangChain to Summarize Long iMessage Conversations](https://medium.com/@rohankumar_75589/using-langchain-to-summarize-long-imessage-text-conversations-c97137851f4c).

## Disclaimer

This project is intended for personal use only. Ensure that you handle your iMessage data responsibly and comply with applicable privacy regulations.

