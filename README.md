**👗 Drape Store - Style That Speaks**
Discover Your Style. Define Your Identity.

Drape Store is a modern fashion e-commerce platform designed to make online clothing shopping effortless, elegant, and enjoyable. From everyday essentials to statement outfits, Drape Store brings a curated fashion experience right to your fingertips.

Built with React, Node.js, Express, and MongoDB, the platform combines a beautiful customer-facing storefront with a powerful admin dashboard for managing products, customers, orders, and the overall shopping experience.

<p align="center">
<img src="https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black" />
<img src="https://img.shields.io/badge/Node.js-Express-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" />
<img src="https://img.shields.io/badge/MongoDB-Database-47A248?style=for-the-badge&logo=mongodb&logoColor=white" />
<img src="https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
<img src="https://img.shields.io/badge/Vercel-Deployment-000000?style=for-the-badge&logo=vercel&logoColor=white" />
</p>

✨ About Drape Store

Fashion is more than clothing. It's a way to express who you are.

Drape Store is built around that idea, offering a seamless online shopping experience where customers can explore collections, discover new styles, manage their shopping carts, and place orders with ease.

Whether it's casual wear, everyday essentials, seasonal collections, or statement fashion, Drape Store provides a flexible foundation for a modern clothing brand.

🌟 Key Features
🛍️ Shopping Experience
Browse a curated collection of clothing and fashion products.
Explore product details, images, descriptions, and pricing.
Filter, sort, and discover products with ease.
Add products to your shopping cart.
Manage cart quantities and remove unwanted items.
Save favorite products to a personal wishlist.
Enjoy a responsive shopping experience across devices.
👤 Customer Account
Secure customer registration and login.
JWT-based authentication.
Personalized customer dashboard.
Manage personal profile information.
Update account passwords.
Save and manage delivery addresses.
View order history and order details.
Track order status.
Manage wishlist items.
📦 Order Management
Smooth checkout experience.
Cash on Delivery (COD) support.
Submit and manage customer orders.
View order details and status.
Cancel eligible orders.
Admin-controlled order status updates.
🔐 Admin Dashboard

A dedicated workspace that gives administrators control over the entire store.

Add, edit, and delete clothing products.
Manage product descriptions, prices, and image URLs.
Manage customer accounts.
View and manage customer orders.
Update order statuses.
View and manage customer messages.
Publish and manage Drape Store Journal articles.
Manage store content from a centralized dashboard.
📰 Drape Store Journal
Publish fashion-related articles and updates.
Create articles with title-based URLs.
Add optional links to original articles or posts.
Manage published content through the admin workspace.
Share fashion inspiration, styling ideas, and collection updates.
🛡️ Security & Reliability
JWT authentication.
Separate customer and admin authentication secrets.
Password hashing.
Role-based access control.
API rate limiting.
Input sanitization.
Security headers.
Protected administrative routes.
MongoDB-backed persistent storage.
🧰 Tech Stack
Technology	Purpose
React 19	Frontend user interface
React Router	Client-side navigation
JavaScript	Application logic
Node.js	Backend runtime
Express.js	REST API
MongoDB	Database
Mongoose	Database modeling
JWT	Authentication
Socket.IO	Realtime communication
Vercel	Frontend deployment
CSS	Responsive styling
📁 Project Structure
text
Drape-Store/
│
├── client/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── context/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── styles/
│   │   └── App.js
│   │
│   ├── package.json
│   ├── vercel.json
│   └── README.md
│
├── server/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── scripts/
│   │   └── server.js
│   │
│   ├── .env.example
│   └── package.json
│
└── README.md


Note: The structure above illustrates the main application areas. Actual filenames and folders may vary depending on the repository.

🚀 Getting Started

Follow these steps to run Drape Store locally.

Prerequisites

Make sure you have installed:

Node.js
npm
MongoDB
Git
A modern web browser
1. Clone the Repository
bash
git clone YOUR_REPOSITORY_URL
cd Drape-Store


Replace YOUR_REPOSITORY_URL with your actual GitHub repository URL.

2. Configure the Backend

Copy the example environment file:

powershell
Copy-Item server/.env.example server/.env


Navigate to the server directory:

bash
cd server


Install dependencies:

bash
npm install


Configure your server/.env file:

env
PORT=5000
NODE_ENV=development

MONGO_URI=mongodb://127.0.0.1:27017/drape-store

CLIENT_URL=http://localhost:3000

JWT_SECRET=your_customer_secret
JWT_ADMIN_SECRET=your_admin_secret

JWT_USER_EXPIRES_IN=7d
JWT_ADMIN_EXPIRES_IN=2h

ADMIN_BOOTSTRAP_EMAIL=admin@example.com
ADMIN_BOOTSTRAP_PASSWORD=your_strong_password


Generate secure JWT secrets using:

bash
node --input-type=module -e "import { randomBytes } from 'node:crypto'; console.log(randomBytes(48).toString('hex'))"


Use separate generated values for customer and administrator authentication.

Start the backend:

bash
npm run dev


Backend URL:

text
http://localhost:5000


API health check:

text
http://localhost:5000/api/health

3. Create the First Administrator

From the server directory, run:

bash
node src/scripts/createAdmin.js


This creates the initial administrator using the bootstrap credentials configured in your environment.

Keep administrator credentials private.

4. Configure the Frontend

Open another terminal:

bash
cd client


Install frontend dependencies:

bash
npm install


If required, create a client .env file:

env
REACT_APP_BACKEND_URL=http://localhost:5000/api


Start the frontend:

bash
npm start


Your storefront will be available at:

text
http://localhost:3000


You're ready to explore Drape Store!

☁️ Deployment

Drape Store supports separate frontend and backend deployments.

Frontend — Vercel
Import the repository into Vercel.
Set the project root directory to client/.
Configure the required frontend environment variables.
Deploy the application.

The project includes a Vercel configuration for client-side routing, asset caching, and security headers.

Backend — Vercel or Node.js Hosting
Configure the project root as server/ if deploying the API separately to Vercel.
Add the required environment variables.
Connect a persistent MongoDB database.
Configure CLIENT_URL with your deployed frontend origin.
Deploy the API.

Important: The current Vercel serverless export supports REST routes only. Socket.IO requires a persistent Node.js server deployment.

🔌 API Overview

All API endpoints use the /api prefix.

Module	Endpoint	Description
Health	GET /api/health	API status
Auth	/api/auth/register	Customer registration
Auth	/api/auth/login	Customer login
Auth	/api/auth/admin/login	Admin login
Auth	/api/auth/me	Current authenticated user
Auth	/api/auth/logout	Logout
Products	GET /api/products	Browse clothing products
Products	GET /api/products/:id	Product details
Orders	/api/orders	Order management
Users	/api/users	Customer account management
Messages	/api/messages	Customer messages

Protected endpoints require a valid bearer token in the Authorization header.

Additional administrative routes support product, order, user, and message management.

🛠️ Useful Development Commands
Frontend
bash
cd client

# Start development server
npm start

# Create production build
npm run build

# Run tests
npm test

Backend
bash
cd server

# Start development server
npm run dev

# Start production server
npm start

📌 Current Project Scope

The following are important implementation details:

Checkout currently supports Cash on Delivery.
No third-party payment gateway is connected.
Product images are managed through image URLs.
Image uploading and dedicated media hosting are not included.
Socket.IO is available for supported persistent server deployments.
The Vercel serverless backend currently serves REST endpoints only.
Public page metadata updates in the browser after the application loads.
🔮 Future Improvements

Drape Store is designed to grow into a more complete fashion commerce platform.

Potential future enhancements include:

Product categories such as Men's Wear, Women's Wear, and Accessories.
Product sizes (XS, S, M, L, XL, XXL).
Product color variations.
Inventory and stock management.
Advanced product search.
Product reviews and ratings.
Discount codes and promotional campaigns.
Secure online payments.
Product image uploading and cloud storage.
Shipping and delivery integrations.
Email order confirmations.
Sales analytics and reporting.
Recently viewed products.
Personalized product recommendations.
Enhanced mobile shopping experience.
🔒 Security Guidelines
Never commit .env files.
Use strong, randomly generated JWT secrets.
Keep customer and administrator secrets separate.
Use HTTPS in production.
Restrict MongoDB access to trusted services.
Protect administrative credentials.
Validate and sanitize user input.
Remove unused administrator bootstrap credentials after initial setup.
Keep dependencies updated.
👨‍💻 Author

Created and developed by Arthur

Passionate about building modern web applications, elegant interfaces, and practical digital experiences.

Project: Drape Store
Developer: Arthur
Focus: Full-Stack Web Development
Stack: MERN (MongoDB, Express, React, Node.js)
🤝 Contributing

Contributions, suggestions, and improvements are welcome!

If you would like to contribute:

Fork this repository.
Create a new feature branch.
Make your changes.
Commit your improvements.
Submit a pull request.

Please ensure your changes are tested before submitting.

📄 License

This project is currently available for personal and educational development.

Add a LICENSE file to the repository if you intend to distribute it under a specific open-source license.

<p align="center">
<strong>DRAPE STORE</strong>
<br />
<em>Wear Your Confidence. Define Your Style.</em>
<br /><br />
Made with ❤️ by Arthur
</p>
