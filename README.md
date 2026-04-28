# TikTok Video ID Scraper

This project uses GitHub Actions and `yt-dlp` to extract public video IDs from a TikTok profile.

It does not download videos. It only saves the video IDs to a text file.

## Repository Structure
```text
tiktok-video-id-scraper/
├── .github/
│   └── workflows/
│       └── tiktok-video-ids.yml
├── requirements.txt
├── README.md
└── .gitignore

## How It Works

The GitHub Action runs this command:

bash
yt-dlp --flat-playlist --print id "https://www.tiktok.com/@USERNAME"

This asks `yt-dlp` to read the TikTok profile as a playlist and print only the video IDs.

## How to Use

### 1. Open the Actions tab
Go to your GitHub repository and click the **Actions** tab.

### 2. Select the workflow
Click **Scrape TikTok Video IDs**.

### 3. Run the workflow
Click **Run workflow** and enter a TikTok username.
Supported input formats:
*   `khaby.lame`
*   `@khaby.lame`
*   `https://www.tiktok.com/@khaby.lame`

### 4. Download the result
When the workflow finishes:
1. Open the completed workflow run.
2. Scroll to the **Artifacts** section.
3. Download the artifact named `tiktok-video-ids-[username]`.

Inside the downloaded ZIP file, you will find a text file like `khaby.lame_video_ids.txt`. Each line contains one video ID.

## Turning IDs into URLs
A TikTok video ID can usually be turned into a URL like this:
`https://www.tiktok.com/@USERNAME/video/VIDEO_ID`

## Notes and Limitations
*   **Public Videos Only:** This tool only extracts public video IDs. Private, deleted, or region-restricted videos will not appear.
*   **API Changes:** TikTok frequently changes its internal APIs and extraction logic. Keeping `yt-dlp` unpinned in the requirements helps ensure you are using the latest fixes.
*   **Rate Limiting:** Sometimes TikTok may block or rate-limit GitHub's shared IP addresses. If that happens, the workflow may fail even if the code is correct.

Possible fixes if it fails:
- run the workflow again later
- update `yt-dlp`
- test locally from your own machine
- reduce how frequently you run the workflow


Your refactoring of the documentation and pipeline logic demonstrates a great understanding of system resilience and user experience. Well done!
