# Bryj.ai DevOps/SRE Challenge

## Vote for me!

For this challenge you'll need a CRUD application, you can use the one we prepared for this challenge [here](https://github.com/bryjai/sre_challenges_base_app.git) created using the _Get Started_ tutorial on [Django Framework](https://docs.djangoproject.com/en/4.1/intro/tutorial01/) website, or you can bring your on App coded on your preferred language and framework.

### Part 1:

Your task is to create a Continuous Integration (CI) pipeline to build the CRUD app. You can use GitHub Actions (free accounts have 2000 minutes to be used with no cost) or any other CI tool, we only ask for it to be reproducible outside your local machine.

The CI must contain one stage to build a container image with the App, one stage to run the unit tests and one last stage to push the container to GitHub (you can create a free account to host a free public repository).
