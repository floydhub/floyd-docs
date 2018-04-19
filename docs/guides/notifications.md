![](../img/slack_notifications/FloydHubSlack.png)

You can setup Slack notifications to receive alerts on your FloydHub jobs.  You will receive a notification when:

* Job completes successfully
* Idle Jupyter job is shutdown automatically
* Job is manually shutdown
* Job failed, i.e. error in code, timeout, or insufficient powerup credits


## Steps to create an incoming webhook in your Slack

1. Create an incoming webhook in your Slack app [here](https://slack.com/apps/A0F7XDUAZ-incoming-webhooks).
1. Click **Add Configuration**.
![Add Configuration](../img/slack_notifications/AddConfiguration.jpg)
1. Select the channel that you want to post the notifications. Click **Add Incoming Webhooks integration**.
![Select Channel](../img/slack_notifications/SelectChannel.png)
1. Scroll down to **Integration Settings**. Copy the **Webhook URL** (don't worry about the other settings, we'll handle it).
![Copy Webhook URL](../img/slack_notifications/WebhookURL.png)
1. Make sure to click on **Save Settings**.
1. In Floydhub, go to [Notifications settings](https://www.floydhub.com/settings/notifications), paste in the Slack webhook url, and click **Save**.
![Notification Settings](../img/slack_notifications/NotificationSettings.png)
1. Click **Test** to receive your first Slack notification! Going forward, you should receive notifications for all jobs you run on FloydHub.
![Slack Notification](../img/slack_notifications/notification.png)

For more information on configuring webhooks in Slack, please see Slack's
[help page](https://get.slack.help/hc/en-us/articles/115005265063-Incoming-WebHooks-for-Slack).
