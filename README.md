# chatframework7

> Buat Project di Firebase
> Aktifkan "Authentication" "Email/Password"
> Aktifkan "Cloud Firestore"

**Atur _"rules"_ di _Firestore Database:_**

  rules_version = '2';
  service cloud.firestore {
    match /databases/{database}/documents {
      match /{room}/{chatId} {
        allow read, write: if request.auth != null;
      }
      match /thorium.users/{userId} {
        allow read, write: if request.auth != null && request.auth.uid == userId;
      }
    }
  }
  
# 082223967676
