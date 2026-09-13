# LogMog

**Track. Adapt. Improve.**

LogMog is a free iOS fitness app that generates a personalised bodyweight (or gym) workout plan, tracks your macros and meals, and adapts your programme every week based on how you actually performed — all entirely on device.

---

## Features

- **Workout plans** — bodyweight or gym exercises, auto-scheduled across your available days (full body / upper-lower / push-pull-legs depending on frequency)
- **Macro & meal tracking** — log meals, see calorie and macro progress in real time, and get example meals tailored to your targets
- **Weekly adaptation** — the app reviews your adherence each week and adjusts volume and calorie targets accordingly
- **TDEE, BMI & Macro calculators** — know your numbers before you start
- **Apple Health integration** — steps and sleep pulled directly from HealthKit, no manual entry needed
- **Fully on-device** — SwiftData persistence, no account, no cloud, no subscription

---

## Tech stack

| Layer | Technology |
|---|---|
| UI | SwiftUI (iOS 17+) |
| Persistence | SwiftData |
| Architecture | MVVM + `@Observable` |
| Health data | HealthKit |
| Notifications | UNUserNotificationCenter |
| Calculations | On-device (TDEE / Mifflin-St Jeor, macro splits) |
| Backend | None |

---

## Project structure

```
LogMog/
├── App/                  AppCoordinator, AppSettings, DesignTokens
├── Calculators/          BMI, TDEE, Macro calculators
├── Data/                 ExerciseLibrary, PersistenceController
├── Engines/              AdaptationEngine, ProgramGenerator
├── Models/               UserProfile, WeeklyProgram, WorkoutDay, DailyLog, …
├── Services/             HealthKitService, NotificationService, HapticManager
└── Views/
    ├── Dashboard/        Today tab
    ├── WeeklyPlan/       Plan tab
    ├── Meals/            Meals tab
    ├── Logging/          Log sheets + AdaptationSheet
    ├── Calculators/      Tools tab
    ├── Settings/         Settings tab
    └── Onboarding/       First-run flow
docs/                     GitHub Pages (logmog.app)
```

---

## Getting started

1. Clone the repo
2. Open `LogMog.xcodeproj` in Xcode 16+
3. Select your development team in **Signing & Capabilities**
4. Enable the **HealthKit** capability if not already present
5. Build and run on an iPhone (iOS 17+) or simulator

No third-party dependencies — everything uses native Apple frameworks.

---

## Roadmap

- [ ] Exercise progression tree traversal (advance to harder variants automatically)
- [ ] Pantry-based meal suggestions respecting dietary restrictions
- [ ] Calorie target adjustment based on weight trend
- [ ] Configurable notification reminder time
- [ ] iCloud sync (optional)

---

## Privacy

LogMog collects no data. All logs, workouts, and health metrics stay on your device. See the full [Privacy Policy](https://logmog.app/privacy.html).

---

## License

MIT © 2026 Chuck Silver

---

## Contact

**Support:** [chuckchuckapps@gmail.com](mailto:chuckchuckapps@gmail.com)  
**Website:** [logmog.app](https://logmog.app)
