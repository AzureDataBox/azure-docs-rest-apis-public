# `batch.core.windows.net.batchservice.job.terminate`

## `summary`
Terminates the specified job, marking it as completed. When a Terminate Job request is received, the Batch service sets the job to the terminating state. The Batch service then terminates any active or running tasks associated with the job, and runs any required Job Release tasks. The job then moves into the completed state.


