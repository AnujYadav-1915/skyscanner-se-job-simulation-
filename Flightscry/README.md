# Flightscry Mobile Flight Itinerary App

Flightscry is an Android application proof-of-concept (PoC) developed for Skyscanner to display a user's flight itinerary using Skyscanner's Backpack Android UI library (`net.skyscanner.backpack:backpack-android`).

## Features

- **Backpack Card View (`BpkCardView`):** Utilizes `BpkCardView` with large rounded corners for structured flight cards.
- **Backpack Text Components (`BpkText`):** Utilizes Backpack typography styles (`bpkTextHeading1`, `bpkTextHeading2`, `bpkTextHeading3`, `bpkTextBase`).
- **Flight Information Card:** Displays flight number `SK 1915`.
- **Departure Card:** Displays departure airport code `EDI` (Edinburgh) and departure time `10:30 AM`.
- **Arrival Card:** Displays arrival airport code `SIN` (Singapore) and arrival time `06:45 PM`.

## Getting Started

1. Open the `Flightscry` project in Android Studio.
2. Sync Gradle dependencies.
3. Run the application on an Android Virtual Device (AVD Emulator) running API 33+.
