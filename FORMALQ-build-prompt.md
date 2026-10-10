# Build FORMALQ — Complete AI-Powered Form Builder

Act as a senior full-stack developer, AI engineer, software architect, and premium SaaS UI/UX designer. Build a complete, production-minded web application called **FORMALQ**.

This is a college hackathon project. The result must be impressive during a live presentation, visually polished, responsive, secure, and genuinely functional.

**IMPORTANT: Do not build just a landing page, static mockup, or frontend prototype. Build the complete application with working navigation, real database integration, authentication, AI integration, public form submissions, analytics, and CSV exports.**

## 1. Product vision

Product name: FORMALQ

Tagline: "Create smarter forms. Understand every response."

Purpose: Enable users to generate forms using AI, edit questions, publish shareable forms, collect responses, visualize results, generate AI insights, and export data from one platform.

Target users:
- Students and colleges
- Teachers and educational institutions
- Event organizers
- Small businesses
- Customer research teams
- HR and recruitment teams
- Product and marketing teams

The product should look like a premium SaaS application suitable for a live college hackathon demonstration.

## 2. Mandatory visual design: premium black glass

**Use a realistic black glassmorphism theme throughout the authenticated application dashboard, form editor, analytics, response management, login, and signup pages.**

The dashboard must NOT use a white-glass theme.

### Design direction

Create an elegant, high-end interface inspired by Apple dark UI, premium creative software, and modern SaaS dashboards.

Color palette:
- Main background: near-black `#08090D`
- Secondary background: `#101116`
- Glass cards: translucent charcoal `rgba(255,255,255,0.045)`
- Elevated panels: `rgba(255,255,255,0.07)`
- Borders: subtle white transparency, around 8–12%
- Main text: `#F5F5F7`
- Secondary text: `#A1A1AA`
- Muted text: `#71717A`
- Primary accent: electric violet `#8B5CF6`
- Secondary accent: blue `#60A5FA`
- Success: `#34D399`
- Warning: `#FBBF24`
- Error: `#F87171`

### Glassmorphism effects

Implement:
- `backdrop-filter: blur(18px)` or similar where supported
- Subtle transparent black surfaces
- Thin glass borders
- Restrained shadows and soft ambient lighting
- Subtle violet and blue light reflections
- Small hover elevation effects
- Smooth transitions
- Premium rounded corners
- Elegant spacing and typography

Use gradients only for subtle ambient lighting and selected highlights. Avoid excessive neon, excessive glow, clutter, or a generic AI-generated template appearance.

Maintain readable contrast, visible focus indicators, keyboard navigation, and reduced-motion support.

### Landing page theme

The landing page can use a carefully balanced dark premium design with a large headline, subtle ambient glow, realistic dashboard preview, feature cards, and a clear call to action.

Public respondent forms should use a separate clean, minimal, highly readable form layout. They may use a light neutral surface if appropriate for readability, while the owner's dashboard remains black glass.

## 3. Technology stack

Use:
- Next.js with App Router
- TypeScript
- Tailwind CSS
- Supabase PostgreSQL
- Supabase Auth
- Server-side AI API integration
- Recharts
- React Hook Form
- Zod
- Lucide React
- Vercel deployment

Choose compatible stable package versions. Organize the code into reusable components, services, validation schemas, database utilities, and route handlers.

Never expose AI keys or Supabase service-role credentials in browser code.

If credentials are missing, provide an explicitly labeled demo mode. Never claim that data was saved or AI was called when it was not.

## 4. Landing page

Route: `/`

Build a premium product landing page with:

- FORMALQ logo and navigation
- Hero headline: "Create smarter forms. Understand every response."
- Description of AI-powered form generation and response analysis
- Primary button: "Create a Form with AI"
- Secondary button: "Explore Demo"
- Realistic black-glass dashboard preview
- AI generation feature section
- Visual form editing feature section
- Public sharing feature section
- Analytics and AI insights feature section
- How-it-works section
- Security and privacy section
- Footer

Functional behavior:
- "Create a Form with AI" navigates to `/forms/new` or the login page when authentication is required.
- "Explore Demo" opens a working demo experience.
- All navigation links work.
- Do not use dead buttons or placeholder links.

## 5. Authenticated dashboard

Route: `/dashboard`

This should be the most visually impressive part of the application.

### Dashboard layout

Use a fixed or collapsible left sidebar on desktop, a responsive mobile navigation menu, and a main content area.

Sidebar:
- FORMALQ logo
- Overview
- My Forms
- Create with AI
- Analytics
- Settings
- User profile
- Sign out

Main dashboard:
- Greeting and user profile
- "Create New Form" primary action
- "Generate with AI" secondary action
- Search forms input
- Filter by All, Draft, Published, and Archived where supported
- Recent forms section
- Recent activity where real data is available

### Dashboard metric cards

Display:
- Total Forms
- Total Responses
- Published Forms
- Average Completion Rate

Use actual database records for every metric. If completion rate cannot be calculated reliably, show "Not enough data" rather than inventing a value.

Metric cards should use dark translucent glass, subtle borders, clear typography, and small Lucide icons.

### Form cards

Each form card should include:
- Form title
- Description
- Draft or Published status
- Response count
- Last-updated timestamp
- Copy public link action when published
- Edit action
- Preview action
- Analytics action
- Duplicate action
- Publish or Unpublish action
- Delete action with confirmation

Implement search, filtering, pagination if needed, and helpful empty states.

All actions must perform their real operation and show loading and error states.

## 6. AI form generation wizard

Route: `/forms/new`

Create a multi-step AI form generation workflow with a premium black-glass interface.

Collect:
- Form title or topic
- Purpose
- Target audience
- Number of questions
- Preferred question types
- Tone
- Language
- Required-question preference

Include example templates:
- Student Feedback
- College Event Registration
- Customer Satisfaction
- Market Research
- Employee Survey
- Course Feedback
- Product Feedback
- Job Application Screening

### AI generation requirements

Generate:
- A suitable form title
- A short description
- Relevant, unbiased questions
- Appropriate question types
- Choice options when needed
- Required/optional settings

Support:
- Short text
- Long text
- Single choice
- Multiple choice
- Dropdown
- Rating
- Yes/no
- Number
- Email
- Date

Use a server-side AI provider and return structured JSON. Validate the response using Zod before accepting or saving it.

Provide:
- Loading state
- Generation progress indicator
- Retry action
- Regenerate questions action
- Clear API error messages
- A manual fallback if AI credentials are unavailable

The user must be able to review and edit generated questions before saving.

## 7. Visual form editor

Route: `/forms/[id]/edit`

Build a working question editor with a live form preview.

Features:
- Edit title and description
- Add a question
- Edit question text
- Change question type
- Add, edit, and remove answer options
- Reorder questions with drag-and-drop or move-up/move-down controls
- Duplicate a question
- Delete a question
- Mark a question as required or optional
- Preview the respondent experience
- Save draft
- Publish
- Unpublish
- Copy public link

Use React Hook Form and Zod where appropriate.

Show clear save states:
- Unsaved changes
- Saving
- Saved
- Save failed

Never show "Saved" before the database confirms success.

## 8. Authentication

Routes:
- `/login`
- `/signup`

Implement Supabase authentication.

Features:
- Email and password signup
- Login
- Logout
- Session persistence
- Protected dashboard and editor routes
- Password validation
- Friendly error messages
- Redirect users appropriately after authentication

Use secure server-side session handling with the recommended Supabase Next.js approach.

## 9. Public forms

Route: `/f/[publicId]`

Each published form receives a unique public URL.

Respondents must be able to complete and submit the form without logging in.

Implement:
- Responsive question rendering
- Required-field validation
- Email and number validation
- Single-choice and multiple-choice controls
- Dropdown menus
- Rating controls
- Date inputs
- Submission progress where useful
- Submit button loading state
- Confirmation screen
- Error handling
- Practical duplicate-submission protection

Reject submissions for unpublished forms.

Never expose the form owner's private profile, email, or other respondents' answers.

## 10. Database and persistence

Use Supabase PostgreSQL for real persistent storage.

Create migrations for:
- `profiles`
- `forms`
- `questions`
- `responses`
- `answers`

Suggested structure:

Forms:
- UUID primary key
- Owner user ID
- Title
- Description
- Status
- Unique public ID
- Created timestamp
- Updated timestamp

Questions:
- UUID primary key
- Form ID
- Question text
- Question type
- Display order
- Required flag
- JSONB options
- Timestamps

Responses:
- UUID primary key
- Form ID
- Submission timestamp
- Optional safe metadata

Answers:
- UUID primary key
- Response ID
- Question ID
- Validated answer value

Add suitable foreign keys, indexes, constraints, and timestamps.

Implement Row Level Security policies:
- Owners can manage only their own forms.
- Owners can view responses to their own forms.
- Public respondents can submit to published forms through a secure server endpoint.
- Public users cannot read responses or edit forms.
- Unauthorized users cannot access analytics or exports.

Use server-side authorization checks and rate limits. Do not expose the service-role key to the client.

Provide all SQL migrations and explain how to run them.

## 11. Analytics

Route: `/forms/[id]/analytics`

Use Recharts to build a premium black-glass analytics dashboard.

Include:
- Total responses
- Response trends over time
- Question-by-question results
- Bar charts for single-choice questions
- Multiple-choice answer distributions
- Rating distributions and averages
- Completion statistics only when reliably measurable
- Date filters
- Searchable response summaries
- Individual response details

Use readable chart labels, dark chart surfaces, subtle gridlines, and accessible colors.

Calculate all metrics from real stored responses. Handle empty datasets and missing answers correctly.

Never display invented data as real analytics. Any seeded demo data must be clearly labeled as demo data.

## 12. AI response analysis

Add an "Analyze with AI" button.

Generate:
- Executive summary
- Main recurring themes
- Common positive points
- Common complaints and pain points
- Suggestions for improvement
- Representative comments when appropriate
- Sample-size limitations

Requirements:
- Analyze actual collected answers.
- Remove unnecessary personal information.
- Limit payload sizes.
- Clearly separate calculated metrics from AI-generated interpretations.
- Avoid unsupported statistical claims.
- Explain when there are too few responses for meaningful analysis.
- Provide retry and error handling.

Store analysis results only when appropriate, and clearly indicate when an analysis was generated.

## 13. Response management

Route: `/forms/[id]/responses`

Implement:
- Response count
- Searchable response table
- Date filtering
- Individual response detail view
- Question-and-answer display
- CSV export
- Empty states
- Loading and error states

Only authorized form owners may access these records.

## 14. CSV export

Implement a functional CSV download.

Requirements:
- Consistent question columns
- One row per submission
- Correct escaping of commas, quotes, and newlines
- Protection against spreadsheet formula injection
- Correct Unicode handling
- Authorized server-side export
- Useful filename based on the form title

Optionally support a downloadable analytics summary.

## 15. Security and reliability

Implement:
- Server-side Zod validation
- Authentication and authorization checks
- Supabase RLS
- Request-size limits
- Rate limiting for AI generation and public submissions
- Input sanitization where appropriate
- Safe error messages
- Loading skeletons
- Empty states
- Error boundaries
- Protection against unauthorized access
- No hardcoded secrets
- No fake success notifications

Never trust client-supplied owner IDs, form status, question definitions, or analytics.

Validate submitted answers against the actual published form definition on the server.

## 16. Environment variables

Create `.env.example` with placeholders such as:

`NEXT_PUBLIC_SUPABASE_URL=`
`NEXT_PUBLIC_SUPABASE_ANON_KEY=`
`SUPABASE_SERVICE_ROLE_KEY=`
`AI_PROVIDER_API_KEY=`

Use the current recommended Supabase key format where appropriate.

AI and privileged database secrets must remain server-only.

Explain how to configure environment variables locally and on Vercel.

## 17. Project structure and documentation

Keep the project maintainable and organized.

Use clear directories for:
- App Router pages
- API routes
- Reusable UI components
- Dashboard components
- Form editor components
- Analytics components
- Supabase clients
- Database queries
- AI services
- Zod schemas
- Shared types
- Utility functions
- SQL migrations

Create a comprehensive README covering:
1. Installation
2. Local development
3. Supabase setup
4. Database migrations
5. Authentication configuration
6. AI provider setup
7. Demo mode
8. Vercel deployment
9. Main workflow testing
10. Troubleshooting

## 18. Implementation strategy

Build in these stages without abandoning the project after the first stage:

Stage 1: Design system, landing page, and dashboard.

Stage 2: Authentication, Supabase database, migrations, and RLS.

Stage 3: AI generation wizard and editable form builder.

Stage 4: Publishing, public respondent page, and response collection.

Stage 5: Analytics, AI insights, and CSV export.

Stage 6: Testing, bug fixing, security verification, and deployment preparation.

After each stage, verify that the project remains buildable.

## 19. Final acceptance tests

Verify:
- User can sign up and log in.
- User can create and edit a form.
- AI generation works when configured.
- Missing AI credentials produce an honest fallback.
- Questions can be reordered and saved.
- Published forms have working public URLs.
- Respondents can submit without signing in.
- Answers persist in Supabase.
- Analytics reflect real responses.
- AI analysis uses actual collected answers.
- CSV export works.
- Unauthorized access is denied.
- Dashboard and forms work on mobile.
- Production build succeeds.

Do not claim tests passed unless you actually ran them.

## 20. Final instruction to Claude

Start by inspecting the current project files and framework. If an existing project is available, modify it instead of replacing working features unnecessarily.

Then implement the complete application, not merely a plan or a visual mockup.

Prioritize a working end-to-end MVP with a premium black-glass dashboard.

If a task is too large for one response, work in small stages, preserve working code, and continue from the actual project state. Do not repeatedly rewrite the same files or stop after generating the homepage.

At completion, report:
- Features implemented
- Files and migrations created
- Commands to run locally
- Environment variables that require my configuration
- Tests actually executed and their results
- Any incomplete functionality

**Final design requirement: FORMALQ's owner dashboard must consistently use premium black glassmorphism with near-black backgrounds, translucent charcoal panels, subtle violet/blue accents, crisp white typography, and a polished, realistic SaaS experience.**
