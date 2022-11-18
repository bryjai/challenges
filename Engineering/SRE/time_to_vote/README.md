# Bryj.ai DevOps/SRE Challenge

## Time to vote!

For this challenge you'll need a CRUD application, we recommend you to use the one we prepared for this challenge [here](https://github.com/bryjai/sre_challenges_base_app.git) created using the _Get Started_ tutorial on [Django Framework](https://docs.djangoproject.com/en/4.1/intro/tutorial01/) website, but you can bring your own App coded on your preferred language and framework. If you're doing so, keep in mind that it should have the same functionality as the App we prepared. 

### Guidelines

* You should deliver your code in a pull request to the CRUD App repository.
* If you're bringing your own App it should be a public git repository.
* You should create a docker compose file to allow running your code with all its external dependencies.

### Part 1:

Your task is to create a Continuous Integration (CI) pipeline to build the CRUD app. You can use GitHub Actions (free accounts have 2000 minutes to be used with no cost) or any other CI tool, we only ask for it to be reproducible outside your local machine.

The CI must contain one stage to build a container image with the App, one stage to run the unit tests and one last stage to push the container to GitHub (you can create a free account to host a free public repository).

### Part 2

Your next task will be to create a metric to measure the number of votes in a given period of time. You'll need to store this metric on a time series database, you are free to choose the database you like (Prometheus, InfluxDB, ...)

You should change the code to send this metric when someone vote for a poll, also the metric must be tagged with the poll question.
Please provide the instructions to run the time series database and the query to show the number of votes in the last 4 hours.

### Part 3

For this next task you should create a new export function to AWS S3. This task should export the poll results to S3 in one CSV file per question and each file must contain one line per vote with the choice (ID or choice's text) and the UTC date of the vote like bellow (you can format the date as you wish, like the example below or in ISO 8601):

```text
question_1.csv:
choice_1_1,2022-11-16 10:21:48
choice_1_2,2022-11-16 10:23:48
choice_1_2,2022-11-16 10:27:48
```

The export should be triggered from a form request indicating the path inside the S3 to save the files.
We suggest you to use a local solution to simulate a AWS S3 server like MinIO. You can run it on Docker like described on [this article](https://simonjcarr.medium.com/running-s3-object-storage-locally-with-minio-f50540ffc239).


### Part 4

Your last task will be to create a Helm template to allow it to be deployed to Kubernetes. Your app should be deployed as a Kubernetes Deployment, with a Horizontal Pod Autoscaler based on CPU and Memory and having the number of replicas between 2 and 4.
