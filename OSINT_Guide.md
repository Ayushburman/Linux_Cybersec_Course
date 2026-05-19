# ░▒▓ OSINT MASTERCLASS ▓▒░
### Open Source Intelligence — From Zero to Op██████╗ ███████╗██╗███╗   ██╗████████╗
██╔═══██╗██╔════╝██║████╗  ██║╚══██╔══╝
██║   ██║███████╗██║██╔██╗ ██║   ██║   
██║   ██║╚════██║██║██║╚██╗██║   ██║   


## 📡 TABLE OF CONTENTS

```
MODULE 00 ──── Foundations & Mindset
MODULE 01 ──── The OSINT Framework
MODULE 02 ──── Search Engine Intelligence (SOCMINT Setup)
MODULE 03 ──── Google Dorking & Advanced Search
MODULE 04 ──── Social Media Intelligence (SOCMINT)
MODULE 05 ──── People Search & Identity Tracing
MODULE 06 ──── Domain & IP Intelligence
MODULE 07 ──── Image & Video OSINT (IMINT)
MODULE 08 ──── Geolocation Intelligence (GEOINT)
MODULE 09 ──── Dark Web & Breach Data Intelligence
MODULE 10 ──── OSINT Automation & Tooling
MODULE 11 ──── Operational Security (OPSEC)
MODULE 12 ──── Case Studies & Capstone
```

---

## ⬛ MODULE 00 — FOUNDATIONS & MINDSET

```
┌─────────────────────────────────────────────────────────┐
│  WHAT IS OSINT?                                         │
│                                                         │
│  Publicly          Legally           Intelligently      │
│  Available    →    Collected    →    Analyzed           │
│  Data              Information       Intelligence       │
└─────────────────────────────────────────────────────────┘
```

### 0.1 Definition

**OSINT** (Open Source Intelligence) is the collection, analysis, and use of information gathered from **publicly available sources** to produce actionable intelligence.

> It is NOT hacking. It is NOT illegal. It IS a skill.

### 0.2 The Intelligence Cycle

```
         ┌──────────────────────────────┐
         │                              │
    ┌────▼────┐    ┌──────────┐    ┌────▼────┐
    │PLANNING │───►│COLLECTION│───►│PROCESS  │
    └─────────┘    └──────────┘    └────┬────┘
         ▲                              │
    ┌────┴────┐    ┌──────────┐    ┌────▼────┐
    │FEEDBACK │◄───│DISSEM.   │◄───│ANALYSIS │
    └─────────┘    └──────────┘    └─────────┘
```

| Phase | Description |
|-------|-------------|
| **Planning** | Define objective, scope, key intelligence requirements |
| **Collection** | Gather raw data from sources |
| **Processing** | Clean, translate, verify data |
| **Analysis** | Find patterns, draw conclusions |
| **Dissemination** | Report findings |
| **Feedback** | Refine based on results |

### 0.3 Legal & Ethical Boundaries

```
✅ LEGAL / ETHICAL          ❌ ILLEGAL / UNETHICAL
─────────────────────────   ──────────────────────────────
Public social profiles      Accessing private accounts
Public records              Bypassing authentication
WHOIS data                  Scraping behind login walls
News & media                Doxxing with intent to harm
Court records               Stalking individuals
Job postings                Unauthorized interception
```

> **Rule #1:** If it requires credentials you don't own, stop.
> **Rule #2:** Knowing someone's address ≠ publishing it.

---

## ⬛ MODULE 01 — THE OSINT FRAMEWORK

### 1.1 Source Categories

```
                        ┌─────────────────┐
                        │  OSINT SOURCES  │
                        └────────┬────────┘
          ┌─────────────────────┼─────────────────────┐
          ▼                     ▼                     ▼
   ┌─────────────┐      ┌─────────────┐      ┌─────────────┐
   │   INTERNET  │      │  DATABASES  │      │   PHYSICAL  │
   │             │      │             │      │             │
   │ Social Media│      │ Gov Records │      │ Newspapers  │
   │ Websites    │      │ Patents      │      │ Magazines   │
   │ Forums      │      │ Court Docs  │      │ Conferences │
   │ Dark Web    │      │ Business Reg│      │ Radio/TV    │
   └─────────────┘      └─────────────┘      └─────────────┘
```

### 1.2 OSINT Framework Map (Simplified)

```
OSINT FRAMEWORK
│
├── 👤 Username
│   ├── Namechk
│   ├── Sherlock
│   └── WhatsMyName
│
├── 📧 Email Address
│   ├── Hunter.io
│   ├── Have I Been Pwned
│   └── EmailRep.io
│
├── 🌐 Domain / IP
│   ├── WHOIS
│   ├── Shodan
│   ├── BuiltWith
│   └── crt.sh (certs)
│
├── 📷 Images
│   ├── TinEye
│   ├── Google Images
│   ├── Yandex
│   └── PimEyes
│
├── 📍 Geolocation
│   ├── Google Maps
│   ├── Bellingcat Toolkit
│   └── SunCalc
│
└── 🧑 People
    ├── LinkedIn
    ├── Pipl
    ├── Spokeo
    └── BeenVerified
```

> Full interactive map: **https://osintframework.com**

---

## ⬛ MODULE 02 — ENVIRONMENT SETUP

### 2.1 Recommended OSINT OS

```
┌──────────────────────────────────────────────────┐
│  OPTION A: Kali Linux (pre-installed tools)      │
│  OPTION B: Tails OS   (ephemeral, maximum OPSEC) │
│  OPTION C: Whonix     (Tor-routed VM)            │
│  OPTION D: Windows + VPN + VM (beginner-safe)    │
└──────────────────────────────────────────────────┘
```

### 2.2 Browser Setup

```
Firefox (Recommended)
│
├── Extensions
│   ├── uBlock Origin          (block trackers)
│   ├── Privacy Badger         (behavioral blocking)
│   ├── EXIF Viewer Pro        (image metadata)
│   ├── SingleFile             (archive pages)
│   └── Web Archives           (cached versions)
│
└── Settings
    ├── DNS-over-HTTPS: ON
    ├── Fingerprinting: STRICT
    └── Cookies: CLEAR ON EXIT
```

### 2.3 VPN + Proxy Chain Concept

```
YOU → VPN → Tor → Target Site
 │
 └── Your real IP is never exposed to target
```

> **Do not investigate from your home IP.** Ever.

### 2.4 Essential Tools (Free)

| Tool | Purpose | Link |
|------|---------|------|
| **Maltego CE** | Link analysis / graph | maltego.com |
| **Spiderfoot** | Automated OSINT | spiderfoot.net |
| **theHarvester** | Emails, domains, IPs | GitHub |
| **Sherlock** | Username across platforms | GitHub |
| **recon-ng** | Modular recon framework | GitHub |
| **Metagoofil** | Document metadata | GitHub |

---

## ⬛ MODULE 03 — GOOGLE DORKING & ADVANCED SEARCH

```
╔═══════════════════════════════════════════════════════╗
║          G O O G L E   D O R K I N G                 ║
║   Using search operators to find hidden information  ║
╚═══════════════════════════════════════════════════════╝
```

### 3.1 Core Operators

```
OPERATOR          EXAMPLE                    WHAT IT FINDS
────────────────────────────────────────────────────────────
site:             site:github.com osint      All indexed GitHub OSINT pages
filetype:         filetype:pdf resume        PDF files matching resume
inurl:            inurl:admin login          URLs containing "admin"
intitle:          intitle:"index of"         Directory listings
intext:           intext:"confidential"      Pages containing that word
cache:            cache:example.com          Google's cached copy
link:             link:example.com           Pages linking to a site
"quotes"          "John Smith" "New York"    Exact phrase match
-minus            python -snake              Exclude word
*wildcard         "CEO of * Inc"             Fill-in-the-blank search
OR                hacking OR security        Either term
..range           salary $50,000..$100,000   Number ranges
```

### 3.2 Powerful Dork Combinations

```bash
# Find exposed login pages
site:target.com inurl:login

# Find exposed documents
site:target.com filetype:pdf OR filetype:xlsx OR filetype:docx

# Find employee emails
"@target.com" filetype:pdf

# Find open directories
intitle:"index of" "parent directory"

# Find exposed cameras (ETHICAL USE ONLY — research/education)
inurl:/view/index.shtml

# Find subdomains
site:*.target.com -www

# Find cached pages
cache:target.com/deleted-page

# Find social profiles
"John Smith" site:linkedin.com OR site:twitter.com

# Exposed passwords (study only)
filetype:env "DB_PASSWORD"
```

### 3.3 Google Dork Cheatsheet Visual

```
┌─────────────────────────────────────────────────────────────┐
│  site: ────► Restrict to domain                            │
│  filetype: ─► Restrict to file extension                   │
│  inurl: ────► URL must contain string                      │
│  intitle: ──► Page title must contain string               │
│  intext: ───► Page body must contain string                │
│  "..." ─────► Exact phrase                                 │
│  -word ─────► Exclude term                                 │
│  OR ────────► Either / both                                │
│  * ─────────► Wildcard                                     │
│  .. ────────► Numeric range                                │
└─────────────────────────────────────────────────────────────┘
```

> **Other Dork-able Engines:** Bing, Yandex, DuckDuckGo, Shodan, Censys

---

## ⬛ MODULE 04 — SOCIAL MEDIA INTELLIGENCE (SOCMINT)

### 4.1 Platform Intelligence Map

```
PLATFORM     WHAT YOU CAN FIND
──────────────────────────────────────────────────────────────
Twitter/X    Real-time location hints, connections, opinions
             Advanced Search: (from:user since:2023-01-01)

LinkedIn     Employment history, connections, company intel
             Skills, endorsements, education

Instagram    Geotags, tagged locations, facial recognition
             Story highlights, tagged by others

Facebook     Life events, family links, check-ins, old posts

Reddit       Usernames, interests, writing style analysis

TikTok       Geotagged videos, background details, metadata

GitHub       Real names, emails in commits, project history

Discord      Server membership, usernames
```

### 4.2 Twitter / X Advanced Search Operators

```
Operator              Example
──────────────────────────────────────────────────
from:user             from:elonmusk
to:user               to:elonmusk
@mention              @CIA
"exact phrase"        "confirmed dead"
#hashtag              #OSINT
since:YYYY-MM-DD      since:2023-01-01
until:YYYY-MM-DD      until:2023-06-01
near:"city"           near:"New York"
geocode:lat,lng,km    geocode:28.61,77.20,5km
filter:media          filter:media (only tweets with images)
filter:links          filter:links
-filter:retweets      (exclude retweets)
lang:en               lang:en
```

> Direct URL: `https://twitter.com/search-advanced`

### 4.3 Facebook OSINT

```
Graph Search (via URL manipulation):

https://www.facebook.com/search/people/?q=John+Smith
https://www.facebook.com/search/posts/?q=osint+tools

Stalkscan.com alternative:
── Enter Facebook profile URL
── Get all public activity aggregated
```

### 4.4 LinkedIn OSINT (No Account Needed)

```bash
# Google dorking LinkedIn:
site:linkedin.com/in "Company Name" "Job Title"
site:linkedin.com/in "software engineer" "Chandigarh"

# Tools:
─ IntelligenceX     ─ LinkedIn Sales Navigator (paid)
─ Proxycurl API     ─ Hunter.io (find emails from profiles)
```

---

## ⬛ MODULE 05 — PEOPLE SEARCH & IDENTITY TRACING

### 5.1 The Identity Web

```
              ┌───────────────┐
              │   REAL NAME   │
              └───────┬───────┘
         ┌────────────┼────────────┐
         ▼            ▼            ▼
   ┌──────────┐ ┌──────────┐ ┌──────────┐
   │ USERNAME │ │  EMAIL   │ │  PHONE   │
   └────┬─────┘ └────┬─────┘ └────┬─────┘
        │            │            │
        ▼            ▼            ▼
   ┌──────────┐ ┌──────────┐ ┌──────────┐
   │  Social  │ │  Breach  │ │  Carrier │
   │ Profiles │ │   Data   │ │   Info   │
   └──────────┘ └──────────┘ └──────────┘
        │            │            │
        └────────────┼────────────┘
                     ▼
              ┌───────────────┐
              │ FULL PROFILE  │
              └───────────────┘
```

### 5.2 Username Enumeration

```bash
# Sherlock (Python tool)
pip install sherlock-project
sherlock username_here

# WhatsMyName (browser + CLI)
https://whatsmyname.app

# Namechk
https://namechk.com

# Knowem
https://knowem.com
```

### 5.3 Email OSINT

```
EMAIL ADDRESS
     │
     ├──► Hunter.io           (find associated domain profiles)
     ├──► HaveIBeenPwned.com  (breach databases)
     ├──► EmailRep.io         (reputation scoring)
     ├──► Epieos.com          (Google/Apple account linked)
     ├──► IntelligenceX.io    (deep web email search)
     └──► Holehe (CLI tool)   (check 100+ services)
```

```bash
# Holehe — checks if email is registered on 100+ sites
pip install holehe
holehe target@email.com
```

### 5.4 Phone Number OSINT

```
PHONE NUMBER
     │
     ├──► Truecaller        (name, spam flag)
     ├──► Sync.me           (social reverse lookup)
     ├──► NumLookup.com     (carrier, region)
     ├──► PhoneInfoga (CLI) (automated recon)
     └──► Telegram          (search by phone if contact)
```

### 5.5 People Search Engines

| Site | Data Type | Country |
|------|-----------|---------|
| Spokeo.com | Name, address, relatives | US |
| BeenVerified | Background, criminal | US |
| Pipl.com | Deep web people search | Global |
| Intelius | Public records | US |
| 192.com | UK electoral roll | UK |
| Truepeople search | Free US lookup | US |

---

## ⬛ MODULE 06 — DOMAIN & IP INTELLIGENCE

### 6.1 Domain Recon Pipeline

```
TARGET DOMAIN
     │
     ├─ WHOIS ──────────────► Registrant, dates, registrar
     ├─ DNS Records ─────────► A, MX, TXT, NS, CNAME
     ├─ Subdomains ──────────► dev., admin., mail., api.
     ├─ Certificate Logs ────► crt.sh (historical subdomains)
     ├─ Tech Stack ──────────► BuiltWith, Wappalyzer
     ├─ Hosting/CDN ─────────► Shodan, Censys
     └─ Historical snapshots ► Wayback Machine, CachedView
```

### 6.2 WHOIS Lookup

```bash
# CLI
whois example.com

# Web Tools
https://who.is
https://whois.domaintools.com
https://lookup.icann.org
```

Output reveals: registrar, creation date, expiry, name servers, sometimes registrant name/email (before GDPR era).

### 6.3 DNS Intelligence

```bash
# Full DNS dump
dig example.com ANY

# Specific records
dig example.com MX        # Mail servers
dig example.com TXT       # SPF, DKIM, verification tokens
dig example.com NS        # Name servers
dig _dmarc.example.com TXT  # DMARC policy

# Reverse DNS
dig -x 8.8.8.8

# Zone transfer (misconfigured servers leak ALL subdomains)
dig axfr @ns1.example.com example.com
```

### 6.4 Subdomain Enumeration

```bash
# Passive (no direct requests to target)
subfinder -d example.com         # Go tool
amass enum -passive -d example.com

# crt.sh (Certificate Transparency logs)
https://crt.sh/?q=%.example.com

# VirusTotal subdomain search
https://www.virustotal.com/gui/domain/example.com/relations
```

### 6.5 Shodan — The Search Engine for Devices

```
Shodan indexes internet-connected devices.

QUERY SYNTAX:
──────────────────────────────────────────────
hostname:example.com        Devices for domain
org:"Target Company"        By organization
port:22                     SSH exposed servers
country:IN city:Mumbai      Geographic filter
"default password"          Misconfigured devices
product:Apache              Specific software
vuln:CVE-2021-44228         Log4Shell vulnerable hosts
ssl:"example.com"           SSL cert matches
```

```bash
# Shodan CLI
pip install shodan
shodan init YOUR_API_KEY
shodan search "hostname:target.com"
```

---

## ⬛ MODULE 07 — IMAGE & VIDEO OSINT (IMINT)

### 7.1 Reverse Image Search Pipeline

```
IMAGE
  │
  ├──► Google Images     → Most comprehensive, entity recognition
  ├──► Yandex Images     → Best for faces (often beats Google)
  ├──► TinEye            → Exact match + oldest source
  ├──► Bing Visual       → Different index than Google
  └──► PimEyes           → Face search across web (paid/free tier)
```

> **Yandex** is especially powerful for facial recognition — often identifies people where Google fails.

### 7.2 Image Metadata (EXIF)

```
EXIF DATA CAN REVEAL:
─────────────────────────────────────────────
📍 GPS Coordinates     ← Location where photo was taken
📅 Date & Time         ← When it was captured
📱 Device Model        ← Phone/camera make and model
🔧 Software            ← Editing software used
👤 Author field        ← Sometimes real name
```

```bash
# ExifTool (CLI)
exiftool image.jpg

# Web Tools
https://exifdata.com
https://jimpl.com
https://exifmeta.com
```

> **Note:** Major platforms (Twitter, Instagram, Facebook) strip EXIF. But screenshots from messaging apps often don't.

### 7.3 Geolocation from Images (Manual)

```
TECHNIQUE: Identify location clues in photo
─────────────────────────────────────────────
🌿 Vegetation         → Narrows climate zone
🏗️ Architecture       → Regional style hints
🛣️ Road signs         → Language, country code
🔌 Power lines        → Insulator type varies by country
☀️ Sun position       → Use SunCalc.org with time
🗻 Terrain/skyline    → Cross-reference with maps
🚗 License plates     → Country/region format
📻 Billboards/text    → Language, brand geography
```

### 7.4 Video OSINT

```bash
# Download video for frame analysis
yt-dlp "https://youtube.com/watch?v=VIDEO_ID"

# Extract frames
ffmpeg -i video.mp4 -vf fps=1 frames/frame_%04d.jpg

# Reverse search individual frames in Google/Yandex
```

**Key tools:**
- **InVID/WeVerify** — browser extension for video verification
- **Amnesty YouTube DataViewer** — extract metadata from YouTube
- **Google Earth Pro** — match terrain in videos

---

## ⬛ MODULE 08 — GEOLOCATION INTELLIGENCE (GEOINT)

### 8.1 GEOINT Toolkit

```
┌────────────────────────────────────────────────────────┐
│  GEOINT = Locating places, assets, and events         │
│  from publicly available geographic information       │
└────────────────────────────────────────────────────────┘
```

| Tool | Use Case |
|------|----------|
| **Google Maps** | Street view, historical imagery |
| **Google Earth Pro** | 3D terrain, historical layers |
| **SunCalc.org** | Sun angle → time + location |
| **Wikimapia** | User-annotated satellite maps |
| **Overpass Turbo** | OSM data query |
| **Bellingcat Toolkit** | Compilation of geo tools |
| **What3Words** | 3-word location codes |

### 8.2 Shadow Analysis with SunCalc

```
METHOD:
1. Take a photo with visible shadows
2. Go to SunCalc.org
3. Move location on map to match terrain
4. Adjust date/time until shadow angle matches
5. Result: precise time AND location estimate
```

### 8.3 Building a Geolocated Timeline

```
EVENT TIMELINE CONSTRUCTION:
─────────────────────────────────────────────────
1. Collect all available images/videos
2. Extract timestamps (EXIF or shadow analysis)
3. Geolocate each piece of media
4. Plot on timeline + map
5. Cross-reference with news/social reports
6. Look for contradictions or confirmations
```

---

## ⬛ MODULE 09 — DARK WEB & BREACH DATA INTELLIGENCE

> ⚠️ **Legal notice:** Accessing dark web is legal in most jurisdictions. Purchasing data, accessing CSAM, or engaging with illegal marketplaces is not.

### 9.1 Dark Web OSINT (Passive)

```
SURFACE WEB        DEEP WEB            DARK WEB
────────────────────────────────────────────────────────
Google-indexed   ─►  Not indexed     ─►  Requires Tor
~5% of web          ~90% of web          ~0.01% of web
Social, news,       Email, banking,      Forums, markets,
public sites        private databases    whistleblower sites
```

```
Tor Onion Services for OSINT:
─────────────────────────────
Ahmia.fi          → Dark web search engine (clearnet accessible)
OnionSearch       → Aggregated .onion search
Hunchly           → Page capture + dark web monitor
DarkSearch.io     → Dark web search (indexed)
```

### 9.2 Breach Data Intelligence

```
SOURCE                WHAT YOU CAN SEARCH
──────────────────────────────────────────────────────────────
HaveIBeenPwned.com    Email → which breaches it appears in
IntelligenceX.io      Email, IP, domain in leaked datasets
Dehashed.com          Username, email, IP, name (paid)
BreachDirectory.org   Plaintext password lookup
LeakCheck.io          Email breach check
Snusbase.com          Breach database search
```

### 9.3 Interpreting Breach Data

```
LEAKED RECORD EXAMPLE:
──────────────────────────────────────────────
Email:    user@example.com
Username: shadow_coder
Password: [hashed or plaintext]
IP:       192.168.x.x
Phone:    +91-XXXXXXXXXX
──────────────────────────────────────────────
What this reveals:
  → Username used on other platforms (search Sherlock)
  → Password reuse on other accounts
  → IP reveals rough location history
  → Phone enables reverse lookup
```

---

## ⬛ MODULE 10 — OSINT AUTOMATION & TOOLING

### 10.1 Recon-ng (Modular Framework)

```bash
# Install
pip install recon-ng

# Launch
recon-ng

# Key commands
workspaces create target_name
modules search recon
modules load recon/domains-hosts/google_site_web
options set SOURCE target.com
run
```

### 10.2 SpiderFoot (Automated OSINT)

```
SpiderFoot automates 200+ OSINT data sources.

INPUT:  Domain, IP, Email, Username, Phone, Name
OUTPUT: Relationship graph + full report

Run locally:
─────────────────────────────────────
git clone https://github.com/smicallef/spiderfoot
cd spiderfoot
pip install -r requirements.txt
python sf.py -l 127.0.0.1:5001
```

### 10.3 Maltego (Visual Link Analysis)

```
┌──────────────────────────────────────────────────┐
│  MALTEGO GRAPH EXAMPLE                           │
│                                                  │
│  [Domain] ──► [IP Address] ──► [Hosting Org]    │
│      │                              │            │
│      └──► [Email] ──► [Person] ──► [LinkedIn]  │
│                │                               │ │
│                └──► [Breach Record]            │ │
└──────────────────────────────────────────────────┘
```

> Maltego CE (Community Edition) is free. Transforms are the modules that pull data.

### 10.4 theHarvester

```bash
# Email + subdomain + IP harvesting
theHarvester -d target.com -b google,bing,linkedin,twitter

# Flags:
# -d  : target domain
# -b  : data source (google, bing, shodan, linkedin...)
# -l  : limit results
# -f  : save output to file
```

### 10.5 OSINT Tool Quick Reference

```
CATEGORY          TOOL              WHAT IT DOES
──────────────────────────────────────────────────────────────
Username Search   Sherlock           100+ platforms
Email OSINT       Holehe             200+ services
DNS Recon         Amass, Subfinder   Passive/active enum
People Search     Pipl, Spokeo       Identity aggregation
Image Reverse     PimEyes, TinEye    Facial + image search
Dark Web          IntelligenceX      Breach + onion data
Network/IP        Shodan, Censys     Device intelligence
Automation        SpiderFoot         All-in-one OSINT
Graph Analysis    Maltego            Visual link mapping
Web Archive       Wayback Machine    Historical snapshots
```

---

## ⬛ MODULE 11 — OPERATIONAL SECURITY (OPSEC)

```
╔═══════════════════════════════════════════════════════╗
║  OPSEC is the discipline of not leaving evidence     ║
║  of your investigation behind.                       ║
╚═══════════════════════════════════════════════════════╝
```

### 11.1 OPSEC Threat Model for OSINT

```
WHAT YOU MUST PROTECT:
─────────────────────────────────────────
→ Your real IP address
→ Your real identity
→ Your investigation scope
→ Your tooling fingerprint
→ Your timing patterns
```

### 11.2 Layered OPSEC Architecture

```
LAYER 1: NETWORK
  └─ VPN (always on) → Tor (for sensitive work)

LAYER 2: DEVICE
  └─ Dedicated investigation machine / VM
  └─ Tails OS for maximum isolation

LAYER 3: ACCOUNTS
  └─ Sock puppet accounts (fake research personas)
  └─ No personal email, no real name

LAYER 4: BEHAVIOR
  └─ Never investigate from patterns (same time daily)
  └─ Never access target's site directly first
  └─ Use archived/cached versions where possible
```

### 11.3 Creating a Sock Puppet Account

```
SOCK PUPPET CREATION CHECKLIST:
─────────────────────────────────────────────
□ New email (ProtonMail / Tutanota)
□ Created via Tor or VPN
□ No recovery linked to real accounts
□ Profile photo: AI-generated face (thispersondoesnotexist.com)
□ Backstory: plausible name, city, profession
□ Age the account before use (30+ days)
□ Never access from real IP
□ Never cross-reference with real accounts
```

### 11.4 Legal Framework (India Context)

```
INDIA — KEY LAWS TO KNOW:
─────────────────────────────────────────────────────────
IT Act 2000 / Amendment 2008
  Section 66    : Computer-related offences
  Section 66E   : Violation of privacy
  Section 72    : Breach of confidentiality

Indian Penal Code
  Section 503   : Criminal intimidation (doxxing harm)
  Section 507   : Criminal intimidation (anonymous)

Safe Zones:
  → Publicly available data = generally safe
  → Academic / security research = documented intent matters
  → Responsible disclosure = protects researchers
```

---

## ⬛ MODULE 12 — CASE STUDIES & CAPSTONE

### 12.1 Case Study: Tracking a Fake Job Posting

```
OBJECTIVE: Determine if a job posting is fraudulent

STEP 1: Extract company details
  → Company name, website, phone, email

STEP 2: Domain OSINT
  → WHOIS: When was domain registered?
  → Very recent? Red flag.
  → No matching LinkedIn company? Red flag.

STEP 3: Email OSINT
  → Run HR email through Hunter.io
  → Check HIBP for breach history
  → Does domain MX match email domain? Check.

STEP 4: Person OSINT
  → Google the recruiter's name + company
  → Reverse image search their profile photo
  → Check LinkedIn for endorsements

STEP 5: Cross-reference
  → Glassdoor / Indeed reviews
  → MCA (India) company registration
  → BBB (US) or Companies House (UK)

CONCLUSION: Build confidence score → Report or avoid
```

### 12.2 Case Study: Geolocating a Photo

```
OBJECTIVE: Determine where a photo was taken

Photo shows:
  → Street scene, Cyrillic + English signs
  → Distinctive gold-domed building in background
  → Russian SUV (Lada Niva)
  → Winter, snow on ground

STEP 1: Language → Russian-speaking country
STEP 2: Architecture → Eastern Orthodox Church
STEP 3: Vehicle → Russia, Ukraine, Central Asia
STEP 4: Google search gold dome orthodox churches
STEP 5: Cross-reference in Google Earth → Match!
STEP 6: Confirm with Yandex Maps Street View

RESULT: City + street identified within 2 hours
```

### 12.3 Capstone Challenge

```
MISSION BRIEF:
──────────────────────────────────────────────────────────
You receive only this information:
  Twitter handle: @shadow_researcher
  A single photo posted 3 years ago

DELIVERABLES:
  □ Real or likely name
  □ Location (city at minimum)
  □ Employer / affiliation
  □ Other platform presence
  □ Timeline of activity
  □ Confidence score (1–10) per finding
  □ Sources cited for every data point

TOOLS ALLOWED: Any free, legal OSINT tools

TIME LIMIT: 2 hours

OPSEC REQUIREMENT: All research via VPN/sock puppet
──────────────────────────────────────────────────────────
```

---

## 📚 RESOURCE LIBRARY

### Books

```
★★★★★  "Open Source Intelligence Techniques" — Michael Bazzell
★★★★★  "OSINT Handbook" — i-intelligence.eu (free PDF)
★★★★☆  "The Art of Invisibility" — Kevin Mitnick
★★★★☆  "Hunting Cyber Criminals" — Vinny Troia
★★★☆☆  "Practical Social Engineering" — Joe Gray
```

### Websites & Blogs

```
https://inteltechniques.com        Michael Bazzell's hub
https://osintframework.com         Full tool map
https://www.bellingcat.com         Investigative journalism OSINT
https://sector035.nl               Advanced OSINT techniques
https://whatismyipaddress.com      Network self-check
https://archive.org/web            Wayback Machine
```

### YouTube Channels

```
The OSINT Curious Project          Weekly OSINT walkthroughs
Trace Labs                         OSINT CTF competition
Michael Bazzell                    Privacy + OSINT
Nahamsec                           Recon for bug bounty
```

### Practice Labs / CTFs

```
Trace Labs OSINT CTF               Missing persons (real impact)
OSINTDojo.com                      Structured training
Sofia Santos OSINT Challenges      Image geolocation
Geoguessr                          Geographic reasoning training
PentesterLab                       Web recon challenges
```

---

## 🗺️ LEARNING PATH

```
WEEK 1–2    Foundations + Google Dorking + Browser Setup
WEEK 3–4    Social Media Intelligence + People Search
WEEK 5–6    Domain/IP/Shodan + Email OSINT
WEEK 7–8    Image OSINT + Geolocation
WEEK 9–10   Dark Web + Breach Data (passive only)
WEEK 11–12  Automation: SpiderFoot, Maltego, Recon-ng
WEEK 13–14  OPSEC deep dive + Sock Puppet creation
WEEK 15–16  Full Capstone Investigations + CTF participation
```

---

## ⚠️ FINAL ETHICS STATEMENT

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   OSINT is a tool. Like all tools, it can build or harm.   │
│                                                             │
│   Use it to:                                               │
│     → Protect people                                       │
│     → Find truth                                           │
│     → Conduct legitimate security research                 │
│     → Verify information                                   │
│                                                             │
│   Never use it to:                                         │
│     → Stalk, harass, or intimidate                        │
│     → Publish private information without consent         │
│     → Enable discrimination or violence                   │
│                                                             │
│   The skill is yours. The responsibility is too.          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

```
╔══════════════════════════════════════════════════════════════╗
║  OSINT MASTERCLASS — COMPLETE                               ║
║  Modules: 13  |  Tools: 50+  |  Techniques: 100+           ║
║                                                              ║
║  "The intelligence community's best-kept secret             ║
║   is that most intelligence is unclassified."               ║
║                                        — CIA Analyst        ║
╚══════════════════════════════════════════════════════════════╝
```

---
*Course authored for educational and ethical security research purposes only.*
*All techniques described are legal when applied to publicly available data.*
