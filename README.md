<h1 align="center">Quick News</h1>

<p align="center">An Android news app with live headlines, a Gemini-powered assistant that pulls news out of images, and Firebase-backed accounts.</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white" />
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white" />
  <img src="https://img.shields.io/badge/Jetpack%20Compose-4285F4?style=flat-square&logo=jetpackcompose&logoColor=white" />
  <img src="https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black" />
  <img src="https://img.shields.io/badge/Gemini%20AI-8E75B2?style=flat-square&logo=googlegemini&logoColor=white" />
</p>

<p align="center">
  <img src="UI.jpeg" alt="Quick News screens" width="750" />
</p>

## Features

- **News by category**: categories and articles are read live from Firebase Realtime Database, and images load with Coil.
- **Ask about an image**: attach one or more images and ask Gemini a question about them. The answer streams in as it's generated.
- **Auth**: email sign-up and sign-in with Firebase Auth.
- **Feedback**: users can send feedback, which is stored per user in Firestore (`users/{uid}/feedback`) and listed in the app.
- **Favourites, library, browse, polls and surveys**: more screens built with Navigation Compose.
- **Settings, About and Contact** screens, plus an account dialog.

## Tech Stack & Structure

| Layer | Tools |
| --- | --- |
| UI | Jetpack Compose, Material 3, Navigation Compose |
| State | MVVM with ViewModel and LiveData / Compose state |
| AI | Google Generative AI SDK (Gemini), multimodal streaming |
| Backend | Firebase Auth, Realtime Database, Firestore, Storage |

```
app/src/main/java/com/example/musicappui/
├── chat/         # Gemini chat with image input (ChatScreen, chatViewModel)
├── Login_data/   # SignIn / SignUp screens, AuthViewModel, UserRepository
├── ui/theme/     # Home, News, Browse, Library, Favourites, Feedback, Settings, Polls
└── MainActivity.kt
```

## Getting Started

1. Clone the repo and open it in **Android Studio**.
   ```bash
   git clone https://github.com/kushagraSrivastava9651/Quick-News.git
   ```
2. Get a Gemini API key from [Google AI Studio](https://aistudio.google.com/) and add it to your **user-level** `~/.gradle/gradle.properties`, not the project file:
   ```properties
   API_KEY=your_gemini_api_key
   ```
3. Create a Firebase project, enable Email/Password auth and Firestore, then replace `app/google-services.json` with your own file.
4. Sync Gradle and run on a device or emulator (minSdk 24).
