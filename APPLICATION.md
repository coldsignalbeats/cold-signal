# YouTube API quota extension: draft application (prepared 19 Oct 2026; not submitted)

Submit from the Google account that owns the Cloud project, via the **"YouTube API Services – Audit and Quota Extension Form"** (search that name; it is linked from the YouTube Data API "Quota and Compliance Audits" page). The form's exact fields change from time to time: paste the matching sections below into whatever it asks. Fill in the [bracketed] items yourself. This application goes to Google only; nothing here is public, so it is fine for it to describe all channels together.

Before submitting, check in Google Cloud Console → APIs & Services → YouTube Data API v3 → **Quotas & system limits** and **Metrics**: confirm the current daily limit (expected 10,000) and note the last 30 days' peak usage, and adjust the numbers below if they differ. Unit costs quoted below are Google's published costs as we understand them (upload 1,600; captions insert 400; thumbnail set 50; playlist item insert 50; list calls 1); recheck against Google's quota calculator.

---

## 1. Contact and organisation
- Name / organisation: [your name], independent creator (no company).
- Contact email: [your email]
- Google Cloud project ID: **mythic-cinema-509318-a1** · Project number: [from Cloud Console → Project settings]
- OAuth client type: Desktop (installed application). Consent screen: published (In production), external, used only by the owner.

## 2. What the API client is
A private, internal command-line tool that runs on the owner's own computer and uploads the owner's own original videos to the owner's own YouTube channels. It has no other users, no public interface, and is not offered to anyone else.

It is used to:
- upload finished videos as **private with a scheduled `publishAt` time** (YouTube's own scheduling), then set the custom thumbnail, add captions (an .srt we write ourselves), and add the video to the channel's own playlist;
- list the channel's own uploads and playlists to avoid duplicates and to confirm schedules;
- occasionally update the title/description of its own videos or move a scheduled time.

It never reads, stores or processes any other user's data, comments, analytics or viewer information. OAuth refresh tokens for the owner's channels are stored only on the owner's computer (outside any synced folder) and are used only by this tool.

## 3. Channels served (all owned by the same Google account)
| Channel | Content (all original, made by the owner's own pipeline) | Planned uploads |
|---|---|---|
| Cold Signal | Original instrumental beats (drill, grime), full videos + Shorts | 1 video + 1 Short per day, plus catch-up of an existing backlog |
| Standing Waves | Original ambient/relaxing music videos | up to 2 per day on 5 days a week |
| The Shape of Waves | Original physics explainer films computed from simulations, with Shorts | 2 films + 2 Shorts + up to 4 extra Shorts per week (uploaded on two mornings: 4 uploads each) |
| [new science channel, planned] | Original narrated science explainers built from simulations | about 1 film + 2 Shorts per week |

## 4. Why the default 10,000 units/day is not enough
- One upload costs about 1,600 units; with thumbnail, captions and playlist calls each video costs roughly 1,700–2,100 units. 10,000 units therefore allows only about **5 complete uploads per day across all channels combined**.
- Our combined steady schedule needs about 6–8 uploads on a normal day and 8–10 on the two science release mornings. To stay inside the limit we currently ration uploads (the music channel's daily uploads are cut from 6 to 2 on two days a week so the science channel can post), backlogs accumulate, and any missed day (e.g. an internet outage on 18 Oct 2026) cannot be caught up without delaying other channels.
- Retries for transient failures (e.g. a thumbnail call that fails while a new upload is still processing) also consume quota.

## 5. Quota requested
**50,000 units per day** for YouTube Data API v3 (about 24 complete uploads a day). This covers the steady schedule (~8–10 uploads/day, ~20,000 units) with headroom for backlog catch-up after outages, retries and the planned fourth channel, without any change in behaviour or scope. [Adjust if your 30-day metrics suggest a different figure.]

## 6. Compliance
- Uses only the official Google API client library and OAuth 2.0; only the scopes needed: `youtube.upload`, `youtube`, `youtube.force-ssl` (the last is needed for captions).
- Uploads only the owner's own original content; all metadata is accurate; synthetic/AI elements are disclosed using YouTube's altered-content setting where applicable.
- No scraping, no data from other users, no storage of API data beyond the video IDs and schedule of our own uploads (kept in a local log to avoid duplicate uploads).
- No attempt to circumvent quota: one project, one OAuth client, one owner. (We are applying here instead of creating additional projects.)
- Privacy policy and terms for the tool: [URL once hosted; draft text in PRIVACY-POLICY.md].

## 7. Demonstration (if the form asks for screenshots or a screencast)
Capture, on your machine:
1. The Google sign-in/consent screen for the app showing the three scopes.
2. A terminal run of a dry-run (`--plan` / no `--go`) showing what would be uploaded, then a real scheduled upload with its log lines (video ID, publish time, thumbnail, captions, playlist).
3. YouTube Studio showing the resulting **scheduled** private video with its publish time.
4. The Cloud Console quota page showing the 10,000 limit being reached on a busy day (if available).
Blur nothing sensitive beyond tokens/keys (never show client secrets or tokens).

## 8. Short answers for common form questions
- *Is your API client used by people outside your organisation?* No, owner only.
- *Do you store YouTube API data?* Only our own uploaded video IDs, titles and scheduled times, in a local log, to prevent duplicates.
- *Does your client display YouTube data to users?* No.
- *Is your client a commercial product?* No; it is an internal publishing tool for the owner's channels.
- *Expected daily units:* steady ~20,000; peak ~35,000 after outages; requested 50,000.
