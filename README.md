# Brochure-Generation
This project focuses on generating brochure-ready marketing content for a company by scraping its website and using a large language model to synthesize and rewrite the content in polished Markdown format.

<img src='hero-img.png' >

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
