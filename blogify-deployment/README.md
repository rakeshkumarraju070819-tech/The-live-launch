# Blogify API - Cloud Deployment Project

A production-ready RESTful API for a blogging platform, deployed on Render cloud platform.

## 🚀 Live Deployment

**Production URL**: `https://blogify-api-yourname.onrender.com`

## 📋 Features 

- Express.js REST API
- MongoDB Atlas databasee integration
- JWT Authentication
- Environment-based configuration
- Production-ready deployment on Render

## 🛠️ Local Development Setup

### Prerequisites

- Node.js >= 18.0.0
- npm >= 9.0.0
- MongoDB Atlas account

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/blogify-api.git
cd blogify-api
```

2. Install dependencies:
```bash
npm install
```

3. Create your `.env` file:
```bash
cp .env.example .env
```

4. Update `.env` with your actual credentials:
- Add your MongoDB Atlas connection string
- Set your JWT secret
- Configure NODE_ENV

5. Start the development server:
```bash
npm run dev
```

The server will run on `http://localhost:3000`

## 🌐 Deployment to Render

### Pre-Flight Checklist

- ✅ Latest code pushed to GitHub main branch
- ✅ `.env` file NOT committed (check `.gitignore`)
- ✅ `"start": "node src/index.js"` in package.json
- ✅ `engines` field specified in package.json

### Deployment Steps

1. **Create Render Account**
   - Go to https://dashboard.render.com/register
   - Sign up using GitHub (IMPORTANT)

2. **Create Web Service**
   - Click "New +" → "Web Service"
   - Connect your GitHub repository
   - If not visible, click "Configure account" to grant permissions

3. **Configure Service**
   - **Name**: `blogify-api-yourname`
   - **Region**: Singapore/Frankfurt (closest to you)
   - **Branch**: `main`
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
   - **Plan**: Free

4. **Add Environment Variables**
   - `MONGO_URI`: Your MongoDB Atlas connection string
   - `JWT_SECRET`: Your secret key
   - `NODE_ENV`: production

5. **Deploy**
   - Click "Create Web Service"
   - Watch the logs for "Your service is live"

## 📡 API Endpoints

### Public Endpoints

- `GET /` - Welcome message
- `GET /health` - Health check
- `GET /posts` - Get all posts (demo)

### Testing in Postman

Create a new environment called "Production":
- Variable: `URL`
- Value: `https://blogify-api-yourname.onrender.com`

Switch to Production environment and test endpoints.

## 🔧 Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `MONGO_URI` | MongoDB Atlas connection string | Yes |
| `JWT_SECRET` | Secret key for JWT tokens | Yes |
| `NODE_ENV` | Environment (development/production) | Yes |
| `PORT` | Server port (auto-set by Render) | No |

## 📂 Project Structure

```
blogify-api/
├── src/
│   └── index.js          # Main server file
├── .env.example          # Environment variables template
├── .gitignore            # Git ignore rules
├── package.json          # Dependencies and scripts
└── README.md             # This file
```

## 🐛 Troubleshooting

### Deployment Failed

- Check build logs in Render dashboard
- Verify all environment variables are set
- Ensure MongoDB URI is correct (no curly braces)
- Check that `npm install` completes successfully

### Application Error

- Review server logs in Render
- Verify MongoDB connection string
- Check that `NODE_ENV=production` is set

### Cannot Connect to Database

- Whitelist Render's IP (0.0.0.0/0) in MongoDB Atlas
- Verify connection string format
- Check database user permissions

## 📝 Assignment Submission

### Required Components

1. **GitHub PR**
   - Branch: `chore/deployment-config`
   - Contains: production configurations, clean .gitignore
   
2. **Video Proof** (Loom/Google Drive)
   - Show Render Dashboard (Green "Service is Live")
   - Browser test of root URL
   - Postman test with live Render URL

## 🔐 Security Notes

- Never commit `.env` file to Git
- Rotate JWT secrets regularly
- Use strong, unique passwords for MongoDB
- Whitelist only necessary IPs in production

## 📄 License

ISC

## 👨‍💻 Author

Your Name - Kalvium Student
