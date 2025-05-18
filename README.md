# ⚡ EV Charging Slot Booking System

A full-stack web application to manage and book EV charging slots, find nearby charging stations using geolocation, and handle real-time data using Firebase.

## 🚀 Project Overview

This project allows users to:
- Register/login as a user or admin
- Admins can add EV bunk details and create time slots
- Users can view nearby EV bunks using Google Maps location
- Users can view bunk details and slot availability

Built using:
- Firebase (Authentication, Firestore, Hosting)
- HTML, CSS, JavaScript
- Google Maps (via embedded URLs and geolocation)

---

## 🔧 Features

### 👤 User Features
- Register & Login securely using Firebase Authentication
- View nearby EV bunks based on location
- View bunk address, mobile, and Google Map location
- Check available charging slots

### 🔐 Admin Features
- Admin login and registration
- Add EV bunk details (name, address, map URL, contact)
- Create time slots for each bunk
- View existing bunks and slots

### 🗺️ Map Integration
- Uses Google Maps URLs stored in Firestore
- Extracts latitude and longitude from the URL
- Filters and displays bunks within a 5–10 km radius

---

## 🛠️ Technologies Used

| Layer       | Technology |
|-------------|------------|
| Frontend    | HTML, CSS, JavaScript |
| Backend     | Firebase Firestore |
| Auth        | Firebase Authentication |
| Maps        | Google Maps (static links & coordinates) |
| Hosting     | Firebase Hosting |

---

## 📁 Firestore Database Structure

### 🔌 Collection: `bunks`
- `bunkName`: string
- `bunkAddress`: string
- `bunkMobile`: string
- `mapUrl`: string (must include coordinates)

### ⏰ Collection: `slots`
- `bunkId`: string (linked to a bunk)
- `slotTime`: string (e.g., 10am - 11am)
- `slotVacant`: number

---

## 📍 How Nearby Bunk Feature Works

1. Browser fetches user's current geolocation.
2. Extracts latitude and longitude from all stored bunk URLs.
3. Calculates distance using Haversine formula.
4. Displays only nearby bunks (within 10 km).

---

## 🧪 Testing

| Feature                   | Tested On | Status |
|---------------------------|-----------|--------|
| User Login/Register       | Chrome    | ✅ Pass |
| Admin Panel (Add bunk)    | Chrome    | ✅ Pass |
| Nearby Search (geolocation)| Chrome    | ✅ Pass |
| Slot Vacancy Display      | Chrome    | ✅ Pass |

---

## 🚀 Firebase Hosting Deployment

1. Install Firebase CLI  
   ```bash
   npm install -g firebase-tools

# EV-Charging-Slot-Booking
