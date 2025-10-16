# HotyDogy - Premium Fast Food Website

<div align="center">

![HotyDogy Logo](https://via.placeholder.com/200x200/f97316/ffffff?text=HotyDogy)

**A modern, production-ready fast food ordering website**

Built with React, Node.js, Express, MongoDB, and Tailwind CSS

[Demo](#) | [Documentation](#installation) | [Report Bug](#) | [Request Feature](#)

</div>

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Deployment on Port 80](#deployment-on-port-80)
- [Configuration](#configuration)
- [API Documentation](#api-documentation)
- [Screenshots](#screenshots)
- [Troubleshooting](#troubleshooting)
- [License](#license)

---

## 🍔 About

**HotyDogy** is a professional, production-level fast food website that provides a complete online ordering experience. Customers can browse the menu, add items to cart, place orders, and track their order status. The admin dashboard allows restaurant staff to manage orders in real-time.

---

## ✨ Features

### Customer Features
- 🏠 **Beautiful Home Page** - Modern hero section with animations
- 🍽️ **Dynamic Menu** - Browse hot dogs, burgers, fries, and drinks
- 🛒 **Shopping Cart** - Add/remove items, update quantities
- 💳 **Checkout System** - Complete order form with validation
- 📦 **Order Tracking** - Track orders by order number
- 🌙 **Dark/Light Theme** - Toggle between themes
- 📱 **Responsive Design** - Works on desktop, tablet, and mobile
- 🎨 **Smooth Animations** - Framer Motion animations throughout

### Admin Features
- 📊 **Dashboard** - View statistics and metrics
- 📋 **Order Management** - View and update order statuses
- 💰 **Revenue Tracking** - Monitor total revenue
- 🔄 **Real-time Updates** - Refresh orders on demand

### Technical Features
- ⚡ **Fast Performance** - Optimized with Vite
- 🔐 **API Validation** - Express validator for data integrity
- 💾 **MongoDB Database** - Persistent data storage
- 🎯 **RESTful API** - Clean API architecture
- 🔄 **Auto-reload** - Hot module replacement in development

---

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI library
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Utility-first CSS framework
- **Framer Motion** - Animation library
- **Lucide React** - Icon library
- **Axios** - HTTP client
- **React Router** - Navigation
- **React Hot Toast** - Notifications

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **CORS** - Cross-origin resource sharing
- **Morgan** - HTTP request logger
- **Dotenv** - Environment variables

---

## 📁 Project Structure

```
/var/www/fastfood/
├── backend/
│   ├── models/
│   │   ├── MenuItem.js          # Menu item schema
│   │   └── Order.js              # Order schema
│   ├── routes/
│   │   ├── menu.js               # Menu API routes
│   │   └── orders.js             # Order API routes
│   ├── server.js                 # Express server
│   ├── package.json              # Backend dependencies
│   └── .env                      # Environment variables
│
├── frontend/
│   ├── public/
│   │   ├── favicon.svg           # HotyDogy favicon
│   │   └── favicon.ico           # Icon symlink
│   ├── src/
│   │   ├── components/
│   │   │   ├── Navbar.jsx        # Navigation bar
│   │   │   └── Footer.jsx        # Footer component
│   │   ├── context/
│   │   │   ├── ThemeContext.jsx  # Theme provider
│   │   │   └── CartContext.jsx   # Cart state management
│   │   ├── pages/
│   │   │   ├── Home.jsx          # Landing page
│   │   │   ├── Menu.jsx          # Menu page
│   │   │   ├── Cart.jsx          # Shopping cart & checkout
│   │   │   ├── Contact.jsx       # Contact page
│   │   │   ├── OrderTracking.jsx # Track orders
│   │   │   └── Admin.jsx         # Admin dashboard
│   │   ├── services/
│   │   │   └── api.js            # API service layer
│   │   ├── App.jsx               # Main app component
│   │   ├── main.jsx              # Entry point
│   │   └── index.css             # Global styles
│   ├── index.html                # HTML template
│   ├── vite.config.js            # Vite configuration
│   ├── tailwind.config.js        # Tailwind configuration
│   ├── postcss.config.js         # PostCSS configuration
│   ├── package.json              # Frontend dependencies
│   └── .env                      # Frontend env variables
│
└── README.md                     # This file
```

---

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v16 or higher) - [Download](https://nodejs.org/)
- **npm** (comes with Node.js)
- **MongoDB** (v5 or higher) - [Installation Guide](https://www.mongodb.com/docs/manual/installation/)
- **Nginx** or **Apache** (for port 80 deployment)
- **Git** (optional, for cloning)

### Check Installed Versions

```bash
node --version    # Should be v16+
npm --version     # Should be 8+
mongod --version  # Should be 5.0+
```

---

## 🚀 Installation

### Step 1: Clone or Navigate to Project Directory

```bash
cd /var/www/fastfood
```

If you need to set proper permissions:

```bash
sudo chown -R $USER:$USER /var/www/fastfood
```

### Step 2: Install Backend Dependencies

```bash
cd /var/www/fastfood/backend
npm install
```

Expected packages:
- express
- mongoose
- cors
- dotenv
- morgan
- express-validator

### Step 3: Install Frontend Dependencies

```bash
cd /var/www/fastfood/frontend
npm install
```

Expected packages:
- react
- react-dom
- react-router-dom
- framer-motion
- lucide-react
- axios
- react-hot-toast
- vite
- tailwindcss

### Step 4: Start MongoDB

**On Ubuntu/Kali Linux:**

```bash
# Start MongoDB service
sudo systemctl start mongod

# Enable MongoDB to start on boot
sudo systemctl enable mongod

# Check MongoDB status
sudo systemctl status mongod
```

**Verify MongoDB is running:**

```bash
mongo --eval 'db.runCommand({ connectionStatus: 1 })'
```

Or for MongoDB 6+:

```bash
mongosh --eval 'db.runCommand({ connectionStatus: 1 })'
```

---

## 🎯 Running the Application

### Development Mode

#### Terminal 1: Start Backend Server

```bash
cd /var/www/fastfood/backend
npm run dev
# OR
npm start
```

Backend will run on: **http://localhost:5000**

#### Terminal 2: Start Frontend Dev Server

```bash
cd /var/www/fastfood/frontend
npm run dev
```

Frontend will run on: **http://localhost:3000**

### Access the Application

- **Frontend:** http://localhost:3000
- **Backend API:** http://localhost:5000/api
- **API Health Check:** http://localhost:5000/api/health

---

## 🌐 Deployment on Port 80

To deploy the application on **port 80** and make it accessible as a production website, follow these steps:

### Option 1: Using Nginx (Recommended)

#### Step 1: Build Frontend for Production

```bash
cd /var/www/fastfood/frontend
npm run build
```

This creates an optimized production build in `/var/www/fastfood/frontend/dist`

#### Step 2: Install Nginx

```bash
sudo apt update
sudo apt install nginx -y
```

#### Step 3: Create Nginx Configuration

Create a new config file:

```bash
sudo nano /etc/nginx/sites-available/hotydogy
```

Add the following configuration:

```nginx
server {
    listen 80;
    listen [::]:80;
    server_name localhost hotydogy.local;

    # Frontend - Serve static files
    location / {
        root /var/www/fastfood/frontend/dist;
        try_files $uri $uri/ /index.html;
        add_header Cache-Control "public, max-age=3600";
    }

    # Backend API - Proxy to Node.js
    location /api {
        proxy_pass http://localhost:5000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_cache_bypass $http_upgrade;
    }

    # Security headers
    add_header X-Frame-Options "SAMEORIGIN" always;
    add_header X-Content-Type-Options "nosniff" always;
    add_header X-XSS-Protection "1; mode=block" always;

    # Gzip compression
    gzip on;
    gzip_vary on;
    gzip_min_length 1024;
    gzip_types text/plain text/css text/xml text/javascript application/x-javascript application/xml+rss application/json;
}
```

#### Step 4: Enable the Site

```bash
# Create symbolic link
sudo ln -s /etc/nginx/sites-available/hotydogy /etc/nginx/sites-enabled/

# Remove default site (optional)
sudo rm /etc/nginx/sites-enabled/default

# Test Nginx configuration
sudo nginx -t

# Restart Nginx
sudo systemctl restart nginx
```

#### Step 5: Create Backend Service (systemd)

Create a systemd service for the backend:

```bash
sudo nano /etc/systemd/system/hotydogy-backend.service
```

Add the following:

```ini
[Unit]
Description=HotyDogy Backend API
After=network.target mongodb.service

[Service]
Type=simple
User=www-data
WorkingDirectory=/var/www/fastfood/backend
Environment=NODE_ENV=production
Environment=PORT=5000
ExecStart=/usr/bin/node server.js
Restart=on-failure
RestartSec=10

[Install]
WantedBy=multi-user.target
```

#### Step 6: Start Backend Service

```bash
# Reload systemd
sudo systemctl daemon-reload

# Start the backend service
sudo systemctl start hotydogy-backend

# Enable to start on boot
sudo systemctl enable hotydogy-backend

# Check status
sudo systemctl status hotydogy-backend
```

#### Step 7: Set Permissions

```bash
sudo chown -R www-data:www-data /var/www/fastfood
sudo chmod -R 755 /var/www/fastfood
```

#### Step 8: Access the Website

Open your browser and navigate to:

```
http://localhost
```

Or use your server's IP address:

```
http://YOUR_SERVER_IP
```

---

### Option 2: Using Apache

#### Step 1: Install Apache and Enable Modules

```bash
sudo apt update
sudo apt install apache2 -y
sudo a2enmod proxy proxy_http rewrite
```

#### Step 2: Create Apache Configuration

```bash
sudo nano /etc/apache2/sites-available/hotydogy.conf
```

Add:

```apache
<VirtualHost *:80>
    ServerName localhost
    DocumentRoot /var/www/fastfood/frontend/dist

    <Directory /var/www/fastfood/frontend/dist>
        Options -Indexes +FollowSymLinks
        AllowOverride All
        Require all granted

        # React Router support
        RewriteEngine On
        RewriteBase /
        RewriteRule ^index\.html$ - [L]
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteRule . /index.html [L]
    </Directory>

    # Proxy API requests to backend
    ProxyPreserveHost On
    ProxyPass /api http://localhost:5000/api
    ProxyPassReverse /api http://localhost:5000/api

    ErrorLog ${APACHE_LOG_DIR}/hotydogy_error.log
    CustomLog ${APACHE_LOG_DIR}/hotydogy_access.log combined
</VirtualHost>
```

#### Step 3: Enable Site and Restart Apache

```bash
sudo a2ensite hotydogy
sudo a2dissite 000-default
sudo systemctl restart apache2
```

Follow Step 5-7 from Nginx section for backend service setup.

---

## ⚙️ Configuration

### Backend Environment Variables

Edit `/var/www/fastfood/backend/.env`:

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/hotydogy
NODE_ENV=production
```

### Frontend Environment Variables

Edit `/var/www/fastfood/frontend/.env`:

```env
VITE_API_URL=/api
```

---

## 📡 API Documentation

### Menu Endpoints

#### Get All Menu Items
```
GET /api/menu
Query params: ?category=hotdogs|burgers|fries|drinks (optional)
```

#### Get Single Menu Item
```
GET /api/menu/:id
```

#### Get Items by Category
```
GET /api/menu/category/:category
```

### Order Endpoints

#### Create Order
```
POST /api/order
Body: {
  customerName: string,
  customerEmail: string,
  customerPhone: string,
  deliveryAddress: string,
  paymentMethod: 'cash'|'card'|'online',
  items: [{
    menuItem: ObjectId,
    name: string,
    price: number,
    quantity: number
  }],
  totalPrice: number,
  notes: string
}
```

#### Get Order by ID/Number
```
GET /api/order/:id
```

#### Get All Orders (Admin)
```
GET /api/order
Query params: ?status=pending&limit=50&page=1
```

#### Update Order Status
```
PATCH /api/order/:id/status
Body: { status: 'pending'|'preparing'|'ready'|'delivered'|'cancelled' }
```

### Health Check
```
GET /api/health
```

---

## 🖼️ Screenshots

### Home Page
Modern hero section with call-to-action buttons and animated elements.

### Menu Page
Grid layout with category filters and add-to-cart functionality.

### Shopping Cart
Cart management with quantity updates and checkout form.

### Admin Dashboard
Order management with statistics and status updates.

---

## 🐛 Troubleshooting

### MongoDB Connection Error

```bash
# Check if MongoDB is running
sudo systemctl status mongod

# View MongoDB logs
sudo tail -f /var/log/mongodb/mongod.log

# Restart MongoDB
sudo systemctl restart mongod
```

### Backend Won't Start

```bash
# Check logs
sudo journalctl -u hotydogy-backend -n 50

# Check if port 5000 is in use
sudo lsof -i :5000

# Restart service
sudo systemctl restart hotydogy-backend
```

### Nginx Configuration Error

```bash
# Test configuration
sudo nginx -t

# View error logs
sudo tail -f /var/log/nginx/error.log

# Restart Nginx
sudo systemctl restart nginx
```

### Port 80 Access Denied

```bash
# Check if port 80 is already in use
sudo lsof -i :80

# Stop Apache if running
sudo systemctl stop apache2

# Ensure Nginx has proper permissions
sudo chown -R www-data:www-data /var/www/fastfood
```

### Frontend Build Errors

```bash
# Clear node_modules and reinstall
cd /var/www/fastfood/frontend
rm -rf node_modules package-lock.json
npm install

# Rebuild
npm run build
```

---

## 🔧 Useful Commands

```bash
# View backend logs
sudo journalctl -u hotydogy-backend -f

# View Nginx access logs
sudo tail -f /var/log/nginx/access.log

# Restart all services
sudo systemctl restart mongod
sudo systemctl restart hotydogy-backend
sudo systemctl restart nginx

# Check service status
sudo systemctl status mongod
sudo systemctl status hotydogy-backend
sudo systemctl status nginx

# Rebuild frontend and reload
cd /var/www/fastfood/frontend
npm run build
sudo systemctl reload nginx
```

---

## 📝 License

This project is licensed under the MIT License.

---

## 👨‍💻 Development Team

- **HotyDogy Development Team**
- Email: info@hotydogy.com
- Website: http://localhost

---

## 🎉 Acknowledgments

- React Team for an amazing library
- Tailwind CSS for the utility framework
- Framer Motion for smooth animations
- MongoDB team for the database
- Express.js community

---

<div align="center">

**Made with ❤️ by the HotyDogy Team**

⭐ Star this project if you found it helpful!

</div>
