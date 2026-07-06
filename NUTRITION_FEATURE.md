# Nutrition Recommendations Feature

## Overview
The HealthFlow Flutter app now includes a **personalized nutrition recommendation system** that analyzes patient vital signs and provides tailored dietary advice with visual food recommendations.

## Features Implemented

### 1. **Intelligent Vital Analysis**
The system analyzes the following patient vitals:
- Blood Pressure (Systolic/Diastolic)
- Blood Sugar Level
- Heart Rate
- BMI (Body Mass Index)
- Cholesterol Level
- SpO2 (Oxygen Saturation)

### 2. **Personalized Recommendations**
Based on vital analysis, the system identifies health conditions and provides:
- **Condition Detection**: High Blood Pressure, High Blood Sugar, High Cholesterol, Overweight, or Healthy
- **Personalized Advice**: Specific dietary guidance for each condition
- **Foods to Eat**: Recommended foods with health benefits
- **Foods to Avoid**: Foods that may worsen the condition

### 3. **Visual Food Catalog**
Each food recommendation includes:
- **High-quality images** from Unsplash
- **Food name** and **category** (Fruits, Vegetables, Grains, Protein, Dairy, Nuts)
- **Health benefit** explanation
- **Visual indicators** (green checkmark for recommended, red X for avoid)

## File Structure

```
lib/
├── models/
│   └── nutrition_model.dart          # Data models for food items and recommendations
├── services/
│   └── nutrition_service.dart        # Vital analysis and recommendation logic
└── screens/
    ├── nutrition_screen.dart         # Full nutrition recommendations display
    └── patient_dashboard_screen.dart # Updated with nutrition card
```

## How It Works

### Step 1: Vital Analysis
```dart
NutritionService.analyzeVitals(
  bloodPressureSystolic: 120,
  bloodPressureDiastolic: 80,
  bloodSugar: 95,
  heartRate: 72,
  bmi: 23.5,
  cholesterol: 180,
  spo2: 98,
)
```

### Step 2: Condition Detection
The service evaluates each vital against healthy ranges:
- **High BP**: Systolic > 140 or Diastolic > 90
- **High Blood Sugar**: > 125 mg/dL
- **High Cholesterol**: > 200 mg/dL
- **Overweight**: BMI > 25

### Step 3: Food Recommendations
Based on detected conditions, the system recommends specific foods:

#### For High Blood Pressure:
**Foods to Eat:**
- 🍌 Bananas (High in potassium)
- 🥬 Spinach (Rich in nitrates)
- 🥣 Oats (High in fiber)
- 🐟 Salmon (Omega-3 fatty acids)
- 🧄 Garlic (Natural BP reducer)
- 🥕 Beetroot (Contains nitrates)

**Foods to Avoid:**
- 🥓 Processed Meats (High sodium)
- 🥒 Pickles (Very high sodium)
- 🥫 Canned Soup (Excessive sodium)

#### For High Blood Sugar:
**Foods to Eat:**
- 🥦 Broccoli (Low glycemic index)
- 🥜 Almonds (Controls blood sugar)
- 🍂 Cinnamon (Improves insulin sensitivity)
- 🍗 Chicken Breast (Lean protein)
- 🫐 Berries (Low glycemic, antioxidants)

**Foods to Avoid:**
- 🍞 White Bread (High glycemic index)
- 🥤 Sugary Drinks (Rapid blood sugar spike)
- 🍟 French Fries (Unhealthy fats and carbs)

#### For High Cholesterol:
**Foods to Eat:**
- 🥑 Avocado (Healthy fats)
- 🌰 Walnuts (Omega-3s)
- 🫒 Olive Oil (Monounsaturated fats)
- 🍎 Apples (Pectin lowers cholesterol)

**Foods to Avoid:**
- 🥩 Red Meat (High saturated fat)
- 🧈 Butter (High saturated fat)
- 🍤 Fried Foods (Trans fats)

#### For Overweight (BMI > 25):
**Foods to Eat:**
- 🌾 Quinoa (High protein, filling)
- 🥛 Greek Yogurt (High protein)
- 🥒 Cucumber (Low calorie, hydrating)

**Foods to Avoid:**
- 🍦 Ice Cream (High sugar and calories)
- 🥔 Chips (High calories, unhealthy fats)

## User Interface

### Patient Dashboard Card
A beautiful gradient card displays:
- **Personalized Diet Plan** title
- Number of foods to eat vs. avoid
- Current health condition
- Tap to view full recommendations

### Nutrition Screen
Full-screen view with:
- **Health Status Banner**: Gradient header with condition and advice
- **Foods to Eat Section**: Grid of recommended foods with images
- **Foods to Avoid Section**: Grid of foods to limit/avoid
- **Category Legend**: Visual guide to food categories

## Food Categories
- 🍎 **Fruits**: Bananas, Berries, Avocado, Apples
- 🥬 **Vegetables**: Spinach, Broccoli, Garlic, Beetroot, Cucumber, Carrots, Tomatoes
- 🌾 **Grains**: Oats, Brown Rice, Quinoa, Olive Oil, Cinnamon
- 🍗 **Protein**: Salmon, Chicken Breast, Eggs
- 🥛 **Dairy**: Greek Yogurt
- 🥜 **Nuts**: Almonds, Walnuts

## Example Scenarios

### Scenario 1: Healthy Patient
**Vitals**: All normal
**Condition**: Healthy
**Advice**: "Maintain your healthy lifestyle!"
**Recommendations**: 6 foods to eat, 2 foods to avoid

### Scenario 2: High Blood Pressure
**Vitals**: BP 145/95
**Condition**: High Blood Pressure
**Advice**: "Reduce sodium intake, increase potassium-rich foods, and maintain a healthy weight."
**Recommendations**: 6 foods to eat, 3 foods to avoid

### Scenario 3: High Blood Sugar
**Vitals**: Blood Sugar 140 mg/dL
**Condition**: High Blood Sugar
**Advice**: "Choose low glycemic index foods, increase fiber intake, and limit refined carbohydrates."
**Recommendations**: 5 foods to eat, 3 foods to avoid

### Scenario 4: Multiple Conditions
**Vitals**: High BP + High Cholesterol + Overweight
**Condition**: Multiple conditions detected
**Recommendations**: Combined list of all relevant foods

## Technical Details

### Data Models
```dart
class FoodItem {
  final String name;
  final String category;
  final String imageUrl;
  final String benefit;
  final bool isRecommended;
}

class NutritionRecommendation {
  final String condition;
  final String advice;
  final List<FoodItem> foodsToEat;
  final List<FoodItem> foodsToAvoid;
  final Map<String, double> vitals;
}
```

### Image Sources
All food images are sourced from Unsplash (https://unsplash.com) with proper attribution.

## Future Enhancements

1. **Dynamic Vital Integration**: Connect to real patient vital data from database
2. **Meal Planning**: Generate daily/weekly meal plans
3. **Recipe Suggestions**: Provide healthy recipes using recommended foods
4. **Portion Control**: Add serving size recommendations
5. **Calorie Tracking**: Calculate daily caloric needs
6. **Shopping List**: Generate grocery lists from recommendations
7. **Food Diary**: Allow patients to log meals
8. **Progress Tracking**: Monitor dietary adherence over time
9. **Multilingual Support**: Translate food names and benefits
10. **Offline Mode**: Cache food images for offline access

## Usage

### For Patients
1. Log in to the patient dashboard
2. View your vitals in the dashboard
3. Tap on the **"Personalized Diet Plan"** card
4. Browse foods to eat and foods to avoid
5. Read health benefits for each food
6. Follow the dietary advice provided

### For Developers
```dart
// Generate recommendations
final recommendation = NutritionService.analyzeVitals(
  bloodPressureSystolic: 120,
  bloodPressureDiastolic: 80,
  bloodSugar: 95,
  heartRate: 72,
  bmi: 23.5,
  cholesterol: 180,
  spo2: 98,
);

// Navigate to nutrition screen
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => NutritionScreen(recommendation: recommendation),
  ),
);
```

## Benefits

✅ **Personalized**: Tailored to individual health conditions
✅ **Visual**: Beautiful images make healthy eating appealing
✅ **Educational**: Explains why each food is beneficial or harmful
✅ **Actionable**: Clear guidance on what to eat and avoid
✅ **Comprehensive**: Covers multiple food categories
✅ **Evidence-based**: Recommendations based on medical guidelines
✅ **User-friendly**: Simple, intuitive interface

## Medical Disclaimer

⚠️ **Important**: This nutrition recommendation system is for educational and informational purposes only. It should not replace professional medical advice, diagnosis, or treatment. Always consult with a qualified healthcare provider before making significant dietary changes, especially if you have existing health conditions or are taking medications.

---

**Created**: February 15, 2026
**Version**: 1.0.0
**Status**: ✅ Fully Implemented and Ready to Use
