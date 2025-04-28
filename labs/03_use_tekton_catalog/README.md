# Use Tekton CD Catalog

This folder holds the files for the lab: _Use Tekton CD Catalog_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

### Install the tkn git-clone task
* `` tkn hub install task git-clone --version 0.8 `` or
* `` kubectl apply -f https://raw.githubusercontent.com/tektoncd/catalog/main/task/git-clone/0.9/git-clone.yaml ``

* Use the following command to run the pipeline, passing in the URL of the repository, the branch to clone, the workspace name, and the persistent volume claim name.
`` tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/ibm-developer-skills-network/wtecc-CICD_PracticeCode.git" \
    -p branch="main" \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog ``

* To check the status of the pipleine run
`` tkn pipelinerun ls ``

* To check the last log
`` tkn pipelinerun logs --last ``