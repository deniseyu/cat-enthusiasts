This is a checklist to help make sure that your new consumer chain PR looks correct! Hypha will doublecheck these properties before merging your PR.

Feel free to delete these comments after opening your PR.

- [ ] `chain_id` matches between:
  - `README`
  - genesis file
  - consumer addition proposal
  - bash script
- [ ] `shasum -a 256 <binary>` matches the checksum in the proposal
- [ ] `shasum -a 256 <binary>` matches `README`
- In the genesis file,
  - [ ] genesis time matches spawn time in consumer addition proposal
  - [ ] includes funded accounts for relayer operations
  - [ ] bank balance denom matches denom in `README`
  - [ ] slashing params must not result in more than 12 hours leeway for downtime
  - [ ] `shasum -a 256 <genesis file without CCV>` matches the checksum in the proposal
  - [ ] `shasum -a 256 <genesis file without CCV>` matches the checksum in the `README`
- Within the consumer addition proposal,
  - [ ] spawn time must match genesis time
  - [ ] spawn time must be later than voting period
  - [ ] `revision_height: 1`
  - [ ] `revision_number: 1` (only if the `chain_id` ends in `-1`)
  - [ ] `transfer_timeout_period` must be less than `block_time` * `blocks_per_distribution_transmission`
  - [ ] `ccv_timeout_period: 2419200000000000` (given current provider params)
  - [ ] `unbonding_period: 1728000000000000` (given current provider params)
- Node configurations
  - [ ] `minimum_gas_prices`
  - [ ] Check with Hypha about any other chain-specific params
- Endpoints
  - [ ] Seeds OR persistent peers
  - [ ] State sync nodes (if any)
- Bash script
  - [ ] version built in script must match `README`
  - [ ] seeds or persistent peers must match `README`
- README
  - Contains instructions on how to join and installation steps 
