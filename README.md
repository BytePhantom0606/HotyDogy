# HotyDogy - Full-Stack Fastfood E-Commerce Application

![HotyDogy Logo](https://img.shields.io/badge/HotyDogy-Savor%20the%20Sizzle!-orange?style=for-the-badge)

A complete, production-ready full-stack web application for a fastfood business, featuring a stunning React frontend, robust Node.js/Express backend, and MongoDB database.

## 🚀 Features

### Frontend (React + Vite)
- **Modern UI/UX**: Beautiful, responsive design with Tailwind CSS
- **Dark/Light Mode**: Toggle between themes with persistent preference
- **Smooth Animations**: Powered by Framer Motion
- **State Management**: Redux Toolkit for global state
- **Data Fetching**: TanStack Query (React Query) for efficient caching
- **Form Handling**: React Hook Form with validation
- **Interactive Components**: Carousels, modals, and dynamic content
- **Real-time Cart**: Persistent shopping cart for logged-in and guest users

### Backend (Node.js + Express)
- **RESTful API**: Well-structured endpoints following best practices
- **Authentication**: JWT-based auth with bcrypt password hashing
- **Database**: MongoDB with Mongoose ODM
- **API Documentation**: Interactive Swagger UI at `/api-docs`
- **Security**: Helmet, CORS, rate limiting, input validation
- **Error Handling**: Centralized error middleware

### Key Functionality
- 🍔 **Menu Browsing**: Search, filter by category/price, view detailed items
- 🛒 **Shopping Cart**: Add/remove items, customize orders, persistent across sessions
- 📦 **Order Placement**: Checkout with delivery/pickup options, guest checkout support
- 👤 **User Accounts**: Registration, login, profile management, order history
- 🎨 **Admin Dashboard**: Manage menu items (CRUD operations) - Admin only
- 📍 **Locations**: Interactive map showing restaurant locations
- 📧 **Contact Form**: Send inquiries via email
- 📱 **Fully Responsive**: Works seamlessly on desktop, tablet, and mobile

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI library
- **Vite** - Build tool and dev server
- **Redux Toolkit** - State management
- **TanStack Query** - Server state management
- **React Router** - Navigation
- **Tailwind CSS** - Styling
- **Framer Motion** - Animations
- **React Hook Form** - Form handling
- **React Toastify** - Notifications
- **Axios** - HTTP client
- **React Slick** - Carousel
- **React Leaflet** - Maps

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM
- **JWT** - Authentication
- **Bcrypt.js** - Password hashing
- **Joi** - Validation
- **Swagger** - API documentation
- **Nodemailer** - Email sending
- **Helmet** - Security headers
- **Morgan** - HTTP logging

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js**: Version 18.0.0 or higher
- **npm**: Version 9.0.0 or higher
- **MongoDB**: Local installation or MongoDB Atlas account

You can verify your installations:

```bash
node --version  # Should be v18.0.0 or higher
npm --version   # Should be v9.0.0 or higher
```

## 🔧 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/hotydogy.git
cd hotydogy
```

### 2. Install Dependencies

Install both root and client dependencies:

```bash
npm run install-all
```

Or manually:

```bash
# Install server dependencies
npm install

# Install client dependencies
cd client
npm install
cd ..
```

### 3. Environment Configuration

Create a `.env` file in the root directory:

```bash
cp .env.example .env
```

Edit the `.env` file with your configuration:

```env
# Server Configuration
PORT=80
NODE_ENV=development

# Database Configuration
MONGODB_URI=mongodb://localhost:27017/hotydogy
# Or use MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/hotydogy

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_change_this_in_production
JWT_EXPIRE=7d

# Email Configuration (optional - for contact form)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-password
EMAIL_FROM=noreply@hotydogy.com

# Frontend URL
CLIENT_URL=http://localhost:3000

# Admin Credentials
ADMIN_EMAIL=admin@hotydogy.com
ADMIN_PASSWORD=Admin@123456
```

### 4. Database Setup

#### Option A: Local MongoDB

1. Install MongoDB from [mongodb.com](https://www.mongodb.com/try/download/community)
2. Start MongoDB service:

```bash
# On macOS
brew services start mongodb-community

# On Linux
sudo systemctl start mongod

# On Windows
net start MongoDB
```

#### Option B: MongoDB Atlas (Cloud)

1. Create a free account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a new cluster
3. Get your connection string and update `MONGODB_URI` in `.env`

### 5. Seed the Database

Populate the database with sample data:

```bash
npm run seed
```

This will create:
- **Admin user**: `admin@hotydogy.com` / `Admin@123456`
- **Sample user**: `john@example.com` / `password123`
- **15 menu items** across all categories

## 🚀 Running the Application

### Development Mode

Run both frontend and backend concurrently:

```bash
npm run dev
```

This starts:
- **Backend**: http://localhost:80
- **Frontend**: http://localhost:3000
- **API Docs**: http://localhost:80/api-docs

### Production Mode

Build and run for production:

```bash
# Build the frontend
npm run build

# Start the server
npm start
```

The app will be available at **http://localhost:80**

> **Note**: Port 80 requires sudo/admin privileges on Unix systems. Run with `sudo npm start` if needed, or change `PORT` in `.env` to 3001 or 8080.

## 📚 API Documentation

Interactive API documentation is available via Swagger UI:

**Development**: http://localhost:80/api-docs

### Key Endpoints

#### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (protected)
- `PUT /api/auth/update` - Update profile (protected)

#### Menu
- `GET /api/menu` - Get all menu items (with filters)
- `GET /api/menu/:id` - Get single menu item
- `POST /api/menu` - Create menu item (admin only)
- `PUT /api/menu/:id` - Update menu item (admin only)
- `DELETE /api/menu/:id` - Delete menu item (admin only)

#### Cart
- `GET /api/cart` - Get user's cart
- `POST /api/cart` - Add item to cart
- `PUT /api/cart/:itemId` - Update cart item
- `DELETE /api/cart/:itemId` - Remove item from cart
- `DELETE /api/cart` - Clear cart

#### Orders
- `POST /api/orders` - Create new order
- `GET /api/orders` - Get user's orders (protected)
- `GET /api/orders/:id` - Get single order

#### Contact
- `POST /api/contact` - Send contact message

## 👥 User Accounts

### Admin Account
- **Email**: admin@hotydogy.com
- **Password**: Admin@123456
- **Access**: Full admin dashboard for menu management

### Sample User Account
- **Email**: john@example.com
- **Password**: password123
- **Access**: Regular user features

### Guest Checkout
Users can browse menu and place orders without creating an account.

## 🗂️ Project Structure

```
hotydogy/
├── client/                 # React frontend
│   ├── public/            # Static files
│   ├── src/
│   │   ├── components/    # Reusable components
│   │   │   ├── common/    # Common components (Loading, ProtectedRoute)
│   │   │   ├── layout/    # Layout components (Navbar, Footer)
│   │   │   └── menu/      # Menu-specific components
│   │   ├── pages/         # Page components
│   │   │   ├── admin/     # Admin pages
│   │   │   ├── Home.jsx
│   │   │   ├── Menu.jsx
│   │   │   ├── Cart.jsx
│   │   │   ├── Checkout.jsx
│   │   │   └── ...
│   │   ├── services/      # API service functions
│   │   ├── store/         # Redux store and slices
│   │   ├── utils/         # Utility functions
│   │   ├── App.jsx        # Main app component
│   │   ├── main.jsx       # Entry point
│   │   └── index.css      # Global styles
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
├── server/                # Node.js backend
│   ├── config/           # Configuration files
│   ├── middleware/       # Custom middleware
│   │   ├── auth.js       # Authentication middleware
│   │   ├── errorHandler.js
│   │   └── rateLimiter.js
│   ├── models/           # Mongoose models
│   │   ├── User.js
│   │   ├── MenuItem.js
│   │   ├── Order.js
│   │   └── Cart.js
│   ├── routes/           # API routes
│   │   ├── auth.js
│   │   ├── menu.js
│   │   ├── cart.js
│   │   ├── order.js
│   │   └── contact.js
│   ├── seed.js           # Database seeder
│   └── server.js         # Server entry point
├── .env.example          # Environment variables template
├── .gitignore
├── package.json
└── README.md
```

## 🔐 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Password Hashing**: Bcrypt with salt rounds
- **Input Validation**: Joi and express-validator
- **Rate Limiting**: Prevents brute-force attacks
- **Helmet**: Security headers
- **CORS**: Configured cross-origin requests
- **MongoDB Injection Prevention**: Mongoose sanitization

## 🎨 Design Features

- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Dark Mode**: System preference detection + manual toggle
- **Smooth Animations**: Page transitions and micro-interactions
- **Loading States**: Spinners and skeleton screens
- **Toast Notifications**: User feedback for all actions
- **Error Boundaries**: Graceful error handling

## 🧪 Testing the Application

### Manual Testing Checklist

1. **Browse Menu**
   - Visit `/menu`
   - Test category filters
   - Search for items
   - View item details

2. **Shopping Cart**
   - Add items to cart
   - Modify quantities
   - Remove items
   - Test persistence across pages

3. **Checkout Flow**
   - Add items to cart
   - Proceed to checkout
   - Fill delivery information
   - Place order
   - View confirmation

4. **User Authentication**
   - Register new account
   - Login
   - View profile and order history
   - Logout

5. **Admin Dashboard**
   - Login as admin
   - Navigate to `/admin`
   - Add/edit/delete menu items
   - View all orders

6. **Additional Pages**
   - Visit About page
   - View Locations with map
   - Submit contact form

## 🐛 Troubleshooting

### Port 80 Access Denied

**Issue**: Cannot bind to port 80 without privileges

**Solutions**:
```bash
# Option 1: Use sudo (Unix/Linux/Mac)
sudo npm start

# Option 2: Change port in .env
PORT=3001

# Option 3: Use authbind (Linux)
authbind --deep npm start
```

### MongoDB Connection Error

**Issue**: Cannot connect to MongoDB

**Solutions**:
1. Ensure MongoDB is running: `brew services list` or `sudo systemctl status mongod`
2. Check connection string in `.env`
3. Verify network access for MongoDB Atlas
4. Check firewall settings

### Frontend Build Errors

**Issue**: Frontend build fails

**Solutions**:
```bash
# Clear cache and reinstall
cd client
rm -rf node_modules package-lock.json
npm install
npm run build
```

### API 404 Errors

**Issue**: API calls return 404

**Solutions**:
1. Verify backend is running on correct port
2. Check proxy configuration in `client/vite.config.js`
3. Ensure API routes are correctly defined

## 📖 Additional Resources

- [React Documentation](https://react.dev/)
- [Express.js Guide](https://expressjs.com/)
- [MongoDB Manual](https://docs.mongodb.com/)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [Redux Toolkit](https://redux-toolkit.js.org/)

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License.

## 👨‍💻 Author

**HotyDogy Team**

- Website: [hotydogy.com](https://hotydogy.com)
- Email: info@hotydogy.com
- GitHub: [@hotydogy](https://github.com/hotydogy)

## 🙏 Acknowledgments

- Images from [Unsplash](https://unsplash.com)
- Icons from [React Icons](https://react-icons.github.io/react-icons/)
- Fonts from [Google Fonts](https://fonts.google.com/)

---

**Savor the Sizzle!** 🌭🔥

For questions or support, please open an issue or contact us at support@hotydogy.com.
