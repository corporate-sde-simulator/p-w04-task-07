# PR Review - Consensus log replication module (by Suresh)

## Reviewer: Vikram Patel
---

**Overall:** Good foundation but critical bugs need fixing before merge.

### `logReplicator.go`

> **Bug #1:** Majority quorum calculation uses total/2 instead of total/2+1 and accepts minority consensus
> This is the higher priority fix. Check the logic carefully and compare against the design doc.

### `consensusManager.go`

> **Bug #2:** Log entries are appended without checking if they conflict with existing entries at same index
> This is more subtle but will cause issues in production. Make sure to add a test case for this.

---

**Suresh**
> Acknowledged. I have documented the issues for whoever picks this up.
