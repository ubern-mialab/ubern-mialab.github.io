---
layout: default
title: 'MIA Lab: Ubelix HPC'
---

<script>
  import Callout from '$lib/Callout.svelte';
</script>

# Ubelix HPC

The UBELIX (University of Bern Linux Cluster) is a HPC cluster of the University of Bern. During the MIA Lab course you can use UBELIX for computing your experiments. Beside this short guide, we recommend reading the [official documentation of UBELIX](https://hpc-unibe-ch.github.io/).

<Callout info>

The access to the UBELIX HPC is only granted to students officially enrolled at the University of Bern.

</Callout>

## Activation and installation

The general activation and installation procedure is independent of your operating system. If you need assistance, please consult your lecturer.

1. Request [UBELIX access](https://hpc-unibe-ch.github.io/getting-Started/account.html) with your student account.
2. Install an SSH client on your machine (see [here](/getting-started/tools/#ssh-clients)).
3. Install an SFTP client on your machine (see [here](/getting-started/tools/#ftp-clients)).
4. Wait until you get the confirmation from the UniBE IT Service department that your access request is approved.
5. After receiving the account activation confirmation, establish a VPN connection to the university network.
6. Login to UBELIX with your SSH client via `[campusaccount]@submit.unibe.ch` to validate that the account is working.
7. Configure your SFTP client for UBELIX:
   - File protocol: `SFTP`
   - Port: `22`
   - Host name: `submit.unibe.ch`
   - User name: `[campusaccount]`
   - Password: `[yoursecretpassword]`

Check the documentation of your SSH and SFTP client to enable autologin (e.g. [Putty autologin](https://superuser.com/a/44117)) or make configurations.

## Project handling

We expect you to work on your local machine and execute the experiments on UBELIX. To deploy your local code and its changes to UBELIX we recommend you to use GitHub. If you set up your MIALab fork correctly you can update the code on UBELIX by console without losing information.

It's crucial that you work on your own fork of the MIALab repository! You need to fork the MIALab repository before proceeding with the next steps.

Make sure that you do not add large-size files (>200kB, e.g. images, results) to your remote GitHub repository! Copy them manually from your local machine to UBELIX. For ignoring the appropriate folders / files, modify your `.gitignore` file.

## Clone your GitHub repository to UBELIX

This procedure needs to be performed once, in order to clone the remote repository to UBELIX as a local repository.

<Callout info>

Make sure that you do **not** clone the original [MIALab repository](https://github.com/ubern-mialab/mialab)! Your remote repository URL should have the following pattern: `https://github.com/[yourgithubaccount]/MIALab.git`.

</Callout>

1. Login via SSH to UBELIX (`[campusaccount]@submit.unibe.ch`).
2. Create a new directory for the MIALab: `mkdir MIALab`
3. Change to your new directory: `cd MIALab`
4. Clone your remote repository: `git clone https://github.com/[yourgithubaccount]/MIALab.git`
5. Login via SFTP to UBELIX.
6. Upload the images and additional large files (>200kB) manually to the correct directories on UBELIX.

## Update your local UBELIX repository from GitHub

This procedure needs to be performed when you want to update your code on UBELIX from GitHub.

Make sure that you commit and push your changes on your local machine to GitHub before updating the UBELIX repository.

1. Login via SSH to UBELIX (`[campusaccount]@submit.unibe.ch`).
2. Change to your MIALab base directory (e.g. `./MIALab`): `cd MIALab`
3. Update the local UBELIX repository from GitHub: `git pull origin master`

If you have multiple branches on GitHub, modify the update command appropriately.

## Set up your UBELIX Python environment

This procedure needs to be performed once before the first computation on UBELIX, and after the cloning of your MIALab fork onto UBELIX. For detailed information we refer to the [official UBELIX Python documentation](https://hpc-unibe-ch.github.io/software/python.html).

If you prefer an automatic generation of your Python environment, you can download and run [`create_ubelix_env.sh`](/files/create_ubelix_env.sh) with `bash scripts/create_ubelix_env.sh` on UBELIX, and skip the following steps.

1. Login via SSH to UBELIX (`[campusaccount]@submit.unibe.ch`).
2. Load the Python module: `module load Anaconda3`
3. Prepare the environment for Python: `eval "$(conda shell.bash hook)"`
   - This command needs to be executed after each `module load Anaconda3`.
   - Do **not** run `conda init`, because it hardcodes environment variables and you need to rework the `.bashrc` file.
4. Create a new Python 3.8 environment with the name mialab (confirm with `y` when prompted during creation): `conda create -n mialab python=3.8`
5. Activate your new environment: `conda activate mialab`
6. Change to your MIALab base directory (e.g. `./MIALab`): `cd MIALab`
7. Install the dependencies of MIALab: `pip install -r requirements.txt`

If you require additional Python packages later in your project, you can add them to your `requirements.txt` file and re-execute the steps 2-3 and 5-7 in the previous procedure.

## Transfer large-size data from UBELIX to your local machine

This procedure is typically used after an experiment is finished and when you need to analyze the results locally on your machine.

1. Login via SFTP to UBELIX.
2. Navigate to the appropriate directory.
3. Copy the files to your local machine by drag-and-drop.

## Computation job handling

The UBELIX contains a job scheduler (SLURM) to assign computational resources to jobs and to handle priorities. The job scheduler is responsible that the necessary resources are available during the execution of the jobs and that no aborts are generated due to unavailable resources.

All normally privileged users on UBELIX have exclusively access to the submission node (`submit.unibe.ch`), where they submit their computational jobs via a job script. Writing a job script can be challenging at the beginning of your HPC life. Therefore, we prepared a template job script for you below. If you need any further assistance, consult the [official UBELIX documentation](https://hpc-unibe-ch.github.io/slurm/submission.html) or ask a lecturer.

### Writing a job script

The job script specifies the resources you require for your computation. Because the experiments you will do in this course require more or less similar resources, we prepared a template job script for you: [`template_jobscript.sh`](/files/template_jobscript.sh).

**SLURM settings**

```
#SBATCH --job-name="GIVE_IT_A_NAME"
#SBATCH --time=24:00:00
#SBATCH --mem-per-cpu=128G
#SBATCH --partition=epyc2
#SBATCH --qos=job_epyc2
#SBATCH --mail-user=your.name@students.unibe.ch
#SBATCH --mail-type=ALL
#SBATCH --output=%x_%j.out
#SBATCH --error=%x_%j.err
```

**Load Anaconda3**

```
module load Anaconda3
eval "$(conda shell.bash hook)"
```

**Load your environment**

```
conda activate mialab
```

**Run your code**

```
srun python3 main_example_file.py
```

<Callout info>

Do **not** use the GPU partition if you do not use specific libraries with GPU support! Your code does not magically speed up when running on a GPU partition. Furthermore, MIALab as it is does not make use of GPUs!

</Callout>

### Submitting and controlling a job

The following procedure needs to be performed whenever you want to submit a computation job.

1. Write a job script or modify an existing one.
2. Copy the job script to the correct location using the SFTP client.
3. Submit the computation job by `sbatch [yourjobscriptname].sh`

Be aware of the paths inside the job script! Use relative paths from the location of the job script.

### Additional useful commands

- Monitor your jobs via `squeue --me`
- Cancel a job via `scancel [yourjobid]`

Cancel jobs which contain errors, such that other users can use the allocated resources.
