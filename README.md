# BeatScan-Portfolio

A private startup project showcasing the concept, features, system design, and production deployment of **BeatScan** — a cloud-based platform that detects unauthorized use of music beats using audio fingerprinting.

🔗 **Live deployment:** https://beatscan.io

---

## Overview

BeatScan is a platform designed to help music producers protect their work from unauthorized use across online platforms. Once beats are shared publicly, they can be reused, sampled, or uploaded to streaming services without permission, making manual tracking nearly impossible.

BeatScan solves this problem by generating **unique audio fingerprints** for uploaded beats and scanning them across large music libraries to detect potential matches. The system returns structured results that allow producers to identify usage, verify ownership, and take appropriate action.

The application is deployed in a **production AWS environment** and optimized for performance, memory efficiency, and concurrent usage.

---

## Preview

- **Beat Upload & Scan Demo**  
  ![BeatScan Upload and Scan Demo](images/upload&scan-demo.gif)

---

## Problem

Music producers frequently sell or share beats online, but once the audio is publicly available:

- Beats are used without proper licensing
- Songs are uploaded to streaming platforms without permission
- Manual searching for misuse does not scale

Without automated detection, producers risk losing:
- Royalties and revenue
- Ownership control
- Credit for their work

---

## Solution

BeatScan provides an automated and scalable solution for monitoring beat usage.

By generating compact **audio fingerprints** and scanning across platforms, BeatScan identifies potential matches efficiently — without storing full audio files long term.

When using BeatScan, producers receive:
- A list of detected match results
- Bulk upload support for large beat catalogs
- Match status tracking via a dropdown system:
  - None
  - Not Paid
  - Contacted
  - Paid
  - Not My Beat
- Automatic duplicate-match removal to avoid repeated scans

This gives creators control, transparency, and protection over their music.

---

## Features

- **Beat Upload & Scanning**  
  Upload audio files to generate fingerprints and scan for matches.

- **Normal Scan Mode**  
  Scans a 10–30 second segment for faster results and reduced API usage.

- **Deep Scan Mode**  
  Scans the entire beat to maximize detection accuracy.

- **Custom Segment Selection**  
  Users can select the exact audio region and length before scanning.

- **Bulk Upload Support**  
  Efficient scanning for large beat catalogs.

- **Audio Fingerprint Matching**  
  Industry-grade recognition powered by ACRCloud.

- **Duplicate Match Removal**  
  Automatically filters repeated matches.

- **Membership & Billing**  
  Stripe-powered subscriptions and scan credit system.

---

## Legal Notice

**YouTube link scanning is currently disabled.**

Saving or processing audio from YouTube violates platform terms of service.  
To ensure legal compliance, BeatScan only supports **user-uploaded audio files** that the producer owns or has rights to use.

---

## Tech Stack

**Backend**
- Django (Python)

**Database**
- PostgreSQL (AWS RDS)

**Audio Recognition**
- ACRCloud File-Scanning API

**Payments**
- Stripe API (subscriptions & credits)

**Frontend**
- HTML, CSS, JavaScript (custom UI)

**Infrastructure**
- AWS Elastic Beanstalk (production)
- AWS RDS (PostgreSQL)

**Version Control**
- Git & GitHub

---

## Production Architecture Highlights

- Deployed on **AWS Elastic Beanstalk**
- PostgreSQL hosted on **AWS RDS**
- Secure environment variables managed via AWS configuration
- Database migrated from SQLite → PostgreSQL
- Fingerprint-only storage (no long-term raw audio storage)
- Optimized scan pipeline for concurrent users
- Improved query performance and result filtering
- UI redesigned for improved usability and visual clarity

---

## Performance & Optimization Work

Significant engineering work was performed to make the system production-ready:

- Fixed **memory leaks** caused by large in-memory audio objects
- Eliminated unnecessary file retention after fingerprint generation
- Reduced API usage through duplicate detection and smarter rescans
- Improved concurrent scan handling without background task queues
- Refactored detection flow to prioritize fingerprint reuse
- Stabilized memory usage to prevent OOM crashes on small instances

These changes made the system:
- Faster
- More scalable
- More cost-efficient
- Stable under real-world usage

---

## Roadmap

### Current Stage (Completed)
- Production deployment on AWS Elastic Beanstalk
- PostgreSQL hosted on AWS RDS
- Core scanning engine optimized
- Memory leaks resolved
- UI redesign completed
- Improved match accuracy and concurrency support

### Next Steps
- Further scalability and reliability improvements
- Advanced analytics and confidence scoring
- Expanded platform coverage (legally compliant sources)
- Enhanced user roles and membership tiers
- Improved monitoring and logging

---

## Disclaimer

This repository is a **portfolio showcase** of a private startup project.  
The source code is not publicly available.

