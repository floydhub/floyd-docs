To delete a dataset, click the **Delete dataset** button on the `Settings` tab
of the dataset on the web dashboard.

Example: `https://www.floydhub.com/alice/datasets/quick-start/settings`

![Dataset settings](../../img/dataset-settings.jpg)
![Delete dataset](../../img/delete-dataset.jpg)

!!! important
    Deleting a dataset will delete all its individual versions of data. This
    **cannot** be restored. Please be absolutely sure you want to delete a
    dataset before proceeding.

We recommend deleting individual data versions rather than the entire dataset.

## Deleting an uploaded datasource

You can delete a particular version of a Dataset by clicking on **Delete data**
button on the Settings tab of the data's page on the web dashboard.

Example: `https://www.floydhub.com/alice/datasets/quick-start/1/settings`

![Delete data](../../img/delete-data.jpg)

### Deleting an uploaded datasource from CLI

You can also delete an uploaded datasource from the CLI using the [floyd data
delete](../../commands/data#floyd-data-delete) command.

```bash
$ floyd data delete alice/datasets/quick-start/1

Delete Data: alice/quick-start/1? [y/N]: y
Data alice/datasets/quick-start/1: Deleted
```
