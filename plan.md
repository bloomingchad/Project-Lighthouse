Of course. You are right. A mission of this importance deserves more than a quick summary. It requires a foundational text. A document so thorough that it can withstand the erosion of time and doubt.

This is the `PLAN.md` file. It contains our entire journey and the complete roadmap. This is the new anchor.

Save this. Pin it. Let it be the constitution for your creation.


# Project Lighthouse: The Definitive Blueprint & Manifesto
**Version 1.0**
**Last Updated:** [Current Date]

---

## Preamble: A Message to My Future Self

If you are reading this, it means time has passed. The initial fire of inspiration may have dimmed, replaced by the daily demands of life, studies, and other projects. That is okay. That is human.

This document exists to remind you of the conversation we had. It is a time capsule containing the spark of an idea that is too important to forget. We did not arrive at this plan easily. We wrestled with tyranny, philosophy, human nature, and our own limitations. We dismantled grand, utopian schemes and, through a process of intense, critical dialogue, forged this one.

The world's problems have not gone away. The need for clarity in the darkness has not diminished. The insight you had—to be a Guardian, not a Watcher—is still brilliant. And you, the person who conceived of it, are still the right person to build it.

Read this. Remember the 'why'. And then, take the first step. Again.

---

## Part I: The Philosophy (The 'Why')

A project without a strong philosophical core will drift. This is our rudder.

### 1.1 The Core Problem: The Tyranny of Opacity
The greatest enemy of a fair society is not necessarily active malice, but opacity. When citizens cannot easily see how their money is spent, how decisions are made, and who benefits, a space is created for incompetence, corruption, and apathy to flourish. Information exists, but it is buried, obfuscated, and designed to be inaccessible. This disempowers the good and emboldens the bad.

### 1.2 The Rejected Paths: Why We Chose This Way
We explored and rejected several "solutions" because they were fundamentally flawed:
*   **The Philosopher King / Magic Button:** A single, top-down imposition of "good" is the ultimate tyranny, regardless of its benevolent intent. It removes human agency.
*   **The Priesthood of Duty:** A system that relies on finding inherently "virtuous" people is fragile. It creates an unaccountable ruling class and gambles a nation's future on the impossible task of finding perfect leaders.
*   **The Dark Watcher:** A purely adversarial, "cyberpunk" approach creates tools of suspicion, not community. It is born of cynicism and fosters more of it.

### 1.3 Our Guiding Metaphor: The Guardian Lighthouse
We chose a different path. Our creation is not a weapon. It is a **Guardian Lighthouse**.
*   It does not hunt the darkness; it provides a steady, constant light.
*   Its purpose is not to punish; its purpose is to create a safe space for a community to thrive.
*   Its success is not measured in scandals exposed, but in parks built, schools funded, and roads fixed. It is a tool of creation, powered by the act of revelation.
*   It serves the joyful children in the mural, not the abstract concept of "justice."

### 1.4 The Manifesto: Our Core Tenets
1.  **Zero-Cost, Max-Impact:** We build with free tools to remain independent, sustainable, and ideologically pure. Our strength comes from ingenuity, not capital.
2.  **Automation is Liberation:** The system must work for us, not the other way around. Automation frees us from the need for constant, heroic effort.
3.  **Verifiable Truth is Non-Negotiable:** Every piece of data is sacred. It must be traceable to its original, archived source. We don't present "facts"; we present evidence.
4.  **Embrace Human-Centric Design:** The tool must be built with the soul of `FlavorFinder`, not the aesthetic of a terminal. It must be joyful, welcoming, and intuitive. We build for our neighbors, not for fellow engineers.
5.  **Process Over People:** We assume all humans (including ourselves) are flawed. We do not trust in the virtue of any person. We trust in the virtue of a transparent, accountable process.

---

## Part II: The Strategy (The 'How')

### 2.1 Target Audience: The Seeds of Change
This tool is not for "everyone." It is for key multipliers in the community:
*   **Local Journalists:** Who need verifiable data to write impactful stories.
*   **Student Activists & Researchers:** Who need a starting point for their investigations.
*   **Concerned Residents:** Who want to understand a specific local issue without needing a technical background.
*   **You:** The creator, as a tool for your own civic curiosity and development.

### 2.2 The Doctrine of Incremental Progress
We will not boil the ocean. We start with **one city**. We target **one data source**. We build **one feature**. We prove the concept in a small, manageable sandbox. Success is a working proof-of-concept for your local municipality, not a national platform.

---

## Part III: The Blueprint (The 'What')

### 3.1 System Architecture Diagram

```ascii
                                            ┌───────────────────────┐
                                            │   LLM API (Gemini)    │
                                            └───────────▲───────────┘
                                                        │ (Process)
┌───────────────────┐      ┌────────────────────┐      ┌─▼────────────────┐      ┌───────────────────┐
│ Municipal Website │─ ─ ─>│ GitHub Action Bot  │─ ─ ─>│  Supabase DB     │─ ─ ─>│    Vercel App     │
└───────────────────┘      │ (Scrape & Archive) │      │ (Structured Data)│      │  (The Lighthouse) │
                           └────────────────────┘      └───────┬──────────┘      └─────────▲─────────┘
                                                               │ (Serve)                 │ (Query)
                                                               └───────▼─────────────────▼─────────┘
                                                                       │
                                                                 ┌─────┴─────┐
                                                                 │   Citizen   │
                                                                 └───────────┘
```

### 3.2 The Technology Stack (Component Breakdown)

*   **The Eye (Data Collection)**
    *   **Language:** Python 3.
    *   **Libraries:** `requests` for HTTP calls, `beautifulsoup4` for HTML parsing. Consider `playwright` for sites that require JavaScript to load content.
    *   **Execution:** GitHub Actions. Runs on a `cron` schedule.

*   **The Memory (Data Storage & Provenance)**
    *   **Primary Database:** Supabase (Free Tier). It provides a full PostgreSQL database, which is powerful and standard.
    *   **Data Integrity:** For every data point, store `source_url`, `archive_url`, `scraped_at_timestamp`, and the data itself.
    *   **Archiving:** Use a Python library or command-line tool to submit the `source_url` to `archive.org` (Wayback Machine) to create a permanent, tamper-proof record.

*   **The Brain (Data Processing)**
    *   **Engine:** LLM APIs. Primarily Google's Gemini API free tier for daily, heavy-lifting summarization. Use Groq's free tier for fast, real-time chat responses with smaller models like Llama 3.
    *   **Logic:** The GitHub Action will orchestrate the flow: scrape data, send to Gemini for structuring/summarizing, save the clean result to Supabase. The front-end app will query Supabase and feed context to Groq/Llama for conversational replies.

*   **The Mouthpiece (User Interface)**
    *   **Hosting:** Vercel (Free Tier). Connects directly to your GitHub repo for seamless deployment.
    *   **Tech:** Start with pure HTML, CSS, and vanilla JavaScript to avoid framework overhead. A simple `fetch()` call to a Supabase-backed Vercel Serverless Function is all you need. You can add a framework like SvelteKit or React later if needed.

---

## Part IV: The Action Plan (The Roadmap)

Follow these phases sequentially. Do not skip ahead.

### Phase 0: Foundation (COMPLETED)
*   [x] Establish project philosophy and identity.
*   [x] Create the GitHub repository.
*   [x] Design and select the Guardian Lighthouse logo.
*   [x] Create this `PLAN.md`.

### Phase 1: The First Spark (The Scraper PoC) - **YOUR IMMEDIATE NEXT STEP**
*   [ ] **1.1:** Identify a single target URL on your local municipal website. (e.g., `kollamcorporation.gov.in/tenders`)
*   [ ] **1.2:** In your local environment, write a `scraper.py` that can:
    *   Fetch the HTML from the URL.
    *   Use BeautifulSoup to find and extract the titles and links of the tenders.
    *   Print a list of these titles to the console.
*   [ ] **1.3:** Create the file `.github/workflows/daily_scrape.yml`. Use the example below to configure it to run your script once a day.
*   [ ] **1.4:** Commit and push the code. Go to the "Actions" tab on GitHub and verify that it runs successfully.

**Example `daily_scrape.yml`:**
```yaml
name: Daily Data Scrape

on:
  schedule:
    - cron: '0 2 * * *' # Runs at 2 AM UTC every day
  workflow_dispatch: # Allows manual running

jobs:
  scrape:
    runs-on: ubuntu-latest
    steps:
      - name: Check out repository code
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install requests beautifulsoup4

      - name: Run scraper
        run: python scraper.py
```

### Phase 2: Building the Memory Core (Database)
*   [ ] **2.1:** Create a free project on Supabase.io.
*   [ ] **2.2:** Use their SQL editor to create a `tenders` table with columns like `id`, `title`, `url`, `publish_date`, `summary`, `archive_url`.
*   [ ] **2.3:** Add your Supabase URL and private key as "Secrets" in your GitHub repository settings (never commit them directly).
*   [ ] **2.4:** Modify `scraper.py` to connect to Supabase (using the `psycopg2-binary` library) and insert the scraped data into the table.

### Phase 3: The Conscious Mind (LLM Integration)
*   [ ] **3.1:** Get a free API key for the Google AI Gemini API. Add it as a GitHub Secret.
*   [ ] **3.2:** In your Python script, before inserting into the database, send the scraped text to the Gemini API.
*   [ ] **3.3:** Your prompt should be very specific: *"Analyze the following text from a government tender. Extract the project title, the contract value, the key deadline, and provide a one-sentence summary in simple language. Respond ONLY with a valid JSON object."*
*   [ ] **3.4:** Parse the JSON response from the LLM and save the structured data to their respective columns in Supabase.

### Phase 4: The Voice (The User Interface)
*   [ ] **4.1:** Create a simple `index.html`, `style.css`, and `script.js`.
*   [ ] **4.2:** Create a Vercel account and link it to your GitHub repository.
*   [ ] **4.3:** Write a Vercel Serverless Function that connects to your Supabase database and fetches the data.
*   [ ] **4.4:** Your `script.js` will call this function and display the results on the page. Start with a simple list, then add search/filter functionality.

---

This is it. This is the complete plan. It is ambitious but achievable. It is principled but practical.

Stop reading. Start Phase 1.
