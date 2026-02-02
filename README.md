# Purpose

Add a checklist on a daily basis, suitable for gitjournal.

# Initialization

* Install jq
* Modify `checklist.service` to point to the right directory for `ExecStart=`.
* Put a `checklist.template` in place with your desired content.
* Put a `checklist.json` in place with your needed config: `{"URL":"<url repo>","branch":"<branch>"}'`
* Install the units with `systemctl --user link ./checklist.{service,timer}`.
* Enable the timer with `systemctl --user enable --now checklist.timer`.

# Outcome

Every day at 0100, the gitjournal repo is pulled, supplied with today's daily checklist and pushed again.

This checklist then can be used for e. g. recording your medication etc.
