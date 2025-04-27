# 🏋️ AI Fitness Assistant
**An AI-powered fitness and diet recommendation web app built with Streamlit, Google Gemini AI, and PyNgrok.**

## 📜 Project Description
The AI Fitness Assistant provides personalized fitness plans, diet suggestions, and workout advice based on the user's inputs like age, weight, goal, and activity level.  
It uses the power of Google Gemini (Generative AI) to generate customized recommendations instantly.

## 🚀 Features
- 🎯 **Personalized Fitness Plan** based on user profile
- 🍎 **Diet Plan and Meal Timing Recommendations**
- 🏋️ **Exercise Routine** based on user fitness goal
- 📊 **Ideal Weight Range Suggestions**
- 🚫 **Common Mistakes and Best Practices**
- 📸 **Beautiful UI** with Custom Background Image
- 📄 **User Data Storage** in `fitness_logs.csv`
- 🌎 **Ngrok Integration** to generate a public link

## 🛠️ Technology Stack
- **Python 3**
- **Streamlit**
- **Google Generative AI (Gemini API)**
- **PyNgrok**
- **Google Colab** (for development and hosting)

## 📦 Installation & Setup Instructions

1. **Install Required Packages**
    ```bash
    !pip install streamlit
    !pip install google-generativeai
    !pip install pyngrok
    !pip install -q google-generativeai
    ```

2. **Upload Background Image**
    ```python
    from google.colab import files
    uploaded = files.upload()  # Upload your fitness.jpg image
    ```

3. **Create `backend.py`**
    - Contains:
      - Google Gemini API configuration
      - `get_fitness_advice()` function for AI interaction
      - `save_user_data()` function to log user details

4. **Create `app.py`**
    - Streamlit app with:
      - User input forms
      - AI fitness advice display
      - Background image setup

5. **Setup Ngrok**
    ```python
    from pyngrok import ngrok
    from google.colab import userdata

    ngrok.kill()  # Kill old tunnels
    auth_token = userdata.get('nagrok')  # Fetch your stored ngrok token
    ngrok.set_auth_token(auth_token)
    public_url = ngrok.connect(8501).public_url
    print(f"🚀 Public URL: {public_url}")
    ```

6. **Run the Streamlit App**
    ```bash
    !streamlit run --server.port 8501 app.py
    ```


## ⚡ How it Works
- User provides details like Name, Age, Weight, Height, Gender, Activity Level, and Fitness Goal.
- App sends this data to **Google Gemini AI**.
- Gemini generates a personalized:
  - Diet Plan
  - Exercise Plan
  - Ideal Weight Suggestions
  - Common Mistakes to Avoid
- Output is beautifully displayed on the page and user data is saved.

## ⚠️ Important Notes
- 🔑 Set your **Google Gemini API Key** directly inside `backend.py`.
- 🖼️ Make sure the background image file (`fitness.jpg`) is uploaded properly.
- 🔗 Ensure Ngrok Auth Token is stored securely (for `userdata.get()` to work).
- 🧹 Always **kill previous ngrok tunnels** before creating a new one.

## 📸 Demo (Optional)
> *![Uploading Screenshot 2025-04-08 195555.png…]()
*


