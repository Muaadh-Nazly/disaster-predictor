# Android Mobile Application

## 📋 Overview

Android mobile application for the Disaster Prediction and Early Warning System. The app provides real-time disaster predictions (Flood, Cyclone, Landslide) to users based on their location and current weather conditions.

## 📁 Project Structure

```
MyApplication/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/myapplication/
│   │   │   │   ├── MainActivity.java
│   │   │   │   ├── FloodActivity.java
│   │   │   │   ├── CycloneActivity.java
│   │   │   │   ├── LandslideActivity.java
│   │   │   │   ├── MapActivity.java
│   │   │   │   ├── LoginActivity.java
│   │   │   │   ├── RegisterActivity.java
│   │   │   │   └── [Other activities]
│   │   │   ├── res/              # Resources (layouts, drawables, values)
│   │   │   ├── assets/           # Asset files (CSV data)
│   │   │   └── AndroidManifest.xml
│   │   ├── androidTest/          # Instrumented tests
│   │   └── test/                 # Unit tests
│   ├── build.gradle.kts          # App-level build configuration
│   └── google-services.json      # Firebase configuration
├── build.gradle.kts              # Project-level build configuration
├── settings.gradle.kts           # Project settings
└── gradle/                       # Gradle wrapper
```

## 🎯 Features

### Core Functionality
- **User Authentication** - Registration and login via Firebase
- **Disaster Predictions** - Real-time predictions for Flood, Cyclone, Landslide
- **Location Services** - GPS-based location detection
- **Weather Integration** - Current weather data display
- **Interactive Maps** - Visual representation of disaster zones
- **Multi-day Forecast** - 4-day prediction horizon
- **Safety Information** - Guidelines and precautions

### User Activities

#### Main Activities
- **MainActivity** - Home screen with navigation
- **FloodActivity** - Flood predictions and alerts
- **CycloneActivity** - Cyclone predictions and alerts
- **LandslideActivity** - Landslide predictions and alerts
- **MapActivity** - Interactive maps with disaster zones

#### Authentication
- **LoginActivity** - User login
- **RegisterActivity** - New user registration

#### Supporting Activities
- **AboutUsActivity** - Project information
- **LoadingActivity** - Loading screens
- **UserLocationPermissionActivity** - Location permission handling
- **More_details** - Additional information screens

### Data Models
- **ForecastItem** - Forecast data structure
- **ForecastResponse** - API response model
- **WeatherResponse** - Weather data model
- **DistrictData** - District information
- **UserLocation** - Location data
- **SelectedLocation** - Selected location data
- **NearbyCities** - Nearby cities information

## 🛠️ Technology Stack

- **Language:** Java
- **Platform:** Android
- **IDE:** Android Studio
- **Backend Services:** Firebase (Authentication, Realtime Database)
- **API Integration:** REST API (Flask backend)
- **Maps:** Google Maps API
- **Location Services:** Android Location Services

## 🚀 Getting Started

### Prerequisites
- Android Studio (latest version)
- Android SDK (API level 21+)
- Firebase account
- Google Maps API key

### Setup

1. **Open Project**
   ```bash
   # Open MyApplication/ in Android Studio
   File > Open > Select MyApplication directory
   ```

2. **Configure Firebase**
   - Create Firebase project
   - Add Android app to Firebase
   - Download `google-services.json`
   - Place in `app/` directory

3. **Configure Google Maps**
   - Get Google Maps API key
   - Add to `AndroidManifest.xml` or `local.properties`

4. **Configure API Endpoint**
   - Update API base URL in code
   - Point to Heroku deployment or local server

5. **Build and Run**
   ```bash
   # Build project
   ./gradlew build

   # Run on emulator/device
   ./gradlew installDebug
   ```

## 📱 App Workflow

### User Journey

1. **Launch App**
   - Show splash/loading screen
   - Check authentication status

2. **Authentication**
   - New users: Register
   - Existing users: Login
   - Firebase authentication

3. **Main Screen**
   - Navigation menu
   - Quick access to predictions
   - Location display

4. **Disaster Selection**
   - Choose disaster type
   - View predictions
   - Check forecast

5. **Location Services**
   - Request location permission
   - Get current location
   - Show location-based predictions

6. **Maps View**
   - Interactive map
   - Disaster zones
   - Location markers

## 🔧 Configuration

### Build Configuration
- **Min SDK:** 21 (Android 5.0)
- **Target SDK:** Latest
- **Build Tools:** Latest
- **Gradle:** Latest

### Permissions Required
```xml
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
```

### Dependencies
- Firebase Authentication
- Firebase Realtime Database
- Google Maps SDK
- HTTP client (for API calls)
- Location services

## 📊 Data Flow

### Prediction Flow
1. User selects location
2. App gets weather data
3. App calls API endpoint
4. API returns predictions
5. App displays results

### Weather Data
- Uses `Rainfall_Daily_Average.csv` from assets
- Integrates with weather API
- Displays current conditions

## 🎨 UI Components

### Layouts
- Main activity layouts
- Disaster-specific layouts
- Map layouts
- Authentication layouts
- Navigation layouts

### Resources
- **Drawables:** Icons, images
- **Values:** Strings, colors, dimensions
- **Fonts:** Custom fonts
- **Themes:** App themes

## 📝 Key Files

### Java Source Files
- **MainActivity.java** - Entry point
- **FloodActivity.java** - Flood predictions
- **CycloneActivity.java** - Cyclone predictions
- **LandslideActivity.java** - Landslide predictions
- **MapActivity.java** - Maps functionality
- **LoginActivity.java** - User authentication
- **RegisterActivity.java** - User registration

### Configuration Files
- **AndroidManifest.xml** - App configuration
- **build.gradle.kts** - Build configuration
- **google-services.json** - Firebase config

## 🔗 API Integration

### Endpoints Used
- `/predict_flood` - Flood predictions
- `/predict_cyclone` - Cyclone predictions
- `/predict_landslide` - Landslide predictions

### Request Format
```java
// Example request
FormData formData = new FormData();
formData.add("Location", location);
formData.add("District", district);
formData.add("Rainfall(mm)", rainfall);
```

### Response Handling
- Parse JSON response
- Extract predictions
- Display in UI
- Handle errors

## 🧪 Testing

### Unit Tests
- Located in `app/src/test/`
- Test business logic
- Mock API calls

### Instrumented Tests
- Located in `app/src/androidTest/`
- Test UI components
- Test on device/emulator

## 📦 Build Outputs

### APK
- Debug APK: `app/build/outputs/apk/debug/app-debug.apk`
- Release APK: Generated for production

### AAB (Android App Bundle)
- Release AAB: `app/release/app-release.aab`
- For Google Play Store
