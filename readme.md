# Graph RAG Application

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MohamedIKenedy/Computer-vision-based-Emotion-tracker/blob/main/GraphRAGs.ipynb)

A sophisticated Retrieval-Augmented Generation (RAG) system that combines Knowledge Graphs, Document Processing, and Google's Gemini LLM for intelligent document analysis and querying.

## 🌟 Features

- **Multi-Format Document Processing**
  - PDF document extraction and chunking
  - Tabular data processing (CSV, Excel)
  - Automatic statistical analysis for numerical data
  - Smart sampling and summarization for large datasets

- **Knowledge Graph Construction**
  - Semantic embedding using Sentence Transformers
  - Automated node and edge creation based on content similarity
  - Graph-based document relationships visualization
  - ChromaDB integration for efficient vector storage

- **Intelligent Querying**
  - Integration with Google's Gemini Pro model
  - Context-aware response generation
  - Hybrid retrieval combining graph traversal and semantic search
  - Automated context aggregation from relevant nodes

## 🔧 Installation

```bash
pip install -r requirements.txt
```

Required dependencies:
```
google-generativeai
sentence-transformers
networkx
pandas
numpy
pypdf
torch
chromadb
matplotlib
scikit-learn
```

## 🔑 Configuration

Before using the application, set up your Google Gemini API key:

```python
import os
os.environ['GOOGLE_API_KEY'] = 'your-api-key-here'
```

## 💻 Usage

### Basic Usage

```python
from graph_rag import GraphRAGApplication

# Initialize the application
app = GraphRAGApplication(gemini_api_key="your-api-key")

# Add documents to the knowledge base
app.add_document("path/to/document.pdf")
app.add_document("path/to/data.csv")

# Query your documents
response = app.query("What are the key insights from the documents?")
print(response)
```

### Advanced Usage

```python
# Custom document processing
doc_processor = DocumentProcessor()
chunks = doc_processor.process_pdf("document.pdf")

# Create and visualize knowledge graph
knowledge_graph = KnowledgeGraph()
knowledge_graph.add_document(chunks, "doc_id")
knowledge_graph.visualize_graph()

# Custom querying
rag_querying = RAGQuerying(api_key="your-api-key")
response = rag_querying.query(
    question="your question",
    knowledge_graph=knowledge_graph,
    top_k=5
)
```

## 🏗️ Architecture

The application consists of three main components:

1. **DocumentProcessor**
   - Handles document ingestion and chunking
   - Supports PDF and tabular data formats
   - Performs statistical analysis on numerical data
   - Implements smart sampling for large datasets

2. **KnowledgeGraph**
   - Creates semantic embeddings using Sentence Transformers
   - Builds graph relationships based on content similarity
   - Stores vector embeddings for efficient retrieval
   - Integrates with ChromaDB for persistence

3. **RAGQuerying**
   - Integrates with Google's Gemini Pro model
   - Implements semantic search for relevant context
   - Traverses graph relationships for context expansion
   - Generates coherent responses based on retrieved context

## 📊 Example Output

```python
question = "What are the key insights from the documents?"
response = app.query(question)

# Sample output:
"""
- PCA finds an orthonormal basis for the data, sorting dimensions in order of importance (variance)
- PCA can be used to get a compact description of the data, view and assess it, ignore noise, and improve clustering
- PCA does not know class labels and can only capture linear variations
- PCA is one of many techniques to reduce dimensionality
"""
```

## 🎯 Use Cases

- **Document Analysis**: Process and analyze large document collections
- **Data Insights**: Extract insights from mixed data sources
- **Intelligent Q&A**: Build context-aware question answering systems
- **Knowledge Discovery**: Uncover relationships between different pieces of information

## ⚠️ Limitations

- PDF processing may be affected by complex layouts or formatting
- Large documents may require significant memory resources
- Query response quality depends on document content quality
- API key required for Gemini model access

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.
