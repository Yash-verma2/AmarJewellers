AmarJewellers — Ready site (Firebase-connected)
===============================================

What this package contains
- AmarJewellers.html  -> a single-file static site that:
  - Reads inventory from Firestore public collection:
    artifacts/amarjewellers-e7f60/public/data/inventory-items
  - Listens to reviews in:
    artifacts/amarjewellers-e7f60/public/data/reviews
  - Allows visitors to submit reviews (written to public reviews path)
  - Provides "Inquire" button which opens WhatsApp with pre-filled message

How to use
1. Download and unzip the package.
2. Open `AmarJewellers.html` in a modern browser (Chrome/Edge/Firefox).
3. Make sure Firestore collections exist in your project:
   - In Firebase Console > Firestore > Start collection:
     Path: artifacts / amarjewellers-e7f60 / public / data / inventory-items
     Add documents for each product with fields:
       - name (string)
       - desc (string)
       - img (string URL)
       - category (string)
       - rating (number, optional)
   - Reviews collection path:
     artifacts / amarjewellers-e7f60 / public / data / reviews
     (Users can submit via the site; you can also manage from Console)

Security & Notes
- Inventory & reviews are read from "public" path to allow the site to display content
  without requiring a login. Only use this for collections you intend to be publicly readable.
- If you'd like to restrict writes (so visitors can't write reviews directly), you should
  configure Firestore Security Rules to only allow writes from authenticated admin users.
- Replace `appId` placeholder in the HTML (firebaseConfig.appId) with the real App ID
  from Firebase Console if you prefer. The site will work without that in most cases.

Want a protected admin panel?
- Currently the site reads public data only and intentionally has no admin UI.
- If you'd like a secure admin UI (login with Firebase Auth and role-based access),
  I can add that and bundle a version with a protected admin interface.

Support
- If you want the ZIP changed (add images, split CSS/JS to files, or include an admin UI),
  reply and I'll update it quickly.
