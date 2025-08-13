# 🌾 ShetiSakha – Farmer's Friend

**ShetiSakha** (meaning *"Farmer's Friend"*) is a comprehensive Android application designed to revolutionize farming practices through automation.  
It serves as the **central control unit** for an agricultural robot, enabling farmers to perform tasks like **ploughing, seeding, and sprinkling** with ease and precision — either manually or via automated path-following.

---

## ✨ Features

### 🌦 Real-time Weather Monitoring
- Fetches and displays current weather conditions: **temperature, humidity, pressure, wind speed**.
- Uses **OpenWeatherMap API** to help farmers make informed decisions.

### 🎮 Manual Remote Control
- Responsive virtual remote control interface for **real-time maneuvering** of the agricultural bot.
- Connects via **Bluetooth**.

### 🤖 Automated Operations
- Simple toggle buttons to **activate/deactivate** specific functions:
  - Ploughing
  - Seeding
  - Sprinkling

### 📍 Path Memorization & Playback
- Record a sequence of manual movements and **save locally**.
- Replay saved paths to automate repetitive tasks.

### 📊 Grid-Based Automated Navigation
- Draw a path on a **predefined grid**.
- The app translates patterns into movement commands for autonomous bot navigation.

### ✏️ Free-Form Path Drawing
- Draw custom paths on a canvas for complex field layouts.
- Uses **Ramer-Douglas-Peucker algorithm** to simplify drawings into optimized motor commands.

---

## ⚙ How It Works

The ShetiSakha app communicates with an **agricultural robot** equipped with:
- **Microcontroller** (e.g., Arduino)
- **HC-05 Bluetooth module**

### 🔗 Connection
- Establishes **Bluetooth Serial Port Profile (SPP)** connection with the bot.

### 📨 Command Transmission
- **Manual Mode**:  
  Directional buttons send commands like:
  - Forward → `F`
  - Backward → `B`
  - Left → `L`
  - Right → `R`
  
- **Automated Mode**:  
  Drawn paths are processed and converted into `"move"` and `"turn"` commands, streamed to the bot.

### 💾 Data Storage
- Uses **SQLite database** to store and retrieve movement sequences (direction + duration).

---

## 📂 Key Components

- **MainActivity3 (Dashboard)**  
  Displays weather info and navigation to control modes.

- **MainActivity4 (Manual Control)**  
  For manual operation with directional controls, toggles, and path recording/playback.

- **activity_grid (Automatic Grid Mode)**  
  Implements grid-based path-following.

- **databases/DatabaseHelper.java**  
  Manages SQLite database for path memorization.

- **classes/PathDrawView.java**  
  Custom view for free-form path drawing, validation, and simplification.

- **classes/PatternLockView.java**  
  Custom grid view for structured path creation.

---

## 🛠 Setup & Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/atkarmanshri/ShetiSakha.git

   ```
2. Open the project in Android Studio.
3. Let Gradle sync and build the project.
4. Run the app on a physical Android device or emulator.

