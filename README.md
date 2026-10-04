# CBA-Bot 24/7 Keep-Alive Sentinel

This public repository runs automated external health checks to keep CBA-Bot permanently active 24/7 on Render.

## How It Works
- Render free tier web services spin down after 15 minutes of zero inbound HTTP traffic.
- Discord Gateway connections are outbound WebSockets, which do not count as inbound HTTP traffic.
- The two scheduled GitHub Actions workflows in this repository ping `https://cba-bot-pkp0.onrender.com/health` every 5 minutes in an interleaved pattern (Alpha at :00, :10, :20... and Bravo at :05, :15, :25...).
- Because this repository is public, GitHub Actions minutes are **100% free and unlimited**.
- This guarantees constant external inbound traffic, keeping CBA-Bot online 24/7 with zero downtime.
