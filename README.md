# RedditWork
The following repo contains- 1. A Colab notebook with the code to scrap,parse and generate the user persona as specified in the prompts. 2. .txt files for the sampled user. 
projectparse/
├── RedditPersonaGenerator.ipynb    
├── Hungry-Move-6603_persona.txt     
├── kojied_persona.txt              
├── README.md                       

This project uses a Google Colab notebook to generate structured personas from any public Reddit profile. It uses a pre-trained LLM like Falcon (or Mistral) to analyze Reddit comments and posts, and outputs a UX-style persona in `.txt` format — with citations.

---

##  Features

-  Built in a single, ready-to-run Colab notebook
- Scrapes Reddit user posts + comments via PRAW
-  Feeds that data to Falcon/Mistral for persona generation
-  Cites each trait with exact Reddit comments/posts
-  Outputs a clean persona text file downloadable in Colab

---

## Quick Start

[ Open in Google Colab](https://colab.research.google.com/github/your-username/projectparse/blob/main/RedditPersonaGenerator.ipynb)

### 1. Setup Reddit API keys

Go to: https://www.reddit.com/prefs/apps  
Create a script-type app. Then fill in the notebook like:

```python
REDDIT_CLIENT_ID = "your_client_id"
REDDIT_SECRET = "your_client_secret"
REDDIT_USER_AGENT = "projectparse"
2. Hugging Face Token (Optional)
If you're using Mistral, Zephyr, or other gated models:


from huggingface_hub import login
login("your_HF_access_token")
How It Works
Enter a Reddit profile URL like:


https://www.reddit.com/user/Hungry-Move-6603/
The notebook will:

Extract the username

Scrape up to 100 comments/posts

Format the data

Generate a structured persona with citations

Save it as a .txt file

You can download the output with:


from google.colab import files
files.download("Hungry-Move-6603_persona.txt")

 Output Sample Format
graphql
Copy
Edit
##  Identity  
- Male, 25–35, lives in Lucknow, works in business or consultancy  
  (Based on comment: "[lucknow] I shifted to LKO in Dec 24 for business purposes.")

##  Personality  
- Observant, sarcastic, outspoken  
  (Based on comment: "[nagpur] Cops keep a civ around to discuss bribes.")
...
🗃 Files in This Repo
File	Description
RedditPersonaGenerator.ipynb	Main Colab notebook
Hungry-Move-6603_persona.txt	Sample generated persona
README.md	This file

## Since the .txt file is just plain text, using PIL libraries I've converted it to be UX friendly like given in the prompt (Lucas). 
