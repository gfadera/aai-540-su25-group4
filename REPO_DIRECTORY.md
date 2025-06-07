aai-540-su25-group4/ # WildScan 
│
├── README.md           # Project overview and setup instructions, must include S3 bucket details (Requirement: Method #3)
├── PROJECT_DIRECTORY.md    # table of contents/structure of the repo
├── requirements.txt    # Python dependencies
├── environment.yml     # environment configuration 
├── ./env.default       # to store default environment variables such as S3 bucket names, etc
├── .gitignore          # list "datasets/" here as it contains large files"
│
├── dataset/            # .gitignored (not tracked by git) - JUST INFO
│   └── README.md       # Dataset overview and instructions for access. details of all S3 buckets used. 
│
├── src/
│   ├── data_processing/  # pdata loading scripts, data engineering (cropping, resizing), other feature engineering, train/test split
│   ├── models/         # modules for various model architectures, transfer learning, custom classifiers        
│   ├── training/       # modules for training, hyperparameter tuning, model selection
│   ├── evaluation/     # modules for various evaluation metrics, class report, visualization
│   ├── inference/      # module/script containing how to load models, preprocess input, make predictions, and postprocess output, include SHAP for interpretability?
│   ├── utils/
│   └── config/
│
├── deployment/          # scripts and configurations for deployment on SageMaker (Module4/5)
│   └── xxx.py           # modules/pipelines to deploy model on SageMaker, endpoint creation, inference, setting up of upload data bucke 
│
├── monitoring/           # Monitoring scripts and configurations for deployed models (Module 5)
│   ├── data_drift.py     # example  
│   └── model_metrics.py  # example      
│
├── ci-cd/                  # Module 6 (Dunno yet)
│   ├── github_actions/
│   └── deploy.py
│
├── experiments/           # Jupyter/Colab notebooks for experiments, feature tests, model comparisons, etc.
│   ├── tyler/
│   ├── edwin/
│   └── geoffrey/
│
├── notebooks/             # Final Jupyter notebooks for demos, visualizations, model comparison, etc.
│   ├── 01_eda.ipynb       # Data sources. loading, size, class distribution, suggested train/val split logic           
│   ├── 02_data_feature_engineering.ipynb   # explanation and sample images for each data/feature engineering method, including cropping, resizing, color histograms, HOG, GLCM texture, and CNN features
│   ├── 03_model_training_tuning.ipynb  # Model training and hyperparameter tuning, including baseline, benchmark, and custom classifiers
│   ├── 04_model_evaluation.ipynb  # Model evaluation, including metrics, confusion matrices, ROC curves, and maybe include SHAP visualization for highlighting pixel importance (?)
│   └── 05_deployment_monitoring.ipynb # Deployment and monitoring, including SageMaker deployment, model monitoring, and data drift detection
│
└──  LICENSE             # License information