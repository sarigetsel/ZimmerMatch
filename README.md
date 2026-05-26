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

## Architecture & Technical Highlights
The project is built using a **decoupled architecture** focused on separation of concerns and secure data flow:

*   **Frontend**: A responsive Single Page Application (SPA) built with **React**, **Vite**, and **SCSS**, utilizing **Redux Toolkit** for clean global state management.
*   **Backend**: A RESTful Web API engineered with **C#** and **.NET 8** following a **Layered Architecture (N-Tier)** pattern, cleanly separating Controllers, Services, and Repositories.
*   **Database & ORM**: Powered by **SQL Server** and **Entity Framework Core** using a **Code-First** approach with structural database migrations.

---

## Key Features

### 🔐 Authentication & Role-Based Access Control (RBAC)
The system implements a secure, stateless authorization model using **JWT Bearer Tokens** with a 30-minute session expiration. Access control is strictly enforced at two levels:

1. **Role-Based Security (`[Authorize]`)**: Restricted API access endpoints based on user claims:
    *   **Admin (System Manager)**: Full oversight across user management, system-wide booking cancellations, and listing moderation.
    *   **Owner (Property Manager)**: Authorized access to manage specific listings, update pricing, and track incoming orders.
    *   **Guest (Customer)**: Standard access for property discovery, booking, and personal order history tracking.
2. **Resource-Based Security**: Backend validation at the Service layer ensures that an `Owner` can exclusively modify availability or data for properties they rightfully own in the database.

### 📅 Availability Calendar & Booking
*   Integrated a dynamic calendar for real-time availability tracking.
*   Seamless booking process that prevents double-booking and manages property schedules.

<p align="center">
  <img src="https://github.com/user-attachments/assets/ab9f8d84-9df2-4079-8621-a7dc3a93abb7" alt="Availability Calendar" width="700">
  <br>
  *Dynamic Availability Calendar and Booking Management*
</p>

### 🔍 Advanced Search & UI
*   **Search Engine**: Implemented a **String Similarity Algorithm** using **Dynamic Programming** to handle typos and provide flexible search results.
*   **Interactive UI**: Data visualization using interactive maps and real-time state management.

<p align="center">
  <img src="https://github.com/user-attachments/assets/32f517d1-01b5-4e79-b764-333366bd3ce5" alt="Interactive Map" width="700">
  <br>
  *Interactive Map Visualization for property discovery*
</p>

### 🤖 AI-Powered Smart Concierge Chat
* **Virtual Holiday Assistant**: Integrated a smart AI assistant within each property detail page to help users explore listings, evaluate value-for-money, and assist in vacation planning.
* **Context-Aware Diagnostics**: The assistant automatically ingests real-time property details (amenities, pricing, location) and local data to provide tailored recommendations.
* **Smart Infrastructure Discovery**: Programmed to intelligently map and suggest nearby points of interest, dining options, and community/religious infrastructure (e.g., Synagogues, Kosher dining, Mikvaot) within a 15-minute drive.
* **Strict Topic Guardrails**: Implemented robust prompt engineering constraints to safely handle off-topic inquiries and keep conversational responses concise, engaging, and highly vacation-focused.

<p align="center">
  <img src="https://github.com/user-attachments/assets/0664eb8c-b5f4-4ec4-9284-ce35b8699450" width="700">
  <br>
  *AI-Powered Smart Concierge helping guests evaluate property value and plan local activities*
</p>

### 🔄 Similar Properties Recommendation Engine (ZimmerMatch Algorithm)
* **Smart Matching**: Implemented a localized scoring algorithm to dynamically suggest alternative vacation rentals to the user based on their current view.
* **Multi-Criteria Similarity**: The matching engine analyzes and weights parameters to find the best alternatives, focusing heavily on:
  * **Geographic Proximity**: Prioritizes properties within the exact same city.
  * **Price Range Matching**: Calculates a delta variance ($\le 20\%$) against the base property's price per night to suggest relevant budget alternatives.
* **Optimized Payload**: Limits results to the top 4 most relevant recommendations to optimize frontend rendering and database query overhead.

<p align="center">
  <img src="https://github.com/user-attachments/assets/473131d8-303f-4b4e-89c6-c9f709e7f053" width="700">
  <br>
  *Personalized "Similar Properties" slider powered by our location-and-price heuristic matching*
</p>
  
## Tech Stack
*   **Backend**: C#, .NET Web API, Entity Framework, SQL Server.
*   **Frontend**: React, Redux Toolkit, Vite, SCSS.
*   **Version Control**: Git & GitHub.

---

## 🚀 Quick Start

### Backend Setup
1. Update your connection string in `appsettings.json`.
2. Run `dotnet ef database update` to create the database schema.
3. Run `dotnet run` to start the API server.

### Frontend Setup
1. Navigate to the client folder: `cd ZimmerMatch-client`
2. Install dependencies: `npm install`
3. Start the local development server: `npm run dev`

---
*Created as part of an academic software engineering project.*
