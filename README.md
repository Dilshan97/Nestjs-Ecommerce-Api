# NestJS E-commerce API

A simple yet powerful e-commerce REST API built with [NestJS](https://nestjs.com/), a progressive Node.js framework for building efficient and scalable server-side applications.

## 🚀 Features

- **User Management**
  - User registration and authentication
  - JWT-based authentication
  - Role-based access control (Admin, Customer)
  - User profile management

- **Product Management**
  - CRUD operations for products
  - Product categories and subcategories
  - Product search and filtering
  - Inventory management
  - Product image handling

- **Shopping Cart**
  - Add/remove items from cart
  - Update item quantities
  - Cart persistence
  - Cart calculation (subtotal, tax, total)

- **Order Management**
  - Place orders from cart
  - Order history tracking
  - Order status management
  - Order confirmation emails

- **Admin Features**
  - Admin dashboard endpoints
  - Product management
  - Order management
  - User management
  - Sales analytics

## 🛠️ Tech Stack

- **Framework**: [NestJS](https://nestjs.com/)
- **Language**: TypeScript
- **Database**: MongoDB/PostgreSQL/MySQL (configurable)
- **ORM**: TypeORM/Mongoose
- **Authentication**: JWT (JSON Web Tokens)
- **Validation**: class-validator
- **Documentation**: Swagger/OpenAPI
- **Testing**: Jest

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v14 or higher)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- Database (MongoDB, PostgreSQL, or MySQL)

## 🚀 Getting Started

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Dilshan97/Nestjs-Ecommerce-Api.git
   cd Nestjs-Ecommerce-Api
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Configuration**
   
   Create a `.env` file in the root directory and add the following variables:
   ```env
   # Application
   PORT=3000
   NODE_ENV=development
   
   # Database
   DB_HOST=localhost
   DB_PORT=5432
   DB_USERNAME=your_username
   DB_PASSWORD=your_password
   DB_DATABASE=ecommerce_db
   
   # JWT
   JWT_SECRET=your_jwt_secret_key
   JWT_EXPIRES_IN=7d
   
   # Email (optional)
   SMTP_HOST=smtp.gmail.com
   SMTP_PORT=587
   SMTP_USER=your_email@gmail.com
   SMTP_PASS=your_app_password
   
   # File Upload (optional)
   MAX_FILE_SIZE=5000000
   UPLOAD_DEST=./uploads
   ```

4. **Database Setup**
   
   Make sure your database is running and accessible. The application will automatically create the necessary tables/collections on first run.

### Running the Application

```bash
# Development mode
npm run start:dev

# Production mode
npm run start:prod

# Debug mode
npm run start:debug
```

The API will be available at `http://localhost:3000`

### API Documentation

Once the application is running, you can access the Swagger API documentation at:
```
http://localhost:3000/api/docs
```

## 🧪 Testing

```bash
# Unit tests
npm run test

# End-to-end tests
npm run test:e2e

# Test coverage
npm run test:cov
```

## 📁 Project Structure

```
src/
├── auth/                 # Authentication module
│   ├── guards/          # Auth guards
│   ├── strategies/      # Passport strategies
│   └── dto/             # Data transfer objects
├── users/               # User management module
├── products/            # Product management module
├── categories/          # Category management module
├── cart/                # Shopping cart module
├── orders/              # Order management module
├── admin/               # Admin-specific endpoints
├── common/              # Shared utilities
│   ├── decorators/      # Custom decorators
│   ├── filters/         # Exception filters
│   ├── guards/          # Custom guards
│   ├── interceptors/    # Custom interceptors
│   └── pipes/           # Custom pipes
├── config/              # Configuration files
├── database/            # Database configuration
└── main.ts              # Application entry point
```

## 🔐 Authentication

The API uses JWT (JSON Web Tokens) for authentication. To access protected endpoints:

1. Register a new user or login with existing credentials
2. Include the JWT token in the Authorization header:
   ```
   Authorization: Bearer <your-jwt-token>
   ```

### User Roles

- **Customer**: Can browse products, manage cart, place orders
- **Admin**: Has all customer permissions plus product/user/order management

## 📊 API Endpoints

### Authentication
- `POST /auth/register` - User registration
- `POST /auth/login` - User login
- `POST /auth/refresh` - Refresh JWT token

### Users
- `GET /users/profile` - Get user profile
- `PUT /users/profile` - Update user profile
- `GET /users` - Get all users (Admin only)

### Products
- `GET /products` - Get all products (with filtering & pagination)
- `GET /products/:id` - Get product by ID
- `POST /products` - Create new product (Admin only)
- `PUT /products/:id` - Update product (Admin only)
- `DELETE /products/:id` - Delete product (Admin only)

### Categories
- `GET /categories` - Get all categories
- `GET /categories/:id` - Get category by ID
- `POST /categories` - Create category (Admin only)
- `PUT /categories/:id` - Update category (Admin only)
- `DELETE /categories/:id` - Delete category (Admin only)

### Cart
- `GET /cart` - Get user's cart
- `POST /cart/items` - Add item to cart
- `PUT /cart/items/:id` - Update cart item quantity
- `DELETE /cart/items/:id` - Remove item from cart
- `DELETE /cart` - Clear cart

### Orders
- `GET /orders` - Get user's order history
- `GET /orders/:id` - Get specific order
- `POST /orders` - Create new order from cart
- `PUT /orders/:id/status` - Update order status (Admin only)

## 🔧 Configuration

The application supports various configuration options through environment variables:

- **Database**: Configure your preferred database connection
- **JWT**: Set your secret key and token expiration
- **File Upload**: Configure file upload limits and destination
- **Email**: Set up SMTP for order confirmations

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Dilshan**
- GitHub: [@Dilshan97](https://github.com/Dilshan97)

## 🙏 Acknowledgments

- [NestJS](https://nestjs.com/) for the amazing framework
- [TypeScript](https://www.typescriptlang.org/) for type safety
- The Node.js community for continuous innovation

## 📞 Support

If you have any questions or issues, please feel free to:

- Open an issue on GitHub
- Contact the author through GitHub

---

⭐ If you found this project helpful, please give it a star on GitHub!
