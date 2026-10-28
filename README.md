# Max & Zak's Christmas Wishlist

## What is included
- Festive mobile-friendly site with Max and Zak tabs.
- Gift name, website URL, price, priority, and notes.
- Amazon wishlist links.
- Family reservation and parent purchase controls in a **local UI demonstration**.
- Safe DOM rendering (no user-provided HTML injected).

## Important: demo limitations
This is a **prototype**, not a live shared wishlist. Data is saved in the browser's localStorage only. It does not synchronize across phones/computers. Sign-in is intentionally disabled: hiding a button or using a JavaScript PIN is not secure access control. Do not use the prototype to track actual family reservations, as other relatives won't see them.

## How to preview
Open `index.html` in a browser. The Family view is read-only by default; the other screens are demonstrated in the code but secure authentication must be added before real deployment.

## What is needed for a production version
1. Create a Firebase project and enable Firebase Authentication (one account per child and parent, with anonymous or email-link family accounts if desired) and Cloud Firestore.
2. Store gift documents with `kid`, `name`, `url`, `price`, `priority`, `notes` and ownership. Store reservations in a separate collection so children cannot read them.
3. Enforce **server-side Firestore security rules**: only the matching child or parent can create/update/delete gift items; family members may read published gift fields and create their own reservation; kids must not read reservation or purchase collections; parent can read and update all. Avoid exposing purchaser identities to children.
4. Implement Firebase client sign-in, Firestore real-time listeners, and transactional reservation writes to prevent double-booking.
5. Test access from two separate devices/accounts, including confirming kids cannot see reservation records even through browser developer tools.
6. Deploy the finished site to GitHub Pages or Firebase Hosting, then share the URL.

**The current demo does not implement steps 1–5 and must not be described as a fully functional multi-user family website.**
