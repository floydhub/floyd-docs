You can delete an individual job by clicking on **Delete job** button on the Settings tab of the job's page on the web dashboard.

Example: `https://www.floydhub.com/mckay/projects/quick-start/1/settings`

![Delete job](../../img/delete-job.jpg)

### Deleting a job using the CLI

You can also delete a job from the CLI using the [floyd delete](../../commands/delete) command.

```bash
$ floyd delete mckay/projects/quick-start/1

Delete Run: mckay/quick-start/1? [y/N]: y
Job mckay/quick-start/1 Deleted
```

Floyd CLI is fairly smart at resolving job names. It defaults to using your
username, the project initialized in the directory you're working in, and the
latest job number. So if you don't pass a job name to `floyd delete`, it will
delete your most recent job. Here are a couple examples of shortened job names
that are valid:

```
# Deletes the most recent job for your user's project called 'foo'
$ floyd delete foo
```

```
# Deletes job 2 for your user's project called 'foo'
$ floyd delete foo/2
```

The same job-name shortcuts available for `floyd delete` are available whenever
you need to specify a job name, including with `floyd status <job_name>`.

For more information on using shortened names, see
[this article](../guides/shortnames)

### Deleting output of a Job

It is not possible to delete just the output of a job. You will have to delete the job itself.
