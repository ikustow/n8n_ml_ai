# ML Analytics Workflows - n8n Automation Project

## 📋 Project Description

This project is a collection of automated workflows for machine learning analysis, built on the **n8n** platform. The system is designed to automate data clustering processes, feature analysis, and the generation of analytical reports using artificial intelligence.

## 🏗️ System Architecture

The project consists of four main workflows that work together to provide a complete data analysis cycle:

### 1. **ML_AI.json** - Main Orchestrator
The primary workflow that coordinates all other components:
- **Chat Trigger**: Receives incoming messages through a chat interface
- **OpenAI Chat Model**: Uses the GPT-4.1-mini model to process requests
- **Memory Buffer**: Maintains conversation context (up to 100 messages)
- **Agent Orchestrator**: Manages the sequence of tool execution

### 2. **context_generator.json** - Context Generator
Responsible for preparing and structuring data for subsequent analysis.

### 3. **Feature Analysis Agent.json** - Feature Analysis Agent
Specialized workflow for:
- Analyzing data structure
- Identifying numerical and categorical features
- Preparing data for clustering

### 4. **data_analyst.json** - Analytical Agent
Generates detailed analytical reports based on clustering results.

## 🔄 Workflow Process

1. **Request Reception**: Chat Trigger receives a user message
2. **Context Generation**: context_generator is launched to prepare data
3. **Feature Analysis**: Feature Analysis Agent analyzes data structure and performs clustering
4. **Report Generation**: data_analyst creates the final analytical report
5. **Result Return**: The system returns a structured response to the user

## 🛠️ Technologies and Tools

- **n8n**: Workflow automation platform
- **OpenAI GPT-4.1-mini**: Language model for natural language processing
- **LangChain**: Framework for working with language models
- **Memory Buffer**: Conversation context management system

## 📦 Installation and Launch

### Installing n8n

```bash
# Using npm
npm install n8n -g

# Starting the service
n8n start
```

### Alternatively via Docker

```bash
docker run -it --rm \
  --name n8n \
  -p 5678:5678 \
  n8nio/n8n
```

## ⚙️ Setup

1. **API Keys**: Configure OpenAI credentials in the Credentials section
2. **Workflows**: Import all JSON files from the `workflows/` folder
3. **Activation**: Activate the main workflow `ML_AI`

## 🔧 Configuration

- **Session Management**: Each session has a unique ID for context management
- **Memory Window**: Configured with a buffer of 100 messages to maintain context
- **Workflow Execution**: Sequential execution is used (v1)

## 📊 System Capabilities

- **Automatic clustering** of student data
- **Feature analysis** with data type determination
- **Generation of analytical reports** using AI
- **Maintaining conversation context** between requests
- **Modular architecture** for easy functionality expansion

## 🚀 Usage

The system operates through a chat interface. The user sends a data analysis request, and the system automatically:

1. Processes the request
2. Initiates the clustering process
3. Analyzes the results
4. Provides a detailed report

Example uses of similar systems include automation of resume analysis and other types of data.

## 📋 Requirements

- Node.js (for npm installation)
- Docker (for containerized launch)
- OpenAI API key
- Minimum 2GB RAM for stable operation

---

*The project utilizes n8n capabilities to create a powerful data analysis automation system with integration of modern machine learning and AI technologies.*