# Navigation Setup Instructions

## Main Menu Configuration

Your navigation should have these items: **Home | Playlists | Shop | Community**

### Steps to Update Navigation in Shopify Admin:

1. **Go to Shopify Admin**
   - Navigate to: **Online Store** → **Navigation**

2. **Edit Main Menu**
   - Click on **Main menu**
   - Remove existing menu items (Catalog, Contact, etc.)

3. **Add New Menu Items**
   
   **Item 1: Home**
   - Name: `Home`
   - Link: `Home page` (or `/`)
   
   **Item 2: Playlists**
   - Name: `Playlists`
   - Link: `Pages` → Select "Playlists" page
   - Note: You'll need to create this page first (see below)
   
   **Item 3: Shop**
   - Name: `Shop`
   - Link: `Collections` → `All products` (or `/collections/all`)
   
   **Item 4: Community**
   - Name: `Community`
   - Link: `Pages` → Select "Community" page
   - Note: You'll need to create this page first (see below)

4. **Save** the menu

---

## Creating the Pages

### Create Playlists Page:
1. Go to **Online Store** → **Pages**
2. Click **Add page**
3. **Title:** `Playlists`
4. **Content:** Add placeholder text like "Coming soon! Check back for curated playlists."
5. **Template:** Select `page.playlists` from the dropdown
6. Click **Save**

### Create Community Page:
1. Go to **Online Store** → **Pages**
2. Click **Add page**
3. **Title:** `Community`
4. **Content:** Add placeholder text like "Join our community! More details coming soon."
5. **Template:** Select `page.community` from the dropdown
6. Click **Save**

---

## Files Created:
- `/templates/page.playlists.json` - Template for Playlists page
- `/templates/page.community.json` - Template for Community page

These templates use the standard page layout and can be customized later when you're ready to add content.
