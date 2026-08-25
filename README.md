## AI-Assisted Resume Portfolio Generator

## Project Overview
This project converts a resume stored in resume.txt into a structured personal portfolio webpage.

The project uses the Gemini API to extract information from the resume and then uses an HTML template and CSS to generate portfolio.html.

## Technologies Used
- Python
- Gemini API
- JSON
- Pydantic
- Jinja2
- HTML
- CSS


## Project Workflow
resume.txt → Python validation and cleaning → Gemini API → structured JSON → Pydantic validation → template.html + style.css → portfolio.html

The sample resume.txt contains a sample student's resume. To generate a portfolio for another student, replace the contents of resume.txt and run the program again.

## Project Structure
```
resume-portfolio-generator/
  main.py
  resume.txt
  template.html
  style.css
  requirements.txt
  README.md
  AI_USAGE_LOG.md
  .gitignore
  .env.example
  portfolio.html
  screenshots/
    01_hero_and_about.png
    02_skills.png
    03_experience_and_contact.png
```

## Setup
Step 1: Install Python
Install Python 3.10 or a newer version.

Step 2: Install the required packages
Open the terminal in the project folder and run:
pip install -r requirements.txt

Step 3: Add the Gemini API key
Copy `.env.example` to `.env` in the project folder, then replace the placeholder with your own key:
GEMINI_API_KEY=your_gemini_api_key

Never commit the real `.env` file — it is already excluded by `.gitignore`.

## How to Run
Put the resume information in resume.txt.

Open the terminal in the project folder.

Run:
python main.py

The final portfolio.html file is created.

Open portfolio.html in a web browser to view the portfolio.

## Limitations
A valid Gemini API key is required.

The project depends on Gemini API availability.

The program uses the resume provided in resume.txt as its input.

The generated portfolio should be checked against the original resume before final use.

The project generates the portfolio locally as portfolio.html.

## Testing Results
The project was tested by running: python main.py

The generated portfolio.html was opened in a web browser and checked to verify that the portfolio was generated from the information in resume.txt.

| Test case | Result |
|---|---|
| Missing resume.txt | Program shows a clear error and stops safely. |
| Empty or very short resume | Input is rejected with a useful message. |
| Valid resume | portfolio.html is generated successfully. |
| Missing API key | Program shows a configuration error. |
| API failure (503 / rate limit) | Handled with retries and fallback models, no crash. |
| Invalid JSON response | Caught and reported without crashing. |

## Screenshots
See the `screenshots/` folder:
- `01_hero_and_about.png` — Hero section and About Me
- `02_skills.png` — Technical Stack / Expertise section
- `03_experience_and_contact.png` — Experience and contact footer

## Responsible AI and Privacy
- The sample resume.txt uses fictional/placeholder personal details only — no real passwords, ID numbers, or financial data.
- The real Gemini API key is never committed; only `.env.example` is included in the repository.
- Gemini is called from the Python backend only, never from browser-side JavaScript, so the API key is never exposed to the client.
- Gemini's output is a draft. Every generated skill, project, date, company, achievement, and link should be checked against the original resume before final use.


## AI Usage
See `AI_USAGE_LOG.md` for a record of the AI tools used during development, what they were used for, and how their output was reviewed and corrected.
