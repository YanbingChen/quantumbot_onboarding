# QuantumBotCore
This is an onboarding project. Just for learning purpose.

## Project overview and purpose
QuantumBotCore is the core component of the QuantumBot project, designed to manage and handle chat messages efficiently using Firebase and Google Cloud Functions. The primary purpose of this project is to provide a scalable backend solution for chat applications, leveraging Firebase's real-time capabilities and cloud functions to process and store chat messages securely.

## Installation instructions
To set up the QuantumBotCore project locally, follow these steps:

1. **Clone the repository:**

    ```bash
    git clone https://github.com/YanbingChen/quantumbot_onboarding.git
    cd quantumbot_onboarding
    ```

2. **Install Firebase CLI:**

    Ensure you have Node.js installed, then install Firebase CLI globally:

    ```bash
    npm install -g firebase-tools
    ```

3. **Set up Firebase project:**

    Log in to Firebase and initialize your project:

    ```bash
    firebase login
    firebase init
    ```
    - Select `Functions` , `FireStore` and any other services you need.
    - Choose the existing Firebase project or create a new one.
    - Set up Firestore rules and indexes as needed.

4. **Install the dependencies:**

    The project uses Firebase Functions, Firestore, and other services. Install the dependencies by running:
    ```bash
    cd functions
    npm install 
    ```


## Usage guildlines

1. **Deploy the functions:**

    To deploy the Firebase functions, use the following command:

    ```bash
    firebase deploy --only functions
    ```

2. **Interacting with the API:**

    The primary API provided by this project is `addMessage`, which can be called using Firebase's client SDK or HTTP request.
    We can use PostMan to send a POST request to the following URL:
    ```https://us-central1-quantumbot-eb4c3.cloudfunctions.net/addMessage```

    The request body should be in the following format:
    ```json
    {
        "data": {
            "text": "Hello, QuantumBot!",
            "userId": "user123"
        }
    }
    ```
    And for the header we need to set Content-Type to application/json.

    The function will then add the message to the Firestore database and return a success message.

## Code structure and organization

The project is organized as follows:
```    
quantumbot_onboarding/
│
├── functions/
│ ├── api/
│ │ └── addMessage.js # Function to handle adding messages
│ ├── helpers/ # Helper functions (if any)
│ ├── models/ # Data models (if any)
│ ├── node_modules/ # Node.js dependencies
│ ├── services/ # Service layer (if any)
│ ├── .eslintrc.js # ESLint configuration
│ ├── .gitignore # Git ignore file
│ ├── index.js # Main entry point for Cloud Functions
│ ├── package-lock.json # NPM lock file
│ └── package.json # NPM package file
│
├── public/ # Public assets (if any)
├── .firebaserc # Firebase project configuration
├── .gitignore # Git ignore file
├── firebase.json # Firebase configuration
├── firestore.indexes.json # Firestore indexes configuration
└── firestore.rules # Firestore security rules
```

## Contribution guidelines

No contribution guidelines at the moment.

## License

No license at the moment.

## Contact details for support or questions

No contact details at the moment.
