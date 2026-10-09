# Operations Runbook

## Market spread warning

1. Confirm the market-data provider is current and the order book is not crossed.
2. Compare bid and ask depth with the previous snapshot.
3. Reduce simulated order size and determine whether slippage normalizes.
4. If the condition persists, acknowledge the incident and notify the product owner.

## Execution slippage warning

1. Check whether the issue is isolated to buy or sell execution.
2. Review available depth and the assumed order notional.
3. Recommend smaller child orders or a temporary execution limit.
4. Document the decision and observed values in the incident record.

## Blockchain congestion warning

1. Confirm mempool count and recommended fees against a second public explorer.
2. Review withdrawal confirmation expectations and fee estimation.
3. Prepare a customer-support notice if delays are material.
4. Resolve only after the backlog returns below threshold for two collection cycles.

## Provider outage

1. Confirm internet access and provider status.
2. Do not treat missing data as a healthy state.
3. Retry with exponential backoff and preserve the error message.
4. Escalate to engineering if the provider fails for three consecutive cycles.

