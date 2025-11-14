# BeatScan-Portfolio
A private startup project portfolio showing the concept, features, and architecture of BeatScan - a cloud-based app that detects unauthorized use of beats using audio fingerprinting.
## Overview
BeatScan is a platform designed to help music producers protect their work from unauthorized use. Many beats are reused, sampled, or released on streaming platforms without permission, making it difficult for creators to track and confirm usage. BeatScan solves this problem by allowing users to upload their beats, generate audio fingerprints, and scan multiple platforms to detect potential matches.

The system analyzes audio using fingerprint recognition, compares it across a large music library, and returns a list of results. This gives producers a reliable way to monitor their catalog, identify copyright violations, and take action when necessary.

## Preview
- BeatScan Upload and Scan Demo
  
  ![BeatScan Upload and Scan Demo](images/upload&scan-demo.gif)
- BeatScan YouTube Link Scanning Demo
  ![BeatScan YouTube Link Scanning Demo](images/youtube-link&scan-demo.gif)
## Problem
Nowadays music producers often share or sell their beats online, but once the audio is released publicly, it becomes difficult to track how and where it is being used. Many artists use beats without purchasing the proper license, and some even upload the song to streaming platforms, profiting from it. Manually searching for unauthorized usage is nearly impossible.

Therefore, without proper monitoring, producers lose:
- Royalties and revenue
- Ownership control
- Recognition for their work

## Solution of Problem
BeatScan provides a reliable way to detect when and where a beat has been used. By generating a unique audio fingerprint for each uploaded beat and scanning music across multiple platforms, BeatScan identifies potential matches quickly and accurately.

When using BeatScan producers receive:
- A list of match results
- Supports beat scanning directly from YouTube links, allowing fast uploads and organized track management without requiring local audio files.
- Bulk upload support for large beat catalogs
- Drop down menue to control status of the song, with the options: 
  - None
  - Not Paid
  - Contacted
  - Paid
  - Not My Beat
- Duplicate detection removal to avoid repeated scans
This gives creators control, transparency, and protection over their music- without manual searching.

## Features
- Upload Beats- Upload audio files directly to generate secure audio fingerprints and scan for results.
- Deep Scan Mode- Scans the entire beat to detect the maximum number of matches across platforms.
- Normal Scan Mode- Scans a 10–30 second segment of the beat for faster results and lower API usage.
- Custom Segment Selection- Users can choose the exact region and length of the audio segment before scanning.
- YouTube Link Scanning- Upload beats instantly by pasting a YouTube link, therefore, no local file required.
- Bulk Upload Support- Add multiple beats at once to streamline large catalog scanning.
- Audio Fingerprint Matching- Detect where beats appear online using industry-grade audio recognition.
- Duplicate Match Removal- Automatically filters repeated matches to keep results clean and meaningful.
- Membership & Billing via Stripe- Users can purchase plans to unlock scan credits, and additional features.

## Tech Stack
- Backend: Django (Python)
- Database: PostgreSQL
- API Integration: ACRCloud (File-Scanning API)
- Payments: Stripe API (Memberships & Credits System)
- Deployment: AWS Elastic Beanstalk (EBS) (Dockerization in progress)
- Frontend: HTML, CSS, JavaScript (custom UI)
- Version Control: Git & GitHub

## Roadmap

Current Stage
- Core scanning system built (Deep Scan + Normal Scan)
- YouTube link scanning and bulk upload functioning
- Stripe memberships integrated
- Dashboard UI active
- The database has been migrated from SQLite to PostgreSQL to support deployment on AWS Elastic Beanstalk.
- Refactored the detection engine to shift from raw segment scanning to fingerprint hashing. By storing only compact audio fingerprints rather than entire tracks, the system now uses significantly less storage and performs matching much faster scans and rescans.
  - This update made the system faster and cheaper to run by cutting storage needs, reducing API costs, and improving scan speed for users.

Next Steps
- Improve reliability, scaling, and query performance.
- Docker Containerization
- Standardize the runtime environment and simplify deployment.
- Deploy to AWS Elastic Beanstalk
- Set up production environment with RDS PostgreSQL and secure env variables.
- User Roles & Membership Tiers
  - Introduce tiered subscription plans with different scanning limits and Deep Scan access.
- Expand Platform Support
  - Add scanning coverage for more streaming services and social platforms.


