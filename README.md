# GitHub Workflow to run the Postman tests via an Alexa Skill

- The `Postman API Tests` workflow is structured to be triggerd when a user instructs Alexa to run these tests via a voice command. Currently the skill is still under development however, the voice command triggers the workflow run and the user receives the build details including the Postman report in the configured Slack channel. 

- The exported collection file and environment variables file which are needed to run the Postman tests are under the `tests` folder and are in `json` format. The `reportingTheme` folder has the custom `hbs` reporting template used to style the output test report. The report is produced at the end of the worflow run as an artifact.  
The tests are run via the CLI runner for Postman, called [Newman](https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/).

- For sending out the notifications to the Slack channel after the run [action-slack-notify](https://github.com/rtCamp/action-slack-notify) is used and added as a step in the workflow job.
