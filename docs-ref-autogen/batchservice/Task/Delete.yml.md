# `batch.core.windows.net.batchservice.task.delete`

## `summary`
Deletes a task from the specified job. When a task is deleted, all of the files in its directory on the compute node where it ran are also deleted (regardless of the retention time). For multi-instance tasks, the delete task operation applies synchronously to the primary task; subtasks and their files are then deleted asynchronously in the background.


