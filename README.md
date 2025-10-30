# 🌿 V1le Farm E-Commerce App

> A full-stack e-commerce platform built for premium product sales with secure authentication, Telegram integration, and advanced admin controls.

---

## ✨ Features

### 🧑‍💻 User Features
- **User Authentication:** Manus OAuth integration for secure login  
- **Profile Management:** Editable bio, username, email, and profile picture upload  
- **Product Ordering:** Order the **God Complex** product in flexible quantities *(2g, 2.5g, 5g, 10g, or custom)*  
- **Telegram Integration:** Orders require Telegram username for communication  
- **Order Management:** View, cancel, and delete personal orders  
- **Reviews:** Leave one review per product with ratings and comments  
- **Profile Display:** Animated spinning profile pictures with red glow effect  

### 🛠️ Admin Features
- **Order Management:** View all orders, approve/reject/cancel orders  
- **User Management:** Search users and assign admin roles  
- **Store Control:** Toggle store open/close status to prevent new orders  
- **Order Statistics:** Dashboard showing pending, approved, rejected, and cancelled orders  
- **Order Deletion:** Delete individual orders from the system  

### ⚙️ Technical Features
- **Dark Mode UI:** Purple-themed dark interface with animated effects  
- **Telegram Bot:** Automatic order notifications with inline approve/deny buttons  
- **S3 Storage:** Profile and product images stored in S3  
- **Database:** MySQL with Drizzle ORM for type-safe queries  
- **Backend API:** tRPC for end-to-end type safety  

---

## 🚀 Setup Instructions

### 🔧 Prerequisites
- Node.js 18+
- MySQL database
- Telegram Bot Token *(optional)*

### ⚙️ Environment Variables
Create a `.env` file with the following:

```bash
# Database
DATABASE_URL=mysql://user:password@host:port/database

# Authentication
JWT_SECRET=your-secret-key
VITE_APP_ID=your-app-id
OAUTH_SERVER_URL=https://api.manus.im
VITE_OAUTH_PORTAL_URL=https://portal.manus.im

# Telegram Bot (Optional)
TELEGRAM_BOT_TOKEN=your-bot-token
TELEGRAM_ADMIN_CHAT_ID=your-admin-chat-id

# Storage
BUILT_IN_FORGE_API_URL=https://api.manus.im
BUILT_IN_FORGE_API_KEY=your-api-key

# App Configuration
VITE_APP_TITLE=V1le Farm
VITE_APP_LOGO=https://your-logo-url