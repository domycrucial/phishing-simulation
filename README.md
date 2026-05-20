# Phishing Attack Simulation — README

## Overview

This project is an interactive cybersecurity awareness training simulation built entirely with HTML, CSS, and JavaScript. It demonstrates how modern phishing attacks work through two realistic attack scenarios:

1. **Email Phishing Simulation**
2. **WhatsApp Phishing Simulation**

The application is designed for:

* Cybersecurity awareness training
* Employee phishing education
* Classroom demonstrations
* Security workshops
* Red-team awareness simulations
* Self-learning environments

The simulation walks users through each stage of a phishing attack, showing:

* How attackers manipulate victims
* How fake login pages steal credentials
* How account takeovers occur
* The downstream consequences of compromise
* Defensive security practices

---

# Features

## Core Features

* Interactive multi-scene phishing simulations
* Realistic phishing email and WhatsApp interfaces
* Voice narration using the browser Speech Synthesis API
* Simulated credential theft
* Real-time attacker capture visualization
* Animated attack-chain progression
* Security awareness explanations
* Interactive quizzes and scoring
* Mobile-friendly UI
* No backend required

---

# Simulation Modules

## 1. Email Phishing Simulation

The email simulation follows a finance officer named Sarah.

### Attack Flow

#### Scene 0 — Introduction

Introduces the victim and scenario.

#### Scene 1 — Inbox

User sees a realistic corporate email inbox with:

* Normal emails
* One malicious phishing email

The phishing email is highlighted visually.

#### Scene 2 — Phishing Email Analysis

Demonstrates:

* Lookalike domains
* Urgency tactics
* Fear manipulation
* Suspicious call-to-action buttons

Example:

```txt
techc0rp-verify.com
```

Uses:

* Zero (`0`) instead of letter `o`

### Security Lessons

* Domain spoofing
* Social engineering
* Urgency attacks
* Trust exploitation

---

#### Scene 3 — Fake Login Page

The victim clicks the phishing link.

The simulation displays:

* Fake browser UI
* Fake HTTPS warning
* Credential harvesting form

User enters:

* Password

The simulation then:

* Displays stolen credentials
* Simulates attacker command-and-control logging

Example capture:

```txt
USERNAME  : sarah.m@techcorp.com
PASSWORD  : user_input_here
IP ADDRESS: simulated
```

---

#### Scene 4 — Attack Chain

Visual attack progression showing:

1. Account takeover
2. Silent monitoring
3. Internal phishing
4. Data theft
5. Ransomware deployment
6. Financial fraud (BEC)

This demonstrates how:

> One stolen password can escalate into organizational compromise.

---

#### Scene 5 — Protection & Quiz

Covers:

* MFA
* Domain verification
* Password managers
* URL inspection
* Reporting suspicious emails

Includes:

* 3-question interactive quiz
* Score evaluation
* Training feedback

---

# 2. WhatsApp Phishing Simulation

The WhatsApp simulation follows David, a software developer.

---

## WhatsApp Attack Flow

### Scene 0 — Introduction

Explains:

* WhatsApp phishing
* OTP theft
* Session hijacking
* Remote device compromise

---

### Scene 1 — Malicious WhatsApp Message

Demonstrates:

* Compromised trusted contact
* Free reward scams
* Chain phishing
* Social propagation

Example:

```txt
Free 10GB Data Bundle
```

Uses:

* Fake Vodacom domain
* Emotional manipulation
* Social trust

---

### Scene 2 — OTP Theft

Victim visits a fake promotional page.

The fake site:

* Mimics telecom branding
* Requests WhatsApp OTP

The simulation demonstrates:

* WhatsApp session hijacking
* OTP abuse
* Real-time attacker capture

Captured data:

```txt
VICTIM NAME
PHONE NUMBER
WHATSAPP OTP
```

---

### Scene 3 — Account Takeover

Explains:

* WhatsApp registration hijacking
* Session theft
* Contact impersonation
* Fraud propagation

Attacker actions:

* Reads chats
* Sends phishing messages
* Requests money from contacts
* Enables attacker-controlled 2FA

---

### Scene 4 — Remote Device Control

Simulates malicious MDM payload attacks.

Demonstrates:

* Device Administrator abuse
* Remote lock
* Camera access
* Microphone access
* GPS tracking
* Remote wipe
* Factory reset

Includes:

* Animated terminal-style attack simulation

---

### Scene 5 — Defense & Quiz

Covers:

* WhatsApp Two-Step Verification
* OTP protection
* Linked device auditing
* App installation safety
* Device administrator review

Includes:

* Interactive security quiz
* Score feedback system

---

# Technical Architecture

## Frontend Stack

Pure frontend implementation:

| Technology     | Purpose                 |
| -------------- | ----------------------- |
| HTML5          | Structure               |
| CSS3           | Styling and animations  |
| JavaScript     | Logic and interactivity |
| Web Speech API | Voice narration         |

No frameworks are used.

No backend is required.

No database is required.

---

# How It Works

## Scene System

Scenes are controlled dynamically using JavaScript.

Each simulation:

* Has indexed scenes
* Uses `.on` CSS class toggling
* Maintains internal state

Example:

```javascript
function eGo(n) {
  currentEScene = n;
}
```

---

# Speech Narration Engine

Uses:

```javascript
window.speechSynthesis
```

Features:

* Auto narration
* Manual replay
* Voice selection
* Playback control
* Scene-based audio

Narration text stored in:

```javascript
var narrations = { ... }
```

---

# Credential Capture Simulation

The credential theft is simulated locally in the browser.

No credentials are transmitted anywhere.

Example:

```javascript
document.getElementById('ePwdShow').textContent = p;
```

The simulation:

* Reads user input
* Displays it in attacker-style logs
* Demonstrates phishing consequences visually

---

# Quiz Engine

The application includes:

* Multiple-choice questions
* Score tracking
* Instant feedback
* Dynamic result screens

Core functions:

```javascript
buildQuiz()
ansQ()
restartE()
restartW()
```

---

# Progress Tracking

Each simulation has:

* Progress bars
* Scene indicators
* Animated transitions

Progress is updated dynamically:

```javascript
buildEProg()
buildWProg()
```

---

# UI/UX Design

## Design Goals

The interface intentionally mimics:

* Email clients
* Browser windows
* WhatsApp mobile UI
* Corporate login portals

This improves realism for awareness training.

---

# Security Awareness Concepts Demonstrated

## Email Threats

* Lookalike domains
* Credential harvesting
* Business Email Compromise (BEC)
* Ransomware delivery
* Internal phishing
* Social engineering

---

## Mobile/WhatsApp Threats

* OTP theft
* Session hijacking
* Chain phishing
* MDM abuse
* Device administrator attacks
* Remote wipe attacks

---

# Important Security Note

This project is:

* A defensive awareness simulation
* Educational only
* Non-malicious
* Self-contained

It does NOT:

* Send real credentials
* Connect to attacker servers
* Exfiltrate data
* Perform real phishing

All actions are simulated locally inside the browser.

---

# Installation

## Option 1 — Open Directly

Save the file as:

```txt
index.html
```

Open in any modern browser:

* Chrome
* Edge
* Firefox
* Brave

---

## Option 2 — Run Local Server

Python:

```bash
python -m http.server 8000
```

Then open:

```txt
http://localhost:8000
```

---

# Browser Requirements

Recommended:

* Chrome
* Edge

Required features:

* JavaScript enabled
* Speech Synthesis API support

---

# File Structure

```txt
project/
│
├── index.html
└── README.md
```

Everything is embedded into a single HTML file:

* CSS
* JavaScript
* UI components
* Simulation logic

---

# Educational Objectives

Users learn to:

* Identify phishing attempts
* Detect fake domains
* Recognize social engineering
* Protect OTPs
* Use MFA
* Avoid malicious links
* Understand breach escalation
* Respond safely to suspicious messages

---

# Potential Improvements

## Suggested Enhancements

### Backend Analytics

Track:

* Quiz scores
* User progress
* Simulation completion

---

### Admin Dashboard

Allow trainers to:

* Monitor trainees
* Generate reports
* Measure phishing awareness

---

### Multi-language Support

Add:

* Swahili
* French
* Arabic
* Spanish

---

### Additional Attack Scenarios

Possible future modules:

* SMS phishing (Smishing)
* QR phishing (Quishing)
* Fake MFA prompts
* Deepfake voice scams
* Social media impersonation
* Fake software update attacks

---

### Real Email Header Analysis

Add:

* SPF inspection
* DKIM inspection
* DMARC verification

---

# Accessibility

The simulation includes:

* Voice narration
* Large clickable controls
* Responsive design
* Keyboard-compatible inputs

---

# Disclaimer

This software is intended strictly for:

* Cybersecurity awareness
* Security education
* Ethical training purposes

Do not use this project for:

* Real phishing campaigns
* Credential theft
* Unauthorized testing
* Malicious activity

---

# License

You may adapt and extend this project for:

* Educational use
* Internal company training
* Security workshops
* Awareness campaigns

Ensure all modifications remain ethical and defensive in nature.
