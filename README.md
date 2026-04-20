# Resume ATS Scorer 📄

An intelligent resume analysis tool that evaluates your resume against job descriptions using Google's Gemini AI. Get an ATS (Applicant Tracking System) compatibility score and actionable feedback to optimize your resume for specific positions.

## Features ✨

- **ATS Score Analysis** - Get a 0-100 score showing how likely your resume will pass ATS filters
- **Keyword Matching** - Identifies matched and missing keywords from the job description
- **Strengths & Weaknesses** - AI-powered analysis of resume strengths and areas for improvement
- **Actionable Suggestions** - Specific recommendations to improve your resume
- **Experience Match** - Evaluate how well your experience aligns with the role requirements
- **Skills Analysis** - Assess skills match with the job description
- **Education Alignment** - Check education relevance to the position
- **PDF Support** - Upload resumes in PDF format
- **User-Friendly Interface** - Clean, intuitive Streamlit-based web application

## Requirements 📋

- Python 3.8 or higher
- Google Gemini API key
- Modern web browser

## Installation 🚀

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/Resume-ATS-Scorer.git
cd Resume-ATS-Scorer
```

### 2. Create Virtual Environment (Optional but Recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

## Configuration ⚙️

### Get Your Gemini API Key

1. Go to [Google AI Studio](https://ai.google.dev/)
2. Click on "Get API Key" or "Create API key"
3. Copy your API key

### Setup Environment Variables

1. Create a `.env` file in the project root:
```bash
touch .env
```

2. Add your API key to `.env`:
```
GEMINI_API_KEY=your_gemini_api_key_here
```

3. **Never commit `.env` to version control** - it's already in `.gitignore`

## Usage 🎯

### Run the Application
```bash
streamlit run app.py
```

The app will open at `http://localhost:8501` (or a different port if 8501 is busy)

### How to Use

1. **Upload Resume** - Click "Browse files" to select your resume PDF
2. **Enter Job Description** - Paste the job description you're applying for
3. **Analyze** - Click "Analyze Resume" button
4. **Review Results** - Get your ATS score and detailed analysis

### Interpreting Results

- **🟢 80-100** - Excellent match for ATS screening
- **🟡 60-79** - Good match, some improvements recommended
- **🔴 0-59** - Poor match, significant improvements needed

## Project Structure 📁

```
Resume-ATS-Scorer/
├── app.py                 # Main Streamlit application
├── requirements.txt       # Python dependencies
├── .env.example          # Example environment variables
├── .env                  # Your actual API key (not committed)
├── .gitignore           # Git ignore rules
└── README.md            # This file
```

## Dependencies 📦

| Package | Version | Purpose |
|---------|---------|---------|
| streamlit | 1.45.1 | Web framework |
| google-genai | 1.73.1+ | Gemini API client |
| PyPDF2 | 3.0.1 | PDF parsing |
| python-dotenv | 1.1.0 | Environment variables |

## Troubleshooting 🔧

### ModuleNotFoundError: No module named 'streamlit'
```bash
pip install -r requirements.txt
```

### GEMINI_API_KEY not found
- Ensure `.env` file exists in the project root
- Check that `GEMINI_API_KEY=your_key` is correctly formatted
- Reload the app (`Ctrl+R` in browser)

### 429 RESOURCE_EXHAUSTED Error
This means you've exceeded the Gemini API free tier quota. Options:
- Wait until tomorrow (daily quota resets)
- Upgrade to a paid plan at [Google AI Studio](https://ai.google.dev/)
- Implement rate limiting in your usage

### PDF Upload Issues
- Ensure PDF is valid and not corrupted
- Try extracting text from the PDF manually to verify content
- Supported: Text-based PDFs (scanned PDFs may not work well)

## API Quotas & Limits 📊

**Free Tier Limits:**
- 15 requests per minute
- 1,500 requests per day
- 0 input tokens per minute (after daily limit)

**To increase limits:**
1. Set up paid billing in [Google Cloud Console](https://console.cloud.google.com/)
2. Paid tier offers significantly higher quotas

## Tips for Best Results 💡

1. **Resume Format** - Use clear, standard formatting
2. **Keywords** - Include relevant industry keywords
3. **Job Description** - Copy the full job posting for accurate analysis
4. **PDF Quality** - Ensure PDF is text-based, not scanned image
5. **Specificity** - More detailed job descriptions yield more accurate analysis

## Security 🔒

- Your API key is loaded from `.env` and never exposed
- Resume text is sent to Gemini API but not stored
- Implement HTTPS if deploying to production
- Never share your `.env` file or API key

## Deployment 🌐

### Deploy to Streamlit Cloud (Free)
```bash
streamlit run app.py --logger.level=error
```

Then push to GitHub and connect at [Streamlit Cloud](https://streamlit.io/cloud)

### Deploy to Other Platforms
- AWS EC2
- Google Cloud Run
- Heroku
- DigitalOcean
- Azure

## Future Enhancements 🚀

- [ ] Support for multiple file formats (DOCX, TXT)
- [ ] ATS keyword database
- [ ] Resume optimization suggestions with examples
- [ ] Comparison with industry standards
- [ ] Export analysis to PDF
- [ ] Batch resume analysis
- [ ] Job market insights
- [ ] Integration with job boards

## Contributing 🤝

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License 📄

This project is licensed under the MIT License - see the LICENSE file for details.

## Support 💬

- Issues? Open a [GitHub Issue](https://github.com/yourusername/Resume-ATS-Scorer/issues)
- Questions? Start a [Discussion](https://github.com/yourusername/Resume-ATS-Scorer/discussions)
- Documentation: See [Google Gemini API Docs](https://ai.google.dev/gemini-api/docs)

## Disclaimer ⚠️

This tool provides analysis based on AI and pattern matching. While it helps identify potential ATS issues, the actual ATS screening depends on:
- Specific ATS software used by companies
- Unique filtering rules and criteria
- Human recruiter review

Always review and personalize your resume for each application!

## Acknowledgments 🙏

- Built with [Streamlit](https://streamlit.io/)
- Powered by [Google Gemini AI](https://ai.google.dev/)
- PDF processing with [PyPDF2](https://pypi.org/project/PyPDF2/)

---

**Made with ❤️ by [Your Name]**

Last updated: April 20, 2026
