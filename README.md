V1le Farm E-commerce AppA full-stack e-commerce application for selling premium products with user authentication, order management, Telegram bot integration, and admin controls.FeaturesUser Features•User Authentication: Manus OAuth integration for secure login•Profile Management: Editable bio, username, email, and profile picture upload•Product Ordering: Order the "God Complex" product with flexible quantities (2g, 2.5g, 5g, 10g, or custom amounts)•Telegram Integration: Orders require Telegram username for communication•Order Management: View, cancel, and delete personal orders•Reviews: Leave one review per product with ratings and comments•Profile Display: Animated spinning profile pictures with red glow effectAdmin Features•Order Management: View all orders, approve/reject/cancel orders•User Management: Search users and assign admin roles•Store Control: Toggle store open/close status to prevent new orders•Order Statistics: Dashboard showing pending, approved, rejected, and cancelled orders•Order Deletion: Delete individual orders from the systemTechnical Features•Dark Mode UI: Purple-themed dark mode with animated effects•Animated Effects: Spinning profile pictures, red glow, grainy background•Telegram Bot: Automatic order notifications with approve/deny buttons•S3 Storage: Profile pictures and product images stored in S3•Database: MySQL with Drizzle ORM for type-safe queries•Backend API: tRPC for end-to-end type safetySetup InstructionsPrerequisites•Node.js 18+•MySQL database•Telegram Bot Token (optional, for Telegram integration)Environment VariablesCreate a .env file or configure through the Management UI with the following variables:Copy# Database
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
VITE_APP_LOGO=https://your-logo-urlInstallation1.Install Dependenciespnpm install2.Set Up Databasepnpm db:push3.Start Development Serverpnpm dev4.Build for Productionpnpm buildProject StructureCopyv1lefarm/
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── pages/         # Page components
│   │   ├── components/    # Reusable UI components
│   │   ├── lib/           # Utilities and helpers
│   │   └── App.tsx        # Main app routing
│   └── public/            # Static assets
├── server/                # Backend Express server
│   ├── routers.ts         # tRPC procedure definitions
│   ├── db.ts              # Database query helpers
│   ├── telegram.ts        # Telegram bot integration
│   ├── webhooks.ts        # Webhook endpoints
│   └── _core/             # Core server setup
├── drizzle/               # Database schema and migrations
└── package.jsonDatabase SchemaTables•users: User accounts with profile information•products: Product catalog (single "God Complex" product)•orders: Customer orders with status tracking•reviews: Product reviews (one per user)•storeSettings: Store open/close status•telegramSettings: Telegram bot configurationAPI RoutesUser Routes•GET /api/trpc/user.getProfile - Get current user profile•POST /api/trpc/user.updateProfile - Update profile information•POST /api/trpc/user.uploadProfilePicture - Upload profile picture•GET /api/trpc/user.getPublicProfile - Get public profile by user IDProduct Routes•GET /api/trpc/product.getGodComplex - Get the God Complex product•GET /api/trpc/product.getAll - Get all productsOrder Routes•POST /api/trpc/order.create - Create new order•GET /api/trpc/order.getMyOrders - Get user's orders•POST /api/trpc/order.cancel - Cancel pending order•POST /api/trpc/order.delete - Delete order•GET /api/trpc/order.getAll - Get all orders (admin only)•POST /api/trpc/order.updateStatus - Update order status (admin only)Review Routes•POST /api/trpc/review.create - Create review•GET /api/trpc/review.getProductReviews - Get product reviews•POST /api/trpc/review.update - Update review•POST /api/trpc/review.delete - Delete reviewAdmin Routes•POST /api/trpc/admin.setUserRole - Assign admin role•GET /api/trpc/admin.getStats - Get order statistics•GET /api/trpc/admin.searchUsers - Search usersStore Routes•GET /api/trpc/store.getSettings - Get store status•POST /api/trpc/store.toggleStatus - Toggle store open/closeTelegram Bot IntegrationSetup1.Create a Telegram bot using BotFather2.Set the webhook URL to: https://your-domain/api/webhooks/telegram3.Configure TELEGRAM_BOT_TOKEN and TELEGRAM_ADMIN_CHAT_ID environment variablesHow It Works1.When a user places an order, a notification is sent to the admin chat2.Admin can approve, reject, or delete the order using inline buttons3.The order status is updated in the database automatically4.Message is edited to show the action takenQuantity OptionsThe app supports the following quantity options:•Preset: 2g, 2.5g, 5g, 10g•Custom: Any amount above 2g (excluding 1.5g)Order Lifecycle1.Pending: Order created, awaiting admin approval2.Approved: Admin approved the order3.Rejected: Admin rejected the order4.Cancelled: User or admin cancelled the orderOrders older than 5 days are automatically deleted.Security•OAuth authentication through Manus•Role-based access control (user/admin)•Protected tRPC procedures•S3 storage for file uploads•CORS protection•Input validation with ZodStylingThe app uses:•Tailwind CSS for utility-first styling•shadcn/ui for component library•Dark mode with purple color scheme•Custom animations for profile pictures and effectsDevelopmentCode Style•TypeScript for type safety•ESLint for code linting•Prettier for code formattingTesting•Manual testing through the dev server•tRPC provides end-to-end type safetyDeploymentThe application can be deployed to any Node.js hosting platform:1.Build the project: pnpm build2.Set environment variables3.Run migrations: pnpm db:push4.Start the server: pnpm startTroubleshootingDatabase Connection Issues•Verify DATABASE_URL is correct•Ensure MySQL server is running•Check database user permissionsTelegram Bot Not Working•Verify bot token is correct•Check webhook URL is accessible•Ensure admin chat ID is validProfile Picture Upload Issues•Check file size (max 5MB)•Verify file type is supported (JPEG, PNG, WebP, SVG)•Ensure S3 credentials are configuredLicenseProprietary - V1le FarmSupportFor issues or questions, please contact the development team.