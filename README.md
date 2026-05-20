# Freelance Platform Backend

Freelance job and project tracking platform backend built with NestJS, Prisma, and MySQL.

## Project
This API manages the full freelance workflow: authentication, job posting, bidding, project tracking, milestones, deliveries, payments, and disputes.

## Testing & Quality Assurance (QA)
The testing, quality assurance, and API validation processes of this project were independently managed and executed by **[Sena Bostan](https://github.com/senabostan)**. 

To ensure system stability, reliability, and security across the entire freelance workflow, the following verification layers were implemented:

- **Functional Workflow Testing:** I designed and executed comprehensive test scenarios covering critical multi-step business logic, such as the complete cycle from job bidding and milestone progression to final payment releases and dispute resolutions.
- **API & Validation Testing:** I systematically verified all API endpoints to validate HTTP response statuses, strict data payload validation rules, and robust error-handling behaviors across all modules.
- **Database Integrity Verification:** Using MySQL and Prisma client inspections, I directly validated backend state transitions, ensuring that complex database relations and status updates (e.g., payment triggers) reflect accurately without breaking constraints.

### QA Tools & Environment Used
- **Postman:** Utilized to build automated and manual request suites, simulating complex end-to-end user journeys (e.g., dynamic login authentication via JWT, token generation, and secure endpoint access control).
- **Swagger UI:** Employed for rapid endpoint exploration, request structure validation, and living documentation alignment.


## Technologies
- NestJS
- Prisma ORM
- MySQL
- JWT + Passport
- Swagger

## Quick Setup
1. Install dependencies:
```bash
npm install
```
2. Prepare environment:
```bash
cp .env.example .env
```
3. Start MySQL with Docker:
```bash
docker compose up -d
```
4. Run Prisma migrations and generate client:
```bash
npm run prisma:generate
npm run prisma:migrate
```
5. Start app:
```bash
npm run start:dev
```

## Swagger
- URL: `http://localhost:3000/docs`

## Main Modules
- auth
- jobs
- bids
- projects
- milestones
- deliveries
- payments
- disputes

## Example Endpoints
```http
POST /auth/register
POST /auth/login
GET  /jobs
POST /jobs/:jobId/bids
GET  /projects
POST /projects/:projectId/milestones
POST /milestones/:id/deliveries
POST /payments/:id/release
POST /projects/:projectId/disputes
GET  /health
```
