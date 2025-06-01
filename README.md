# 🚀 Gravitas Hackathon Platform

A comprehensive web-based platform for managing hackathon events at VIT, featuring team formation, project submissions, and faculty administration.

## 🌟 Features

### 👥 **User Management**
- 🔐 Google OAuth authentication
- 📝 Profile completion with hostel block, mobile number, and registration number
- 👤 User dashboard with real-time updates

### 🤝 **Team Formation**
- 🎯 Create teams with 3-4 members
- 🔍 Validate team members using registration numbers
- 📊 Track selection (Web Development, Mobile App, AI/ML, Blockchain, IoT, Cybersecurity)
- 📋 Project description and presentation link submission

### 🎓 **Faculty Administration**
- 👨‍🏫 Faculty-only access control
- ✅ Team approval/rejection system
- 📈 Real-time statistics dashboard
- 👥 User and team management
- 📊 Submission tracking

### 💻 **Project Submission**
- 🔗 GitHub repository link submission
- 📱 LinkedIn post link for project showcase
- ⏰ Timestamp tracking for submissions
- 📋 Submission status monitoring

### 📱 **Responsive Design**
- 📱 Mobile-friendly interface
- ⚡ Loading animations and skeleton screens
- 🎨 Modern UI with smooth transitions
- 🔄 Real-time data updates

## 🛠️ Tech Stack

### **Backend**
- 🟢 **Node.js** - Runtime environment
- 🚀 **Express.js** - Web framework
- 🔥 **Firebase Admin SDK** - Authentication & database
- 🗄️ **Firestore** - NoSQL database
- 🍪 **Express Session** - Session management

### **Frontend**
- 🌐 **HTML5** - Markup
- 🎨 **CSS3** - Styling with animations
- ⚡ **Vanilla JavaScript** - Dynamic functionality
- 🔥 **Firebase Web SDK** - Client-side authentication

### **Authentication**
- 🔐 **Google OAuth 2.0** - Secure sign-in
- 🎫 **Firebase ID Tokens** - Token verification
- 🛡️ **Session-based authorization** - Route protection

## 📦 Installation

### 📋 **Prerequisites**
- 🟢 Node.js (v14 or higher)
- 📦 npm or yarn package manager
- 🔥 Firebase project with Firestore enabled
- 🌐 Google Cloud Console project for OAuth

### 🚀 **Setup Steps**

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd gravitas-hackathon-platform
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Configuration**
   Create a `.env` file in the root directory:
   ```env
   # Server Configuration
   PORT=3000
   SESSION_SECRET=your-super-secret-session-key

   # Firebase Configuration
   FIREBASE_PROJECT_ID=your-project-id
   FIREBASE_PRIVATE_KEY_ID=your-private-key-id
   FIREBASE_PRIVATE_KEY="-----BEGIN PRIVATE KEY-----\nYour-Private-Key\n-----END PRIVATE KEY-----\n"
   FIREBASE_CLIENT_EMAIL=your-service-account@your-project.iam.gserviceaccount.com
   FIREBASE_CLIENT_ID=your-client-id
   FIREBASE_API_KEY=your-api-key
   FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
   FIREBASE_STORAGE_BUCKET=your-project.appspot.com
   FIREBASE_MESSAGING_SENDER_ID=123456789
   FIREBASE_APP_ID=1:123456789:web:abcdef
   FIREBASE_MEASUREMENT_ID=G-ABCDEFGHIJ

   # Faculty Access Control
   FACULTY_EMAILS=faculty1@vit.ac.in,faculty2@vit.ac.in,admin@vit.ac.in
   ```

4. **Firebase Setup**
   - 🔥 Create a Firebase project
   - 🗄️ Enable Firestore database
   - 🔐 Enable Google Authentication
   - 🔑 Generate service account credentials
   - 🌐 Add your domain to authorized domains

5. **Start the server**
   ```bash
   npm start
   ```

6. **Access the application**
   ```
   🌐 http://localhost:3000
   ```

## 🗄️ Database Structure

### 👤 **Users Collection**
```javascript
{
  email: "student@vitstudent.ac.in",
  name: "John Doe",
  profilePicture: "https://...",
  regNumber: "21BCE1234",
  hostelBlock: "A Block",
  mobileNumber: "+91-9876543210",
  profileComplete: true,
  createdAt: Timestamp,
  lastLoginAt: Timestamp
}
```

### 🤝 **Teams Collection**
```javascript
{
  teamName: "Code Warriors",
  leaderId: "user-uid",
  leaderRegNumber: "21BCE1234",
  members: ["21BCE1234", "21BCE5678", "21BCE9012"],
  memberDetails: [
    {
      id: "user-uid",
      name: "John Doe",
      regNumber: "21BCE1234",
      email: "student@vitstudent.ac.in"
    }
  ],
  track: "web-development",
  topic: "E-commerce Platform",
  pptLink: "https://docs.google.com/presentation/...",
  description: "A modern e-commerce solution...",
  status: "approved", // pending, approved, rejected
  statusDescription: "Great project idea!",
  githubLink: "https://github.com/team/project",
  linkedinLink: "https://linkedin.com/posts/...",
  submissionVisible: true,
  createdAt: Timestamp,
  submittedAt: Timestamp
}
```

## 🔒 API Endpoints

### 🔐 **Authentication**
- `POST /api/auth/signin` - Google OAuth sign-in
- `POST /api/auth/signout` - User sign-out
- `GET /api/auth/status` - Check authentication status

### 👤 **User Management**
- `GET /api/user/profile` - Get user profile
- `POST /api/profile/update` - Update user profile

### 🤝 **Team Management**
- `POST /api/team/create` - Create new team
- `GET /api/team/my-team` - Get user's team
- `POST /api/team/submit` - Submit project

### 🎓 **Faculty (Admin)**
- `GET /api/faculty/users` - Get all users
- `GET /api/faculty/teams` - Get all teams
- `GET /api/faculty/submissions` - Get all submissions
- `POST /api/faculty/team/approve` - Approve/reject teams

### 📊 **Statistics**
- `GET /api/stats` - Get platform statistics

## 🌊 User Flow

### 👥 **Student Journey**
1. 🔐 **Sign In** → Google OAuth authentication
2. 📝 **Profile Setup** → Complete registration details
3. 🤝 **Team Formation** → Create or join team
4. ⏳ **Wait for Approval** → Faculty reviews team
5. 💻 **Project Submission** → Submit GitHub & LinkedIn links
6. 🏆 **Results** → View final standings

### 🎓 **Faculty Journey**
1. 🔐 **Sign In** → Faculty email authentication
2. 📊 **Dashboard** → View statistics and overview
3. 👥 **Review Teams** → Approve/reject team applications
4. 📋 **Monitor Submissions** → Track project submissions
5. 📈 **Analytics** → View participation metrics

## 🔒 Security Features

- 🛡️ **Route Protection** - Session-based authentication
- 🔐 **Token Verification** - Firebase ID token validation
- 👨‍🏫 **Role-based Access** - Faculty-only admin features
- 🔍 **Input Validation** - Server-side data validation
- 🚫 **Duplicate Prevention** - Unique registration numbers
- ⏰ **Session Management** - Automatic session expiry

## 🎯 Key Features

### ⚡ **Real-time Updates**
- 🔄 Auto-refresh team status every 30 seconds
- 📊 Live statistics dashboard
- 🔔 Instant feedback on actions

### 📱 **User Experience**
- 🎨 Loading animations and skeletons
- ✅ Success/error message system
- 📱 Responsive design for all devices
- 🆘 Help modal with support contact

### 🔧 **Admin Features**
- 📊 Comprehensive statistics
- 👥 User management
- 📋 Team approval workflow
- 📈 Submission tracking

## 🆘 Support

For technical issues or queries:
- 📧 **Email**: standardsclub@vit.ac.in
- ⏰ **Response Time**: 10-15 minutes
- 📸 **Pro Tip**: Include screenshots for faster resolution

## 📈 Event Timeline

- 📅 **Registration**: May 1-15, 2025
- 🤝 **Team Formation**: May 16-20, 2025
- 💻 **Hackathon Event**: June 1-2, 2025
- 🏆 **Results**: June 5, 2025

## 🤝 Contributing

1. 🍴 Fork the repository
2. 🌿 Create feature branch (`git checkout -b feature/amazing-feature`)
3. 💾 Commit changes (`git commit -m 'Add amazing feature'`)
4. 📤 Push to branch (`git push origin feature/amazing-feature`)
5. 🔄 Create Pull Request

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- 🏫 **VIT Standards Club** - Event organization
- 🔥 **Firebase** - Backend infrastructure
- 🌐 **Google OAuth** - Authentication service
- 👥 **VIT Community** - Testing and feedback

---

Made with ❤️ for **Gravitas 2025** by VIT Standards Club

🌟 **Star this repository if you found it helpful!**
