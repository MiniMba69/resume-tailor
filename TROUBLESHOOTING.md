# TROUBLESHOOTING GUIDE

## Common Issues and Solutions

### Installation Issues

#### "Python is not recognized as an internal or external command"
**Solution:**
1. Uninstall Python
2. Download Python again from https://www.python.org/downloads/
3. During installation, **CHECK THE BOX** that says "Add Python to PATH"
4. Complete installation
5. Restart your computer
6. Try again

#### "npm is not recognized"
**Solution:**
1. Uninstall Node.js
2. Download from https://nodejs.org/
3. Install with default settings
4. Restart your computer
5. Try again

#### "pip install fails with permission error"
**Windows Solution:**
- Run Command Prompt as Administrator
- Right-click Command Prompt → "Run as administrator"

**Mac/Linux Solution:**
```bash
sudo pip install -r requirements.txt
```

#### Virtual environment won't activate
**Windows:**
If you get an error about scripts being disabled:
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```
Then try activating again.

**Mac/Linux:**
Make sure you're using:
```bash
source venv/bin/activate
```
NOT `./venv/bin/activate`

---

### Backend Issues

#### "Module not found" errors
**Solution:**
1. Make sure virtual environment is activated (you should see `(venv)` in terminal)
2. Run:
   ```
   pip install -r requirements.txt
   ```

#### "Address already in use" error
**Solution:**
Another program is using port 5000. Either:
- Close other programs and try again
- Or change the port in `app.py`:
  ```python
  app.run(debug=True, host='0.0.0.0', port=5001)  # Changed to 5001
  ```
  Then update frontend `.env`:
  ```
  REACT_APP_API_URL=http://localhost:5001
  ```

#### Import errors with Google auth
**Solution:**
```
pip install --upgrade google-auth
pip install --upgrade google-auth-httplib2
```

---

### Frontend Issues

#### "npm install" takes forever or fails
**Solution:**
1. Delete `node_modules` folder and `package-lock.json` if they exist
2. Clear npm cache:
   ```
   npm cache clean --force
   ```
3. Try again:
   ```
   npm install
   ```

#### "Cannot find module" errors
**Solution:**
```
rm -rf node_modules package-lock.json  # Mac/Linux
# OR
del /s node_modules package-lock.json  # Windows

npm install
```

#### Page loads but shows blank screen
**Solution:**
1. Open browser console (F12)
2. Check for errors
3. Make sure `.env` file exists in frontend folder
4. Make sure backend is running

#### "Failed to fetch" or CORS errors
**Solution:**
1. Make sure backend is running on port 5000
2. Check that `REACT_APP_API_URL` in frontend `.env` matches backend URL
3. Clear browser cache (Ctrl+Shift+Delete)
4. Try a different browser

---

### Google OAuth Issues

#### "Invalid client ID"
**Solution:**
1. Double-check your Client ID in `.env` files
2. Make sure there are no extra spaces
3. Make sure you copied the entire ID
4. Verify it's the Client ID, not Client Secret

#### "Redirect URI mismatch"
**Solution:**
1. Go to Google Cloud Console
2. Go to your OAuth credentials
3. Under "Authorized redirect URIs", add:
   - `http://localhost:3000`
   - `http://localhost:3000/`
4. Under "Authorized JavaScript origins", add:
   - `http://localhost:3000`
5. Save changes
6. Wait 5 minutes for changes to propagate
7. Try again

#### Google login button doesn't appear
**Solution:**
1. Check browser console (F12) for errors
2. Make sure `REACT_APP_GOOGLE_CLIENT_ID` is set in frontend `.env`
3. Clear browser cache
4. Try incognito/private window

---

### API Issues

#### "Anthropic API error"
**Solution:**
1. Check your API key is correct
2. Check you have credits in your Anthropic account
3. Go to https://console.anthropic.com/ to check usage
4. Try generating a new API key

#### Resume processing fails
**Solution:**
1. Make sure resume is PDF or DOCX format
2. Make sure file isn't corrupted
3. Check file size (should be under 10MB)
4. Try a different resume file

#### Download doesn't start
**Solution:**
1. Check popup blocker settings
2. Allow downloads from localhost
3. Try a different browser
4. Check backend logs for errors

---

### File and Directory Issues

#### Can't find project folder
**Solution:**
Use `dir` (Windows) or `ls` (Mac/Linux) to list files:
```
dir          # Windows
ls           # Mac/Linux
```

Navigate up one folder:
```
cd ..
```

See current directory:
```
cd           # Windows
pwd          # Mac/Linux
```

#### .env file not working
**Solution:**
1. Make sure it's named exactly `.env` (not `.env.txt`)
2. Windows: Enable viewing file extensions
   - Open File Explorer
   - View tab → Check "File name extensions"
3. Make sure there are no quotes around values
4. Make sure there are no extra spaces

---

### Deployment Issues

#### Heroku deployment fails
**Solution:**
1. Make sure `Procfile` exists in backend folder
2. Make sure `gunicorn` is in requirements.txt
3. Check Heroku logs:
   ```
   heroku logs --tail
   ```

#### Environment variables not set on Heroku
**Solution:**
```
heroku config:set VARIABLE_NAME=value
```

Check what's set:
```
heroku config
```

---

## Still Having Issues?

### Steps to Debug:

1. **Check all files exist**
   - Backend: `app.py`, `requirements.txt`, `.env`
   - Frontend: `src/App.js`, `package.json`, `.env`

2. **Verify installations**
   ```
   python --version    # Should show 3.x
   node --version      # Should show v18+
   npm --version       # Should show 9+
   ```

3. **Check if services are running**
   - Backend should show: "Running on http://127.0.0.1:5000"
   - Frontend should show: "Compiled successfully!"

4. **Check ports**
   - Backend: http://localhost:5000/api/health should return JSON
   - Frontend: http://localhost:3000 should load the page

5. **Look at logs**
   - Backend terminal shows Python errors
   - Frontend terminal shows React errors
   - Browser console (F12) shows JavaScript errors

### Get Help:
- Copy the exact error message
- Note what step you were on
- Include your operating system
- Share relevant log output

### Emergency Reset:
If nothing works, start fresh:
1. Delete the project folder
2. Extract the files again
3. Follow QUICKSTART.md exactly
4. Don't skip any steps!
