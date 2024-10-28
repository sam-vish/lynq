# Product Requirements Document (PRD)

## Project Overview

### Product Name
**LynqAI**

### Purpose
LynqAI is a LinkedIn post generator that enables users to create engaging posts based on their existing content and profile information. By logging into their LinkedIn accounts, users can allow LynqAI to scrape their profile and recent posts. The application will then generate new post suggestions using a language model.

### Objectives
- To simplify content creation for LinkedIn users.
- To leverage existing user data for generating relevant and personalized posts.
- To enhance user engagement on LinkedIn by providing timely and contextually appropriate post suggestions.

## Key Features

1. **User Authentication**
   - Secure login system for users to input their LinkedIn credentials.
   - Use of HTTPS for secure data transmission.

2. **Data Scraping**
   - Automated scraping of user profile data and recent posts using Puppeteer.
   - Collection of relevant information to feed into the language model.

3. **Post Generation**
   - Integration with a language model (Hugging Face's Mistral LLM) to generate new LinkedIn posts based on scraped data and user-defined topics.
   - Customization options for users to specify the tone and style of the generated posts.

4. **User Interface**
   - A user-friendly web interface built with Next.js and React.
   - Options for users to view, edit, and post generated content directly to their LinkedIn profiles.

5. **Data Management**
   - Use of Supabase for user authentication, profile data storage, and management.
   - Compliance with data protection regulations and ethical data handling.

## Technical Stack

- **Frontend**: Next.js, React
- **Backend**: Node.js (using Next.js API routes)
- **Database**: Supabase
- **Web Scraping**: Puppeteer
- **Language Model**: Hugging Face's Mistral LLM
- **State Management**: React Context API
- **Deployment**: Vercel (for Next.js)

## User Flow

1. **User Registration/Login**
   - Users visit the LynqAI web application.
   - Users enter their LinkedIn credentials to log in.
   - The application authenticates and starts a session.

2. **Data Scraping**
   - Upon successful login, the application runs a Puppeteer script to scrape the user's LinkedIn profile and recent posts.
   - The scraped data is sent to the backend for processing.

3. **Post Generation**
   - Users input a topic for their new LinkedIn post.
   - The application uses the scraped data and user input to generate a new post using the Mistral LLM.
   - Users can preview the generated post and make any necessary edits.

## Requirements

### Functional Requirements
1. **User Authentication**
   - Ability to log in using LinkedIn credentials securely.
   
2. **Scraping Functionality**
   - Ability to scrape user profile information and recent posts from LinkedIn.

3. **Post Generation**
   - Integration with the LLM for generating new content based on user inputs and scraped data.

4. **User Interface**
   - Responsive design for ease of use on various devices.
   - User-friendly navigation to access features.

### Non-Functional Requirements
1. **Security**
   - Secure handling of user credentials and data.
   - Compliance with data protection regulations (e.g., GDPR).

2. **Performance**
   - Fast response times for scraping and post generation.
   - Scalable architecture to handle multiple users concurrently.

3. **Usability**
   - Intuitive user interface with clear instructions and feedback.


## Future Enhancements

- **Enhanced User Profiles**: Allow users to customize their profile information and preferences for post generation.
- **Analytics Dashboard**: Provide users with insights on engagement metrics for their LinkedIn posts.
- **Integration with Other Social Media**: Extend the platform to support post generation for other social media platforms.
