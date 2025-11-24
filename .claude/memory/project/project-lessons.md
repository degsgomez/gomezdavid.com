# Project-Specific Lessons Learned

## Project Development Practices

### Web Scraping with Playwright for Portfolio Data Extraction
**Practice**: Python-based web scraping using Playwright to extract project portfolio data from marketing website
**Context**: Needed to bulk extract multiple project entries from https://thinkhub.marketing/portfolio/ pages to populate local projects.json file
**Implementation**:
- Created extract_projects.py with sync_playwright API
- Implemented per-page extraction function with error handling
- Used `wait_until='networkidle'` with 30s timeout plus 2s additional delay for slow-loading site
- Extracted structured data: h1 for name, .project-info-item divs for type, article paragraphs for description
- Truncated descriptions to 300 chars for UI consistency
- Processed 14 URLs in batch with progress reporting
**Results**: Successfully extracted all 14 projects with 100% success rate. Clean data integration into existing JSON structure. Demonstrates effective approach for bulk content migration from external sources.
**Added**: 2025-11-23T22:40:56+00:00
**Additional Details**:
```python
# Key implementation pattern for reliable scraping
page.goto(url, wait_until='networkidle', timeout=30000)
time.sleep(2)  # Extra wait for slow site
name = page.locator('h1').first.text_content().strip()
description = text[:300] + "..." if len(text) > 300 else text
```

### JSON Content File Structure for Portfolio Projects
**Practice**: Maintain standardized JSON structure for project portfolio entries
**Context**: Managing project showcase data for personal portfolio website
**Implementation**: Each project entry contains: name (string), description (string, 300 char max), type (string: "Social Media" or "Video Production"), image (path string), link (URL string)
**Results**: Clean, maintainable project data structure that supports easy filtering and display. Successfully integrated 11 new entries without breaking existing structure.
**Added**: 2025-11-24T00:36:48+00:00
**Additional Details**:
```json
{
  "name": "Project Name",
  "description": "Brief description under 300 chars",
  "type": "Social Media | Video Production",
  "image": "/images/projects/filename.png",
  "link": "https://..."
}
```

### Temporary File Cleanup Workflow
**Practice**: Explicitly remove temporary extraction and processing files after successful integration
**Context**: Web scraping workflow creates intermediate files (scripts, raw data) that should not persist in repository
**Implementation**: After successful data integration, used `rm` command to delete extract_projects.py, projects_data.json, and extract_portfolio.js. Verified deletion with grep verification command.
**Results**: Clean repository state maintained. No temporary files committed to version control.
**Added**: 2025-11-24T00:41:19+00:00
