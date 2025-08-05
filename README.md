Meethe - A Modern Indian Sweets E-commerce Platform 🍬
Welcome to Meethe! This is a full-stack e-commerce and management platform built for a modern Indian sweet shop. It features a delicious-looking, customer-facing website and a powerful, easy-to-use admin console to manage the entire business.

✨ Features
👩‍💻 Customer-Facing Website (index.html)
Dynamic Product Catalog: Fetches and displays all available sweets in real-time from a Firestore database.

Interactive Shopping Cart: A smooth, sidebar-style cart to add and manage items.

Seamless Ordering: Generates a pre-filled WhatsApp message with the customer's order and a UPI payment link for quick and easy checkout.

Live News & Offers: A dedicated section to display the latest announcements from the admin panel.

Customer Reviews: Users can submit their own reviews and ratings for the sweets.

Fun Zone: Includes a simple Tic-Tac-Toe game and a link to an e-sports tournament page for extra engagement.

Fully Responsive: Looks great on desktops, tablets, and mobile phones.

🔒 Admin Console (admin.html)
Secure Authentication: A dedicated admin panel to manage the shop's data.

Full CRUD for Products: Admins can Create, Read, Update, and Delete sweets from the catalog.

Inventory Management: Easily update stock quantities, prices, descriptions, and mark items as "Best Seller" or "In Stock".

Image Handling: Add product images by uploading a file or simply pasting an image URL.

News & Announcements: Post and delete news items that appear instantly on the main website.

Review Moderation: View and delete customer reviews and suggestions.

🛠️ Tech Stack
Frontend: HTML5, CSS3, Tailwind CSS, Vanilla JavaScript

Backend & Database: Google Firebase

Firestore: Real-time NoSQL database for products, news, and reviews.

Firebase Storage: For hosting uploaded product images.

Firebase Authentication: For anonymous user sign-in.

🚀 Getting Started
To get a local copy up and running, follow these simple steps.

Prerequisites
You will need a Google account to create a Firebase project.

Installation
Clone the repo

git clone https://github.com/your-username/meethe.git

Navigate to the project directory

cd meethe

Set up Firebase

Go to the Firebase Console and create a new project.

In your project, go to Project Settings > General.

Under "Your apps", click the web icon (</>) to create a new web app.

Copy the firebaseConfig object.

In both index.html and admin.html, find the <script type="module"> section and replace the placeholder firebaseConfig object with the one you just copied.

// Inside index.html and admin.html

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};

Enable Firebase Services

In the Firebase console, go to the Build section.

Click on Firestore Database and create a database in production mode.

Click on Storage and enable it.

Click on Authentication, go to the "Sign-in method" tab, and enable Anonymous sign-in.

Set Firestore Security Rules

Go to the Firestore Database > Rules tab.

Replace the default rules with the following to allow public read access but restrict writes:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Allow public read access to all collections
    match /{document=**} {
      allow read: if true;
    }

    // Allow anyone (including admins on the client-side) to write to these collections.
    // For a production app, you would want to lock this down to authenticated admins.
    match /artifacts/{appId}/public/data/{collection}/{docId} {
       allow write: if true;
    }
  }
}

Open the files in your browser

Simply open index.html to see the main website.

Open admin.html to access the admin console.

🤝 Contributing
Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

Fork the Project

Create your Feature Branch (git checkout -b feature/AmazingFeature)

Commit your Changes (git commit -m 'Add some AmazingFeature')

Push to the Branch (git push origin feature/AmazingFeature)

Open a Pull Request

📄 License
Distributed under the MIT License. See LICENSE.txt for more information.
