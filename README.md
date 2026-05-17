# ZimmerMatch – Vacation Rental Management System

## 🔗 Project Links
*   📂 **[Frontend Repository](https://github.com/sarigetsel/ZimmerMatch-client)**: Contains the React & Redux logic.
*   📂 **[Backend Repository](https://github.com/sarigetsel/ZimmerMatch-Server)**: Contains the .NET API and Database migrations.

---

## Overview
A comprehensive Full-Stack web application designed for managing vacation rentals. The system provides an end-to-end solution for searching, viewing, and managing properties with a focus on high performance and user experience.

<p align="center">
  <img src="https://github.com/user-attachments/assets/cee68cc7-ffb7-471b-b327-8c0817936a59" alt="Home Page View 1" width="400">
  <img src="https://github.com/user-attachments/assets/02a6cfaa-2c42-466f-96ca-a6fb14d7c12b" alt="Home Page View 2" width="400">
</p>


## Architecture
The project is built using a **decoupled architecture**, consisting of two main components:
*   **Frontend**: A responsive Single Page Application (SPA).
*   **Backend**: A RESTful Web API following a layered architecture.

## Key Features

### 🔐 Authentication & Role-Based Access Control (RBAC)
The system implements a secure and granular permission model based on user roles:

*   **Admin (System Manager)**:
    *   **User Management**: View all registered users and manage accounts (including deletion).
    *   **Property Oversight**: Access to all rental listings with full authority to delete listings.
    *   **Booking Management**: View all system-wide reservations with the ability to modify statuses (e.g., canceling bookings).
*   **Owner (Property Manager)**:
    *   **Listing Management**: View and edit personal property details and pricing.
    *   **Order Tracking**: View and manage all incoming reservations specifically for their properties.
*   **Guest (Customer)**:
    *   **Booking History**: View and track personal reservations and order status.
    *   **Search & Discovery**: Full access to the search engine and property details.

### 📅 Availability Calendar & Booking
*   Integrated a dynamic calendar for real-time availability tracking.
*   Seamless booking process that prevents double-booking and manages property schedules.

<p align="center">
  <img src="https://github.com/user-attachments/assets/ab9f8d84-9df2-4079-8621-a7dc3a93abb7" alt="Availability Calendar" width="700">
  <br>
  <em>Dynamic Availability Calendar and Booking Management</em>
</p>

### 🔍 Advanced Search & UI
*   **Search Engine**: Implemented a **String Similarity Algorithm** using **Dynamic Programming** to handle typos and provide flexible search results.
*   **Interactive UI**: Data visualization using interactive maps and real-time state management.

<p align="center">
  <img src="https://github.com/user-attachments/assets/32f517d1-01b5-4e79-b764-333366bd3ce5" alt="Interactive Map" width="700">
  <br>
  <em>Interactive Map Visualization for property discovery</em>
</p>

### 🤖 AI-Powered Smart Concierge Chat
* **Virtual Holiday Assistant**: Integrated a smart AI assistant within each property detail page to help users explore listings, evaluate value-for-money, and assist in vacation planning.
* **Context-Aware Diagnostics**: The assistant automatically ingests real-time property details (amenities, pricing, location) and local data to provide tailored recommendations.
* **Smart Infrastructure Discovery**: Programmed to intelligently map and suggest nearby points of interest, dining options, and community/religious infrastructure (e.g., Synagogues, Kosher dining, Mikvaot) within a 15-minute drive.
* **Strict Topic Guardrails**: Implemented robust prompt engineering constraints to safely handle off-topic inquiries and keep conversational responses concise, engaging, and highly vacation-focused.

<p align="center">
  <img src="https://github.com/user-attachments/assets/0664eb8c-b5f4-4ec4-9284-ce35b8699450" width="700">
  <br>
  <em>AI-Powered Smart Concierge helping guests evaluate property value and plan local activities</em>
</p>

## Tech Stack
*   **Backend**: C#, .NET Web API, Entity Framework, SQL Server.
*   **Frontend**: React, Redux Toolkit, Vite, SCSS.
*   **Version Control**: Git & GitHub.

---
*Created as part of an academic software engineering project.*
