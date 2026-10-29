# Ente Naadu (നാട്ടിലെ ആപ്പ്) 🌴

> **നാട്ടിലെ ഡിജിറ്റൽ കൂട്ടായ്മ** — A hyper-local community, local business, and citizen engagement platform designed for zero-cost early development and village/town pilot testing.

---

## 📌 പ്രോജക്റ്റ് തത്വം (Core Philosophy)

1. **ഒരു ബാക്കെൻഡ്, മൂന്ന് പ്ലാറ്റ്ഫോം (One Backend, Multi-Platform):** Django + Django REST Framework ബാക്കെൻഡ്; Flutter മൊബൈൽ ആപ്പും (Android/iOS) Django Web ടെംപ്ലേറ്റുകളും ഇതിൽ പ്രവർത്തിക്കും.
2. **പൂർണ്ണമായും സൗജന്യ ടിയറുകൾ (100% Free Tiers First):** പ്രാരംഭ ഘട്ടത്തിൽ സെർവർ വാടകയോ മറ്റ് ഫീസോ ഇല്ലാതെ ₹0 ചെലവിൽ ലൈവ് ചെയ്യുക.
3. **ചെലവ് വരുന്ന ഫീച്ചറുകൾ പിന്നീട് (Defer Paid Services):** SMS OTP-ക്ക് പകരം Phone+Password auth; വിപുലമായ ഉപയോഗം വരുമ്പോൾ മാത്രം പണമടച്ച സേവനങ്ങളിലേക്ക് മാറുക.

---

## 🏗️ ആർക്കിടെക്ചർ & സൗജന്യ സേവനങ്ങൾ (Tech Stack & Free Infrastructure)

| ഘടകം (Component) | സാങ്കേതികവിദ്യ (Technology) | സൗജന്യ സേവനദാതാവ് (Free Provider) | പരിധി / കുറിപ്പ് |
| :--- | :--- | :--- | :--- |
| **Backend & APIs** | Python / Django REST Framework | **Render Web Service** (Free) | 15 മിനിറ്റ് ഉപയോഗമില്ലെങ്കിൽ sleep ആകും (30-60s wake-up) |
| **Database** | PostgreSQL | **Neon Serverless Postgres** | 0.5 GB സൗജന്യം (Render-ൻ്റെ 30-day expiring DB ഒഴിവാക്കുന്നു) |
| **Media / Storage** | S3 compatible / Cloudinary | **Cloudinary** അല്ലെങ്കിൽ **Supabase Storage** | ഇമേജ് ഒപ്റ്റിമൈസ് ചെയ്ത് സൂക്ഷിക്കുക (1 GB ഫ്രീ) |
| **Mobile App** | Flutter (Dart) | **Android APK / Web PWA** | Google Play ഫീ ($25) നൽകുന്നതുവരെ നേരിട്ടുള്ള APK വിതരണം |
| **Maps & Location** | OpenStreetMap | `flutter_map` + OSM Tiles | Google Maps-ൻ്റെ ചെലവ് ഒഴിവാക്കാം |
| **Push Notifications** | Firebase Cloud Messaging (FCM) | **Firebase Spark Plan** | സൗജന്യം (Blaze പ്ലാനിലേക്ക് മാറേണ്ടതില്ല) |
| **Authentication** | Django Token/JWT Auth | Django Native Database | ഫോൺ നമ്പറും പാസ്‌വേഡും (SMS OTP ഒഴിവാക്കി ₹0 ചെലവ്) |

---

## 📁 പ്രോജക്റ്റ് ഘടന (Repository Structure)

```text
Ente Naadu/
├── backend/                  # Django REST API & Web Portal
│   ├── manage.py
│   ├── requirements.txt
│   ├── render.yaml           # Render deployment configuration
│   ├── entenaadu/            # Main project configuration (settings, urls, wsgi)
│   ├── apps/
│   │   ├── accounts/         # Custom User (Phone+Password), Profiles, Roles
│   │   ├── shops/            # Shop registrations, Categories, Menus/Products
│   │   ├── orders/           # Local orders, Status tracking
│   │   ├── events/           # Village/town news, Notices, Emergency alerts
│   │   ├── complaints/       # Citizen complaints, Suggestions, Feedback
│   │   └── services/         # Local services, Bookings (Phase 2)
│   └── templates/            # Django Web templates for Admin/Portal
├── mobile/                   # Flutter cross-platform mobile app
│   ├── pubspec.yaml
│   └── lib/
│       ├── main.dart
│       ├── core/             # API client, Theme, Local storage, Constants
│       ├── models/           # Data models
│       ├── screens/          # UI views (Auth, Home, Shops, Orders, Events)
│       └── widgets/          # Reusable UI components
├── docs/                     # Documentation & Setup Guides
│   └── free_tier_architecture_guide.md
└── README.md
```

---

## 🚀 വികസന ഘട്ടങ്ങൾ (Development Roadmap)

### 🟢 ഘട്ടം 1: അടിസ്ഥാന ഫീച്ചറുകൾ (₹0)
- [ ] Django യൂസർ മോഡൽ (ഫോൺ നമ്പറും പാസ്‌വേഡും അടിസ്ഥാനമാക്കിയുള്ള ലോഗിൻ).
- [ ] അഡ്മിൻ പാനൽ & റോൾ മാനേജ്മെന്റ് (Super Admin, Shop Owner, Citizen).
- [ ] കടകളുടെ രജിസ്ട്രേഷൻ (Shop profile, category, contact, timing).
- [ ] ഉൽപ്പന്നങ്ങൾ / മെനു മാനേജ്മെന്റ് (Products & Menus).
- [ ] ഓർഡർ പ്ലേസിംഗും സ്റ്റാറ്റസ് ട്രാക്കിംഗും (Simple local orders).
- [ ] പഞ്ചായത്ത് / നാട്ടിലെ പരിപാടികളും നോട്ടീസുകളും (Event notifications & announcements).
- [ ] പരാതികളും നിർദ്ദേശങ്ങളും (Complaints & suggestions portal).

### 🟡 ഘട്ടം 2: മാപ്പിംഗും സർവീസുകളും (₹0)
- [ ] കടകളുടെയും സേവനങ്ങളുടെയും ലൊക്കേഷൻ മാപ്പിൽ കാണിക്കൽ (OpenStreetMap).
- [ ] സർവീസ് ബുക്കിംഗ് / റിക്വസ്റ്റ് (പ്ലംബർ, ഇലക്ട്രീഷ്യൻ, ടാക്സി തുടങ്ങിയവ).
- [ ] ഫോട്ടോ അപ്‌ലോഡ് (Supabase/Cloudinary ഇൻ്റഗ്രേഷൻ).

### 🔵 ഘട്ടം 3: കമ്മ്യൂണിക്കേഷൻ (₹0)
- [ ] മെമ്പർ കണക്ഷനുകൾ (Friends & Community).
- [ ] ടെക്സ്റ്റ് ചാറ്റ് (Shop-to-Customer & Peer-to-Peer messaging).

### 🟣 ഘട്ടം 4: ലൊക്കേഷനും കോളുകളും (₹0)
- [ ] അടുത്തുള്ള സുഹൃത്തുക്കൾ / കടകൾ (GPS Nearby Discovery).
- [ ] വോയ്സ് കോളിംഗ് (Agora Free 10,000 മിനിറ്റ് പരിധിക്കുള്ളിൽ).

### 🔴 ഘട്ടം 5 & 6: റിലീസും സ്കെയിലിംഗും (Paid)
- [ ] Google Play Store റിലീസ് (ഒറ്റത്തവണ $25).
- [ ] ആപ്പിൾ ആപ്പ് സ്റ്റോർ റിലീസ് ($99/വർഷം).
- [ ] SMS OTP & 24/7 ലൈവ് ഇൻസ്റ്റൻസ് (Render Starter ~$7/മാസം).

---

## 🛠️ വിശദമായ ഗൈഡ് (Detailed Guide)
സൗജന്യ സെറ്റപ്പും അപകടസാധ്യതകളും ഒഴിവാക്കാനുള്ള വിശദ വിവരങ്ങൾക്ക് [docs/free_tier_architecture_guide.md](docs/free_tier_architecture_guide.md) കാണുക.
