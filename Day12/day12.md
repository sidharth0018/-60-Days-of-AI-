Day [12/60] — Job Search & Personal Branding Toolkit with Claude AI

**What I did today**
Used Claude AI as a Technical Recruiter + Career Coach + Resume Writer combo to generate a
complete job search toolkit targeting Data Analyst roles at Deloitte, EY, KPMG, Accenture, and Genpact
— all from a single prompt with my resume and a sample JD as input.
What Claude generated
A 12-section interactive toolkit covering every stage of the job search funnel:
SectionOutputS1ATS-optimized cover letter (tailored to Big 4 / GCC analyst JDs) S2Recruiter
outreach emailS3Hiring manager cold emailS4LinkedIn connection request (≤300 characters) 
S5Referral request messageS6Follow-up email (5-day no-response trigger)
S730-second professional self-introductionS8Top 10 job titles best suited to my profileS9Key
strengths recruiters will noticeS10Skill gap analysis with a 90-day learning roadmapS11Personal 
brand summary — UVP, positioning statement, LinkedIn headlinesS12Interview talking points — stories, likely questions, and how to answer them
The prompt technique used
This was a multi-role mega-prompt — a single prompt that assigns Claude multiple expert personas simultaneously:
You are an expert Technical Recruiter, Hiring Manager, Career Coach,
Executive Resume Writer, and Personal Branding Consultant.
This technique is called role-stacking — assigning multiple complementary expert roles forces Claude to approach
the same profile from different professional lenses in one pass.

Key Claude AI concepts demonstrated
Role-stacking prompts — Assigning multiple expert personas in one prompt produces richer, more cross-functional output than single-role prompting.
A recruiter sees your resume differently than a career coach does.
Grounding with real artifacts — Uploading the actual resume + a real JD means Claude calibrates every output to
specific evidence, not generic templates. The cover letter references NutriScope and the IIT Delhi hackathon because 
those were in the resume — not because Claude invented them.
Structured output specification — Defining all 12 sections upfront with word counts and formatting rules gives Claude 
a clear production contract. The output arrives organized and immediately usable.
Constraint-driven quality — Adding constraints like "avoid generic AI language", "quantify wherever possible",
and "ready to send without edits" pushes the model toward specificity. Vague prompts get vague outputs; constrained prompts get deployable ones.
What I learned about my own profile
Claude's skill gap analysis flagged the honest picture:

Power BI and Tableau are at ~30% — the single biggest gap versus every JD in my target list
Statistics needs a dedicated push — correlation, hypothesis testing, descriptive stats
ETL exists conceptually in my projects but needs one standalone Python → MySQL pipeline to become a real resume point
ML fundamentals are optional for analyst roles now but will differentiate me at KPMG-level screens within 6 months

The personal brand summary Claude generated crystallized something I hadn't articulated 
clearly before: my ECE background is not a liability for a Data Analyst role — it's the differentiator. 
I understand data at its origin (sensors, APIs, hardware outputs), which makes me faster at diagnosing data quality issues than a pure CS analyst would be.
Immediate action items from this session

 Rebuild the Environmental Dashboard in Tableau Public and publish it — one live viz closes the tool gap faster than any course
 Build one Power BI dashboard using a mock sales dataset (Microsoft Learn, free)
 Add Index-Match and Power Query to Excel skill set (Chandoo.org, 2 hrs/week)
 Write one Python ETL script: CSV → pandas transform → MySQL load → document on GitHub
 Update LinkedIn headline to: Aspiring Data Analyst | SQL · Python · Dashboard Development | B.Tech ECE @ ABES

Target companies context (from Claude's analysis)
CompanyFresher FilterPriority story to useDeloitteSQL + Excel + communication in R1NutriScope pipeline
architectureEYSQL + analytical reasoningLeetCode stats + IIT hackathonKPMGStructured thinking,
tightest filterHackathon KPI definition storyAccentureHighest fresher intake volumeEnvironmental
Dashboard multi-source dataGenpactAnalytics Associate track, Excel + SQLMIS Analyst angle, data validation work
Files in this session

Resume: Sidharth_Kumar_DataAnalyst_Resume.docx
Toolkit: Interactive 12-section HTML widget (Claude artifact)

Prompt template (reusable)
You are an expert Technical Recruiter, Hiring Manager, Career Coach,
Executive Resume Writer, and Personal Branding Consultant.

Carefully analyze my resume, target role, and the sample job description below.
Generate the following 12 sections — use only resume information, quantify
achievements, ATS-friendly language, and content ready to use without edits:

Resume: [attached seperately in this folder]
Target Role: [Data Analyst]
Target Companies: [deliotte , EY, KPMG, Accenture, Genpact]
Sample JD:  Sample Job Description
Role: Data Analyst
Responsibilities
Analyze datasets to identify trends and business insights.
Create dashboards using Power BI/Tableau.
Write SQL queries for reporting and analysis.
Clean and validate data from multiple sources.
Collaborate with stakeholders to define KPIs.
Required Skills
SQL
Excel
Power BI/Tableau
Data Analysis
Data Visualization
Statistics
Preferred Skills
Python
ETL Concepts
Machine Learning Fundamentals
