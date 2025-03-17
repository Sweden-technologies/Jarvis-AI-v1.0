# Jarvis AI Project Structure

This document outlines the organization of the Jarvis AI codebase to help developers understand the system architecture.

## Directory Structure

```
Jarvis-AI-v1.0/
├── Backend/                 # Backend processing modules
│   ├── Automation.py        # System automation capabilities
│   ├── Chatbot.py           # Conversational AI functionality
│   ├── ImageGeneration.py   # Image generation capabilities
│   ├── Model.py             # Decision-making module
│   ├── RealtimeSearchEngine.py # Web search integration
│   ├── SpeechToText.py      # Speech recognition
│   └── TextToSpeech.py      # Text-to-speech synthesis
│
├── Frontend/                # User interface components
│   ├── Graphics/            # Visual assets
│   └── GUI.py               # Graphical user interface
│
├── Data/                    # Data storage
│   ├── ChatLog.json         # Conversation history
│   └── speech.mp3           # Generated speech audio
│
├── Files/                   # Application files
│   ├── Database.data        # User data storage
│   ├── ImageGeneration.data # Image generation parameters
│   ├── Mic.data             # Microphone status
│   ├── Responses.data       # Response templates
│   └── Status.data          # Assistant status
│
├── docs/                    # Documentation
│   ├── future-version-planning.md # Future roadmap
│   └── project-structure.md # This file
│
├── .env.example             # Environment variables template
├── Main.py                  # Application entry point
├── README.md                # Project overview
└── Requirements.txt         # Dependencies
```

## Core Components

### Main.py
The entry point of the application that initializes all components and manages the main execution flow. It coordinates between frontend and backend modules.

### Backend Modules

#### TextToSpeech.py
Handles the conversion of text responses to spoken audio using edge-tts. Manages audio playback and provides functions for handling long text responses.

#### SpeechToText.py
Converts user's spoken input to text using speech recognition. Provides the primary input method for interacting with Jarvis.

#### Chatbot.py
Implements the conversational AI capabilities using language models. Processes user queries and generates contextually relevant responses.

#### RealtimeSearchEngine.py
Provides up-to-date information by searching the web. Integrates with Google search and processes results for natural language responses.

#### Model.py
Contains the decision-making logic (FirstLayerDMM) that routes user queries to appropriate handling modules based on intent recognition.

#### Automation.py
Handles system automation tasks like opening applications, playing media, and controlling system functions.

#### ImageGeneration.py
Provides capabilities for generating images based on text descriptions.

### Frontend Modules

#### GUI.py
Implements the graphical user interface using PyQt5. Displays conversation history, assistant status, and provides visual feedback.

## Data Flow

1. User speaks to Jarvis (or types input)
2. SpeechToText converts audio to text
3. Model analyzes the query and determines the appropriate action
4. Based on the decision:
   - Chatbot generates a conversational response
   - RealtimeSearchEngine retrieves information from the web
   - Automation executes system commands
   - ImageGeneration creates images
5. The response is displayed in the GUI
6. TextToSpeech converts the response to spoken audio
7. The conversation is saved to ChatLog.json

## Extension Points

The modular architecture allows for easy extension of Jarvis's capabilities:

1. Add new backend modules for additional functionality
2. Enhance existing modules with improved algorithms
3. Extend the GUI with new visualization features
4. Add new automation capabilities
5. Integrate additional API services

## Future Development

See the [future-version-planning.md](future-version-planning.md) document for detailed information about planned enhancements and architectural changes for future versions of Jarvis AI.