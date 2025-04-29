# Integrate Unit Test Automation

This folder holds the files for the lab: _Integrate Unit Test Automation_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.


## Steps:

* Relace the linting task to the one on Tekton Hub. Use the following Tekton CLI command to install the flake8 task into your namespace.
`` kubectl apply -f tasks.yaml ``
`` tkn hub install task git-clone ``
`` tkn hub install task flake8 ``
`` kubectl apply -f pvc.yaml ``
`` kubectl apply -f pipeline.yaml ``

* Run the following code to start the pipeline
`` tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/ibm-developer-skills-network/wtecc-CICD_PracticeCode.git" \
    -p branch="main" \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog ``

`` tkn pipelinerun ls ``
`` tkn pipelinerun logs --last ``
