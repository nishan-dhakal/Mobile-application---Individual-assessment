# Wrangle

A bill-tracking and negotiation-assistant mobile app, built in Flutter for ICT725 Assessment 4.

Wrangle centralises a user's recurring bills into one dashboard and generates a
personalised negotiation script for each bill, so the user can call their
provider and ask for a lower rate themselves — no fees, no shared credentials,
unlike automated bill-negotiation services.

## Implemented major features

1. **Add New Bill** (`lib/screens/add_bill_screen.dart`) — validated form (provider,
   category, amount, due date via native date picker, billing cycle) that adds
   a new bill to shared app state.
2. **Bill Detail — negotiation script & status** (`lib/screens/bill_detail_screen.dart`) —
   dynamically generates a negotiation script from the bill's own data, copies
   it to the clipboard, and updates the bill's status (Active / Negotiating /
   Renewed), reflected immediately on the Home Dashboard.

See the Assessment 4 report for the full breakdown of implemented vs.
not-yet-implemented functionality.

## Design reference

High-fidelity Figma prototype: https://www.figma.com/design/bEHfqOUZSQUdhYjFeZGdNf

## Getting started

1. Install the [Flutter SDK](https://flutter.dev/docs/get-started/install) and confirm setup with `flutter doctor`.
2. Clone this repo and fetch dependencies:
   ```
   git clone <your-repo-url>
   cd wrangle
   flutter pub get
   ```
3. Run on a connected emulator/device:
   ```
   flutter run
   ```

## Project structure

```
lib/
  main.dart                  Entry point, theme + state provider setup
  models/bill.dart           Bill data model
  state/app_state.dart       ChangeNotifier holding the live bill list
  theme/app_theme.dart       Colours/typography matching the Figma design
  screens/home_screen.dart        Dashboard shell (navigation host)
  screens/add_bill_screen.dart    Major feature 1
  screens/bill_detail_screen.dart Major feature 2
```

## Pushing this to your own GitHub repository

```
cd wrangle_flutter
git init
git add .
git commit -m "Initial Wrangle Flutter implementation"
git branch -M main
git remote add origin https://github.com/<your-username>/wrangle.git
git push -u origin main
```
(Create the empty repository on github.com first, then run the commands above from this folder.)
