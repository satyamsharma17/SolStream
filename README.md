# SolStream - Solana Music App

SolStream App is a decentralized music platform integrated with the Solana blockchain. The app includes an Android application, a React Native application, a backend service, Solana programs, and a database. It allows users to upload and stream music content, make payments, and manage notifications securely.

## Table of Contents

- [Project Structure](#project-structure)
- [Features](#features)
- [Setup](#setup)
- [Usage](#usage)
- [License](#license)

## Project Structure

```plaintext
solana-music-app/
├── app/
│   ├── android/
│   │   ├── src/
│   │   │   ├── main/
│   │   │   │   ├── java/com/example/app/
│   │   │   │   │   ├── ui/
│   │   │   │   │   │   ├── MainActivity.kt
│   │   │   │   │   │   ├── OnboardingScreen.kt
│   │   │   │   │   │   ├── ContentScreen.kt
│   │   │   │   │   │   ├── PaymentScreen.kt
│   │   │   │   │   │   └── NotificationScreen.kt
│   │   │   │   │   ├── data/
│   │   │   │   │   │   ├── models/
│   │   │   │   │   │   │   ├── User.kt
│   │   │   │   │   │   │   ├── Content.kt
│   │   │   │   │   │   │   └── Payment.kt
│   │   │   │   │   │   ├── repository/
│   │   │   │   │   │   │   ├── UserRepository.kt
│   │   │   │   │   │   │   ├── ContentRepository.kt
│   │   │   │   │   │   │   └── PaymentRepository.kt
│   │   │   │   │   ├── network/
│   │   │   │   │   │   ├── ApiClient.kt
│   │   │   │   │   │   ├── ApiService.kt
│   │   │   │   │   │   └── SolanaService.kt
│   │   │   │   │   └── utils/
│   │   │   │   │       ├── JwtUtils.kt
│   │   │   │   │       ├── SolanaWalletAdapter.kt
│   │   │   │   │       └── Constants.kt
│   │   │   │   ├── res/
│   │   │   │   │   ├── layout/
│   │   │   │   │   │   ├── activity_main.xml
│   │   │   │   │   │   ├── onboarding_screen.xml
│   │   │   │   │   │   ├── content_screen.xml
│   │   │   │   │   │   └── payment_screen.xml
│   │   │   │   │   ├── values/
│   │   │   │   │   │   ├── strings.xml
│   │   │   │   │   │   └── colors.xml
│   │   │   │   └── AndroidManifest.xml
│   │   └── build.gradle
│   ├── react-native/
│   │   ├── src/
│   │   │   ├── components/
│   │   │   │   ├── Button.js
│   │   │   │   ├── InputField.js
│   │   │   │   ├── ContentCard.js
│   │   │   │   └── NotificationItem.js
│   │   │   ├── screens/
│   │   │   │   ├── OnboardingScreen.js
│   │   │   │   ├── ContentScreen.js
│   │   │   │   ├── PaymentScreen.js
│   │   │   │   └── NotificationScreen.js
│   │   │   ├── services/
│   │   │   │   ├── ApiService.js
│   │   │   │   ├── SolanaService.js
│   │   │   │   └── StorageService.js
│   │   │   └── utils/
│   │   │       ├── JwtUtils.js
│   │   │       ├── SolanaWalletAdapter.js
│   │   │       └── Constants.js
│   │   └── package.json
├── backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/app/
│   │   │   │   ├── controller/
│   │   │   │   │   ├── UserController.java
│   │   │   │   │   ├── ContentController.java
│   │   │   │   │   └── PaymentController.java
│   │   │   │   ├── model/
│   │   │   │   │   ├── User.java
│   │   │   │   │   ├── Content.java
│   │   │   │   │   └── Payment.java
│   │   │   │   ├── repository/
│   │   │   │   │   ├── UserRepository.java
│   │   │   │   │   ├── ContentRepository.java
│   │   │   │   │   └── PaymentRepository.java
│   │   │   │   ├── service/
│   │   │   │   │   ├── UserService.java
│   │   │   │   │   ├── ContentService.java
│   │   │   │   │   └── PaymentService.java
│   │   │   │   ├── utils/
│   │   │   │   │   ├── JwtUtils.java
│   │   │   │   │   ├── SolanaUtils.java
│   │   │   │   │   └── Constants.java
│   │   ├── resources/
│   │   │   └── application.properties
│   └── build.gradle
├── solana-programs/
│   ├── src/
│   │   ├── accounts/
│   │   │   ├── UserAccount.rs
│   │   │   ├── ContentAccount.rs
│   │   │   └── PaymentAccount.rs
│   │   ├── instructions/
│   │   │   ├── CreateUser.rs
│   │   │   ├── UploadContent.rs
│   │   │   └── MakePayment.rs
│   │   ├── programs/
│   │   │   └── main.rs
│   │   ├── utils/
│   │   │   ├── validation.rs
│   │   │   └── serialization.rs
│   ├── Cargo.toml
├── database/
│   ├── migrations/
│   │   ├── V1__Initial_Setup.sql
│   │   └── V2__Add_Content_Metadata.sql
│   └── seed/
│       ├── seed_users.sql
│       └── seed_content.sql
└── README.md
```

## Features

- **User Authentication:** Secure user authentication using JWT tokens.
- **Onboarding:** User-friendly onboarding process for new users.
- **Content Management:** Upload, manage, and stream music content.
- **Payment Processing:** Secure payments and transactions using Solana blockchain.
- **Notifications:** Real-time notifications for user activities.
- **Wallet Integration:** Solana wallet integration for decentralized payments.
- **Cross-Platform Support:** Android and React Native applications for cross-platform usage.
- **Backend Services:** Comprehensive backend services for user, content, and payment management.
- **Solana Programs:** Decentralized operations using Solana smart contracts.

## Setup

### Prerequisites

- [Android Studio](https://developer.android.com/studio)
- [Node.js and npm](https://nodejs.org/)
- [Java Development Kit (JDK)](https://www.oracle.com/java/technologies/javase-downloads.html)
- [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
- [Rust](https://www.rust-lang.org/tools/install)

### Installation

1. **Clone the repository:**

```bash
git clone https://github.com/your-username/solana-music-app.git
cd solana-music-app
```

2. **Android App Setup:**

   - Open the project in Android Studio.
   - Ensure you have the correct SDK location configured in `local.properties`.
   - Build and run the app on an emulator or physical device.

3. **React Native App Setup:**

   - Navigate to the `react-native` directory:
   
   ```bash
   cd app/react-native
   ```
   - Install the dependencies:
   
   ```bash
   npm install
   ```
   - Run the app on an emulator or physical device:
   
   ```bash
   npm run android
   ```

4. **Backend Setup:**

   - Navigate to the `backend` directory:
   
   ```bash
   cd backend
   ```
   - Build and run the backend service:
   
   ```bash
   ./gradlew bootRun
   ```

5. **Solana Programs Setup:**

   - Navigate to the `solana-programs` directory:
   
   ```bash
   cd solana-programs
   ```
   - Build the Solana programs:
   
   ```bash
   cargo build-bpf
   ```
   - Deploy the programs to the Solana blockchain (ensure you are connected to the correct cluster and have sufficient SOL):
   
   ```bash
   solana program deploy path/to/your/program.so
   ```

6. **Database Setup:**

   - Apply the database migrations:
   
   ```bash
   cd database
   ./apply_migrations.sh
   ```
   - Seed the database:
   
   ```bash
   ./seed_database.sh
   ```

## Usage

- **Android App:** Launch the app on your Android device to explore features like onboarding, content streaming, payments, and notifications.
- **React Native App:** Launch the React Native app on your device for cross-platform usage.
- **Backend Service:** The backend service provides APIs for user management, content management, and payment processing.
- **Solana Programs:** The Solana programs handle decentralized operations like creating users, uploading content, and processing payments.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
