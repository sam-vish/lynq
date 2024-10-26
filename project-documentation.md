# AI Social Media Post Generator Documentation

## 1. Project Overview
This conversational AI-driven social media post generator helps users create viral and engaging posts for multiple platforms like LinkedIn, Twitter, Facebook, and Instagram. The user can connect to these platforms through a navigation drawer and engage in voice-based conversations with AI to create posts. Once the conversation ends, the AI will generate the post based on the user's commands.

This project uses cutting-edge AI models for both text and image generation, Firebase for user authentication and data storage, and a modern, seamless UI/UX interface to ensure an intuitive experience for users.

## 2. Basic Functionalities
* **User Authentication**: Google-based login/signup using Firebase Authentication
* **Platform Connection**: Users can connect their social media platforms (LinkedIn, Twitter, etc.) directly from the navigation drawer
* **Conversational Input**: Users interact with AI via chat or voice (audio input)
* **Post Generation**: The AI generates social media posts based on the conversation
* **Conversation History**: Users can view and manage previous conversations stored in Firebase Firestore
* **Post Generation Commands**: After finishing the conversation, the user commands AI to generate the post, and the AI generates both text and accompanying images

## 3. Core Functionalities

### Social Media Platform Integration
* The navigation drawer features buttons like 'Connect with LinkedIn', 'Connect with Twitter', etc., for seamless platform integration
* Once connected, the AI will tailor the post generation for that specific platform

### Voice Input for Chat
* Users can provide input to the AI through voice (audio) in the chat
* This is implemented using Web Speech API or other libraries like React Speech Recognition to capture voice and convert it to text

### AI Post & Image Generation
* Mistral model is used for generating viral text posts
* Flux is used to generate custom images for the post

### Post Generation Command
* After the conversation ends, the AI generates a post when the user commands it (e.g., "Create the post")
* The AI will analyze the collected data from the conversation and generate the appropriate post

### Firestore Integration
* Conversations (text/audio) and generated images are stored in Firestore
* Users can view, rename, or delete conversations in the navigation drawer

## 4. App/File Structure

```
/root
│── /frontend
│   ├── /components
│   │   ├── Header.js              # Top bar with logo and logout button
│   │   ├── Sidebar.js             # Navigation drawer with 'Connect with LinkedIn', 'Connect with Twitter', etc.
│   │   ├── ChatBox.js             # Main chat interface with text/audio input for conversing with AI
│   │   ├── Cards.js               # Cards for conversation suggestions
│   │   ├── ImageCard.js           # Displays AI-generated images
│   │   └── AudioInput.js          # Component for capturing audio input
│   ├── /pages
│   │   ├── Home.js                # Homepage with chat interface
│   │   ├── Login.js               # Google Auth login page
│   │   ├── Pricing.js             # Pricing page for LynqAI Plus
│   │   └── Signup.js              # Signup page
│   └── App.js                     # Main frontend application file
│
├── /backend
│   ├── /models
│   │   ├── postGenerator.js       # Handles Mistral API for post generation
│   │   ├── imageGenerator.js      # Handles Flux API for image generation
│   ├── /controllers
│   │   ├── authController.js      # Manages Firebase Authentication
│   │   ├── chatController.js      # Handles conversation storage in Firestore
│   └── /routes
│       ├── authRoutes.js          # Authentication routes
│       ├── chatRoutes.js          # Chat-related routes
│       └── postRoutes.js          # Routes for post and image generation
│
├── firebase-config.js             # Firebase configuration and initialization
└── .env                           # Environment variables (API keys, Firebase credentials)
```

## 5. Documentation

### Firebase Integration

#### Authentication
* Google Auth for sign-up/login using Firebase. Refer to authController.js
* Firestore stores chat conversations (including audio) and images

#### Storing Audio Data
* Convert audio input to text for post generation using Web Speech API or React Speech Recognition
* Store audio files in Firestore under the same conversation thread, allowing AI to retrieve context

### Post Generation
* AI post generation logic is in postGenerator.js (text generation) and imageGenerator.js (image generation)
* The AI analyzes user conversations (audio/text) and responds with suggestions or post generation

### Key Libraries & Dependencies
* Firebase: For authentication and Firestore database
* React Speech Recognition: For voice input
* Hugging Face Inference API: For AI model integration (Mistral and Flux)
* Tailwind CSS: For modern UI styling
* Framer Motion: For simple animations (fade-in, fade-out, sweep)

## 6. Pages & Components Overview

### /frontend/pages/Home.js
* This will handle the chat interface where users can converse with the AI
* Include both text and voice inputs here

### /frontend/components/Sidebar.js
* This navigation drawer contains buttons like 'Connect with LinkedIn', 'Connect with Twitter', etc.
* When clicked, users are asked for permissions, and the platform will be connected to generate posts for that specific platform

### /frontend/components/AudioInput.js
* Captures audio inputs and converts them to text
* Use React Speech Recognition or Web Speech API to handle this

## 7. Conclusion
This modified project version enhances user interaction with the addition of audio input, giving users the ability to speak to the AI for post creation. Additionally, the social media integration in the navigation drawer provides a more seamless way for users to connect with various platforms. Storing conversations in Firestore ensures that previous interactions and generated images are easily accessible and modifiable. This structure ensures a clean, scalable, and user-friendly app with powerful AI-driven post generation.
