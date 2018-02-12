# `batch.core.windows.net.batchservice.pool.listusagemetrics`

## `summary`
Lists the usage metrics, aggregated by pool across individual time intervals, for the specified account. If you do not specify a $filter clause including a poolId, the response includes all pools that existed in the account in the time range of the returned aggregation intervals. If you do not specify a $filter clause including a startTime or endTime these filters default to the start and end times of the last aggregation interval currently available; that is, only the last aggregation interval is returned.


