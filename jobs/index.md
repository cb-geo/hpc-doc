# Job submission
SLURM is an open source workload management and job scheduling system. 
Once an application is ready to run (e.g., compiled and tested on a login node), it can be submitted to the computational nodes. There are three steps to submit a job.

> **Warning** Never run any computationally intensive or long-duration applications on login nodes, use computational nodes instead. Only use login nodes to compile, run small test-cases and visualise results.


## Step 1. Find and copy the template SLURM submission script
On Darwin, we use a submission script to instruct the HPC to run the jobs. This script tells which programme is going to run, how many computational nodes it is going to occupy, which project should be charged and so on. When logged in to Darwin, use command ls ~/ to show contents under your home directory. There should be a template SLURM submission script named slurm_submit.sandybridge. This is read only, so we need to copy it to a text file using cp slurm_submit.sandybridge your_working_directory/slurm_submit.txt. You can edit the .txt file to generate your own submission script, while the template is still there for future use. It is preferable to have the submission script in the same working directory as the application.

## Step 2. Modify parameters in the submission script
Open the copied submission script using a Unix text editor, e.g., nano: `nano slurm_submit.txt`. The items need to be changed in the script include:

	#SBATCH -J Your_job_name, e.g. #BATCH -J Darwin_job;
	#SBATCH -A Your_subject_name, e.g. #SBATCH -A SOGA-SL2-CRSid;
	#SBATCH --nodes=number_of_nodes_to_use, e.g. #SBATCH --nodes=1;
	#SBATCH --tasks=number_of_threads (< nodes×16), e.g. #SBATCH --threads=16;
	#SBATCH --time=esitmiate_time_of_running, e.g. #SBATCH --time=02:00:00; (2 hours)
	#SBATCH --mail-type=email_notifications, e.g. #SBATCH --mail-type=ALL;
	CMD=``executable”, e.g. CMD=``./fem”.

Then exit the text editor by pressing Ctrl+X if you are using nano. Say yes to save the submission script with a proper name.

## Step 3. Use sbatch command to submit a job

Now we can submit the job to a computational node. The command to do this is `sbatch submission_script_name`. You will receive an email when the job starts to run or finishes. Here are some useful commands you might need at this stage:

`squeue`: This command offers similar functions as showq, but has more options. To monitor the statues of the jobs you have submitted, use `squeue -u CRSid` or use `showq -u` to monitor status of the jobs. 

`scancel <jobid>`: This command can cancel a job that is running or still queuing. Users can use squeue -u CRSid to check their job ID.

`mybalance`: This command tells the remaining core hours of the user.
For more information on job submission, please refer to [http://www.hpc.cam.ac.uk/using-clusters/running-jobs](http://www.hpc.cam.ac.uk/using-clusters/running-jobs).


# Job submission scripts
* [Abaqus](./abaqus)
* [COMSOL](./comsol)
* [Darwin CPU](./darwin)
* [LEM](./lem)
* [Tesla GPU](./tesla)

