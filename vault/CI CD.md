[[DevOps]]

## Definition
- Alron: ci/cd 3 things to learn
	- Version control - git workflows (ways to structure the project)
		- Github flow - basic branch then merge, good for small projects
		- Gitflow - Temasek
		- Trunk-based development - 1gie
	- CI/CD pipelines - everything that aims to automate the steps between your code on git to deployment
		- Usually these services are also offered by the Git providers (e.g. Github, gitlab)
			- Build a Docker image of your service
			- Deploy that Docker image to your deployment manager (e.g. K8s)
	- Deployment “stack” - making a service available to a user
		- Simplest core goal: Computer in the cloud running server - e.g. uvicorn
		- More complicated ones automate the process - e.g. docker build
		- K8s: a simpler way to manage deployments if you need the complexity (e.g. dynamically scaling the number of “VMs”/pods, auto-restarting a pod)
- C: how do you know if a project is big enough?
	- A: 1. Frequent release cadence, 2. potential for many bug fix
	- A: depends on need for multiple iterations in code
	- A: critical bugs and need to deploy, you expect more bugs

## Way to do it
make docker
push to docker registry
deploy k8s pod
k8s pod pulls from registry
[source](https://www.youtube.com/watch?v=sH-trYwjkkY)

cicd with github actions [source](https://nicwortel.nl/blog/2022/05/27/continuous-deployment-to-kubernetes-with-github-actions)
InfraCost CI

## Tools
conan-io [[C++]] package manager for easier CI
[[Go]] has easy devops
[Earthly](https://earthly.dev/) - dockerfile + makefile for easier CI CD

Tutorials
[ACloudGuru](https://acloudguru.com/course/implementing-a-full-ci-cd-pipeline)