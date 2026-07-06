# HealthFlow Flutter App

This project contains the Flutter mobile and web application frontend for HealthFlow.

## Project Structure

Below is the structured tree of all the important source files contained within this Flutter application. (Note: Build outputs, temporary files, and platform-specific generated directories (.git, .idea, build, ios, android, web, windows, macos, linux) have been omitted for clarity).

```text
- healthflow_flutter/
  - .flutter-plugins
  - .flutter-plugins-dependencies
  - .gitignore
  - .metadata
  - analysis_options.yaml
  - BUILDING_SCREENS.md
  - FILE_STRUCTURE.md
  - FUNCTIONALITY_GUIDE.md
  - healthflow_flutter.iml
  - IJONS MANUSCRIPT TEMPLATE.pdf
  - IMPLEMENTATION_PLAN.md
  - IMPLEMENTATION_SUMMARY.md
  - NUTRITION_FEATURE.md
  - pubspec.lock
  - pubspec.yaml
  - QUICK_START_NUTRITION.md
  - README.md
  - RUN_APP.md
  - assets/
    - data/
      - healthflow_final_patients_dataset.csv
    - fonts/
      - Nirmala.ttc
    - images/
  - lib/
    - main.dart
    - models/
      - appointment_model.dart
      - message_model.dart
      - notification_model.dart
      - nutrition_model.dart
      - patient_model.dart
      - user_model.dart
      - vital_model.dart
    - screens/
      - appointments_screen.dart
      - chat_screen.dart
      - doctor_dashboard_screen.dart
      - login_screen.dart
      - medical_records_screen.dart
      - nutrition_screen.dart
      - patient_dashboard_screen.dart
      - patient_list_screen.dart
      - role_selection_screen.dart
      - settings_screen.dart
      - signup_screen.dart
    - services/
      - appointment_service.dart
      - auth_service.dart
      - chat_service.dart
      - database_helper.dart
      - language_service.dart
      - nutrition_service.dart
      - patient_data_service.dart
      - theme_service.dart
  - test/
    - widget_test.dart
```

## Getting Started

To run this project:
1. Ensure you have Flutter installed.
2. Run `flutter pub get` to install dependencies.
3. Run `flutter run` to launch the application.

For more detailed information tailored to specific features, review the various markdown files (.md) included in the root directory.
