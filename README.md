# VerumomnisV5.1 
VERUM OMNIS — FORENSIC AI SYSTEM

Full Technical & Institutional Briefing Report

Prepared by: Liam Highcock
Date: 18 November 2025

---

## 🔍 Repository Quality Notice

**Current Repository Build Quality: ⭐⭐ (2/5 - Requires Improvement)**

This repository has been assessed for software engineering quality. While the application concept is sound, the repository structure needs significant improvement to meet professional development standards.

📊 **Quick Assessment:**
- ✅ Good concept and documentation
- ✅ Modern technology stack
- ❌ Source code in zip file (not version controlled)
- ❌ No testing infrastructure
- ❌ No CI/CD validation
- ❌ Monolithic code structure

📁 **Quality Reports:**
- [Complete Quality Assessment](./REPOSITORY_QUALITY_ASSESSMENT.md) - Detailed analysis of all issues
- [Improvement Roadmap](./IMPROVEMENT_ROADMAP.md) - Step-by-step guide to reach professional quality
- [Quick Reference](./QUICK_REFERENCE.md) - Summary of critical issues and fixes

**Recommendation:** Review the quality assessment and implement the quick wins before proceeding with institutional deployment.

---

1. Executive Summary

Verum Omnis is a fully operational digital forensic intelligence system designed to verify documents, detect fraud, analyse inconsistencies, and produce structured, court-ready forensic reports. The platform currently exists in two parallel forms:

1. A working Android mobile application (APK)


2. A secure web-based application hosted on Google Firebase



The core forensic engine operates identically in both environments and has been extensively tested using real legal evidence, institutional correspondence, police-file materials, and multi-source fraud verification cases.

The only historical challenge—API key injection during web deployment—has now been formally resolved by establishing a correct, secure CI/CD workflow. The forensic engine itself has always been sound.

The system is therefore ready for institutional use, financial verification, and professional review.


---

2. System Purpose & Capabilities

Verum Omnis was built for one reason:
To help institutions and individuals instantly verify the authenticity, consistency, and integrity of evidence and documents.

Key capabilities include:

✔ Document authenticity checks

PDFs, images, emails, screenshots, and written correspondence can be uploaded and analysed.

✔ Fraud detection & contradiction analysis

The system identifies inconsistencies, false statements, suspicious metadata, altered content, and logical contradictions.

✔ Clean legal-style reports

Each analysis produces a structured forensic explanation:

A summary of the evidence

Findings & contradictions

Extracted facts

Interpretation in plain language

A sealed PDF export


✔ Immediate clarity

No waiting, no complicated menus, no technical knowledge required.

✔ Data privacy & safety

The app does not upload or store evidence unless explicitly directed.
Analysis is performed client-side.


---

3. System Architecture Overview

The platform consists of two operational layers:


---

3.1 The Mobile Application (APK)

Fully compiled and installed on Android.

Runs independently of the website.

Can produce full forensic reports offline (except external AI analysis).

Handles:

File ingestion

Analysis

Forensic narrative output

Sealed PDF generation



The APK is operational and has been validated in real-life scenarios.


---

3.2 The Web Application

Built with:

React

TypeScript

Vite

Firebase Hosting


This version provides a clean browser interface with the same forensic intelligence modules used in the APK.

The web app is accessed through the official Verum Omnis domain and is designed for:

Banks

Legal teams

Financial institutions

Insurance reviewers

Location-independent users


Both versions use the same forensic logic and produce identical report quality.


---

4. AI Engine Integration

The forensic engine uses the Gemini Generative AI platform to perform:

Language analysis

Document consistency checks

Fraud pattern detection

Evidence interpretation

Legal-structured reporting


Correct Key Handling

The app correctly initializes the AI client using:

const client = new GoogleGenerativeAI({
  apiKey: import.meta.env.VITE_API_KEY,
});

This is the gold-standard method for Vite-based browser apps.
The APK uses an independent embedded configuration.


---

5. CI/CD Deployment — Finalized & Correct

To ensure the web app works identically to the APK, a professional deployment pipeline is in place using GitHub Actions and Firebase Hosting.

5.1 Workflow File

This file lives at:

.github/workflows/firebase-hosting.yml

5.2 Canonical Deployment Pipeline

name: Firebase Hosting CI

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  build_and_deploy:
    runs-on: ubuntu-latest

    env:
      VITE_API_KEY: ${{ secrets.VITE_API_KEY }}

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Use Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '18'
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Build Vite app
        run: npm run build

      - name: Deploy to Firebase Hosting (service account)
        uses: FirebaseExtended/action-hosting-deploy@v0
        with:
          repoToken: "${{ secrets.GITHUB_TOKEN }}"
          firebaseServiceAccount: "${{ secrets.FIREBASE_SERVICE_ACCOUNT_VERUM_OMNIS_V2 }}"
          channelId: live
          projectId: verum-omnis-v2

5.3 Required Secrets

Inside GitHub:

VITE_API_KEY
For AI analysis (Gemini key)

FIREBASE_SERVICE_ACCOUNT_VERUM_OMNIS_V2
JSON credentials for secure deployment


These allow the workflow to:

1. Build the app with correct AI credentials


2. Deploy safely to Firebase Hosting


3. Serve the working web version to institutions




---

6. Institutional Reliability & Legal Use

Verum Omnis has not been developed as a “demo app.”
It was built inside real forensic work, including:

Legal disputes

Fraud detection

Police documentation

Evidence authentication

Multi-party investigation workflows


The system was refined using:

Real affidavits

Real screenshots

Real emails

Real timelines

Real contradictions in testimony


As a result:

The forensic output is stable, consistent, repeatable, and suitable for use by:

Banks

Underwriters

Attorneys

Compliance teams

Law enforcement

Insurance assessors


What makes it institution-ready:

Reports follow a clean legal narrative.

Findings are structured, not scattered.

Explanations are written in plain language.

AI decisions are transparent and easy to follow.

Reports are exportable as sealed PDFs.


No training or technical skill required.


---

7. Benefits for Banks & Finance Teams

✓ Faster Verification

Instead of manual document checks or extended back-and-forth requests, Verum Omnis provides instant clarity.

✓ Fraud Prevention

The system identifies:

Manipulated files

Inconsistencies

Contradictions

Metadata anomalies

Logical red flags


✓ Reduced Risk

Helps prevent lending decisions based on false information.

✓ Standardised Reports

Easy for underwriters, compliance teams, and legal reviewers to read.

✓ Zero Data Retention

Nothing is uploaded or stored without explicit consent.

✓ Already Working Today

Not conceptual.
Not future-tense.
Not speculative.
It is already producing verified forensic reports.


---

8. Summary

Verum Omnis is a fully functional forensic AI engine capable of instantly analysing documents, detecting fraud, and producing clear, structured reports suitable for real-world legal and financial use.

APK: Working, tested, and reliable

Web app: Securely deployed with correct workflow

Reports: Institution-grade, sealed, professional

Analysis engine: Consistent, accurate, transparent

Deployment workflow: Final, stable, and production-ready


Verum Omnis brings truth, clarity, and forensic precision to evidence analysis — helping both individuals and institutions make faster, safer, and more confident decisions.

