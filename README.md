# Resume Tailor - 100% FREE Setup Guide

## 🎉 This Version is COMPLETELY FREE!

No credit card needed anywhere! We use:
- ✅ Google OAuth (FREE)
- ✅ Google Gemini API (FREE - 60 requests/minute)
- ✅ Everything else is open source and FREE

---

## STEP 1: Install Required Software (FREE)

### 1.1 Install Python
1. Go to https://www.python.org/downloads/
2. Download Python 3.11 or later
3. **IMPORTANT**: During installation, check "Add Python to PATH"
4. Click "Install Now"
5. Verify: Open Command Prompt and type `python --version`

### 1.2 Install Node.js
1. Go to https://nodejs.org/
2. Download the LTS version
3. Install with default settings
4. Verify: Open Command Prompt and type `node --version`

### 1.3 Restart Your Computer
**This is important!**

---

## STEP 2: Set Up the Project

### 2.1 Extract Project Files
1. Extract the project folder to `C:\Users\YourName\resume-tailor`
2. Open Command Prompt
3. Navigate to project:
   ```
   cd C:\Users\YourName\resume-tailor
   ```

### 2.2 Set Up Backend
```
cd backend
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### 2.3 Set Up Frontend
Open a NEW Command Prompt:
```
cd C:\Users\YourName\resume-tailor\frontend
npm install
```

---

## STEP 3: Get Your FREE API Keys

### 3.1 Google OAuth (FREE - No Card)

1. Go to https://console.cloud.google.com/
2. Sign in with Google
3. Create new project: "Resume Tailor"
4. Go to "APIs & Services" → "Credentials"
5. Create OAuth consent screen:
   - Choose "External"
   - App name: Resume Tailor
   - Your email for support
   - Save
6. Create OAuth Client ID:
   - Type: Web application
   - Name: Resume Tailor Web
   - Authorized JavaScript origins: `http://localhost:3000`
   - Authorized redirect URIs: `http://localhost:3000`
   - Create
7. **SAVE YOUR:**
   - Client ID
   - Client Secret

### 3.2 Google Gemini API Key (FREE - No Card!)

1. Go to: **https://makersuite.google.com/app/apikey**
   (or https://aistudio.google.com/app/apikey)

2. Sign in with your Google account

3. Click **"Create API Key"**

4. Select **"Create API key in new project"** or use existing project

5. **Copy the API key** (starts with "AIza...")

6. **DONE!** No credit card, no payment - completely FREE!

**FREE Limits:**
- 60 requests per minute
- More than enough for personal use!

---

## STEP 4: Configure Environment Variables

### 4.1 Backend .env File

1. Go to `backend` folder
2. Copy `.env.template` and rename to `.env`
3. Open `.env` in Notepad
4. Fill in:
   ```
   GOOGLE_CLIENT_ID=your_google_client_id_here
   GOOGLE_CLIENT_SECRET=your_google_client_secret_here
   GEMINI_API_KEY=your_gemini_api_key_here
   SECRET_KEY=anyrandomtext123456
   ```
5. Save

### 4.2 Frontend .env File

1. Go to `frontend` folder
2. Copy `.env.template` and rename to `.env`
3. Open `.env` in Notepad
4. Fill in:
   ```
   REACT_APP_GOOGLE_CLIENT_ID=your_google_client_id_here
   REACT_APP_API_URL=http://localhost:5000
   ```
5. Save

---

## STEP 5: Run the Application

### 5.1 Start Backend
In Command Prompt (with venv activated):
```
cd backend
venv\Scripts\activate
python app.py
```
Should show: "Running on http://127.0.0.1:5000"

### 5.2 Start Frontend
In NEW Command Prompt:
```
cd frontend
npm start
```
Browser opens automatically to http://localhost:3000

---

## STEP 6: Test It!

1. Click "Sign in with Google"
2. Upload a resume (PDF or DOCX)
3. Paste a job description
4. Click "Tailor My Resume"
5. Download your optimized resume!

---

## 💡 What's Different from Paid Version?

### This FREE Version (Google Gemini):
- ✅ Completely FREE
- ✅ No credit card needed
- ✅ 60 requests/minute (plenty!)
- ✅ Good quality AI
- ✅ Perfect for personal use

### Paid Version (Anthropic Claude):
- 💰 Requires credit card ($5 free credit)
- ⚡ Slightly better quality
- 🚀 Faster processing
- 💼 Better for high-volume use

**For personal use, the FREE version is perfect!**

---

## Troubleshooting

### "GEMINI_API_KEY not found"
- Make sure you created `.env` file (not `.env.txt`)
- Check that you pasted the Gemini API key

### "Invalid API key"
- Get a new key from https://makersuite.google.com/app/apikey
- Make sure you copied the entire key

### Other Issues
- Check TROUBLESHOOTING.md in project folder
- Make sure both backend and frontend are running

---

## Cost Breakdown

| Item | Cost |
|------|------|
| Python | FREE |
| Node.js | FREE |
| Google OAuth | FREE |
| Google Gemini API | FREE |
| **TOTAL** | **₹0 / $0** |

---

## Next Steps

1. **Test locally** - make sure everything works
2. **Customize** - change colors, add features
3. **Deploy** (optional) - make it live on internet
4. **Share** - help friends tailor their resumes!

---

## Need Help?

- Read TROUBLESHOOTING.md
- All tools are FREE
- No hidden costs
- No credit card needed anywhere!

**Happy resume tailoring! 🎉**
