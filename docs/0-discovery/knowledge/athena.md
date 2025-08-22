# Athena

It is an online assessment and learning platform developed by Gemini Solutions.
The application aims to facilitate flow to conduct online tests for placement drives and internal quizzes

· It also facilitates learning and development courses to improve skills in different domains such as technical, behavioral, communication and cyber security etc.

· It comprises of two modules

· One to create and manage tests and trainings

· And one is to attempt the test & assigned courses


## High Level Feature list

· Cater diverse type of questions - (Subjective, MCQ, Comprehensions, Video, Image)

· Policy Violation monitoring and Auto Submission of Test if user tries to exist full screen

· User Management Module along with Role management and Entitlement service

· Bulk upload utility - (Questions, Users, Campuses etc)

· Question Paper can be downloaded if test is in offline mode

· Batches creation and assigning multiple courses to a batch

· Course completion certificate mailed to users and downloadable in UI


Stand Out Features

· Register New Users and Assign them to test with a single click

· Auto submission of tests and manage suppress auto submit by Admin

· Capturing screenshots of test page every 30 seconds for proctoring purpose

· Sending E-Mails on policy violation to management/ college TPO


(Primary and secondary purpose of application):

Primary purpose

· To conduct test and quizzes for placement drives and internal users

· To facilitate courses for learning and development purpose


Secondary purpose

· To organize quizzes for events in Gemini

BRD Link: Athena BRD.docx


Architecture diagram (for Production):


Work in Progress


Connected systems:

The application consists of the following services and each service is independent of each other.

1. User Management Service: This service consists of CRUD APIs for users and Role management.

2. Test Management Service: This service consists of CRUD APIs for test management. Each test may include multiple sections and each section includes multiple questions. This service also handles the candidate/learner side functionalities. It captures the answers submitted by each candidate and their respective test reports.

3. Common Service: This service is used to send emails to users on various events such as user creation, assigned to test and test reports. It is also responsible for sending policy violation emails to specific team members.

4. Campus Service: This Service is used to perform CRUD operations on campus details. It is also used to get campus performance reports based on various filters.

5. Async Service: This service is mainly to perform asynchronous operations throughout the application. For example: to synchronize the users from MIS, to save the users in Master DB.

6. AWS Service: This service handles the data upload to the S3 bucket such as Images and Videos for the questions.


Deployment: <For PROD>

· FrontEnd Deployment details – Frontend is deployed on AWS S3 https://athena.geminisolutions.com/

· BackEnd deployment details – Backend is deployed on Gemini EKS servers https://athenaapi.geminisolutions.com/ http://eapi.geminisolutions.com/gemassessment


QA Signoff from EC QA Governance for prod release: · Susheel Mahobia- susheel.mahobia@geminisolutions.com · Saloni Nagpal- saloni.nagpal@geminisolutions.com


Github repos: · Backend repo link- https://github.com/Gemini-Solutions/GemAssessmentBackend.git · Frontend repo link- https://github.com/Gemini-Solutions/AthenaFrontend.git


Tech Stack:

· Backend: Java Spring Boot

· Database: PostgreSQL

· Frontend: Angular with NX

· Infrastructure- AWS

PreSales ppt available: Yes, Athena_Deck.pptx

Audience:

· All HRs, EC, and DC chairs/co-chairs and their extended Team, Delivery heads (Neeraj Yadav, Prashank Chaudhary, Anil Singh)

· Gemini Employees taking internal quiz and courses on LnD

· Users/ Candidates taking test


Security: <Below 3 fields are mandatory>

· SonarQube integrated – Yes

· OAUTH2 implemented – Yes

· All API secured (No Open API): No, all APIs are secured except 4-5, for-eg.- Forgot password API, GetCampus API etc.


