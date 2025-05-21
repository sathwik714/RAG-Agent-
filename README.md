# Agent for Complex RAG Tasks 🧠📚

An advanced Retrieval-Augmented Generation (RAG) solution designed to tackle complex questions that simple semantic similarity-based retrieval cannot solve. This project showcases a sophisticated deterministic graph acting as the "brain" of a highly controllable autonomous agent capable of answering non-trivial questions from your own data

## 🌟 Key Features

- **Sophisticated Deterministic Graph**: Acts as the "brain" of the agent, enabling complex reasoning.
- **Controllable Autonomous Agent**: Capable of answering non-trivial questions from custom datasets.
- **Hallucination Prevention**: Ensures answers are solely based on provided data, avoiding AI hallucinations.
- **Multi-step Reasoning**: Breaks down complex queries into manageable sub-tasks.
- **Adaptive Planning**: Continuously updates its plan based on new information.
- **Performance Evaluation**: Utilizes `Ragas` metrics for comprehensive quality assessment.


## 🧠 How It Works
![Solution Schema](graphs/final_graph_schema.jpeg)

1. **PDF Loading and Processing**: Load PDF documents and split them into chapters.
2. **Text Preprocessing**: Clean and preprocess the text for better summarization and encoding.
3. **Summarization**: Generate extensive summaries of each chapter using large language models.
4. **Book Quotes Database Creation**: Create a database for specific questions that will need access to quotes from the book.
5. **Vector Store Encoding**: Encode the book content and chapter summaries into vector stores for efficient retrieval.
6. **Question Processing**:
   - Anonymize the question by replacing named entities with variables.
   - Generate a high-level plan to answer the anonymized question.
   - De-anonymize the plan and break it down into retrievable or answerable tasks.
7. **Task Execution**:
   - For each task, decide whether to retrieve information or answer based on context.
   - If retrieving, fetch relevant information from vector stores and distill it.
   - If answering, generate a response using chain-of-thought reasoning.
8. **Verification and Re-planning**:
   - Verify that generated content is grounded in the original context.
   - Re-plan remaining steps based on new information.
9. **Final Answer Generation**: Produce the final answer using accumulated context and chain-of-thought reasoning.

## 📊 Evaluation

The solution is evaluated using `Ragas` metrics:
- Answer Correctness
- Faithfulness
- Answer Relevancy
- Context Recall
- Answer Similarity

### Example Question
**Q: How did the protagonist defeat the villain's assistant?**

To solve this question, the following steps are necessary:

1. Identify the protagonist of the plot.
2. Identify the villain.
3. Identify the villain's assistant.
4. Search for confrontations or interactions between the protagonist and the villain.
5. Deduce the reason that led the protagonist to defeat the assistant.

The agent's ability to break down and solve such complex queries demonstrates its sophisticated reasoning capabilities.



## 🛠️ Technologies Used

- LangChain
- FAISS Vector Store
- Ragas (for evaluation)
- Flexible integration with various LLMs (e.g., OpenAI GPT models, Groq, or others of your choice)
