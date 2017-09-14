You can delete an individual job by clicking on **Delete job** button on the Settings tab of the job's page on the web dashboard.

Example: `https://www.floydhub.com/alice/projects/quick-start/1/settings`

![Delete job](../../img/delete-job.jpg)

### Deleting a job using the CLI

You can also delete a job from the CLI using the [floyd delete](../../commands/delete) command.

```bash
$ floyd delete alice/projects/quick-start/1

Delete Run: alice/quick-start/1? [y/N]: y
Job BD4JMXSgCi2r2afbq3n3Vo: Deleted
```
### Deleting output of a Job

It is not possible to delete just the output of a job. You will have to delete the job itself.
