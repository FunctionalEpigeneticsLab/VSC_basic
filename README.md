# Cheat Sheet

Get access to VSC. For full information: [https://vlaams-supercomputing-centrum-vscdocumentation.readthedocs-hosted.com/en/latest/index.html](https://vlaams-supercomputing-centrum-vscdocumentation.readthedocs-hosted.com/en/latest/index.html)

## Account
Manage account and groups through: [https://account.vscentrum.be/django/](https://account.vscentrum.be/django/)
```bash
#login to the VSC

#for genius
ssh vsc3XXXX@login.hpc.kuleuven.be
#or
ssh vsc3XXXX@login1-tier2.hpc.kuleuven.be
#or
ssh vsc3XXXX@login2-tier2.hpc.kuleuven.be
#genius login nodes for visualization:
ssh -X vsc3XXXX@login3-tier2.hpc.kuleuven.be
#or
ssh -X vsc3XXXX@login4-tier2.hpc.kuleuven.be
```

## The Module System
```bash
#give a list of available modules
module av
#load a module
module load modulename
module load modulename/moduleversion
#show a list of all loaded modules
module list
#unload a module
module unload modulename
#unload all modules at once
module purge
#show the help
module help
```
## PBS job submission

PBS script header:
```bash
#!/bin/bash -l
#PBS -l walltime=1:00:00
#PBS -l pmem=5gb
#PBS -l nodes=1:ppn=2
#PBS -M mail@mail.com
#PBS -m abe
#PBS -N jobname
#PBS -A lp_creditaccount
module load modulename modulename2
```
## Start Basic Jobs
```bash
#submit a job
qsub job.pbs
#show system jobs
showq
#show all requested
qstat
#show the estimated start for a job
showstart jobID
#check the status of a job
checkjob jobID