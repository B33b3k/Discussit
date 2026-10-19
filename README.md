# Discussit

A community discussion app built with Flutter and Firebase. People can create communities, share posts, and take part in comment threads.

## Features

- Google sign-in and guest sign-in
- Create, search, join, and leave communities
- Text, image, and link posts, with comments and voting
- User profiles, community editing, and moderator tools
- Light and dark themes

## Stack

Flutter and Dart, Riverpod, Routemaster, Firebase Authentication, Cloud Firestore, and Firebase Storage.

## Project layout

The Flutter app is in `discussit/`. The root also contains a `discuss_it` gitlink; it is not the app directory used by the commands below.

```text
discussit/
  lib/core/         Routing, shared widgets, and Firebase providers
  lib/features/     Authentication, communities, posts, feed, and profiles
  lib/models/       User, community, post, and comment models
  lib/theme/        Theme configuration
  assets/           Images and fonts
```

## Local setup

Use a Flutter release compatible with the Dart constraint in `discussit/pubspec.yaml` (`>=3.0.6 <4.0.0`). The dependencies are from an older Flutter/Firebase generation; compatibility with the latest Flutter release has not been verified.

1. Create a development Firebase project and enable Authentication, Cloud Firestore, and Storage. Enable the Google and anonymous sign-in providers used by the app.
2. From `discussit/`, use the FlutterFire CLI to configure that project for your target platforms. Review `lib/firebase_options.dart` and the platform Firebase configuration so local testing does not use someone else's backend.
3. Configure Firestore and Storage rules for your development project before using real data. Rules are not supplied at the repository root.
4. Install dependencies and start the app:

```bash
cd discussit
flutter pub get
flutter run
```

## Development checks

From `discussit/`:

```bash
flutter analyze
flutter test
```

These are development commands, not a claim that the current source passes them. Native platform builds and backend access need separate verification.

## License

See [LICENSE](LICENSE).
