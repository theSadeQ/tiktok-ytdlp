# TikTok Video ID Scraper

This repository uses GitHub Actions and `yt-dlp` to safely and efficiently scrape all video IDs from a target TikTok profile. 

By utilizing `--flat-playlist`, this tool only fetches metadata without downloading video files, minimizing bandwidth and avoiding IP bans.

## How to Run the Scraper

1. Navigate to the **Actions** tab at the top of this GitHub repository.
2. In the left sidebar, click on **Scrape TikTok Video IDs**.
3. On the right side of the screen, click the **Run workflow** dropdown button.
4. Enter the target TikTok username (e.g., `khaby.lame` or `@khaby.lame`).
5. Click the green **Run workflow** button.

## How to Download the IDs

1. Once the workflow finishes running (it will show a green checkmark), click on the run itself.
2. Scroll down to the **Artifacts** section at the bottom of the page.
3. You will see a downloadable `.zip` file named `tiktok-video-ids-[username]`.
4. Extract the zip to find your `[username]_video_ids.txt` file containing the list of IDs.
