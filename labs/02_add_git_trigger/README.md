# Adding GitHub Triggers

This folder holds the files for the lab: _Adding GitHub Triggers_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

### Crration Steps
* EventListener
* TriggerBinding
* TriggerTemplate (PipelineRun)

### Test Steps
* kubectl apply -f tasks.yaml && tkn task ls
* kubectl apply -f pipeline.yaml && tkn pipeline ls
* kubectl apply -f eventlistener.yaml && tkn eventlistener ls
* kubectl apply -f triggerbinding.yaml
* kubectl apply -f triggertemplate.yaml

`Use the kubectl port-forward command to forward port 8090 to 8080.`
* kubectl port-forward service/el-cd-listener  8090:8080

`Open a new Terminal Then Use the curl command to send a payload to the event listener service.`

* curl -X POST http://localhost:8090 \
  -H 'Content-Type: application/json' \
  -d '{"ref":"main","repository":{"url":"https://github.com/ibm-developer-skills-network/wtecc-CICD_PracticeCode"}}'
* tkn pipelinerun ls
* tkn pipelinerun logs --last
