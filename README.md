# 🤖 NextJSRAGAI

### Your Intelligent Document Assistant

> Transform your documents into interactive knowledge with RAG-powered conversations

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Next.js](https://img.shields.io/badge/Next.js-13.0-black)](https://nextjs.org/)
[![LangChain](https://img.shields.io/badge/LangChain-0.1.0-blue)](https://js.langchain.com/)
[![OpenAI](https://img.shields.io/badge/OpenAI-Compatible-green)](https://openai.com/)

## 🌟 What is NextJSRAGAI?

NextJSRAGAI is a modern document interaction platform that leverages the power of Retrieval-Augmented Generation (RAG) to create intelligent conversations with your documents. Built with Next.js and LangChain, it transforms static documents into dynamic knowledge bases that you can query naturally.

## 🧠 Understanding RAG

Retrieval-Augmented Generation (RAG) is a powerful AI architecture that combines the benefits of large language models with precise information retrieval. Here's how it works:

### The RAG Workflow:

1. **Document Processing** 📄
   - Documents are chunked into smaller segments
   - Each chunk is converted into a vector embedding
   - Embeddings are stored in a vector database

2. **Query Processing** 🔍
   - User questions are converted into vector embeddings
   - Similar vectors from the database are retrieved
   - Relevant context is extracted

3. **Response Generation** 💬
   - Retrieved context is combined with the user's question
   - LLM generates accurate, contextual responses
   - Information is grounded in your actual documents

## 🛠️ Technical Stack

- **Frontend**: Next.js 13+ with App Router
- **UI Components**: shadcn/ui
- **Vector Store**: ChromaDB
- **Embeddings**: OpenAI Ada-2
- **LLM Integration**: LangChain.js
- **Styling**: Tailwind CSS
- **Theme**: Dark/Light mode support

## 🚀 Getting Started

### Prerequisites

```bash
Node.js 18+
OpenAI API Key
```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/firasabdelaziz/vectorvault.git
cd vectorvault
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
cp .env.example .env.local
# Add your OpenAI API key to .env.local
```

4. Run the development server:
```bash
npm run dev
```

## 🎯 Features

- 📝 Document parsing and chunking
- 🔍 Semantic search capabilities
- 💾 Vector storage and retrieval
- 🤖 Conversational AI interface
- 🌓 Dark/Light mode support
- 📱 Responsive design
- ⚡ Real-time responses
- 🔐 Secure document handling

## 🔧 Configuration

### Vector Store Settings

```typescript
const CHUNK_SIZE = 1000;
const CHUNK_OVERLAP = 200;

const vectorStoreConfig = {
  collection: "documents",
  embeddingSize: 1536,
  similarity: "cosine"
};
```

### LangChain Pipeline

```typescript
const chain = RunnableSequence.from([
  vectorStore.asRetriever(),
  promptTemplate,
  llm,
  outputParser
]);
```

## 📚 API Reference

### Document Upload

```typescript
POST /api/documents
Content-Type: multipart/form-data

Response:
{
  "success": true,
  "documentId": "doc_123",
  "vectorCount": 15
}
```

### Query Endpoint

```typescript
POST /api/query
Content-Type: application/json

{
  "question": "What is the main topic of chapter 3?",
  "documentId": "doc_123"
}
```

## 🎨 Customization

### Custom Prompt Templates

```typescript
const promptTemplate = PromptTemplate.fromTemplate(`
Answer the question based on the context below:
Context: {context}
Question: {question}
Answer: Let's approach this step by step:
`);
```

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Next.js team for the amazing framework
- LangChain community for the powerful tools
- OpenAI for the API access
- shadcn for the beautiful UI components

## 📞 Contact

Firas Abdelaziz

GitHub: [@firasabdelaziz](https://github.com/firasabdelaziz)

Project Link: [https://github.com/firasabdelaziz/NextJSRAGAI](https://github.com/firasabdelaziz/NextJSRAGAI)

---

Built with ❤️ by [Firas Abdelaziz](https://github.com/firasabdelaziz)