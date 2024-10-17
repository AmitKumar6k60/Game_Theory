# Sports Booking Application

The **Sports Booking Application** is a web-based platform that allows users to browse and book sports facilities across different centers. Users can view available resources (e.g., courts, fields) and make bookings for specific time slots. The application includes CRUD operations for resources and bookings, ensuring efficient management of sports venues.

## Table of Contents
- [Deployment](#deployement)
- [Images](#images)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [API Endpoints](#api-endpoints)
- [Setup and Installation](#setup-and-installation)

---
## Deployement

   Frontend and Backend facing problem to communicate because of error :  net::ERR_SSL_PROTOCOL_ERROR , was unable to resolve in given time.
   
   Frontend Deployed on vercel : https://game-theory-frontend.vercel.app/ 
   
   Backend Deployed on AWS with PublicIPs: 13.60.199.62
   
   The application is functioning properly on localhost.
   
---

## Images
![Screenshot 2024-10-17 at 1 32 15 AM (2)](https://github.com/user-attachments/assets/9635a457-e447-4a16-853e-93aa0bc8fb2b)
![Screenshot 2024-10-17 at 1 33 40 AM (2)](https://github.com/user-attachments/assets/0b386db0-d27e-40de-a1e8-0befc96efb83)
![Screenshot 2024-10-17 at 1 34 07 AM (2)](https://github.com/user-attachments/assets/70e5a154-33a8-40e9-91d1-e4e84f6a2036)
![Screenshot 2024-10-17 at 1 34 32 AM (2)](https://github.com/user-attachments/assets/3c807b68-014a-44d1-a2fc-216a48f773a7)
![Screenshot 2024-10-17 at 1 35 04 AM (2)](https://github.com/user-attachments/assets/123fd2d6-fa3a-490b-b6d2-42e4fcd9488f)

---
## Features

- View available resources by sport and center.
- Make bookings for available time slots, avoiding conflicts.
- Admin-side functionality for resource management (add, delete resources).
- Error handling for booking conflicts and invalid data.

---

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MySQL or PostgreSQL (via Sequelize ORM)
- **Frontend**: React
- **ORM**: Sequelize (for handling database models and queries)
- **Middleware**: Express, Body-parser
- **Environment**: Node.js runtime

---

## Project Structure

```bash
sports-booking-backend/
├── config/
│   └── db.js                 # Database configuration (Sequelize)
├── controllers/
│   ├── bookingController.js   # Controller for handling bookings
│   ├── centreController.js    # Controller for handling centers
│   ├── resourceController.js  # Controller for handling resources (e.g., courts, fields)
│   └── sportController.js     # Controller for handling sports types
├── models/
│   ├── Booking.js             # Model schema for Booking entity
│   ├── Centre.js              # Model schema for Centre entity (sports venue)
│   ├── Resource.js            # Model schema for Resource entity (e.g., sports courts)
│   └── Sport.js               # Model schema for Sport entity (e.g., soccer, tennis)
├── routes/
│   ├── bookingRoutes.js       # Routes related to booking operations
│   ├── centreRoutes.js        # Routes related to sports center operations
│   ├── resourceRoutes.js      # Routes related to resource operations
│   └── sportRoutes.js         # Routes related to sport operations
├── .env                       # Environment configuration (database credentials, etc.)
├── package.json               # Project metadata and dependencies
├── package-lock.json          # Lockfile for dependencies
├── app.js                     # Main entry point for the Express server

sports-booking-frontend/
├── src/
│   ├── pages/                 # Main pages of the application
│   │   ├── BookingPage.js      # Page for booking sports facilities
│   │   ├── Dashboard.js        # Admin dashboard
│   │   ├── ManageCentres.js    # Page to manage sports centers (admin)
│   │   ├── ManageResources.js  # Page to manage resources (courts, fields)
│   │   ├── ManageSports.js     # Page to manage different sports (admin)
│   ├── App.js                 # Main application component
│   ├── App.css                # Global styles for the app
│   ├── App.test.js            # Test file for the main app component
│   ├── index.js               # React entry point for rendering the app
│   ├── index.css              # Global CSS styles
│   ├── reportWebVitals.js     # Performance measuring tool
│   └── setupTests.js          # Setup for testing environment (Jest)
├── tailwind.config.js         # Tailwind CSS configuration file
├── postcss.config.js          # PostCSS configuration file
├── package.json               # Project metadata and dependencies
├── package-lock.json          # Lockfile for dependencies
└── README.md                  # Project documentation

```
---
## API Endpoints

### Booking Endpoints
```
| Method | Endpoint                             | Description                                      |
|--------|--------------------------------------|--------------------------------------------------|
| `GET`  | `/api/bookings`                      | Get all bookings                                 |
| `GET`  | `/api/:centreId/:sportId/bookings`   | Get bookings filtered by `centreId` and `sportId`|
| `POST` | `/api/bookings`                      | Create a new booking                             |
| `DELETE`| `/api/bookings/:id`                 | Delete a booking by its ID                       |
```
### Centre Endpoints
```
| Method  | Endpoint                              | Description                                     |
|---------|---------------------------------------|-------------------------------------------------|
| `GET`   | `/api/centres`                        | Get all centres                                 |
| `GET`   | `/api/centres/:centreId`              | Get a specific centre by `centreId`             |
| `POST`  | `/api/centres`                        | Create a new centre                             |
| `DELETE`| `/api/centres/:centreId`              | Delete a centre by `centreId`                   |
```
### Resource Endpoints
```
| Method  | Endpoint                                      | Description                                     |
|---------|-----------------------------------------------|-------------------------------------------------|
| `GET`   | `/api/resources`                              | Get all resources                               |
| `GET`   | `/api/resources/:resourceId`                  | Get a specific resource by `resourceId`         |
| `POST`  | `/api/resources`                              | Add a new resource                              |
| `DELETE`| `/api/resources/:resourceId`                  | Delete a resource by `resourceId`               |
| `GET`   | `/api/resources/:centreId/:sportId`           | Get resources filtered by `centreId` and `sportId`|
```
### Sport Endpoints
```
| Method  | Endpoint                                      | Description                                     |
|---------|-----------------------------------------------|-------------------------------------------------|
| `GET`   | `/api/sports`                                 | Get all sports                                  |
| `GET`   | `/api/sports_with_centreId/:centreId`         | Get sports filtered by `centreId`               |
| `GET`   | `/api/sports/:sportId`                        | Get a specific sport by `sportId`               |
| `POST`  | `/api/sports`                                 | Add a new sport                                 |
| `DELETE`| `/api/sports/:sportId`                        | Delete a sport by `sportId`                     |
```

## Setup and Installation

### Prerequisites

Before starting, ensure you have the following installed on your machine:

- **Node.js**: Make sure you have Node.js installed. You can download it from [Node.js official website](https://nodejs.org/).
- **npm**: npm comes with Node.js. You can check if it is installed by running `npm -v` in your terminal.
- **MySQL** or **PostgreSQL**: You need a database to store your application data. Download and install either [MySQL](https://www.mysql.com/downloads/) or [PostgreSQL](https://www.postgresql.org/download/).
- **Sequelize CLI**: This is optional but recommended for managing migrations and seeders.

### Installation Steps

1. **Clone the repository**:

   First, clone this repository to your local machine. Open your terminal and run:

   ```bash
   git clone https://github.com/your-username/sports-booking-app.git
   cd sports-booking-app
2. **Install dependencies**:

    Navigate to the project directory and install the necessary npm packages by running:
    ``bash
     npm install

3. **Configure Database**: 
   Create a .env file in the root directory of your project to store your database credentials. Here's an example of what you should include:
    ```
    DB_HOST=localhost
    DB_USER=your_db_username
    DB_PASSWORD=your_db_password
    DB_NAME=sports_booking_db

4. **Run database migrations**:
    ```
    npx sequelize-cli db:migrate

5. **Start the server**:
   ```
   npm start
   ```
   The server will be running on http://localhost:3000 by default.
