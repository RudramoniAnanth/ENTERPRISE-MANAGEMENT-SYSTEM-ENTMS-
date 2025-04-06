# Jai Hanuman Traders - Enterprise Management System (EPMS)

## Overview

This repository contains the front-end HTML, CSS, and associated client-side JavaScript code for the Enterprise Management System (EPMS) designed for Jai Hanuman Traders. The system facilitates online presence, customer ordering for cement and steel, and administrative management of inventory, pricing, orders, and customer messages.

This system uses Google Firebase for backend data storage (products, prices, inventory, orders, messages) and Firebase Authentication for user login.

**Note:** The functionality described assumes a correctly configured Firebase project (including Authentication and Database/Firestore) linked to this front-end code.

## Features

This system provides functionalities for users (primarily administrators based on the login page) and potentially customers:

**Public / General User:**

* **Public Website (`index.html`):** Displays company information, services (Cement & Steel), team details, client associations, and contact information.
* **Contact Form (`index.html`):** Allows users to submit inquiries directly to the business.

**Authenticated User (Admin Focus):**

* **Admin Authentication (`LOGIN.HTML`):**
    * Provides a secure login form for users (explicitly noted for Admins).
    * Uses Firebase Authentication (Email & Password) to verify credentials.
    * Redirects to the Admin Dashboard (`buy.html`) upon successful login.
    * Provides user-friendly error messages for common login issues.
* **Admin Control Hub (`buy.html`):** Serves as a central dashboard accessible after login, linking to various management sections.
* **Product Ordering (`cement.html`, `steel.html`):**
    * Browse and select specific cement and steel products.
    * Input desired quantity (units).
    * View dynamically calculated total price.
    * Provide necessary details and select payment type (Cash/UPI).
    * Preview order details before submission.
    * *(Accessed after successful login).*
* **Order Confirmation (`success.html`):** Displays a success message and order summary upon successful purchase.
* **Inventory Management:**
    * Add new stock batches (`inventory_stock.html`): Record Batch ID, Product Type, Name, Quantity, Price/Unit, Date.
    * View current stock levels (`stock_details.html`).
* **Price Management (`cement_price_update.html`, `steel_price_update.html`):**
    * View current prices for cement and steel products.
    * Update prices individually for each product.
* **Order Tracking (`orders.html`):** View a detailed history of all customer orders placed through the system.
* **Message Review (`messages.html`):** Access and read messages submitted via the website's contact form.
* **Update Log (`update_records.html`):** View a timestamped log of system changes, primarily focusing on price updates.

## Technology Stack

* **Front-End:** HTML, CSS, JavaScript
* **Back-End:** Google Firebase
    * Firebase Authentication (Email/Password)
    * Firebase Realtime Database / Firestore (implied for data storage based on JavaScript interactions)

## Setup

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd <your-repo-directory>
    ```
2.  **Front-End:** The HTML/CSS/JS files can be served locally using any simple HTTP server (like Python's `http.server`, Node.js `serve`, or VS Code Live Server).
3.  **Back-End (Crucial):**
    * Set up a Google Firebase project.
    * Enable Firebase Authentication (Email/Password provider). Create admin user(s) in the Firebase console.
    * Configure Firebase Realtime Database or Firestore according to the data structures expected by the JavaScript code (e.g., collections/nodes for products, prices, inventory, orders, messages, update logs). Ensure appropriate database security rules.
    * **Important:** Replace the placeholder Firebase configuration details found in `LOGIN.HTML` (and potentially other files) with your actual Firebase project configuration. Consider using environment variables or a separate configuration file for better security practices instead of hardcoding keys directly in the source code.

## Usage

* **Administrator:** Navigate to `LOGIN.HTML`. Enter registered admin email and password to log in. Upon success, you are redirected to `buy.html` (Admin Hub). From there, access various sections to manage inventory, update prices, view orders, check messages, and review update logs. Administrators can also potentially place orders via `cement.html`/`steel.html` after login.
* **General User/Customer:** Access `index.html` to view the site and use the contact form. The ordering process (`cement.html`, `steel.html`) requires login via `LOGIN.HTML`. (Note: The current login page is explicitly marked for Admins; customer-specific registration or login flows are not present in the provided files).

## Key Files

* `index.html`: Main public-facing landing page.
* `LOGIN.HTML`: Admin login page using Firebase Authentication.
* `buy.html`: Administrator dashboard/navigation hub (post-login).
* `cement.html` / `steel.html`: Product ordering pages (post-login).
* `inventory_stock.html`: Admin page to add new inventory.
* `stock_details.html`: Admin page to view current inventory.
* `cement_price_update.html` / `steel_price_update.html`: Admin pages to update product prices.
* `orders.html`: Admin page to view order history.
* `messages.html`: Admin page to view contact form messages.
* `update_records.html`: Admin page to view price update logs.
* `success.html`: Order confirmation page for customers.
* `/assets/css/`: Contains stylesheets (`style.css`, `buy.css`, `login_register.css`).

## Dependencies

* **Google Firebase:** Required for Authentication and all dynamic data operations.

## Limitations & Notes

* **Firebase Configuration:** Sensitive Firebase API keys and project details are hardcoded in `LOGIN.HTML`. For production or shared environments, these should be externalized (e.g., using environment variables).
* **Admin-Focused Login:** The provided `LOGIN.HTML` specifically mentions it's for admins.
* **Firebase Backend :** The application's core functionality is entirely dependent on a properly configured Firebase backend. Without it, only static page content will display, and login/data operations will fail.
* **Admin-Centralisation :** As this application is intended to manage all the works such as Inventory Management, Sales, Price Updates so the main role is played by the admin itself so there wont be much user or customer functionalities.

## Project Update

We are currently undergoing a significant update to this project. This involves transitioning to a PHP backend with an SQL database.

The update focuses on:

* **Enhancements:** Improving existing features and adding new functionalities.
* **UI Improvements:** Creating a more user-friendly and intuitive interface.
* **Better Functioning:** Optimizing performance and ensuring a more robust application.

Stay tuned for further updates!
