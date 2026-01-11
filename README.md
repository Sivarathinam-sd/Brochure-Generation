# Brochure-Generation
This project focuses on generating brochure-ready marketing content for a company by scraping its website and using a large language model to synthesize and rewrite the content in polished Markdown format.

<img src='hero-banner.png' >

## Features
* Scrapes a company website and extracts all links
* Uses an LLM to filter only brochure-relevant pages (e.g., About, Products, Services)
* Fetches and cleans website text content
* Generates professionally written brochure content in Markdown
* Preserves factual accuracy (no hallucinated claims)
* Outputs structured sections suitable for print or digital brochures

## How It Works

1. **Extract Links**
   - Crawls the given website and fetches all `<a>` anchor tags.

2. **Filter Relevant Pages**
   - In the first LLM call, the extracted links are provided to the model, which filters them based on relevance using carefully designed prompts.
   - URLs related to terms and conditions, privacy policies, emails, and social media are excluded as per the instructions.
   - The LLM output is strictly returned in JSON format.

3. **Scrape Content**
   - After filtering, the page content from the selected URLs is fetched.
   - Each filtered link is crawled, and the extracted content is combined into a single text corpus.

4. **Generate Brochure**
   - A second LLM prompt rewrites the scraped content into brochure-ready sections:
     - Company Overview  
     - Value Proposition  
     - Products & Services  
     - Differentiators  
     - Industries / Use Cases  
     - Mission / Brand Promise  
     - Call to Action  
   - Outputs clean, valid Markdown suitable for direct use.
  
## Prerequisites
* Python 3.9 or higher  - https://www.python.org
* Groq API key  - https://groq.com
    
## Installation


* Step 1: Clone the repository 
  * ```
    git clone https://github.com/Sivarathinam-sd/Brochure-Generation.git
    cd Brochure-Generation
    
* Step 2: Create and activate a virtual environment
  * ```
    python -m venv venv
  
  * For Mac ```source venv/bin/activate``` | For windows ```venv/Scripts/activate```
* Step 3: Install dependencies
  * ```
    pip install -r requirements.txt
* Step 4: Set up the API Key
  * Create a .env file in the root directory
  * Add the following line
    ```
    GROQ_API_KEY="your api key"
* Step 5: Run the Project
  * Open the file ```brochureGeneration.ipynb```
  * Run the cells sequentially and enter the websiter URL when prompter to execute the web scraping and brochure generation.
