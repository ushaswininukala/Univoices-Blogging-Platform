# ⚡ Quick Start - AI Blog Assistant

## 5-Minute Setup

### 1️⃣ Get OpenAI API Key (2 min)
```
1. Visit: https://platform.openai.com/api-keys
2. Click "Create new secret key"
3. Copy the key (save it somewhere safe!)
```

### 2️⃣ Configure Backend (1 min)
```bash
# Create/edit .env in univoices-backend/
OPENAI_API_KEY=sk-your-key-here
```

### 3️⃣ Install Dependencies (1 min)
```bash
cd univoices-backend
npm install node-fetch@2
```

### 4️⃣ Start Servers (1 min)
```bash
# Terminal 1
cd univoices-backend
npm start

# Terminal 2 (new terminal)
cd univoices-frontend
npm run dev
```

## Done! 🎉

Go to `http://localhost:5173` and start writing blogs with AI assistance!

---

## Using AI Features

In the **Blog Editor**:
- ✨ **Enhance** - Click to improve your content
- 📝 **Title** - Get 5 title suggestions
- 🏷️ **Tags** - Get auto-generated tags

In the **Publish Form**:
- 🤖 **AI Suggest** - Get tag suggestions before publishing

---

## Troubleshooting

❌ **"Invalid API key"**
→ Check your OpenAI API key in `.env`, make sure no extra spaces

❌ **"Failed to enhance content"**
→ Write some content first, then try again

❌ **Buttons not working**
→ Restart backend: `npm start`

---

## Cost Warning ⚠️

Each AI call costs ~$0.01-0.05 USD. Monitor usage:
https://platform.openai.com/account/billing/usage

Set spending limits:
https://platform.openai.com/account/billing/limits
