# Automater
A framework to create, run, and schedule python scripts.

## Directories
  - scripts (Holds all the scripts you would like to run)
  - static (only needed if you require static files)
  - logs (auto generated logs from scheduler)
  - output (output from scripts)

## Abstract Script class
Each script will inherit from this ABC class.
  - cron_schedule: cron_time = None  # Time representation of how often you would like to have the script run in the scheduler.
  - def setup()
  - def compute()  # The main computation for the script
  - def teardown()
  - def execute()  # Calls all the above functions; this is what's called in the scheduler.

## CLI tool
Run all scripts
`automater run all`

Run a specific script, ref by filename (w/o *.py* extension)
`automater run my_script`

Start scheduler
`automater scheduler`

List all scheduled tasks
`automater scheduler -ls`