# 🤖 AI Blog Assistant Setup Guide

## Features Implemented

Your UniVoices blogging platform now has AI-powered writing assistance:

1. **✨ Content Enhancement** - AI fixes grammar, improves clarity, and adds insights to your blog content
2. **📝 Title Suggestions** - AI generates 5 creative, SEO-friendly blog title options
3. **🏷️ Tag Suggestions** - AI suggests relevant tags based on your blog content

## Setup Instructions

### Step 1: Install Dependencies

**Backend:**
```bash
cd univoices-backend
npm install openai node-fetch@2
```

**Frontend:**
```bash
cd univoices-frontend
npm install
```

### Step 2: Configure Environment Variables

Create/update `.env` file in `univoices-backend/`:

```env
DB_LOCATION=mongodb+srv://YOUR_MONGODB_URI
AWS_REGION=us-east-1
AWS_ACCESS_KEY=YOUR_AWS_ACCESS_KEY
AWS_SECRET_ACCESS_KEY=YOUR_AWS_SECRET_ACCESS_KEY
AWS_BUCKET_NAME=YOUR_BUCKET_NAME
SECRET_ACCESS_KEY=YOUR_SECRET_KEY
OPENAI_API_KEY=sk-your-openai-api-key-here
```

**To get OpenAI API Key:**
1. Go to https://platform.openai.com/api-keys
2. Sign up or login with your OpenAI account
3. Create a new API key
4. Paste it in the `.env` file

### Step 3: Start Your Application

**Terminal 1 - Backend:**
```bash
cd univoices-backend
npm start
```

**Terminal 2 - Frontend:**
```bash
cd univoices-frontend
npm run dev
```

## How to Use

### In the Blog Editor

1. **Enhance Content**: Click the "✨ Enhance" button
   - AI will improve your written content with better grammar, clarity, and insights
   - The enhanced content will replace your original text

2. **Suggest Titles**: Click the "📝 Title" button
   - AI generates 5 creative blog title suggestions
   - Click any suggestion to use it as your blog title

3. **Suggest Tags**: Click the "🏷️ Tags" button
   - AI analyzes your content and suggests relevant tags
   - Click any tag with the "+" to add it to your blog

### Before Publishing

- Use "🤖 AI Suggest" button in the Publish form to get tag suggestions
- All AI features can be used multiple times to refine your content

## API Endpoints

The following endpoints are now available on your backend:

### POST `/enhance-content`
```json
{
  "content": "Your blog content text here"
}
```
Returns enhanced content with improved grammar and clarity.

### POST `/suggest-title`
```json
{
  "content": "Your blog content",
  "existingTitle": "Optional current title"
}
```
Returns array of 5 suggested titles.

### POST `/suggest-tags`
```json
{
  "content": "Your blog content",
  "title": "Your blog title"
}
```
Returns array of suggested tags.

## Troubleshooting

### "API key is invalid" Error
- Check that your `OPENAI_API_KEY` in `.env` is correct
- Make sure the key has no extra spaces
- Verify the key is active on https://platform.openai.com/api-keys

### "Failed to enhance content" Error
- Ensure you have written some content in the editor
- Check backend logs for detailed error message
- Verify your internet connection

### AI features not appearing
- Make sure backend server is running (`npm start`)
- Check browser console for network errors
- Refresh the page

## Pricing

OpenAI API usage costs money. Pricing is based on tokens:
- GPT-3.5-turbo: ~$0.001 per 1000 tokens
- Each feature use will cost a small amount

**Monthly estimate for heavy usage:** ~$10-20

To monitor usage:
1. Go to https://platform.openai.com/account/billing/overview
2. Set up usage limits to prevent unexpected charges

## Feature Customization

You can modify the AI behavior by editing the backend endpoints:

**File:** `univoices-backend/server.js`

Look for the `// ===== AI ENDPOINTS =====` section to adjust:
- Temperature (creativity level)
- Max tokens (response length)
- Model (currently using gpt-3.5-turbo)

## Next Steps

1. Configure OpenAI API key
2. Start backend and frontend servers
3. Navigate to blog editor and test the AI features
4. Monitor OpenAI usage to manage costs

Enjoy your AI-powered writing assistant! 🚀
