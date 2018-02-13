# `batch.core.windows.net.batchservice.jobschedule.delete`

## `summary`
Deletes a job schedule from the specified account. When you delete a job schedule, this also deletes all jobs and tasks under that schedule. When tasks are deleted, all the files in their working directories on the compute nodes are also deleted (the retention period is ignored). The job schedule statistics are no longer accessible once the job schedule is deleted, though they are still counted towards account lifetime statistics.


