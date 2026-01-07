# 🚗 AllWomen RideShare

<div align="center">
  <img src="app/src/main/res/mipmap-xxxhdpi/ic_launcher.png" alt="AllWomen RideShare Logo" width="120" height="120">
  
  ### A Safety-First Rideshare Platform Designed Exclusively for Women
  
  [![Android](https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://www.android.com/)
  [![Kotlin](https://img.shields.io/badge/Language-Kotlin-0095D5?style=for-the-badge&logo=kotlin&logoColor=white)](https://kotlinlang.org/)
  [![Firebase](https://img.shields.io/badge/Backend-Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com/)
  [![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](LICENSE)
</div>

---

## 📖 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Screenshots](#-screenshots)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🎯 About

**AllWomen RideShare** is a revolutionary rideshare platform that prioritizes safety, security, and comfort for women. Built with modern Android development practices, this app provides a women-only environment where riders and drivers can feel safe and secure.

### 🌟 Why AllWomen RideShare?

- **Safety First:** Women-only verification ensures a trusted community
- **Emergency Features:** Panic button, live tracking, and emergency contacts
- **Transparent Ratings:** Comprehensive review system for both riders and drivers
- **Real-time Tracking:** Share your ride with trusted contacts
- **Secure Payments:** Integrated payment processing with multiple options

---

## ✨ Features

### 🔐 Safety & Security
- ✅ **Women-Only Verification** - Rigorous verification process for all users
- 🚨 **Emergency Panic Button** - One-tap emergency alert to contacts and authorities
- 📍 **Live Location Sharing** - Share real-time location with trusted contacts
- 👥 **Emergency Contacts** - Add up to 5 emergency contacts
- 🔔 **Safety Check-ins** - Automatic safety checks during rides
- 🎥 **In-App Recording** (Planned) - Optional audio/video recording for safety

### 🚗 Ride Management
- 🗺️ **Real-time Tracking** - Track your driver's location in real-time
- 📱 **Ride Booking** - Easy-to-use interface for booking rides
- ⏰ **Scheduled Rides** - Book rides in advance
- 💺 **Multiple Ride Types** - Standard, Premium, Shared, and Scheduled rides
- 🚦 **Route Optimization** - Efficient routing with Google Maps
- 📊 **Ride History** - Complete history of all your rides

### ⭐ Ratings & Reviews
- 🌟 **Comprehensive Rating System** - Rate drivers on multiple categories
- 💬 **Detailed Reviews** - Leave detailed feedback for drivers
- 📈 **Driver Profiles** - View driver ratings and reviews before booking
- 🏆 **Top-Rated Drivers** - Highlight the best drivers in the community

### 💳 Payments
- 💰 **Multiple Payment Methods** - Credit/Debit cards, PayPal, Google Pay, Apple Pay
- 🧾 **Fare Estimates** - Get accurate fare estimates before booking
- 💵 **Tipping** - Option to tip your driver
- 🎟️ **Promo Codes** - Apply promo codes for discounts
- 📜 **Payment History** - Track all your payments

### 👤 User Experience
- 🎨 **Material Design 3** - Modern, beautiful UI following Material Design guidelines
- 🌙 **Dark Mode** - Comfortable viewing in any lighting condition
- 🌐 **Multi-language Support** (Planned) - Support for multiple languages
- ♿ **Accessibility** - Designed with accessibility in mind
- 📱 **Responsive Design** - Works seamlessly on all Android devices

---

## 📱 Screenshots

<div align="center">
  <img src="screenshots/home.png" alt="Home Screen" width="200">
  <img src="screenshots/find_ride.png" alt="Find Ride" width="200">
  <img src="screenshots/ride_tracking.png" alt="Ride Tracking" width="200">
  <img src="screenshots/profile.png" alt="Profile" width="200">
</div>

---

## 🛠️ Tech Stack

### **Frontend**
- **Language:** Kotlin
- **UI Framework:** Android Views + Material Design 3
- **Architecture:** MVVM (Model-View-ViewModel)
- **Navigation:** Navigation Component
- **Dependency Injection:** Hilt (Planned)

### **Backend**
- **BaaS:** Firebase
  - Authentication (Email/Password, Google Sign-In)
  - Firestore (NoSQL Database)
  - Cloud Storage (Profile photos, documents)
  - Cloud Functions (Serverless backend logic)
  - Cloud Messaging (Push notifications)

### **Maps & Location**
- **Google Maps SDK** - Map display and route visualization
- **Google Places API** - Location search and autocomplete
- **Google Directions API** - Route calculation and optimization
- **Fused Location Provider** - Accurate location tracking

### **Payments**
- **Stripe SDK** - Payment processing
- **PayPal SDK** - Alternative payment method
- **Google Pay API** - Seamless mobile payments

### **Libraries & Dependencies**
```kotlin
// Core Android
androidx.core:core-ktx:1.12.0
androidx.appcompat:appcompat:1.6.1
androidx.constraintlayout:constraintlayout:2.1.4

// Material Design
com.google.android.material:material:1.11.0

// Navigation
androidx.navigation:navigation-fragment-ktx:2.7.6
androidx.navigation:navigation-ui-ktx:2.7.6

// Lifecycle & ViewModel
androidx.lifecycle:lifecycle-viewmodel-ktx:2.7.0
androidx.lifecycle:lifecycle-livedata-ktx:2.7.0

// Firebase
com.google.firebase:firebase-auth-ktx:22.3.1
com.google.firebase:firebase-firestore-ktx:24.10.1
com.google.firebase:firebase-storage-ktx:20.3.0
com.google.firebase:firebase-messaging-ktx:23.4.0

// Google Maps
com.google.android.gms:play-services-maps:18.2.0
com.google.android.gms:play-services-location:21.1.0
com.google.android.libraries.places:places:3.3.0

// Image Loading
com.github.bumptech.glide:glide:4.16.0

// Networking
com.squareup.retrofit2:retrofit:2.9.0
com.squareup.okhttp3:okhttp:4.12.0

// Coroutines
org.jetbrains.kotlinx:kotlinx-coroutines-android:1.7.3
```

---

## 🏗️ Architecture

This project follows **Clean Architecture** principles with **MVVM** pattern:

```
app/
├── data/
│   ├── model/          # Data models (User, Ride, Driver, etc.)
│   ├── repository/     # Data repositories
│   └── remote/         # Firebase integration
│
├── domain/
│   ├── usecase/        # Business logic
│   └── repository/     # Repository interfaces
│
├── presentation/
│   ├── ui/
│   │   ├── home/       # Home screen
│   │   ├── ride/       # Ride booking & tracking
│   │   ├── profile/    # User profile
│   │   └── auth/       # Authentication
│   │
│   └── viewmodel/      # ViewModels
│
└── utils/              # Utility classes
```

### **Design Patterns Used:**
- ✅ MVVM (Model-View-ViewModel)
- ✅ Repository Pattern
- ✅ Observer Pattern
- ✅ Singleton Pattern
- ✅ Factory Pattern

---

## 🚀 Getting Started

### **Prerequisites**
- Android Studio Hedgehog (2023.1.1) or later
- JDK 17 or later
- Android SDK (API 29+)
- Google Maps API Key
- Firebase Project

### **Installation**

1. **Clone the repository**
   ```bash
   git clone https://github.com/RichiebM3/AllWomenRideShare.git
   cd AllWomenRideShare
   ```

2. **Open in Android Studio**
   - Launch Android Studio
   - Select "Open an Existing Project"
   - Navigate to the cloned directory

3. **Configure Firebase**
   - Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
   - Add an Android app to your Firebase project
   - Download `google-services.json`
   - Place it in `app/` directory

4. **Add Google Maps API Key**
   - Get API key from [Google Cloud Console](https://console.cloud.google.com/)
   - Add to `local.properties`:
     ```properties
     MAPS_API_KEY=your_api_key_here
     ```

5. **Build and Run**
   ```bash
   ./gradlew assembleDebug
   ```

---

## 📂 Project Structure

```
AllWomenRideShare/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/allwomenrideshare/
│   │   │   │   ├── data/
│   │   │   │   │   ├── model/
│   │   │   │   │   │   ├── User.kt
│   │   │   │   │   │   ├── Driver.kt
│   │   │   │   │   │   ├── Ride.kt
│   │   │   │   │   │   ├── Vehicle.kt
│   │   │   │   │   │   ├── Rating.kt
│   │   │   │   │   │   ├── Location.kt
│   │   │   │   │   │   ├── SafetyFeatures.kt
│   │   │   │   │   │   ├── EmergencyContact.kt
│   │   │   │   │   │   └── Enums.kt
│   │   │   │   │   │
│   │   │   │   │   └── repository/
│   │   │   │   │
│   │   │   │   ├── presentation/
│   │   │   │   │   ├── ui/
│   │   │   │   │   │   ├── home/
│   │   │   │   │   │   ├── ride/
│   │   │   │   │   │   ├── profile/
│   │   │   │   │   │   └── auth/
│   │   │   │   │   │
│   │   │   │   │   └── viewmodel/
│   │   │   │   │
│   │   │   │   └── utils/
│   │   │   │
│   │   │   ├── res/
│   │   │   │   ├── layout/
│   │   │   │   ├── drawable/
│   │   │   │   ├── values/
│   │   │   │   └── navigation/
│   │   │   │
│   │   │   └── AndroidManifest.xml
│   │   │
│   │   └── test/
│   │
│   ├── build.gradle.kts
│   └── google-services.json
│
├── build.gradle.kts
├── settings.gradle.kts
├── gradle.properties
└── README.md
```

---

## 🗺️ Roadmap

### **Phase 1: MVP (Current)** ✅
- [x] User authentication
- [x] Basic ride booking
- [x] Google Maps integration
- [x] User profiles
- [x] Data models

### **Phase 2: Core Features** 🚧
- [ ] Real-time ride tracking
- [ ] Driver matching algorithm
- [ ] Payment integration
- [ ] Rating system
- [ ] Push notifications

### **Phase 3: Safety Features** 📋
- [ ] Emergency panic button
- [ ] Live location sharing
- [ ] Emergency contacts
- [ ] Safety check-ins
- [ ] In-app recording

### **Phase 4: Advanced Features** 🔮
- [ ] Scheduled rides
- [ ] Ride sharing
- [ ] In-app chat
- [ ] Promo codes
- [ ] Referral system
- [ ] Multi-language support

### **Phase 5: Polish & Launch** 🚀
- [ ] Performance optimization
- [ ] Security audit
- [ ] Beta testing
- [ ] Google Play Store submission
- [ ] Marketing materials

---

## 🤝 Contributing

This is a private project. Contributions are currently limited to the development team.

If you'd like to contribute:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is proprietary software. All rights reserved.

---

## 📧 Contact

**Project Maintainer:** [Richard A Bruce]

- 📧 Email: rbruce85@uw.edu
- 💼 LinkedIn: [Richard Bruce](https://www.linkedin.com/in/richard-bruce-613314b5/)


**Project Link:** [https://github.com/RichiebM3/AllWomenRideShare](https://github.com/RichiebM3/AllWomenRideShare)

---

<div align="center">
  <p>Made with ❤️ for women's safety</p>
  <p>⭐️ Star this repo if you find it helpful!</p>
</div>
