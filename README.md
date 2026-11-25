# NSFW Image Detector & Image Tagger - Moderation + Categories

Send image URLs and get, for each one, **moderation scores, a verdict and what the image shows**, in a single call:

**[Run it on Apify](https://apify.com/pomlabs/image-moderation-tagger?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)**: no install, no login, free credit on a new Apify account.

## What you get

- **User uploads**: avatars, marketplace listings, dating profiles, community posts. Block the clear cases, send the grey zone to a human with the reason attached.
- **Scraped images**: chain it after an Instagram, Reddit, Google Images or e-commerce scraper to filter or tag what you collected.
- **Catalogs**: category and tags for product photos, and custom labels for your own listing rules.
- **AI image generators**: check outputs before showing them. Half of the benchmark above is AI-generated images.
- **Ad and brand safety**: weapons, drugs, political and hateful content next to your brand.

## Pricing

**$2 per 1,000 images** ($0.002 per image), everything included: moderation, category, tags, signals and custom labels. Images that cannot be downloaded or decoded are **not charged**.

That is the free-plan price; Apify paid plans (Bronze, Silver, Gold) pay less per item.

## Call it by API

```bash
curl -X POST "https://api.apify.com/v2/acts/pomlabs~image-moderation-tagger/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"imageUrls": ["https://upload.wikimedia.org/wikipedia/commons/3/3a/Cat03.jpg", "https://upload.wikimedia.org/wikipedia/commons/0/05/Glass_of_beer.jpg", "https://www.gstatic.com/webp/gallery/1.webp"]}'
```

Python:

```python
from apify_client import ApifyClient

client = ApifyClient("YOUR_APIFY_TOKEN")
run = client.actor("pomlabs/image-moderation-tagger").call(run_input={"imageUrls": ["https://upload.wikimedia.org/wikipedia/commons/3/3a/Cat03.jpg", "https://upload.wikimedia.org/wikipedia/commons/0/05/Glass_of_beer.jpg", "https://www.gstatic.com/webp/gallery/1.webp"]})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Use it from Claude, Cursor or any MCP client

```bash
claude mcp add image-moderation-tagger "https://mcp.apify.com?tools=pomlabs/image-moderation-tagger" -t http
```

## More Actors by Pom Labs

- [YouTube Transcript Scraper: Translate, No Login · $3/1K](https://apify.com/pomlabs/youtube-transcript-scraper?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [Instagram Transcript Scraper: Reels, TikTok, Facebook, Hook](https://apify.com/pomlabs/social-video-transcript?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [Reddit Scraper: Deleted & Removed, Mods, Hidden Profiles](https://apify.com/pomlabs/reddit-posts-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [LinkedIn Company Scraper (No Cookies): Posts, Similar Companies](https://apify.com/pomlabs/linkedin-company-scraper?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [YouTube Comments Scraper + Replies, Shorts · No API Key · $1/1K](https://apify.com/pomlabs/youtube-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [Instagram Profile Scraper: Exact Followers, Reels Views](https://apify.com/pomlabs/instagram-profile-data?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [LinkedIn Profile Scraper (No Cookies) + Similar Profiles](https://apify.com/pomlabs/linkedin-profile-scraper?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [Threads Scraper: Keyword Search, Posts & Profiles · No Login](https://apify.com/pomlabs/threads-scraper?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [AliExpress Scraper: Exact Units Sold, Prices, Search · $1/1K](https://apify.com/pomlabs/aliexpress-scraper?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [AI Brand Visibility Tracker - ChatGPT, Claude & Perplexity](https://apify.com/pomlabs/ai-brand-visibility?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [Mercado Livre & Amazon BR Coupon Code Checker](https://apify.com/pomlabs/mercadolivre-coupon-checker?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [Page Time Machine · Wayback Diff + AI · No Login · $2.5/1K](https://apify.com/pomlabs/page-time-machine?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [Video Downloader: TikTok No Watermark, Instagram, YouTube, X](https://apify.com/pomlabs/video-downloader?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)
- [Google Trends Scraper: Related Queries, No 429 · $2/1K](https://apify.com/pomlabs/google-trends-scraper?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger)

Full documentation, input fields and output format: [NSFW Image Detector & Image Tagger - Moderation + Categories on Apify](https://apify.com/pomlabs/image-moderation-tagger?utm_source=github&utm_medium=readme&utm_campaign=image-moderation-tagger).
