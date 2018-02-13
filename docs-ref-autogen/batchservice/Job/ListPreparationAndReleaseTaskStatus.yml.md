# `batch.core.windows.net.batchservice.job.listpreparationandreleasetaskstatus`

## `summary`
Lists the execution status of the Job Preparation and Job Release task for the specified job across the compute nodes where the job has run. This API returns the Job Preparation and Job Release task status on all compute nodes that have run the Job Preparation or Job Release task. This includes nodes which have since been removed from the pool. If this API is invoked on a job which has no Job Preparation or Job Release task, the Batch service returns HTTP status code 409 (Conflict) with an error code of JobPreparationTaskNotSpecified.


