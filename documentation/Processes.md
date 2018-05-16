## Processes for Employees & Contractors

### Confidentiality
Unless otherwise noted, all source code is confidential, intellectual property and covered under the terms of your NDA.

### Software / Product Development

#### Source Code Change Management
As a software/product developer, you will be granted access to the appropriate project repositories on github.

##### Your Responsibilities
* Set up and identify your github account which is to be used for access
* Familiarize yourself with proper git and github usage
* Hand off your contributions via Pull Request from a feature branch off of the primary development branch
* Ensure that your feature branch is up-to-date (via rebase or periodic merges, or however you prefer)
* Always `git pull` prior to `git push` unless you have a specific, technical reason not to.

##### DigiStratum Responisibilities
* Grant access to appropriate github project repositories
* Provide documentation as needed to explain branching strategy (GitFlow)
* Monitor Pull Request activity, review, comment, and reject or merge as needed

#### Task Management
As a software/product developer, you will be provided with a link and login as needed for task management where you will find your assigned tasks.

##### Your Responsibilities
* Ensure that you have access to the task management system
* Understanding, communicate about, and deliver on assigned tasks
* Monitor changes and communications pertaining to your assigned tasks (by web, email, or otherwise)
* Communicate questions and status updates via threaded comments in task management system
* Translate acceptance criteria into your own, written implementation plan BEFORE beginning work on an assigned task
* Immediately indicate whether an assigned task is beyond your range of experience / expertise

##### DigiStratum Responisibilities
* Provide clear, concise acceptance criteria for tasks
* Prioritize and assign tasks such that it is clear what comes next
* Respond to questions and/or requests for clarification expediently
* Review developer-provided implementation plan and approve to proceed
* Ensure that task assignments are aligned with developer experience / expertise

#### Standards Compliance
As a software/product developer, you will be working on applications with documented standards and requirements which must be adhered to.

##### Your Responsibilities
* Read the application's project documentation beginning with the README.md located in the project root
* Familiarize yourself with both internal and external standards and requirements linked to the project
* Ensure that your changes are consistent with the documented standards and requirements
* Ensure that your changes are consistent with the existing application code base

##### DigiStratum Responisibilities
* Create application project documentation (README.md)
* Link internal and external standards and requirements to the project documentation
* Review developer-provided changes for standards compliance and communicate about additional changes needed

#### Test Coverage
As a software/product developer, you will be testing your own work with automatable test coverage which is key to Continuous Integration / Deployment (CICD). Different projects will have different requirements and types of test automation in place for unit, integration, functional, performance, security, scalability, etc.

##### Your Responsibilities
* Follow the established testing model/conventions for the application/service that you are working on
* Existing tests document expected behavior; if one fails, the behavior is broken, not the test, so don't "fix" the test unless the test can be shown to be invalid (and be prepared to explain why)
* Familiarize yourself with the established testing model/conventions, framework and its capabilities
* Ensure that the changes you make to application/service code are covered by at least one automated test
* Inquire before introducing additional types/methods of testing not already established
* If test coverage cannot be provided for a given change, be prepared to explain why
* Consider Test Driven Development (TDD) process for your workflow if you do not already practice this
* Get set up to execute the test automation suite locally in your development environment

##### DigiStratum Responisibilities
* Document the test coverage requirements and types in the project documentation
* Integrate the test coverage automation via CI/CD platform
* Monitor test automation execution and file bugs and assign as tasks for developers as needed for corrective action
