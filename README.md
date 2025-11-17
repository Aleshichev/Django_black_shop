## E-Commerce Shop - Django Web Application
A full-featured e-commerce web application built with Django 5.2, featuring product catalog, shopping cart, user authentication, order management, and Stripe payment integration.

### Technology Stack
Framework: Django 5.2.7  
Database: PostgreSQL  
Image Processing: Pillow 12.0.0  
Database Driver: psycopg2-binary 2.9.11  
Frontend: Bootstrap 5, Custom CSS  
Payment: Stripe API (configured via environment variables)  

### Customer Features
- Product Catalog: Browse products by categories with pagination
- Product Details: View detailed product information with images
- Shopping Cart: Session-based cart with add/remove/quantity management
- User Authentication: Registration, login, logout, and profile management
- Order System: Create orders with delivery information
- Payment Integration: Stripe payment gateway (ready for integration)
- Discount System: Products can have percentage-based discounts

### User Profile:  
- Upload profile images  
- View order history  
- Update personal information  

### Admin Features  
Django Admin Panel: Full CRUD operations for:
- Products (name, price, description, images, availability, discounts)
- Categories
- Orders and Order Items
- Users

### Project Structure
```
.
├── config/                    # Project configuration
│   ├── settings.py           # Django settings
│   ├── urls.py               # Root URL configuration
│   └── wsgi.py               # WSGI configuration
├── main/                      # Main shop app
│   ├── models.py             # Category and Product models
│   ├── views.py              # Product list and detail views
│   ├── admin.py              # Admin configuration
│   └── templates/            # Shop templates
│       ├── base.html
│       └── product/
├── cart/                      # Shopping cart app
│   ├── cart.py               # Cart class with session storage
│   ├── views.py              # Cart operations
│   ├── forms.py              # Add to cart form
│   └── context_processors.py # Cart context for templates
├── users/                     # User management app
│   ├── models.py             # Custom User model
│   ├── forms.py              # Login, registration, profile forms
│   ├── views.py              # Authentication views
│   └── templates/            # User templates
├── orders/                    # Order management app
│   ├── models.py             # Order and OrderItem models
│   ├── forms.py              # Order creation form
│   └── views.py              # Order processing
├── payment/                   # Payment app (Stripe integration)
└── manage.py
```

### Environment Variables
Create a .env file in the project root:  
```
# Stripe Configuration (optional, for payment integration)
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_webhook_secret
STRIPE_PUBLISHABLE_KEY=your_publishable_key
STRIPE_API_VERSION=2024-06-20
```
### Admin Panel
- Access admin panel at http://localhost:8000/admin/
- Login with superuser credentials
- Add categories and products
- Manage orders and users

### Customer Flow  
1.Browse Products: Visit /shop to see all products  
2.Filter by Category: Click category names in sidebar  
3.View Details: Click on product to see details  
4.Add to Cart: Select quantity and add to cart  
5.View Cart: Click cart icon in header  
6.Checkout: Click "Checkout" button 
7.Create Account/Login: Register or login to proceed  
8.Enter Delivery Info: Fill order form  
9.Payment: Process payment (Stripe integration)  
10.View Orders: Check profile for order history  

## URL Structure
```
/                          # Homepage (popular products)
/shop/                     # All products list
/shop/<slug>/              # Product detail
/shop/category/<slug>/     # Category filtered products
/cart/                     # Shopping cart
/cart/add/<id>/            # Add to cart (POST)
/cart/remove/<id>/         # Remove from cart (POST)
/user/login/               # User login
/user/registration/        # User registration
/user/profile/             # User profile and orders
/user/logout/              # Logout
/orders/create/            # Create order
/admin/                    # Django admin panel
```

### License
This project is provided as-is for educational purposes. 
### Author
Igor Aleshichev - Aleshichev.git@email.ua  
