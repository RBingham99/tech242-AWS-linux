# Gitlab architecture
Gitlab architecture is similar to jenkins in that it has a main server (master node) that creates runner nodes (worker nodes) that actually run the jobs.

# Runners 
When the runner node finishes a job it:
- Saves and uploads any artifacts you have specified to the main server so it can pass it on to future jobs.
- Saves the logs so we can look through them later.
- Deletes the job to free up space.

By default your project will run on "shared runners" (runner nodes shared by everyone using Gitlab), however you can specify your own runners if:
- Your jobs use a lot of resources (CPU for example) so the shared nodes are to small/slow.
- Your runner needs some special characteristics for the jobs you are running.
- You want to seperate your jobs, for example you may have 1 runner that just runs a specific job freeing up the others to run other jobs.