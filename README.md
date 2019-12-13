# vacation-trigger

This is the code accompanying the blogpost at TODO.

## Running the example

```sh
# Clone the repository
git clone https://github.com/cocreature/vacation-trigger.git
# Switch to the directory
cd vacation-trigger
# Build the example and run sandbox and navigator
daml start
# Open another terminal in the repository and run the trigger
daml trigger --dar .daml/dist/vacation-trigger-0.0.1.dar --trigger-name Trigger:autoApproveTrigger --ledger-host localhost --ledger-port 6865 --ledger-party Alice
```

You can now login as `Bob` in Navigator and request a vacation using
the `RequestVacation` choice on the `EmployeeVacationAllocation`
contract. If you switch back to the `Contracts` view afterwards, you
should see a `Vacation` contract which was created as a result of the
trigger exercising the `AcceptRequest` choice on the
`VacationRequest`.
