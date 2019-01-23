# Release lock

This step releases a lock on a specified string value.

**Tip:** Applications, components, and generic processes share some process steps. This step applies to application processes, component processes, and generic processes. This step applies to application processes that are associated with application templates.

To create a lock, use the [Acquire lock](app_processsteps_lock_acquire.md) step. If multiple processes are waiting for the same lock, when the lock is released, the server selects the process that made the earliest request to acquire the lock.

|Field|Description|
|-----|-----------|
|**Lock Name**|A string value that identifies the lock.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

