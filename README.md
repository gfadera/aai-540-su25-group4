# aai-540-su25-group4
AAI-540 Summer 2025 Group 4 Final Project Repo

# WildScan: Wildlife Image Classification using SageMaker

WildScan is a machine learning system designed to automatically classify wildlife species in static images collected by motion-triggered trail cameras. Built by Group 4 for the AAI-540 course at the University of San Diego, this project leverages AWS SageMaker, CodePipeline, and CodeBuild to create an end-to-end, production-ready image classification pipeline.

## Project Overview

- **Type:** Multi-class image classification
- **Model:** CNN (ResNet-18 via SageMaker's built-in image-classification algorithm)
- **Dataset:** Caltech Camera Traps (CCT20)
- **Goal:** Classify 20 wildlife species with ≥80% accuracy on real-world trail camera images
- **Deployment:** Batch inference on SageMaker with infrastructure monitoring and CI/CD

## Pipeline Summary

This project implements a modular ML pipeline, covering:

1. **Data Ingestion**  
   - Uploads and preprocesses annotated CCT20 images to S3  
2. **Preprocessing**  
   - Resizes and formats images to 224×224, prepares `.lst` label files  
3. **Training**  
   - Runs a SageMaker training job using transfer learning (ResNet-18)  
4. **Evaluation**  
   - Calculates accuracy, weighted/macro F1 scores, and per-class metrics  
5. **Monitoring**  
   - Visualizes performance metrics via AWS CloudWatch  
6. **CI/CD**  
   - CodePipeline & CodeBuild automatically trigger model retraining on GitHub push

## Repository Structure
```
├── notebooks/ # Jupyter notebooks for each pipeline stage
│ ├── 01_eda_&_preprocessing.ipynb
│ ├── 02_preprocessing_split.ipynb
│ ├── 03_model_training_tuning.ipynb
│ ├── 04_model_evaluation_comparison.ipynb
│ └── 05_deployment_monitoring.ipynb
├── src/ # Source scripts (utils, helper functions)
├── buildspec.yml # CI/CD pipeline instructions for AWS CodeBuild
├── README.md # You're here!
```

## Setup Instructions

> Prerequisites:
- AWS account with access to SageMaker, S3, CodePipeline, and CodeBuild
- GitHub repository connected via CodePipeline
- Python 3.8+ environment (for local testing)

### Clone the repository

git clone https://github.com/gfadera/aai-540-su25-group4.git
cd aai-540-su25-group

Run notebooks (optional local testing)
You can test any notebook in the notebooks/ directory using JupyterLab or VS Code.

Model Performance
Metric	Validation Score
Accuracy	83%
Weighted F1 Score	0.83
Macro F1 Score	0.64

Note: Per-class performance is detailed in the 04_model_evaluation_comparison.ipynb

Cloud Architecture
Training: SageMaker (GPU-backed ResNet-18)

CI/CD: GitHub → AWS CodePipeline → CodeBuild → SageMaker

Monitoring: AWS CloudWatch dashboards

Storage: S3 buckets for data, model artifacts, and outputs

Team Members
Tyler Clinscales
Geoffrey Fadera
Edwin Merchan	

License
This project is for academic purposes as part of the AAI-540 course at the University of San Diego.

Special Thanks
Thanks to the creators of the Caltech Camera Traps dataset and the AWS Educate program for providing the tools and resources used in this project.

Citations:

Caltech Camera Traps (CCT20)

Amazon SageMaker: https://aws.amazon.com/sagemaker/

CodePipeline: https://aws.amazon.com/codepipeline/

CodeBuild: https://aws.amazon.com/codebuild/

OpenAI. (2024). ChatGPT (June 2025 version) [Large language model]. https://chat.openai.com

Course Citation:

This project was developed as part of the AAI-540 course — Machine Learning Systems Design — at the University of San Diego, Summer 2025.

GitHub Repository Citation:

Clinscales, T., Merchan, E., & Fadera, G. (2025). WildScan: Wildlife Image Classification using SageMaker (v1.0). GitHub. https://github.com/gfadera/aai-540-su25-group4
