🏋️ AI Fitness Assistant
Welcome to the AI Fitness Assistant — a personalized AI-powered app that generates customized fitness and diet plans based on your details and goals using Google Gemini AI!
Built with Streamlit, Google Generative AI, and Ngrok for easy sharing.

🚀 Features
📜 Personalized diet and workout plans based on user input.

🧠 Powered by Google's Gemini 1.5 Pro model.

📈 Saves user details like name, age, weight, height, gender, and goals.

🌄 Custom background image for enhanced UI.

🌐 Share your app with anyone using an Ngrok public URL.

🛠️ Tech Stack
Python

Streamlit - Frontend web app

Google Generative AI - Backend intelligence

Pyngrok - Exposing local app online

Pandas - Saving user logs

📦 Installation
First, install the required libraries:

bash
Copy
Edit
!pip install streamlit
!pip install google-generativeai
!pip install pyngrok
!pip install -q google-generativeai
📁 Project Structure
bash
Copy
Edit
├── app.py          # Streamlit Frontend
├── backend.py      # Handles AI interaction and user data saving
├── fitness.jpg     # Background image
├── fitness_logs.csv # User data logs (auto-generated)
├── README.md       # Project Documentation
⚙️ Setup Instructions
Upload your background image
Upload a fitness-themed image (e.g., fitness.jpg) to your working directory.

Create Files
Your code already writes backend.py and app.py automatically.

Set Ngrok Authentication Token

You can get your Ngrok Auth Token from Ngrok Dashboard.

Start the Server

python
Copy
Edit
import os
import streamlit as st
from pyngrok import ngrok
from google.colab import userdata

auth_token = userdata.get('nagrok')  # Ngrok token securely stored
ngrok.kill()
ngrok.set_auth_token(auth_token)

public_url = ngrok.connect(8501).public_url
print(f"🚀 Public URL: {public_url}")

!streamlit run --server.port 8501 app.py
Access the App
Copy and open the public URL printed in the output.

🧩 How It Works
User fills basic information (name, age, height, weight, gender, activity level, goal).

AI generates a detailed fitness and diet plan.

User data is saved into a CSV log file for analysis.

Everything happens inside a clean and visually appealing web interface.

📸 Screenshots

Home Page	Result Page
(Replace with real screenshots if you want.)

❗ Important Notes
API Key Security: You have hardcoded your Gemini API key inside backend.py. Avoid this for production apps — use environment variables or secret managers.

Ngrok Token: Your nagrok token must be stored in Colab's userdata.

📚 References
Streamlit Documentation

Google Generative AI Python SDK

Ngrok Documentation

✨ Future Improvements
Add user authentication (login/signup).

Store logs in Google Sheets or a database.

Add downloadable PDF reports for generated fitness plans.

Enhance UI using Streamlit components (e.g., animations, charts).
