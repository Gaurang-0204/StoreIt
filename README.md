# 📁 StoreIt - Cloud Storage & File Sharing Platform

<div align="center">

![StoreIt](https://img.shields.io/badge/StoreIt-v1.0-blue?style=for-the-badge)
![Next.js](https://img.shields.io/badge/Next.js-15-black?style=for-the-badge&logo=next.js)
![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?style=for-the-badge&logo=typescript)
![Appwrite](https://img.shields.io/badge/Appwrite-Backend-FF6B6B?style=for-the-badge)

**A modern, full-featured cloud storage and file sharing platform built with Next.js 15, React 19, and Appwrite.**

[Live Demo](#) • [Documentation](#documentation) • [Installation](#local-setup) • [Features](#-features)

</div>

---

## 📖 Table of Contents

- [Introduction](#-introduction)
- [Tech Stack](#%EF%B8%8F-tech-stack)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Backend Setup (Appwrite)](#-backend-setup-appwrite)
- [Local Setup](#-local-setup)
- [Environment Variables](#-environment-variables)
- [Usage Guide](#-usage-guide)
- [API Integration](#-api-integration)
- [Database Schema](#-database-schema)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🤖 Introduction

**StoreIt** is a comprehensive cloud storage management and file-sharing platform that enables users to securely upload, organize, manage, and share files with others. Built with cutting-edge web technologies, it provides a Google Drive-like experience with an intuitive interface and powerful file management capabilities.

### Why StoreIt?

- 🔐 **Secure**: All files encrypted and stored securely with Appwrite
- ⚡ **Fast**: Server-side rendering for optimal performance
- 🎨 **Modern UI**: Clean, responsive design with ShadCN components
- 🔄 **Real-time**: Instant file operations and updates
- 📱 **Mobile-Friendly**: Fully responsive across all devices
- 🌐 **Scalable**: Built on Appwrite's robust infrastructure

---

## ⚙️ Tech Stack

### Frontend
| Technology | Version | Purpose |
|-----------|---------|---------|
| **Next.js** | 15 | React framework with SSR and App Router |
| **React** | 19 | UI library with concurrent features |
| **TypeScript** | 5.0+ | Type-safe JavaScript |
| **TailwindCSS** | Latest | Utility-first CSS framework |
| **ShadCN/UI** | Latest | Pre-built, accessible UI components |

### Backend & Infrastructure
| Technology | Version | Purpose |
|-----------|---------|---------|
| **Appwrite** | Cloud | Backend-as-a-Service (Auth, Database, Storage) |
| **Node.js** | 18+ | Server runtime |
| **npm** | 9+ | Package manager |

### Key Libraries
```json
{
  "next": "^15.0.0",
  "react": "^19.0.0",
  "react-dom": "^19.0.0",
  "typescript": "^5.0.0",
  "tailwindcss": "^3.4.0",
  "appwrite": "^14.0.0",
  "axios": "^1.6.0",
  "zustand": "^4.0.0"
}
```

---

## 🎯 Features

### 👤 Authentication & User Management
- ✅ **Secure User Authentication**: Passwordless OTP-based login/signup
- ✅ **User Profile Management**: Store and manage user account details
- ✅ **Session Management**: Automatic session handling and logout
- ✅ **Avatar Support**: User profile pictures with Appwrite Avatars API

### 📁 File Management
- ✅ **Upload Files**: Support for multiple file types (documents, images, videos, audio)
- ✅ **File Viewing**: Preview files directly in the browser
- ✅ **Download Files**: Download files locally with one click
- ✅ **Rename Files**: Update file names without re-uploading
- ✅ **Delete Files**: Permanently remove files from storage
- ✅ **File Type Detection**: Automatic categorization (Document, Image, Video, Audio, Other)

### 🔗 File Sharing & Collaboration
- ✅ **Share Files**: Share files with specific users via email
- ✅ **Manage Sharing**: View and revoke shared access
- ✅ **Shared File Access**: Access files shared by other users
- ✅ **Permission Control**: Fine-grained access control

### 📊 Dashboard & Analytics
- ✅ **Storage Overview**: Visual dashboard showing storage statistics
- ✅ **Total Storage**: Display total available storage
- ✅ **Used Storage**: Show consumed storage capacity
- ✅ **File Type Summary**: Breakdown of files by type (documents, images, etc.)
- ✅ **Recent Uploads**: Quick access to recently uploaded files

### 🔍 Search & Organization
- ✅ **Global Search**: Fast search across all files and shared content
- ✅ **Sorting Options**: Sort files by date, name, or size
- ✅ **Filtering**: Filter files by type and status
- ✅ **Advanced Queries**: Complex queries with Appwrite

### 🎨 User Experience
- ✅ **Responsive Design**: Works seamlessly on desktop, tablet, and mobile
- ✅ **Modern UI**: Clean, minimalist interface using ShadCN components
- ✅ **Dark Mode Support**: Easy on the eyes during extended usage
- ✅ **Keyboard Shortcuts**: Productivity-focused navigation
- ✅ **Loading States**: Smooth loading transitions and feedback

### ⚡ Performance
- ✅ **Server-Side Rendering**: Fast initial page load
- ✅ **Image Optimization**: Automatic image optimization with Next.js
- ✅ **Code Splitting**: Lazy loading of components
- ✅ **Caching**: Intelligent caching strategies

---

## 📁 Project Structure

```
StoreIt/
│
├── app/                              # Next.js App Router
│   ├── layout.tsx                   # Root layout with providers
│   ├── page.tsx                     # Landing/Home page
│   ├── (auth)/                      # Auth route group
│   │   ├── sign-up/
│   │   │   └── page.tsx
│   │   └── sign-in/
│   │       └── page.tsx
│   └── (root)/                      # Protected routes
│       ├── layout.tsx               # App layout with sidebar
│       ├── dashboard/
│       │   └── page.tsx             # Main dashboard
│       └── [id]/
│           └── page.tsx             # File detail page
│
├── components/                       # React Components
│   ├── ui/                          # ShadCN UI components
│   │   ├── button.tsx
│   │   ├── input.tsx
│   │   ├── dialog.tsx
│   │   ├── form.tsx
│   │   └── ...
│   ├── FileCard.tsx                 # File display component
│   ├── FileUpload.tsx               # File upload form
│   ├── SearchBar.tsx                # Global search
│   ├── Dashboard.tsx                # Dashboard layout
│   ├── Sidebar.tsx                  # Navigation sidebar
│   ├── Header.tsx                   # Top navigation bar
│   └── ...
│
├── lib/                              # Utility functions & configs
│   ├── appwrite.ts                  # Appwrite client configuration
│   ├── utils.ts                     # Helper functions
│   ├── constants.ts                 # App constants
│   ├── types.ts                     # TypeScript interfaces
│   └── validators.ts                # Input validation
│
├── actions/                          # Server Actions (Server-side)
│   ├── auth.actions.ts              # Authentication operations
│   ├── user.actions.ts              # User profile operations
│   ├── file.actions.ts              # File CRUD operations
│   └── search.actions.ts            # Search operations
│
├── styles/                           # Global styles
│   ├── globals.css                  # TailwindCSS imports
│   └── variables.css                # CSS variables
│
├── public/                           # Static assets
│   ├── images/
│   ├── icons/
│   └── ...
│
├── .env.local                        # Environment variables (local)
├── .env.example                      # Environment variables template
├── tsconfig.json                     # TypeScript configuration
├── tailwind.config.ts                # TailwindCSS configuration
├── next.config.js                    # Next.js configuration
├── package.json                      # Project dependencies
├── package-lock.json                 # Locked dependency versions
└── README.md                         # This file
```

---

## 🔧 Backend Setup (Appwrite)

### Prerequisites for Appwrite Setup

Before running the application, you need to set up the Appwrite backend. Follow these steps carefully:

### Step 1: Create Appwrite Project

1. Visit [Appwrite Cloud](https://cloud.appwrite.io)
2. Sign up or log in to your account
3. Click **"Create Project"**
4. Enter project name: `StoreIt` (or any name)
5. Click **"Create"**
6. Copy the **Project ID** and save it

### Step 2: Configure Web Platform

1. Go to **Settings** → **Platforms**
2. Click **"Add Platform"** → **"Web App"**
3. Set Hostname: `localhost` (for development)
4. Set Hostname: `yourdomain.com` (for production)
5. Click **"Save"**

### Step 3: Generate API Key

1. Navigate to **Settings** → **API Keys**
2. Click **"Create API Key"**
3. Name: `StoreIt Server Key`
4. Select these scopes:
   - `databases.*` (all database permissions)
   - `storage.*` (all storage permissions)
   - `users.*` (all user permissions)
5. Click **"Create"**
6. Copy the API Key and save it securely

### Step 4: Create Database

1. Go to **Databases** in the sidebar
2. Click **"Create Database"**
3. Name: `storeit_database`
4. Click **"Create"**
5. Copy the **Database ID**

### Step 5: Create Tables (Updated from Collections)

#### **Table 1: Users**

1. Click **"Create Table"** inside your database
2. Name: `users`
3. Copy the **Table ID**
4. Create these columns:

| Column Name | Type | Size | Required |
|------------|------|------|----------|
| `fullName` | String | 255 | Yes |
| `email` | Email | 255 | Yes |
| `avatar` | URL | 2000 | No |
| `accountId` | String | 255 | Yes |

**Create Indexes:**
- Index on `accountId` (Key)
- Index on `email` (Unique)

#### **Table 2: Files**

1. Click **"Create Table"** inside your database
2. Name: `files`
3. Copy the **Table ID**
4. Create these columns:

| Column Name | Type | Size | Required | Array |
|------------|------|------|----------|-------|
| `name` | String | 255 | Yes | No |
| `type` | String | 50 | Yes | No |
| `extension` | String | 10 | Yes | No |
| `size` | Integer | - | Yes | No |
| `bucketFileId` | String | 255 | Yes | No |
| `owner` | String | 255 | Yes | No |
| `accountId` | String | 255 | Yes | No |
| `users` | String | 50 | No | **Yes** |
| `url` | URL | 2000 | Yes | No |

**Create Indexes:**
- Index on `owner` (Key)
- Index on `accountId` (Key)
- Index on `type` (Key)
- Index on `bucketFileId` (Unique)

### Step 6: Create Storage Bucket

1. Navigate to **Storage** in the sidebar
2. Click **"Create Bucket"**
3. Name: `files`
4. Copy the **Bucket ID**
5. Configure:
   - **Maximum File Size**: 50 MB
   - **Encryption**: Enabled ✅
   - **Antivirus Scan**: Enabled ✅
   - **File Security**: Enabled ✅

### Step 7: Configure Authentication

1. Go to **Auth** → **Settings**
2. Enable **Email/Password** authentication
3. Enable **Magic URL** for OTP-based login
4. Configure email templates (optional)

### Step 8: Collect Credentials

Save all these values safely:
- ✅ Project ID
- ✅ Database ID
- ✅ Users Table ID
- ✅ Files Table ID
- ✅ Storage Bucket ID
- ✅ API Key

You'll need these for the `.env.local` file.

---

## 🚀 Local Setup

### Prerequisites

Before you begin, ensure you have the following installed:

- **Git** - Version control
- **Node.js** - Runtime (v18.0.0 or higher)
- **npm** - Package manager (v9.0.0 or higher)
- **Appwrite Account** - Backend service (free tier available)

### Step 1: Clone the Repository

```bash
git clone https://github.com/Gaurang-0204/StoreIt.git
cd StoreIt
```

### Step 2: Install Dependencies

```bash
npm install
```

This installs all required packages including Next.js, React, Appwrite SDK, TailwindCSS, and ShadCN components.

### Step 3: Set Up Environment Variables

Create a `.env.local` file in the root directory:

```bash
cp .env.example .env.local
```

Or manually create `.env.local` with the following content:

```env
# Appwrite Configuration
NEXT_PUBLIC_APPWRITE_ENDPOINT="https://cloud.appwrite.io/v1"
NEXT_PUBLIC_APPWRITE_PROJECT="YOUR_PROJECT_ID"
NEXT_PUBLIC_APPWRITE_DATABASE="YOUR_DATABASE_ID"
NEXT_PUBLIC_APPWRITE_USERS_TABLE="YOUR_USERS_TABLE_ID"
NEXT_PUBLIC_APPWRITE_FILES_TABLE="YOUR_FILES_TABLE_ID"
NEXT_PUBLIC_APPWRITE_BUCKET="YOUR_BUCKET_ID"
NEXT_APPWRITE_KEY="YOUR_API_KEY"
```

Replace placeholders with actual values from your Appwrite setup.

### Step 4: Run Development Server

```bash
npm run dev
```

The application will start at `http://localhost:3000`

### Step 5: Open in Browser

```
http://localhost:3000
```

You should see the StoreIt landing page. Create an account and start uploading files!

---

## 🔐 Environment Variables

### Frontend Variables (Public)

These are accessible in the browser and prefixed with `NEXT_PUBLIC_`:

```env
# Appwrite Cloud Endpoint
NEXT_PUBLIC_APPWRITE_ENDPOINT="https://cloud.appwrite.io/v1"

# Your Appwrite Project ID
NEXT_PUBLIC_APPWRITE_PROJECT="project_id_here"

# Database ID
NEXT_PUBLIC_APPWRITE_DATABASE="database_id_here"

# Table IDs
NEXT_PUBLIC_APPWRITE_USERS_TABLE="users_table_id_here"
NEXT_PUBLIC_APPWRITE_FILES_TABLE="files_table_id_here"

# Storage Bucket ID
NEXT_PUBLIC_APPWRITE_BUCKET="bucket_id_here"
```

### Server Variables (Private)

These are only accessible on the server and used for secure operations:

```env
# Server-side API Key (Keep this secret!)
NEXT_APPWRITE_KEY="your_api_key_here"
```

### Getting These Values

| Variable | Where to Find |
|----------|---------------|
| `ENDPOINT` | Appwrite Dashboard (always `https://cloud.appwrite.io/v1`) |
| `PROJECT` | Settings → Project Details |
| `DATABASE` | Databases → Your Database → Copy ID |
| `USERS_TABLE` | Databases → users table → Copy ID |
| `FILES_TABLE` | Databases → files table → Copy ID |
| `BUCKET` | Storage → files bucket → Copy ID |
| `API_KEY` | Settings → API Keys → Create/Copy |

### Security Best Practices

⚠️ **Important Security Guidelines:**

1. **Never commit `.env.local`** to Git
2. **Never share your `NEXT_APPWRITE_KEY`** - it's sensitive!
3. **Use `.env.example`** to document required variables
4. **Rotate API Keys** regularly in production
5. **Use different keys** for development and production
6. **Restrict API Key scopes** to minimum required permissions

---

## 📖 Usage Guide

### User Authentication

#### Sign Up

1. Click **"Sign Up"** on the landing page
2. Enter your full name and email
3. You'll receive an OTP via email
4. Enter the OTP to verify and create your account
5. You're now logged in!

#### Sign In

1. Click **"Sign In"**
2. Enter your email address
3. Enter the OTP sent to your email
4. Access your dashboard

#### Sign Out

1. Click your **Profile Avatar** in the top-right corner
2. Select **"Sign Out"**

### File Operations

#### Upload Files

1. Navigate to **Dashboard**
2. Click **"Upload Files"** or drag & drop files
3. Select file(s) from your computer
4. Wait for upload to complete
5. File appears in your dashboard

#### View Files

1. All uploaded files display on the **Dashboard**
2. Click any file to **preview** it
3. View file details (name, size, type, date)

#### Download Files

1. Find the file you want to download
2. Click the **Download Icon** (or three-dot menu)
3. File downloads to your computer

#### Rename Files

1. Click the **three-dot menu** on any file
2. Select **"Rename"**
3. Enter the new name
4. Click **"Save"**

#### Delete Files

1. Click the **three-dot menu** on any file
2. Select **"Delete"**
3. Confirm deletion
4. File is permanently removed

#### Share Files

1. Click the **three-dot menu** on any file
2. Select **"Share"**
3. Enter the email of the person to share with
4. Click **"Share"**
5. They'll receive notification and can access the file

### Dashboard Features

#### Storage Overview

- View total storage available
- See storage currently in use
- Visual storage usage indicator

#### File Statistics

- Total number of files
- Files grouped by type (Documents, Images, Videos, Audio, Other)
- Recent file activity

#### Search & Filter

1. Use the **Search Bar** at the top
2. Type file name or keyword
3. Results update in real-time
4. Filter by file type or date

#### Sort Files

1. Click **"Sort By"** dropdown
2. Choose sorting option:
   - **Date** (newest first)
   - **Name** (A-Z)
   - **Size** (largest first)

---

## 🔌 API Integration

### Appwrite SDK Usage

All backend operations are handled through Next.js Server Actions using the Appwrite SDK.

### Authentication Actions

```typescript
// Sign up new user
export async function signUp(email: string, name: string) {
  // OTP authentication flow
}

// Sign in user
export async function signIn(email: string) {
  // Email verification with OTP
}

// Sign out
export async function signOut() {
  // End user session
}
```

### File Operations

```typescript
// Upload file
export async function uploadFile(
  formData: FormData,
  ownerId: string,
  accountId: string
) {
  // Upload to Appwrite storage
  // Create file metadata in database
}

// Get user files
export async function getUserFiles(accountId: string) {
  // Query files table
  // Return paginated results
}

// Get shared files
export async function getSharedFiles(userEmail: string) {
  // Query files shared with user
}

// Delete file
export async function deleteFile(fileId: string, bucketFileId: string) {
  // Remove from storage
  // Delete database record
}
```

### Query Examples

```typescript
import { Query } from "appwrite";

// Get files by user
const files = await databases.listRows(
  databaseId,
  filesTableId,
  [Query.equal("accountId", "user123")]
);

// Search files by name
const results = await databases.listRows(
  databaseId,
  filesTableId,
  [Query.search("name", "document")]
);

// Sort by date (newest first)
const sorted = await databases.listRows(
  databaseId,
  filesTableId,
  [Query.orderDesc("$createdAt")]
);
```

---

## 📊 Database Schema

### Users Table

Stores user profile information and account details.

| Field | Type | Description |
|-------|------|-------------|
| `$id` | String | Unique document ID (auto-generated) |
| `fullName` | String | User's full name |
| `email` | Email | User's email address (unique) |
| `avatar` | URL | Profile picture URL |
| `accountId` | String | User's account identifier from Auth |
| `$createdAt` | DateTime | Account creation timestamp |
| `$updatedAt` | DateTime | Last update timestamp |

### Files Table

Stores file metadata and sharing information.

| Field | Type | Description |
|-------|------|-------------|
| `$id` | String | Unique document ID |
| `name` | String | File name |
| `type` | String | File type (Document, Image, Video, Audio, Other) |
| `extension` | String | File extension (pdf, jpg, docx, etc.) |
| `size` | Integer | File size in bytes |
| `bucketFileId` | String | Reference to file in storage bucket |
| `owner` | String | Owner's user ID |
| `accountId` | String | Owner's account ID |
| `users` | String[] | Array of emails the file is shared with |
| `url` | URL | File download/view URL |
| `$createdAt` | DateTime | Upload timestamp |
| `$updatedAt` | DateTime | Last modified timestamp |

### Relationships

```
┌─────────────────┐
│     Users       │
│─────────────────│
│ $id             │
│ fullName        │
│ email           │
│ accountId       │◄─────────┐
│ avatar          │          │ One-to-Many
└─────────────────┘          │
                    ┌─────────────────┐
                    │     Files       │
                    │─────────────────│
                    │ $id             │
                    │ name            │
                    │ owner (FK)      ├─────┘
                    │ accountId (FK)  │
                    │ users (array)   │
                    │ bucketFileId    │
                    └─────────────────┘
```

---

## 🌐 Deployment

### Deploy to Vercel (Recommended)

Vercel is the creators of Next.js and provides seamless deployment.

#### Step 1: Push to GitHub

```bash
git add .
git commit -m "Ready for deployment"
git push origin main
```

#### Step 2: Connect to Vercel

1. Go to [Vercel Dashboard](https://vercel.com)
2. Click **"New Project"**
3. Select your GitHub repository
4. Click **"Import"**

#### Step 3: Configure Environment Variables

1. Go to **Settings** → **Environment Variables**
2. Add all variables from `.env.local`:
   ```
   NEXT_PUBLIC_APPWRITE_ENDPOINT
   NEXT_PUBLIC_APPWRITE_PROJECT
   NEXT_PUBLIC_APPWRITE_DATABASE
   NEXT_PUBLIC_APPWRITE_USERS_TABLE
   NEXT_PUBLIC_APPWRITE_FILES_TABLE
   NEXT_PUBLIC_APPWRITE_BUCKET
   NEXT_APPWRITE_KEY
   ```
3. Click **"Save"**

#### Step 4: Deploy

1. Click **"Deploy"**
2. Wait for deployment to complete
3. Your app is live!

### Update Appwrite Platform Settings

After deployment, add your Vercel domain to Appwrite:

1. Go to Appwrite Console → **Settings** → **Platforms**
2. Add Web Platform with your Vercel domain
3. Example: `storeit-production.vercel.app`

### Deploy to Other Platforms

#### Netlify

```bash
npm run build
netlify deploy --prod
```

#### Docker (Self-hosted)

```dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package.json .
RUN npm install

COPY . .
RUN npm run build

EXPOSE 3000
CMD ["npm", "start"]
```

#### Build and Deploy

```bash
docker build -t storeit .
docker run -p 3000:3000 storeit
```

---

## 🧪 Testing

### Run Tests

```bash
npm run test
```

### Build for Production

```bash
npm run build
```

Verify the build completes without errors.

### Run Production Build Locally

```bash
npm run build
npm run start
```

---

## 🔒 Security Considerations

### Authentication Security

- ✅ Passwordless OTP-based authentication (no passwords to crack)
- ✅ Email verification required for account creation
- ✅ Session tokens managed securely by Appwrite
- ✅ HTTPS encryption for all data in transit

### Data Security

- ✅ File encryption at rest (Appwrite default)
- ✅ Encrypted database storage
- ✅ Row-level security on shared files
- ✅ API key restrictions and scoping

### Best Practices

1. **API Key Management**
   - Rotate keys every 90 days
   - Use separate keys for dev/prod
   - Never commit keys to repository

2. **File Handling**
   - Validate file types on upload
   - Scan files for malware (Appwrite handles this)
   - Set maximum file size limits

3. **User Data**
   - Users can only access their own files
   - Shared files have explicit access control
   - No unauthorized data access possible

---

## 🐛 Troubleshooting

### Common Issues and Solutions

#### Issue: "Invalid API Key"

**Solution:**
- Verify `NEXT_APPWRITE_KEY` is correct
- Check API key hasn't expired
- Create a new API key in Appwrite console

#### Issue: "Database not found"

**Solution:**
- Verify `NEXT_PUBLIC_APPWRITE_DATABASE` ID is correct
- Ensure database exists in Appwrite console
- Check project ID matches

#### Issue: "File upload fails"

**Solution:**
- Check file size doesn't exceed 50MB limit
- Verify bucket ID is correct
- Ensure user is authenticated
- Check browser console for detailed errors

#### Issue: "Search not working"

**Solution:**
- Verify full-text search is enabled on table
- Clear browser cache
- Restart development server
- Check database indexes are created

#### Issue: "Email OTP not received"

**Solution:**
- Check spam/junk email folder
- Verify email is correctly spelled
- Wait 30 seconds before requesting new OTP
- Check Appwrite email settings are configured

---

## 📚 Documentation Links

- [Next.js Documentation](https://nextjs.org/docs)
- [React Documentation](https://react.dev)
- [Appwrite Documentation](https://appwrite.io/docs)
- [TailwindCSS Documentation](https://tailwindcss.com/docs)
- [ShadCN/UI Documentation](https://ui.shadcn.com)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)

---

## 🤝 Contributing

Contributions are welcome! Here's how to contribute:

### Step 1: Fork the Repository

Click the **"Fork"** button on GitHub

### Step 2: Clone Your Fork

```bash
git clone https://github.com/YOUR_USERNAME/StoreIt.git
cd StoreIt
```

### Step 3: Create a Feature Branch

```bash
git checkout -b feature/your-feature-name
```

### Step 4: Make Changes

- Write clean, readable code
- Follow existing code style
- Add comments for complex logic
- Update documentation as needed

### Step 5: Commit Changes

```bash
git add .
git commit -m "Add description of changes"
```

### Step 6: Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### Step 7: Create Pull Request

1. Go to original repository
2. Click **"New Pull Request"**
3. Select your branch
4. Describe your changes
5. Submit the pull request

### Contribution Guidelines

- Follow the existing code style
- Write meaningful commit messages
- Test your changes thoroughly
- Update README if needed
- Be respectful and constructive

---


---

## ❓ FAQ

### Is my data secure with StoreIt?

Yes! Your files are:
- Encrypted at rest in Appwrite's secure storage
- Encrypted in transit with HTTPS
- Only accessible by you and people you explicitly share with
- Protected by Appwrite's security infrastructure

### What are the file size limits?

- **Single File**: 50 MB
- **Total Storage**: Depends on Appwrite plan (Starter: 300GB)

### Can I export my data?

Yes, you can download all your files individually or as a batch.

### Is there a mobile app?

Currently, the web app is fully responsive and works on mobile devices. A native mobile app is planned for future releases.

### Can I self-host StoreIt?

Yes, you can modify the code to work with self-hosted Appwrite. See self-hosting documentation for details.

### How do I report security issues?

Please email security concerns to the repository maintainer rather than creating public issues.

### Can I contribute to this project?

Absolutely! See the **Contributing** section above for guidelines.

---

## 👨‍💼 Author

**Gaurang Salvi**
- GitHub: [@Gaurang-0204](https://github.com/Gaurang-0204)
- Portfolio: [Your Portfolio Link]
- Email: [Your Email]


---

## 📊 Project Stats

- **Stars**: ⭐ Show your support!
- **Forks**: 🍴 Feel free to fork
- **Issues**: 🐛 Report bugs or suggest features
- **PRs**: 🔄 Contribute improvements

---

<div align="center">

**Made with ❤️ by Gaurang Salvi*

If you found this project helpful, please give it a ⭐ on GitHub!

[⬆ Back to Top](#-storeit---cloud-storage--file-sharing-platform)

</div>

