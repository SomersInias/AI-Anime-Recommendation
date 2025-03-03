# Anime Recommendation Chatbot App

This project is a showcase application demonstrating an anime recommendation chatbot built using collaborative filtering, content-based filtering, and hybrid approaches. It leverages models built with libraries like `scikit-surprise` and `scikit-learn`, and integrates with `ChatGPT`, `LangChain`, and `Streamlit` for an interactive user experience. The primary goal is to provide anime recommendations based on user preferences and anime similarities, delivered through a conversational chatbot interface.

## Project Overview

### Features
- **Collaborative Filtering Recommendations**: Provides personalized anime recommendations based on user ratings using a Singular Value Decomposition (SVD) model.
- **Content-Based Recommendations**: Suggests anime similar to a given anime title using TF-IDF vectorization and cosine similarity.
- **Hybrid Recommendation System**: Combines collaborative and content-based filtering to generate more nuanced and relevant recommendations.
- **Smart Anime Title Matching**: Employs fuzzy matching and optionally Language Model (LLM) assistance to accurately identify anime titles, even with typos or variations.
- **Interactive Chatbot Interface**: Utilizes Streamlit for a user-friendly chat interface to interact with the recommendation system.
- **User Profile Creation (Simulated)**: Allows users to simulate creating a new user profile by providing ratings for a few anime, influencing collaborative filtering recommendations.
- **Intent-Based Conversation**: Uses ChatGPT and LangChain to understand user intent (user-based, anime-based, hybrid recommendations, new user creation) and guide the conversation.

## **How It Works**

This application provides an interactive chatbot interface using **Streamlit** to get anime recommendations. It leverages different recommendation strategies and smart title matching to provide relevant suggestions. Here's a breakdown of the workflow:

1. **User Interaction via Chatbot**
   - Users interact with the system through a Streamlit chat interface, asking for recommendations or specifying their preferences.

2. **Intent Recognition**
   - The chatbot uses **ChatGPT and LangChain** to understand the user's intent. It classifies requests into categories like:
     - **User-Based Recommendations**: Requests for recommendations based on a user ID.
     - **Anime-Based Recommendations**: Requests for recommendations similar to a specific anime title.
     - **Hybrid Recommendations**: Requests combining user preferences and a specific anime title.
     - **New User Creation**: Initiates the process of creating a new simulated user profile.
     - **General Chat**: Handling general conversation and clarifying user requests.

3. **Parameter Extraction**
   - Based on the identified intent, the system extracts relevant parameters from the user's input, such as:
     - **User ID**:  Extracted from user messages when requesting user-based or hybrid recommendations.
     - **Anime Title**: Extracted when requesting anime-based or hybrid recommendations.
     - **Anime Ratings**: When creating a new user, the system prompts for and parses anime titles and ratings provided by the user.

4. **Recommendation Generation**
   - **Collaborative Filtering (SVD)**: For user-based recommendations, the pre-trained SVD model predicts ratings for anime the user hasn't seen and recommends the highest-rated ones.
   - **Content-Based Filtering (TF-IDF & Cosine Similarity)**: For anime-based recommendations, the system uses TF-IDF to vectorize anime descriptions and cosine similarity to find anime similar to the user's chosen title.
   - **Hybrid Approach**: Combines scores from both collaborative and content-based methods to generate a blended set of recommendations.

5. **Smart Title Matching**
   - **Fuzzy Matching**:  Uses `fuzzywuzzy` to find close matches for anime titles entered by the user, handling minor typos and variations.
   - **LLM Title Resolution (Optional)**:  For more ambiguous titles, the system can optionally use ChatGPT to resolve the title to its canonical or most common name.

6. **Display Results**
   - The chatbot displays the recommendations in a clear, user-friendly format within the Streamlit app, listing anime names and relevant details such as predicted ratings or genre information, depending on the recommendation type.

This workflow enables an engaging and effective way to discover new anime, leveraging AI-powered recommendation techniques and natural language interaction.

## Usage

To run the Anime Recommendation Chatbot App:

1. **Google Colab Environment**: run the [anime_recommendation_app notebook](https://github.com/SomersInias/AI-Anime-Recommendation/blob/main/notebooks/anime_recommendation_app.ipynb) script in a Google Colab environment, 
2. Provide API keys for Open AI and ngrok
3. **Upload Model and Data Files**: Ensure you have uploaded the following files to your Google Drive or Google Colab environment. The models can be trained with the code provided in this [notebook](https://github.com/SomersInias/AI-Anime-Recommendation/blob/main/notebooks/anime_recommendation.ipynb)
    - `svd_model.joblib`
    - `tfidf_vectorizer.joblib`
    - `cosine_sim_matrix.joblib`
    - `indices.joblib`
4. **Run the Streamlit App**: Run the full notebook script
5. **Access via Public URL**: Open the `Streamlit App:` URL provided by ngrok in your web browser to interact with the Anime Recommendation Chatbot.

**Interacting with the Chatbot:**

- You can ask for recommendations in natural language, such as:
    - "Recommend me an anime for user 73517"
    - "What anime is similar to Naruto?"
    - "Hybrid recommendations for user 5856 based on Attack on Titan"
    - "Create a new user" (and then follow the prompts to provide anime ratings)

## Demo

Here are some short demo videos showcasing the project (Note: These are GIFs with a low frame rate.) 

![2025-03-0314-44-21-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/62299963-f47d-4f8a-ac33-53be30e43c7c)

![2025-03-0314-45-14-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/adb36a40-54c9-411f-aff2-e67aab47e4ec)

![2025-03-0314-46-22-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/85e1b702-a542-4aa3-8b42-2ae56e05e78b)

![2025-03-0314-48-02-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/3cd3ed1d-995c-43de-986a-a65b04a15559)






