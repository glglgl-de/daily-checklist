# Purpose

Add a checklist on a daily basis, suitable for gitjournal.

# Initialization

* Create a clone of the gitjournal repo with `git clone (wherever) j`.
* Modify `checklist.service` to point to the right directory for `ExecStart=`.
* Put a `checklist.template` in place with your desired content.
* Install the units with `systemctl --user link ./checklist.{service,timer}`.
* Enable the timer with `systemctl --user enable --now checklist.timer`.

# Outcome

Every day at 0100, the gitjournal repo is pulled, supplied with today's daily checklist and pushed again.

This checklist then can be used for e. g. recording your medication etc.
