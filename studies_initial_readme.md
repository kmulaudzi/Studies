You are the lead software engineer responsible for building the first production-quality release of **Studies**, an education platform owned by Consulting in 7.

The repository contains `STUDIES_SPEC.md`.

Read that entire document before making any implementation decisions.

Your task is to implement **Studies R001** according to the specification.

## Non-negotiable architecture

Use:

- Next.js
- TypeScript
- App Router
- Tailwind CSS
- shadcn/ui
- Supabase PostgreSQL
- Supabase Auth
- Supabase Storage
- Supabase Row Level Security
- KaTeX or equivalent for mathematics rendering

Do not substitute another backend, database, authentication system or frontend framework.

## Primary objective

Implement one complete vertical learning journey:

Student registers  
→ logs in  
→ enters dashboard  
→ opens Grade 12 CAPS Mathematics  
→ selects Algebra  
→ selects Quadratic Equations  
→ opens Factorisation lesson  
→ learns concept/method/example  
→ opens practice question  
→ submits answer  
→ result is saved  
→ mastery is updated  
→ progress is visible.

Also implement the initial admin interface needed to manage the content behind that journey.

## Work autonomously

Do not ask for confirmation after every small implementation decision.

Use reasonable engineering judgement where `STUDIES_SPEC.md` leaves minor implementation details unspecified.

Do not change major architecture or product requirements without clearly documenting why.

## Build sequence

Implement in this order:

### 1. Project foundation

Set up:

- Next.js
- TypeScript strict mode
- Tailwind
- shadcn/ui
- linting
- environment variable structure
- Supabase clients
- route layouts

Create `.env.example`.

Do not place secrets in source code.

### 2. Database

Create version-controlled Supabase migrations for the data model defined in `STUDIES_SPEC.md`.

Include:

- tables
- foreign keys
- indexes
- enums or constraints where appropriate
- timestamps
- RLS
- policies

Do not create schema manually without migrations.

### 3. Seed data

Create repeatable seed data for:

CAPS  
→ Grade 12  
→ Mathematics  
→ Paper 1  
→ Algebra  
→ Quadratic Equations  
→ Factorisation

Also seed all major Grade 12 Mathematics Paper 1 and Paper 2 topic headings listed in the specification.

Seed one complete Factorisation lesson and at least three clearly-labelled demo questions.

Do not falsely label demo questions as actual NSC questions.

### 4. Authentication

Implement:

- signup
- login
- logout
- forgot password
- reset password
- protected routes
- profile creation

New learners should receive a student profile and Grade 12 CAPS Mathematics enrolment.

### 5. Student experience

Implement:

- landing page
- student dashboard
- Mathematics overview
- topic page
- skill page
- lesson experience
- practice page
- progress page

All relevant data must come from Supabase rather than hard-coded frontend objects.

### 6. Practice engine

Allow a learner to:

- view question
- enter answer
- submit attempt
- see whether the answer is correct where objective marking is possible
- see marks
- request/reveal hint
- reveal solution
- move to next question

Store every submitted attempt.

Update skill mastery after submissions.

### 7. Admin experience

Implement:

- admin dashboard
- curriculum management
- topic/skill management
- lesson management
- exam-paper management
- examination-question management
- publish/draft workflow

Protect admin routes and operations.

### 8. Responsive design

Optimise primarily for mobile.

The UI should feel like a premium modern educational application for learners aged roughly 15–19.

Avoid childish visual language.

Use strong spacing, readable typography, clear cards and simple navigation.

### 9. Testing

Add meaningful tests for critical areas.

At minimum verify:

- authentication protection
- student privacy
- mastery calculation
- question submission
- content retrieval

Run:

- TypeScript checks
- lint
- tests
- production build

Fix failures rather than simply documenting them.

### 10. Documentation

Create/update README.md with:

- project description
- architecture
- setup instructions
- Supabase instructions
- migration commands
- seed commands
- environment variables
- running locally
- testing
- deployment
- major routes
- future roadmap

## Security requirements

Students must never be able to query another student's:

- attempts
- mastery
- profile-private information
- study sessions

Use Supabase RLS rather than relying only on frontend route protection.

Never expose the Supabase service-role key to the client.

Never expose future OpenAI API keys to the client.

## Data modelling requirements

Do not hard-code assumptions that there will only ever be:

- CAPS
- Grade 12
- Mathematics
- Paper 1/2

Studies must later accommodate multiple curricula, grades and subjects.

Questions must support many-to-many relationships with skills.

Skills must support optional parent/child nesting.

## Development behaviour

Before implementing, inspect the repository and write a concise implementation plan.

Then implement the plan.

After each major phase:

1. run relevant checks
2. fix errors
3. continue

Do not leave avoidable TypeScript errors, broken imports, placeholder routes or dead UI.

Prefer functioning simple features over elaborate unfinished features.

## Important product principle

Studies is not primarily an online past-paper library.

It is a learning engine based on:

**Teach → Demonstrate → Practise → Apply to Real Exam Questions → Diagnose → Improve → Master**

Preserve this principle throughout the UI and architecture.

## Final output

When implementation is complete, provide:

1. Summary of what was built
2. Database migrations created
3. Routes created
4. Tests performed
5. Any remaining known limitations
6. Exact local setup instructions
7. Exact commands needed to run the application
8. Exact steps needed to connect the Supabase project
9. Exact deployment steps
10. Recommended next task for Studies R002

Do not begin R002.

Complete R001 first.