RAG Chatbot with Mistral AI
A Retrieval-Augmented Generation (RAG) chatbot built with Flask and Mistral AI that can answer questions based on a provided text document.
Created by Halim Madi
This is a sample project designed for students, workshops, and educational purposes. Feel free to use, modify, and distribute this code as you wish for learning and development.
About the Creator

Website: www.halimmadi.com
Instagram: @yalla_halim

Features

Retrieval-Augmented Generation: Combines document retrieval with AI generation for accurate, context-aware responses
Web Interface: Clean, retro-styled chat interface
Real-time Processing: Processes questions and generates responses in real-time
Semantic Search: Uses vector embeddings to find relevant document chunks
Error Handling: Comprehensive error handling and logging
CORS Support: Enables cross-origin requests for flexible deployment

How It Works

Document Processing: The system chunks the provided text document (essay.txt) into manageable pieces
Embedding Creation: Uses Mistral's embedding model to create vector representations of text chunks
Query Processing: When a user asks a question, it creates an embedding for the query
Similarity Search: Finds the most relevant document chunks using cosine similarity
Response Generation: Combines retrieved context with the query to generate accurate responses using Mistral's language model

Project Structure
├── app.py                 # Main Flask application
├── mistral_rag.py        # Standalone RAG implementation with FAISS
├── essay.txt             # Source document for RAG system
├── requirements.txt      # Python dependencies
├── vercel.json          # Vercel deployment configuration
├── .env                 # Environment variables (create this)
├── templates/
│   └── index.html       # Chat interface template
└── static/
    └── css/
        └── style.css    # Styling for the chat interface
Setup and Installation
Prerequisites

Python 3.7+
Mistral AI API key

Local Development

Clone the repository
bashgit clone <repository-url>
cd rag-chatbot

Create and activate virtual environment
bashpython -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

Install dependencies
bashpip install -r requirements.txt

Set up environment variables
Create a .env file in the project root:
MISTRAL_API_KEY=your_mistral_api_key_here

Add your source document
Replace essay.txt with your own text document, or use the provided sample essay about RAG systems.
Run the application
bashpython app.py
The application will be available at http://localhost:5001

Alternative: Standalone Script
You can also run the RAG system as a standalone script using mistral_rag.py:
bashpython mistral_rag.py
This version uses FAISS for vector similarity search and runs in the terminal.
Deployment
Vercel Deployment

Push your code to GitHub
Connect your GitHub repository to Vercel
Add environment variables in the Vercel dashboard:

MISTRAL_API_KEY: Your Mistral AI API key


Deploy!

The vercel.json configuration file is already set up for deployment.
Other Platforms
The application can be deployed on any platform that supports Python web applications (Heroku, Railway, PythonAnywhere, etc.). Make sure to:

Set the MISTRAL_API_KEY environment variable
Install dependencies from requirements.txt
Ensure essay.txt is included in your deployment

Environment Variables
VariableDescriptionRequiredMISTRAL_API_KEYYour Mistral AI API keyYes
Dependencies

Flask: Web framework for the chat interface
mistralai: Official Mistral AI Python client
numpy: Numerical computing for embeddings
python-dotenv: Environment variable management
flask-cors: Cross-origin resource sharing support
gunicorn: WSGI server for production deployment
faiss-cpu: Vector similarity search (for standalone script)

Usage

Start the application using the setup instructions above
Open your browser and navigate to the application URL
Type your question in the chat interface
The system will:

Find relevant chunks from the source document
Generate a response based on the retrieved context
Display the answer in the chat interface



Customization
Using Your Own Documents

Replace essay.txt with your own text document
Adjust the chunk_size variable in app.py if needed (default: 1000 characters)
Restart the application

Modifying the UI

Edit templates/index.html for HTML structure changes
Modify static/css/style.css for styling changes
The current design features a retro, terminal-inspired aesthetic

Adjusting RAG Parameters
In app.py, you can modify:

chunk_size: Size of document chunks (default: 1000)
k parameter in find_nearest_neighbors(): Number of similar chunks to retrieve (default: 3)
Mistral model: Change mistral-tiny to other available models

API Endpoints

GET /: Serves the chat interface
POST /ask: Processes questions and returns responses

Request body: {"question": "your question here"}
Response: {"answer": "generated response"}



Error Handling
The application includes comprehensive error handling for:

Missing API keys
File reading errors
Embedding generation failures
Model inference errors
Network connectivity issues

All errors are logged and user-friendly error messages are displayed in the chat interface.
Educational Use
This project is designed as a learning resource for understanding:

Retrieval-Augmented Generation (RAG) concepts
Vector embeddings and semantic search
Flask web application development
AI API integration
Modern web interface design

Contributing
This is an educational project, but contributions are welcome! Feel free to:

Report bugs or issues
Suggest improvements
Add new features
Improve documentation

License
This project is provided as a learning resource for students and workshop participants. You are free to:

Use this code for educational purposes
Modify and adapt it for your own projects
Share it with others for learning
Use it in workshops and tutorials

Contact
Feel free to reach out to Halim Madi with any questions or feedback!
Troubleshooting
Common Issues

"MISTRAL_API_KEY environment variable is not set"

Make sure you've created a .env file with your API key
Verify the API key is valid and active


"essay.txt file not found"

Ensure essay.txt exists in the project root directory
Check file permissions


Embedding creation errors

Verify your internet connection
Check if your Mistral API key has sufficient credits
Ensure the text chunks aren't too large


Slow response times

Consider reducing chunk size or number of retrieved chunks
Check your internet connection speed
Verify Mistral API service status



Getting Help
If you encounter issues:

Check the console logs for detailed error messages
Verify all dependencies are installed correctly
Ensure environment variables are set properly
Test with a simple question first
