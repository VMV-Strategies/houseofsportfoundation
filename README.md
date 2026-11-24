# The House of Sport Foundation (`www.thehouseofsport.ca`)

Official static website for **The House of Sport Foundation**, built for zero-cost hosting on **GitHub Pages** and connected to **GoDaddy**.

---

## Files Included in This Repository

1. **`index.html`** — The complete, self-contained website (HTML, Tailwind CSS, and interactive JavaScript).
2. **`CNAME`** — Tells GitHub Pages to serve this site on your custom domain (`www.thehouseofsport.ca`).
3. **`README.md`** — This step-by-step deployment and DNS setup guide.

---

## Part 1: Upload Your Files to GitHub

1. **Sign in to GitHub:** Go to [github.com](https://github.com) and log into your account (or create a free account).
2. **Create a New Repository:**
   - Click the **`+`** icon in the top-right corner and select **New repository**.
   - **Repository name:** `house-of-sport-website` (or any name you prefer).
   - **Visibility:** Select **Public** (required for free GitHub Pages hosting).
   - Click **Create repository**.
3. **Upload the Files:**
   - On your new repository page, click **uploading an existing file** (or **Add file** -> **Upload files**).
   - Drag and drop **`index.html`** and **`CNAME`** (and optionally `README.md`) into the upload box.
   - At the bottom, click **Commit changes**.

---

## Part 2: Enable GitHub Pages

1. Inside your GitHub repository, click the **Settings** tab at the top.
2. In the left sidebar, click **Pages** (under *Code and automation*).
3. Under **Build and deployment** -> **Source**, ensure **Deploy from a branch** is selected.
4. Under **Branch**:
   - Change `None` to **`main`**.
   - Keep the folder set to **`/ (root)`**.
   - Click **Save**.
5. Under **Custom domain**, verify that `www.thehouseofsport.ca` appears automatically from your `CNAME` file (if blank, type `www.thehouseofsport.ca` and click **Save**).

---

## Part 3: Connect Your GoDaddy Domain (`www.thehouseofsport.ca`)

1. **Open GoDaddy DNS Management:**
   - Log in to [GoDaddy.com](https://www.godaddy.com).
   - Go to **My Products** -> find **`thehouseofsport.ca`** -> click **DNS** (or **Manage DNS**).
2. **Remove Conflicting Records:**
   - Look at your existing **DNS Records** table.
   - If there is an existing **`A`** record with Name **`@`** (often pointing to `Parked` or a GoDaddy IP), delete or edit it.
   - If there is an existing **`CNAME`** record with Name **`www`**, delete or edit it.
3. **Add the 4 GitHub Pages `A` Records (for root domain `thehouseofsport.ca`):**
   Click **Add New Record** four times to create these four `A` records:

   | Type | Name | Value | TTL |
   | :--- | :--- | :--- | :--- |
   | `A` | `@` | `185.199.108.153` | Default (1 Hour) |
   | `A` | `@` | `185.199.109.153` | Default (1 Hour) |
   | `A` | `@` | `185.199.110.153` | Default (1 Hour) |
   | `A` | `@` | `185.199.111.153` | Default (1 Hour) |

4. **Add the `CNAME` Record (for `www.thehouseofsport.ca`):**
   Click **Add New Record** and enter:

   | Type | Name | Value | TTL |
   | :--- | :--- | :--- | :--- |
   | `CNAME` | `www` | `<YOUR-GITHUB-USERNAME>.github.io` | Default (1 Hour) |

   *(Replace `<YOUR-GITHUB-USERNAME>` with your actual GitHub username, e.g., `randeepchhinzer.github.io` — do **not** include the repository name.)*

---

## Part 4: Enable Free HTTPS (SSL Certificate)

1. Wait **15–30 minutes** for GoDaddy's DNS changes to propagate.
2. Return to your GitHub repository -> **Settings** -> **Pages**.
3. Once GitHub shows *"DNS check successful"*, check the box for **Enforce HTTPS**.
4. Visit **`https://www.thehouseofsport.ca`** — both `thehouseofsport.ca` and `www.thehouseofsport.ca` will now load securely over HTTPS!
