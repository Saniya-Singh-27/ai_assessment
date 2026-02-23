AI-Powered Smart Assessment System – Feature Breakdown (Implementation Version)
1️ Question Management
1.1 Admin Question Upload

Upload questions via CSV / JSON

Validate format & required fields

Store in PostgreSQL

1.2 Question Validation

Missing fields check

Duplicate Question ID check

Valid type (MCQ / Short Answer)

Difficulty & topic validation

1.3 Question Storage

Store question text

Options (MCQ)

Correct answer

Topic & difficulty tagging

2️ Assessment Engine
2.1 Session Initialization

Generate session ID

Assign question set

Track session timestamps

2.2 MCQ Evaluation

Exact match scoring

Immediate correctness feedback

Score storage

2.3 Short Answer Evaluation (NLP)

Text preprocessing (spaCy)

Embedding generation (Sentence Transformers)

Cosine similarity scoring

Threshold-based grading

Partial credit logic

3️ Feedback & Scoring System
3.1 Real-Time Feedback

Correct / Partially Correct / Incorrect

Similarity score display

Reference answer display

3.2 Final Score Calculation

Total score aggregation

Percentage calculation

Topic-wise accuracy

4️ Analytics Module
4.1 Topic-Level Analysis

Accuracy per topic

Weak vs strong area identification

4.2 Difficulty-Level Analysis

Easy / Medium / Hard performance

Comparative breakdown

4.3 Session Summary

Total questions attempted

Average similarity score

Time taken

5️ Dashboard & UI Layer
5.1 Student Dashboard

Active session

Previous scores

Topic performance summary

5.2 Chat-Style Assessment UI

Sequential question display

Answer submission

Auto-scroll interaction

5.3 History View

Past session list

Detailed session results

6️ REST API Functionality
6.1 Authentication APIs

POST /register

POST /login

JWT-based authentication

6.2 Question APIs

GET /questions

POST /admin-upload

6.3 Evaluation APIs

POST /submit-answer

GET /session-result

6.4 Analytics APIs

GET /topic-performance

GET /difficulty-breakdown

7️ Database Entities (PostgreSQL)
7.1 User

id

email

role

7.2 Question

id

text

type

correct_answer

topic

difficulty

7.3 Session

id

user_id

start_time

end_time

7.4 Response

id

session_id

question_id

user_answer

score

similarity_score

feedback

8️ Deployment & Infrastructure
8.1 Containerization

Dockerized backend

Environment config

8.2 Cloud Deployment

AWS EC2 (single region)

PostgreSQL integration

8.3 Performance Constraints

<1.5 sec semantic scoring

CPU-based embeddings

Dataset <50k questions

9️ Explainability & Trust
9.1 Transparent Scoring

Show similarity score

Display threshold logic

9.2 Confidence Indicator

Provide grading confidence score

10 Risk & Edge Case Handling

Invalid question upload → HTTP 400

Missing session → HTTP 404

Unauthorized access → HTTP 401

Empty answer → validation error

Similarity below threshold → partial scoring

1️1️ ML Integration Plan

Pre-trained Sentence Transformer

Cosine similarity-based grading

No LLM usage

Threshold tuning via validation set
