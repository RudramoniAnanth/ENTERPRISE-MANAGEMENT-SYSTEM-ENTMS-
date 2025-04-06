# Jai Hanuman Traders - Enterprise Management System (EPMS)

## Overview

This repository contains the front-end HTML, CSS, and associated client-side JavaScript code for the Enterprise Management System (EPMS) designed for Jai Hanuman Traders. The system facilitates online presence, customer ordering for cement and steel, and administrative management of inventory, pricing, orders, and customer messages.

**Note:** This system relies heavily on Google Firebase for backend data storage (products, prices, inventory, orders, messages) and potentially authentication. The functionality described assumes a correctly configured Firebase project linked to this front-end code.

## Features

This system provides functionalities for both customers and administrators:

**Customer-Facing:**

* **Public Website (`index.html`):** Displays company information, services (Cement & Steel), team details, client associations, and contact information.
* **Contact Form (`index.html`):** Allows users to submit inquiries directly to the business.
* **Product Ordering (`cement.html`, `steel.html`):**
    * Browse and select specific cement and steel products.
    * Input desired quantity (units).
    * View dynamically calculated total price.
    * Provide customer details and select payment type (Cash/UPI).
    * Preview order details before submission.
    * *(Assumes user is logged in; login mechanism/page `LOGIN.HTML` was not provided).*
* **Order Confirmation (`success.html`):** Displays a success message and order summary upon successful purchase.

**Administrative Features:**

* **Admin Dashboard (`buy.html`):** Central navigation hub linking to various management sections.
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
* **Back-End:** Google Firebase (Realtime Database/Firestore implied for data storage based on JavaScript interactions within HTML files)

## Setup

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd <your-repo-directory>
    ```
2.  **Front-End:** The HTML/CSS/JS files can be served locally using any simple HTTP server (like Python's `http.server`, Node.js `serve`, or VS Code Live Server).
3.  **Back-End (Crucial):**
    * Set up a Google Firebase project.
    * Configure Firebase Realtime Database or Firestore according to the data structures expected by the JavaScript code within the HTML files (e.g., collections/nodes for products, prices, inventory, orders, messages, update logs).
    * Ensure appropriate database security rules are in place.
    * Update the Firebase configuration details within the relevant JavaScript sections of the HTML files to connect the front-end to your Firebase project.

## Usage

* **Customer:** Access `index.html` to view the site. Navigate to `cement.html` or `steel.html` (likely requiring login) to place orders. Use the contact form on `index.html` for inquiries.
* **Administrator:** Access the admin hub `buy.html` (likely requiring login). From there, navigate to manage inventory, update prices, view orders, check messages, and review update logs using the respective pages.

## Key Files

* `index.html`: Main public-facing landing page.
* `buy.html`: Administrator dashboard/navigation hub.
* `cement.html` / `steel.html`: Customer ordering pages for specific products.
* `inventory_stock.html`: Admin page to add new inventory.
* `stock_details.html`: Admin page to view current inventory.
* `cement_price_update.html` / `steel_price_update.html`: Admin pages to update product prices.
* `orders.html`: Admin page to view order history.
* `messages.html`: Admin page to view contact form messages.
* `update_records.html`: Admin page to view price update logs.
* `success.html`: Order confirmation page for customers.
* `/assets/css/`: Contains stylesheets (`style.css`, `buy.css`, `login_register.css`).

## Dependencies

* **Google Firebase:** Required for all dynamic data operations (storing/retrieving product info, prices, inventory, orders, messages).

## Limitations & Notes

* **Login Page (`LOGIN.HTML`) Missing:** The provided files reference a login page, but it is not included. Therefore, the authentication flow and how users access protected customer/admin pages cannot be fully tested or demonstrated with these files alone.
* **Firebase Dependency:** The application's core functionality is entirely dependent on a properly configured Firebase backend. Without it, only the static HTML structure and basic CSS styling will be visible; data loading, saving, and dynamic calculations will not work.
* **Client-Side Logic:** Much of the application logic (price calculation, form handling, Firebase interaction) is embedded within JavaScript inside the HTML files.
