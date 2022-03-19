![Untitled_Artwork 5](https://user-images.githubusercontent.com/24437648/159130796-6966d033-863e-4e1b-8467-160637cce0a1.png)


# Automater
A framework to create, run, and schedule python scripts.

Automater is a light weight task scheduler that can be run on any computer. Only requirement is Python and Docker.

## Directories
  - scripts (Holds all the scripts you would like to run)
  - static (only needed if you require static files. This will be the cwd for all scripts during runtime. The outermost directory will automatically be added to the PYTHONPATH env var.)
  - logs (auto generated logs from scheduler)
  - output (output from scripts)

## Abstract Script class
Each script will inherit from this ABC class.
  - `cron_schedule: cron_time` = None  # Time representation of how often you would like to have the script run in the scheduler.
  - `def setup()`
  - `def compute()`  # The main computation for the script
  - `def teardown()`
  - `def execute()`  # Calls all the above functions; this is what's called in the scheduler.

## CLI tool
Run all scripts
`automater run all`

Run a specific script, ref by filename (w/o *.py* extension)
`automater run my_script`

Start scheduler
`automater scheduler`

List all scheduled tasks
`automater scheduler -ls`

Start GUI
`automater app start`

## Web App
  - Displays all scheduled tasks.
  - Displays logs, searchable.
  - Can start/stop scheduler and run specific scripts.
