The **cron** service allows us to schedule commands to run at regular intervals like:
* Every 30 minutes
* Every day at midnight
* Every 1st of the month
* Every March 31th

### Editing the crontab

To set up a cron job, we need to edit the crontab configurations file. Rather than the edit files directly, it's best to use the **crontab -e** command.

```bash
crontab -e
```