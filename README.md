# 🌿 V1LE Farm — Setup Guide

> **V1LE Farm** is a premium cannabis ordering web application built with Telegram authentication, real-time bot notifications, and admin controls — all wrapped in a sleek dark red aesthetic.

---

## 📖 Overview

V1LE Farm lets customers browse, order, and track their purchases while admins receive instant Telegram alerts with interactive approval buttons.

---

## ✨ Features

✅ **Telegram Authentication** — Secure login via Manus OAuth  
✅ **Product Ordering** — “God Complex” strain at **$10/gram** (min 0.5g)  
✅ **Order Management** — Track order status and order history  
✅ **Telegram Notifications** — Real-time updates to admin + group chat  
✅ **Interactive Buttons** — Approve/reject orders from Telegram  
✅ **Dark Theme** — Black and red palette with V1LE branding  

---

## 🗺️ Pages

| Page | Route | Description |
|------|--------|-------------|
| 🏠 **Home** | `/` | Landing page with branding & navigation |
| 🌿 **Category** | `/category` | Product catalog and ordering page |
| 📜 **Order History** | `/orders` | Displays all past orders with status badges |

---

## 🤖 Telegram Bot Setup

### 🔧 Bot Configuration
The bot is already configured with:

```env
Bot Token: 7815244310:AAH_Pr-8qbKysycnnznahrAQ4zZOfva0XUg
Admin Chat ID: 6665237815
Group Chat ID: -4959546169 orders  
- **Order Deletion:** Delete individual orders from the system  

### ⚙️ Technical Features
- **Dark Mode UI:** red-themed dark interface with animated effects  
- **Telegram Bot:** Automatic order notifications with inline approve/deny buttons  
- **S3 Storage:** Profile and product images stored in S3  
- **Database:** MySQL with Drizzle ORM for type-safe queries  
- **Backend API:** tRPC for end-to-end type safety  

---