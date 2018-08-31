A [Project]() is a collection of the jobs you run along with their logs and
results. If you have used GitHub, projects in FloydHub are a lot like code
repositories.

To create a new Project, visit [www.floydhub.com/projects](https://www.floydhub.com/projects) and click on the "New Project" button on the top right hand corner.

![Create new project](../../img/create_new_project.jpg)

Give the project a name and an apt description.

The `Visibility` field indicates who can see your project. If you set it to `Public`, anyone can see your project, your code and data. If you are working on an open source project, this is a great way to share and contribute to the FloydHub community. If your code or data is proprietary, please select `Private`. This will ensure that only you and your team will have access to this project.

Once you have created a Project, you can start running jobs using the [floyd run](../../commands/run) command.

```bash
$ floyd init quick-start
Project "quick-start" initialized in the current directory

$ floyd run --gpu --env tensorflow
Syncing code ...
```

### Adding a Project README

Each project on FloydHub can display a README. Click the 'Edit' button the Project overview page to edit your project's README file. Markdown syntax is supported (and encouraged!)

![Project Readme](../../img/readmegif.gif)

### Video Tutorial
#### Organizing your jobs with FloydHub Projects

<iframe width="560" height="315" src="https://www.youtube.com/embed/NTGIQ2iU_tc?rel=0" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>
