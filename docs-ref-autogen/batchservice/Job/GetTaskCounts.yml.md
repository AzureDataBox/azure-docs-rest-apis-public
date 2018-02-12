# `batch.core.windows.net.batchservice.job.gettaskcounts`

## `summary`
Gets the task counts for the specified job. Task counts provide a count of the tasks by active, running or completed task state, and a count of tasks which succeeded or failed. Tasks in the preparing state are counted as running. If the validationStatus is unvalidated, then the Batch service has not been able to check state counts against the task states as reported in the List Tasks API. The validationStatus may be unvalidated if the job contains more than 200,000 tasks.


