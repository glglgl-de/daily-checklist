# Purpose

Add a checklist on a daily basis, suitable for gitjournal.

# Initialization

* Install jq
* Modify `checklist.service` to point to the right directory for `ExecStart=`.
* Modify `checklist.service` to contain a line for the config:
  `Environment=checklist_config=<base64>`
  where the base64 string is created with `base64 -w1000 <<<'{"URL":"<url repo>","branch":"<branch>"}'`
  * TODO: change that, we can also have a cfg file in the directory, that's easier
* Put a `checklist.template` in place with your desired content.
* Install the units with `systemctl --user link ./checklist.{service,timer}`.
* Enable the timer with `systemctl --user enable --now checklist.timer`.

# Outcome

Every day at 0100, the gitjournal repo is pulled, supplied with today's daily checklist and pushed again.

This checklist then can be used for e. g. recording your medication etc.
