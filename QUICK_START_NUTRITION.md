# 🍎 Quick Start Guide - Nutrition Feature

## Step-by-Step Instructions

### 1️⃣ Login to the App
- Open the app in your browser (Edge)
- Select **"Patient"** role
- Enter credentials:
  - Email: `patient@test.com`
  - Password: `patient123`
- Click **Login**

### 2️⃣ Find the Nutrition Card
After login, you'll see the Patient Dashboard. Scroll down past:
- ✅ Vitals section (Blood Pressure, Sugar, Heart Rate, BMI, Cholesterol, SpO2)
- ✅ Active Medications section
- ✅ Appointments section

You'll find a **beautiful green gradient card** titled:
**"Personalized Diet Plan"**

### 3️⃣ View Your Recommendations
Tap/Click on the green nutrition card to see:

**Top Section (Blue Gradient Banner):**
- 🏥 Your health status (e.g., "Healthy", "High Blood Pressure")
- 💡 Personalized dietary advice

**Middle Section (Foods to Eat):**
- Grid of food cards with images
- Green checkmark badges
- Food names and categories
- Health benefits for each food

**Bottom Section (Foods to Avoid):**
- Grid of foods to limit/avoid
- Red X badges
- Warning explanations

**Footer:**
- Food category legend with icons

## 🎯 What You'll See (Current Test Data)

Since the test patient has normal vitals, you'll see:

**Health Status:** "Healthy"
**Advice:** "Maintain your healthy lifestyle!"

**Foods to Eat (6 items):**
1. 🫐 Mixed Berries - Antioxidants support overall health
2. 🥬 Leafy Greens - Vitamins and minerals for vitality
3. 🍚 Brown Rice - Complex carbs for sustained energy
4. 🥚 Eggs - Complete protein source
5. 🥕 Carrots - Beta-carotene for eye health
6. 🍅 Tomatoes - Lycopene supports heart health

**Foods to Avoid (2 items):**
1. 🍬 Candy - Empty calories, no nutritional value
2. 🥤 Soda - High sugar, damages teeth

## 🧪 Testing Different Health Conditions

Want to see recommendations for different conditions? 

### Option 1: Modify Code (For Developers)
Edit `lib/screens/patient_dashboard_screen.dart` around line 522:

```dart
// For High Blood Pressure recommendations:
final recommendation = NutritionService.analyzeVitals(
  bloodPressureSystolic: 150,  // High BP
  bloodPressureDiastolic: 95,
  bloodSugar: 95,
  heartRate: 72,
  bmi: 23.5,
  cholesterol: 180,
  spo2: 98,
);
```

Then hot reload (press `r` in the terminal or save the file).

### Option 2: Future Enhancement
In a production version, this would automatically pull real vital data from the patient's medical records.

## 📱 Navigation

**From Dashboard → Nutrition Screen:**
- Tap the green "Personalized Diet Plan" card

**From Nutrition Screen → Dashboard:**
- Tap the back arrow (←) in the top-left corner

## 🎨 Visual Features

✨ **Gradient Cards** - Beautiful color gradients
🖼️ **Food Images** - High-quality photos from Unsplash
🏷️ **Category Tags** - Color-coded food categories
✅ **Status Badges** - Green checkmarks and red X marks
📊 **Stats Display** - Count of foods to eat vs. avoid
💡 **Health Tips** - Personalized advice based on vitals

## ⚡ Quick Tips

- **Scroll** to see all food recommendations
- **Read benefits** to understand why each food is recommended
- **Check categories** to plan balanced meals
- **Note the advice** at the top for overall dietary guidance

## 🔧 Troubleshooting

**Q: I don't see the nutrition card**
A: Make sure you're logged in as a **patient** (not doctor) and scroll down past the vitals and medications sections.

**Q: Images not loading**
A: Check your internet connection. Images are loaded from Unsplash CDN.

**Q: Want different recommendations**
A: Modify the vital values in the code (see "Testing Different Health Conditions" above).

---

**Enjoy your personalized nutrition recommendations! 🎉**
