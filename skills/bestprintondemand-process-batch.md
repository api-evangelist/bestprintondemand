---
name: bestprintondemand-process-batch
description: Upload a file, start its processing, monitor the job, and retrieve the result.
api: openapi/bestprintondemand-openapi.json
operations:
- createBatch
- startBatch
- getBatch
- downloadBatchResult
generated: '2026-10-06'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/bestprintondemand-openapi.json ; every operationId checked against the contract
---

# bestprintondemand-process-batch

Upload a file, start its processing, monitor the job, and retrieve the result.

## Steps

1. 1. `createBatch` – send the file in the request body; include the `X-Api-Key` header for authentication.
2. 2. `startBatch` – POST to start the uploaded job (if it was created with `start=false`).
3. 3. `getBatch` – poll this endpoint to check the job status until it is completed.
4. 4. `downloadBatchResult` – GET the result file once the job status is completed.

## Rules

- Authentication: provide the API key in the `X-Api-Key` header or use a Bearer token.
- Idempotency: not defined for these endpoints; callers should avoid duplicate requests.
