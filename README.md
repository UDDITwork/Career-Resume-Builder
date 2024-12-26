<div align="center">
  <h1>Career-Resume-Builder</h1>
  
  [![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](/)
  [![License](https://img.shields.io/badge/license-MIT-green.svg)](/)
</div>

🚀 **Under pre-released Beta Module | Shree-AI Version** 🚀  

Welcome to **Career-Resume-Builder**, the pre-release beta glimpse of Shree-AI's capabilities—a **next-gen AI-powered resume builder** for crafting professional, ATS-ready resumes in real-time. Designed to make resume creation fast, intelligent, and hassle-free, this beta version offers a powerful sneak peek into Shree-AI's transformative potential.  
**RESUME-PARSER-ALGORITHM**
---

Career-Resume-Builder is a powerful open-source resume builder and resume parser.

The goal of Career-Resume-Builder is to provide everyone with free access to a modern professional resume design and enable anyone to apply for jobs with confidence.

Official site: [https://notdecided.com](https://Career-Resume-Builder.com)

## ⚒️ Resume Builder

CareerResumeBuilder's resume builder allows user to create a modern professional resume easily.

![Resume Builder Demo](https://i.ibb.co/jzcrrt8/career-resume-builder-demo-optimize.gif)

It has 5 Core Features:
| <div style="width:285px">**Feature**</div> | **Description** |
|---|---|
| **1. Real Time UI Update** | The resume PDF is updated in real time as you enter your resume information, so you can easily see the final output. |
| **2. Modern Professional Resume Design** | The resume PDF is a modern professional design that adheres to U.S. best practices and is ATS friendly to top ATS platforms such as Greenhouse and Lever. It automatically formats fonts, sizes, margins, bullet points to ensure consistency and avoid human errors. |
| **3. Privacy Focus** | The app only runs locally on your browser, meaning no sign up is required and no data ever leaves your browser, so it gives you peace of mind on your personal data. (Fun fact: Running only locally means the app still works even if you disconnect the internet.) |
| **4. Import From Existing Resume PDF** | If you already have an existing resume PDF, you have the option to import it directly, so you can update your resume design to a modern professional design in literally a few seconds. |
| **5. Successful Track Record** | OpenResume users have landed interviews and offers from top companies, such as Dropbox, Google, Meta to name a few. It has been proven to work and liken by recruiters and hiring managers. |

## 🔍 Resume Parser

Career-Resume-Builder’s second component is the resume parser. For those who have an existing resume, the resume parser can help test and confirm its ATS readability.

![Resume Parser Demo](https://i.ibb.co/JvSVwNk/resume-parser-demo-optimize.gif)

You can learn more about the resume parser algorithm in the ["Resume Parser Algorithm Deep Dive" section](https://Career-Resume-Builder.com/resume-parser).

## 📚 Tech Stack

| <div style="width:140px">**Category**</div> | <div style="width:100px">**Choice**</div> | **Descriptions** |
|---|---|---|
| **Language** | [TypeScript](https://github.com/microsoft/TypeScript) | TypeScript is JavaScript with static type checking and helps catch many silly bugs at code time. |
| **UI Library** | [React](https://github.com/facebook/react) | React’s declarative syntax and component-based architecture make it simple to develop reactive reusable components. |
| **State Management** | [Redux Toolkit](https://github.com/reduxjs/redux-toolkit) | Redux toolkit reduces the boilerplate to set up and update a central redux store, which is used in managing the complex resume state. |
| **CSS Framework** | [Tailwind CSS](https://github.com/tailwindlabs/tailwindcss) | Tailwind speeds up development by providing helpful css utilities and removing the need to context switch between tsx and css files. |
| **Web Framework** | [NextJS 13](https://github.com/vercel/next.js) | Next.js supports static site generation and helps build efficient React webpages that support SEO. |
| **PDF Reader** | [PDF.js](https://github.com/mozilla/pdf.js) | PDF.js reads content from PDF files and is used by the resume parser at its first step to read a resume PDF’s content. |
| **PDF Renderer** | [React-pdf](https://github.com/diegomura/react-pdf) | React-pdf creates PDF files and is used by the resume builder to create a downloadable PDF file. |

## 📁 Project Structure

Career-Resume-Builder is created with the NextJS web framework and follows its project structure. The source code can be found in `src/app`. There are a total of 4 page routes as shown in the table below. (Code path is relative to `src/app`)

| <div style="width:115px">**Page Route**</div> | **Code Path** | **Description** |
|---|---|---|
| / | /page.tsx | Home page that contains hero, auto typing resume, steps, testimonials, logo cloud, etc |
| /resume-import | /resume-import/page.tsx | Resume import page, where you can choose to import data from an existing resume PDF. The main component used is `ResumeDropzone` (`/components/ResumeDropzone.tsx`) |
| /resume-builder | /resume-builder/page.tsx | Resume builder page to build and download a resume PDF. The main components used are `ResumeForm` (`/components/ResumeForm`) and `Resume` (`/components/Resume`) |
| /resume-parser | /resume-parser/page.tsx | Resume parser page to test a resume’s AST readability. The main library util used is `parseResumeFromPdf` (`/lib/parse-resume-from-pdf`) |

## 💻 Local Development

### Method 1: npm

1. Download the repo 
2. Change the directory `cd Career-Resume-Builder`
3. Install the dependency `npm install`
4. Start a development server `npm run dev`
5. Open your browser and visit [http://localhost:3000](http://localhost:3000) to see Career-Resume-Builder live

## 🌐 Hosting on Google Cloud  

### Prerequisites:  
- A Google Cloud account ([Sign up here](https://cloud.google.com/)).  
- Google Cloud SDK installed ([Installation guide](https://cloud.google.com/sdk/docs/install)).  

### Steps:  
1. **Enable Cloud Run and Container Registry**:  
   - Go to the [Google Cloud Console](https://console.cloud.google.com/).  
   - Enable **Cloud Run** and **Container Registry APIs**.  

2. **Clone the Repository**:  
   ```bash
   git clone https://github.com/UDDITwork/Career-Resume-Builder.git
   cd Career-Resume-Builder
Build the Docker Image:


docker build -t gcr.io/<your-project-id>/career-resume-builder .
Push the Image to Google Container Registry:

bash
Copy code
docker push gcr.io/<your-project-id>/career-resume-builder
Deploy to Cloud Run:

bash
Copy code
gcloud run deploy career-resume-builder \
  --image=gcr.io/<your-project-id>/career-resume-builder \
  --platform=managed \
  --region=us-central1 \
  --allow-unauthenticated
Access Your App:

Google Cloud Run provides a public URL, e.g., https://career-resume-builder-<unique-id>.a.run.app.
🐳 Hosting with Docker
Prerequisites:
Docker installed (Installation guide).
Steps:
Clone the Repository:


git clone https://github.com/UDDITwork/Career-Resume-Builder.git
cd Career-Resume-Builder
Build the Docker Image:


docker build -t career-resume-builder .
Run the Docker Container:

bash
Copy code
docker run -p 3000:3000 career-resume-builder
Access Your App:

Open http://localhost:3000 in your browser to see the application running.
Optional Deployment to Any Cloud:

Push the Docker image to a container registry (e.g., Docker Hub, AWS, Azure) and deploy it using their respective services.
🔥 Hosting with Firebase Hosting
Prerequisites:
Firebase CLI installed (Installation guide).
A Firebase project (Create one here).
Steps:
Initialize Firebase in Your Project:


firebase login
firebase init
Select Hosting.
Choose your Firebase project or create a new one.
Set build/ as the public directory when prompted.
Build the Application:


npm install
npm run build
Deploy to Firebase:


firebase deploy
Access Your App:

Firebase will provide a live URL, e.g., https://<your-project-id>.web.app.
🎯 Choosing the Right Platform
Google Cloud: Best for scalable, production-ready deployments with serverless capabilities.
Docker: Ideal for local hosting or portable deployment across various platforms.
Firebase: Simplest option for hosting static or single-page applications.
💻 GitHub Repository: Career-Resume-Builder
🌐 Official Site: [Coming Soon 🚧]

Copy code







1. Download the repo `git clone https://github.com/UDDITwork/Career-Resume-Builder.git`
2. Change the directory `cd Career-Resume-Builder`
3. Build the container `docker build -t Career-Resume-Builder .`
4. Start the container `docker run -p 3000:3000 Career-Resume-Builder`
5. Open your browser and visit [http://localhost:3000](http://localhost:3000) to see Carrer-Resume-Builder live
