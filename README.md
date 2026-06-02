# 🎤 UniVoices - AI-Powered Blogging Platform

A full-stack blogging platform with AI-powered writing assistance, built with React.js, Node.js, Express.js, MongoDB, and OpenAI API integration.

## ✨ Features

- **📝 Blog Management** - Create, edit, delete, and manage blog posts
- **🤖 AI Writing Assistant**
  - Content Enhancement - Improve grammar, clarity, and expand your writing
  - Title Suggestions - Generate 5 SEO-optimized title options
  - Tag Suggestions - Auto-generate relevant tags from content
- **👥 User Authentication** - Secure JWT-based authentication with Firebase
- **💬 Comments & Discussions** - Interactive commenting system
- **🔔 Notifications** - Real-time notification system
- **🔍 Search & Filter** - Powerful search with pagination
- **☁️ Cloud Storage** - AWS S3 integration for image uploads
- **📱 Responsive Design** - Mobile-friendly UI with Tailwind CSS

## 🛠️ Tech Stack

### Frontend
- **React.js** - UI library
- **Vite** - Build tool
- **EditorJS** - Rich text editor
- **Tailwind CSS** - Styling
- **Framer Motion** - Animations
- **Axios** - HTTP client
- **React Hot Toast** - Notifications
- **Firebase** - Authentication

### Backend
- **Node.js** - Runtime
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM
- **Firebase Admin SDK** - User management
- **JWT** - Authentication
- **bcrypt** - Password hashing
- **AWS SDK** - Cloud storage
- **OpenAI API** - AI features
- **CORS** - Cross-origin requests

## 📦 Project Structure

```
univoices/
├── univoices-frontend/          # React frontend
│   ├── src/
│   │   ├── components/          # Reusable components
│   │   ├── pages/               # Page components
│   │   ├── common/              # Utility functions & hooks
│   │   ├── imgs/                # Images
│   │   └── App.jsx
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
│
├── univoices-backend/           # Express backend
│   ├── server.js                # Main server file
│   ├── routes/
│   │   └── ai.routes.js         # AI endpoints
│   ├── Schema/                  # MongoDB schemas
│   │   ├── User.js
│   │   ├── Blog.js
│   │   ├── Comment.js
│   │   └── Notification.js
│   ├── package.json
│   ├── .env.example
│   └── .gitignore
│
├── AI_SETUP_GUIDE.md            # AI setup instructions
├── IMPLEMENTATION_SUMMARY.md    # Feature documentation
├── QUICK_START.md               # Quick setup guide
└── README.md                    # This file
```

## 🚀 Quick Start

### Prerequisites
- Node.js (v14+)
- MongoDB Atlas account
- Firebase project
- AWS S3 bucket
- OpenAI API key

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/univoices.git
cd univoices
```

**2. Backend Setup**
```bash
cd univoices-backend
npm install

# Create .env file
cp .env.example .env
# Add your credentials to .env
```

**3. Frontend Setup**
```bash
cd ../univoices-frontend
npm install
```

### Environment Variables

**Backend (.env)**
```env
# Database
DB_LOCATION=mongodb+srv://username:password@cluster.mongodb.net/univoices

# Firebase
FIREBASE_PROJECT_ID=your-firebase-project
FIREBASE_PRIVATE_KEY=your-firebase-key
FIREBASE_CLIENT_EMAIL=your-firebase-email

# AWS
AWS_REGION=us-east-1
AWS_ACCESS_KEY=your-aws-access-key
AWS_SECRET_ACCESS_KEY=your-aws-secret-key
AWS_BUCKET_NAME=your-s3-bucket

# Authentication
SECRET_ACCESS_KEY=your-jwt-secret

# AI
OPENAI_API_KEY=sk-your-openai-key
```

**Frontend (.env)**
```env
VITE_FIREBASE_API_KEY=your-firebase-api-key
VITE_FIREBASE_AUTH_DOMAIN=your-firebase-domain
VITE_FIREBASE_PROJECT_ID=your-firebase-project
```

### Running the Application

**Terminal 1 - Backend**
```bash
cd univoices-backend
npm start
# Server runs on http://localhost:3000
```

**Terminal 2 - Frontend**
```bash
cd univoices-frontend
npm run dev
# App runs on http://localhost:5173
```

## 🤖 AI Features Guide

### Content Enhancement
1. Write or edit your blog content
2. Click **✨ Enhance** button
3. AI improves grammar, clarity, and adds insights
4. Accept or reject the enhancement

### Title Suggestions
1. Create a new blog post
2. Click **📝 Title** button
3. View 5 SEO-optimized title suggestions
4. Click to select a title

### Tag Suggestions
1. Write your blog content
2. Click **🏷️ Tags** button
3. AI suggests relevant tags
4. Click **+** to add tags to your blog

## 📚 API Endpoints

### AI Endpoints
- `POST /enhance-content` - Enhance blog content
- `POST /suggest-title` - Generate title suggestions
- `POST /suggest-tags` - Generate tag suggestions

### User Endpoints
- `POST /register` - User registration
- `POST /login` - User login
- `GET /user/:id` - Get user profile
- `PUT /user/:id` - Update user profile

### Blog Endpoints
- `POST /create-blog` - Create new blog
- `GET /blogs` - Get all blogs
- `GET /blog/:id` - Get blog details
- `PUT /edit-blog/:id` - Edit blog
- `DELETE /delete-blog/:id` - Delete blog

### Comment Endpoints
- `POST /add-comment` - Add comment
- `GET /comments/:blogId` - Get comments
- `DELETE /comment/:id` - Delete comment

## 💡 Usage Tips

1. **For Content Creation**
   - Use EditorJS for rich text formatting
   - Add images directly from AWS S3
   - Use AI features to enhance your content

2. **For Best AI Results**
   - Provide clear, detailed content
   - Use AI suggestions as starting points
   - Refine titles and tags based on your preferences

3. **For Performance**
   - Images are optimized and cached
   - MongoDB queries are indexed for speed
   - Frontend uses lazy loading for components

## 🔒 Security Features

- ✅ JWT-based authentication
- ✅ Bcrypt password hashing
- ✅ CORS protection
- ✅ Secure Firebase Admin authentication
- ✅ Environment variable protection
- ✅ Input validation and sanitization

## 📊 Database Schema

### User
```javascript
{
  username: String,
  email: String,
  password: String (hashed),
  bio: String,
  profilePicture: String,
  joinedAt: Date
}
```

### Blog
```javascript
{
  title: String,
  content: Object (EditorJS format),
  author: ObjectId (User),
  tags: [String],
  createdAt: Date,
  updatedAt: Date,
  views: Number
}
```

### Comment
```javascript
{
  content: String,
  author: ObjectId (User),
  blog: ObjectId (Blog),
  createdAt: Date
}
```

## 🚀 Deployment

### Backend (Heroku/Railway)
```bash
# Set environment variables
git push heroku main
```

### Frontend (Vercel/Netlify)
```bash
npm run build
# Deploy build folder
```

## 📝 License

MIT License - feel free to use this project for personal or commercial purposes.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📧 Support

For issues or questions, please open an issue on GitHub.

---

**Built with ❤️ using React, Node.js, and AI**
