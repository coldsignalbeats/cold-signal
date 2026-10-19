# A minimal website for the quota application (Google Sites, free)

Google asks for a website (home page) and usually a privacy policy URL for the API client. A Google Sites page is enough. It does not need to name you or your channels. Avoid the word "YouTube" in the tool's name (Google's branding rules).

## Steps (about 10 minutes)
1. Go to **https://sites.google.com**, signed in as the Google account that owns the Cloud project. Click **+ Blank site**.
2. Site name (top left): **Channel Publisher**. Page title: **Channel Publisher**.
3. Paste the **Home** text below into the page (Insert → Text box).
4. Add two pages (right panel → **Pages** → **+**): **Privacy Policy** and **Terms of Use**; paste the texts below.
5. Click **Publish** (top right). Web address: choose something neutral, e.g. `channel-publisher-tool` → your site is `https://sites.google.com/view/channel-publisher-tool`. Under "Who can view my site": **Public**.
6. Copy the three URLs (home, /privacy-policy, /terms-of-use).
7. Put them in two places:
   - **Google Cloud Console → Google Auth Platform → Branding** (OAuth consent screen): App home page = home URL; Privacy policy link = privacy URL; Terms of service link = terms URL. App name there should also be **Channel Publisher**. Save.
   - The **quota form** (https://support.google.com/youtube/contact/yt_api_form): website / privacy policy fields.

Tip: in Sites → Settings → you can turn off "Show 'Report abuse'"/footer items only partly; that is fine. Nothing on the site needs to identify you; the contact email can be a dedicated address if you prefer (e.g. a new Gmail alias for the tool).

---

## Home (paste)

**Channel Publisher**

Channel Publisher is a private, internal publishing tool used only by its owner to upload the owner's own original videos to the owner's own channels, using the YouTube API Services.

What it does:
- Uploads finished videos as private with a scheduled publish time
- Sets the owner's own thumbnails and captions
- Adds the owner's videos to the owner's own playlists
- Lists the owner's own uploads to avoid duplicates

It has no other users, does not collect or store anyone else's data, and is not offered to the public.

Privacy Policy · Terms of Use · Contact: [contact email]

---

## Privacy Policy (paste)

**Channel Publisher – Privacy Policy**
Last updated: [date]

Channel Publisher is a private, internal application used only by its owner to upload the owner's own videos to the owner's own channels through the YouTube API Services. It is not offered to, or used by, anyone else.

Information accessed. With the owner's permission (Google OAuth), the tool accesses only the owner's own channels to upload videos, set thumbnails and captions, manage the owner's own playlists and list the owner's own uploads. It does not access, collect or store information about any other person, viewer or user.

Storage. The tool keeps a local record of the owner's own uploaded video IDs, titles and scheduled publish times to avoid duplicate uploads. Authorisation tokens are stored only on the owner's computer. No data is sold, shared or sent to any third party other than Google as required to perform the uploads.

YouTube and Google. Use of YouTube features is subject to the YouTube Terms of Service: https://www.youtube.com/t/terms. Google's Privacy Policy applies to data processed by Google: https://policies.google.com/privacy. Access can be revoked at any time at https://security.google.com/settings/security/permissions.

Contact: [contact email]

---

## Terms of Use (paste)

**Channel Publisher – Terms of Use**
Last updated: [date]

Channel Publisher is for its owner's personal use only and is provided without warranty. Use of YouTube through this tool is subject to the YouTube Terms of Service: https://www.youtube.com/t/terms.
