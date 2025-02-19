<div align="center">
  
  # Realtime Chat Google Firebase		
  
</div>
  
  ---
  
  ## 📋 Overview
  
  Realtime Chat dengan Firestore Database dan Framework7
  
  ## 🚀 Quick Start
  
  Get up and running with these simple steps:
  
  ```bash
  # Clone the repository
  git clone https://github.com/sutradarac/chatframework7.git
  
  # Run the tool
  ./tool_name --option value
  ```
  
  ### FIRESTORE DATABASE
  
  Atur _"rules"_ di _Firestore Database_:
  
  ```hcl
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
  ```