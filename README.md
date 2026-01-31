# Theory Test Multi Language 🚗

A comprehensive driving theory test preparation app supporting multiple languages (English, Turkish, Polish). Built with Flutter and Firebase.

[![Flutter](https://img.shields.io/badge/Flutter-3.10.7+-02569B?logo=flutter)](https://flutter.dev)
[![Firebase](https://img.shields.io/badge/Firebase-Cloud-FFCA28?logo=firebase)](https://firebase.google.com)
[![License](https://img.shields.io/badge/License-DVSA_Licensed-green.svg)](LICENSE)

## 📱 Features

### Core Functionality
- **Multi-Language Support**: English, Turkish (Türkçe), Polish (Polski)
- **Question Categories**: 14 official DVSA categories including:
  - Alertness, Attitude, Essential Documents
  - Hazard Awareness, Road Signs, Motorway Rules
  - Safety & Vehicle, Vulnerable Road Users, and more
- **Test Modes**:
  - Practice Mode: Learn with instant feedback
  - Mock Test: Simulate real exam conditions
  - Category-Specific Tests: Focus on weak areas
- **Smart Features**:
  - Flag questions for review
  - Detailed statistics and progress tracking
  - Timer for mock tests
  - Question bookmarks

### Premium Features 💎
- Remove ads (planned)
- Extended question bank
- Advanced statistics
- Priority support
- Managed via Apple/Google in-app purchases

### User Experience
- **Profile System**: Customizable avatars and names
- **Notifications**: Exam reminders and practice prompts (iOS)
- **Exam Date Tracking**: Set your exam date and get daily countdown
- **Dark/Light Mode**: Respects system preferences
- **Offline Support**: All questions available without internet

### Admin Features 🔧
- User statistics dashboard
- Error report management
- Contact message inbox
- Premium user analytics
- Data management tools

## 🛠 Tech Stack

### Frontend
- **Framework**: Flutter 3.10.7+
- **State Management**: Provider
- **Languages**: Dart

### Backend & Services
- **Database**: Firebase Cloud Firestore
- **Authentication**: Anonymous (UUID-based)
- **Storage**: SharedPreferences (local)
- **Notifications**: flutter_local_notifications + timezone
- **Payments**: in_app_purchase (Apple/Google)

### Key Packages
```yaml
firebase_core: ^3.15.2
cloud_firestore: ^5.6.12
provider: ^6.1.2
uuid: ^4.5.1
flutter_local_notifications: ^18.0.1
timezone: ^0.9.4
google_fonts: ^6.2.1
in_app_purchase: ^3.2.2
shared_preferences: ^2.3.4
```

## 🏗 Architecture

```
lib/
├── main.dart                 # App entry point
├── constants/                # App-wide constants
├── localization/             # Multi-language support
├── models/                   # Data models
│   ├── question.dart
│   └── test_provider.dart
├── screens/                  # UI screens
│   ├── home_screen.dart
│   ├── test_screen.dart
│   ├── results_screen.dart
│   └── admin_panel_screen.dart
├── services/                 # Business logic
│   ├── firebase_service.dart
│   ├── device_service.dart
│   └── notification_service.dart
└── widgets/                  # Reusable components
```

## 🚀 Getting Started

### Prerequisites
- Flutter SDK 3.10.7 or higher
- Dart SDK 3.0.0 or higher
- Firebase account with Firestore enabled
- iOS 12.0+ / Android 5.0+ (API 21+)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/theory_test_multi_language.git
   cd theory_test_multi_language
   ```

2. **Install dependencies**
   ```bash
   flutter pub get
   ```

3. **Firebase Setup**
   - Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com)
   - Add iOS and Android apps to your Firebase project
   - Download and place configuration files:
     - `google-services.json` → `android/app/`
     - `GoogleService-Info.plist` → `ios/Runner/`
   - Enable Cloud Firestore
   - Deploy Firestore rules:
     ```bash
     firebase deploy --only firestore:rules
     ```

4. **Run the app**
   ```bash
   # iOS
   flutter run -d ios

   # Android
   flutter run -d android

   # Web (for testing)
   flutter run -d chrome
   ```

## 🔐 Privacy & Security

- **Zero Personal Data**: Only anonymous UUIDs collected
- **Local Storage**: All user data stays on device
- **Optional Reporting**: Error reports and contact messages only
- **GDPR/CCPA Compliant**: Full privacy policy included
- **Secure**: Firebase Security Rules enforced

See [PRIVACY_POLICY.md](PRIVACY_POLICY.md) for full details.

## 📊 Firebase Structure

### Collections

**users**
```javascript
{
  deviceId: "uuid-v4-string",
  isPremium: boolean,
  createdAt: timestamp,
  lastSeenAt: timestamp
}
```

**error_reports**
```javascript
{
  categoryName: string (Turkish),
  questionId: string,
  errorType: string,
  timestamp: timestamp,
  viewed: boolean
}
```

**contact_messages**
```javascript
{
  email: string,
  message: string,
  timestamp: timestamp
}
```

## 🎨 Customization

### Adding New Languages
1. Create translation file in `lib/localization/`
2. Update `LocalizationProvider` in `lib/localization/localization_provider.dart`
3. Add language flag to UI

### Adding Questions
Questions are stored in JSON files under `assets/` directory:
```
assets/
├── alertness/alertness.json
├── attitude/attitude.json
└── ...
```

Each question follows this format:
```json
{
  "id": "unique-id",
  "questionText": "Question in English",
  "options": ["Option 1", "Option 2", "Option 3", "Option 4"],
  "correctAnswer": 0,
  "explanation": "Why this is correct",
  "imageUrl": "optional-image-path"
}
```

## 👨‍💼 Admin Access

1. Navigate to Profile tab
2. Tap on version number 5 times
3. Enter password: `1482`
4. Access admin panel features:
   - View total users and premium users
   - Manage error reports
   - Read contact messages
   - Reset statistics

## 🧪 Testing

```bash
# Run all tests
flutter test

# Run specific test
flutter test test/widget_test.dart

# Run with coverage
flutter test --coverage
```

## 📦 Build & Release

### Android
```bash
flutter build appbundle --release
```

### iOS
```bash
flutter build ipa --release
```

## 📄 License & Disclaimer

⚠️ **NOT AN OFFICIAL DVSA APPLICATION**

This app uses officially licensed DVSA (Driver and Vehicle Standards Agency) question content under a licensing agreement. DVSA is a trademark of the UK government.

**Important:**
- This app does NOT guarantee exam success
- Questions are for educational purposes only
- Not affiliated with or endorsed by DVSA
- Consult official DVSA materials for exam preparation

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Contact & Support

- **Email**: sevimli.sezgin@gmail.com
- **Issues**: [GitHub Issues](https://github.com/yourusername/theory_test_multi_language/issues)
- **In-App**: Use "Contact Developer" feature in Profile tab

## 🙏 Acknowledgments

- DVSA for official question content licensing
- Flutter team for the amazing framework
- Firebase for backend infrastructure
- Contributors and beta testers

## 📱 Download

- **iOS**: [App Store Link - Coming Soon]
- **Android**: [Google Play Link - Coming Soon]

---

**Made with ❤️ using Flutter**

*Last Updated: January 31, 2026*
