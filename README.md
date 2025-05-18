# trajectory_test1

In this Repository we are using One Recent Trajectory analysis software StaVia (Via 2.0) or pyVia Installation and Usage :

## Installation : 

In order to run Pyvia software (which is very difficult) both in Linux and Mac , we have to follow below steps carefully .
- I have tried and Installed both in Mac (Personal laptop ) and in Linux (Either in workstation or in Gitpod or in any cloud environment). 

- Here I am giving Gitpod platoform example : 

** Step - 1 :  Create Github  account and  and repository with any name (Here it is 1rajecroy_test1 )
** Step - 2 :  Connect this repository w+inside Gitpod (which opens vscode interface)
** Step - 3 :  We create miniconda_install.sh and pyvia_env.yml (to create conda environment and pyvia installation) . Copy the content and paste in your required files 
** Step - 4 :  Open Terminal in vscode (from Gitpod) and Run bash miniconda_install.sh . This will install miniconda inside virtual machine.
** Step - 5 :  Open new bash Terminal (very important) , so conda will be accesible .
** Step - 6 :  Run conda create -s pyvia_env.yml to install all pyvia and dependency packages .
** Step - 7 : create trajectory_analysis_test.ipynb and click select kernel and Python environments and then select installed conda environment (here in my case ViaEnv2 ) which is present in my pyvia_env.yml name .

## Working Example :
Run the basic analysis steps with basic example

** Step - 1 : Load the libaries 


1. Basic workflow
This vignette shows the basic workflow of Via and how to access the different visualizations after running the computations. The dataset is a toy multifurcation. We start by importing modules.

from pyVIA.core import *
import pyVIA.datasets_via as datasets_via
import pandas as pd 
import scanpy as sc
 
import warnings 
warnings.filterwarnings('ignore') 
First load all the data.

adata_counts = datasets_via.toy_multifurcating()
print(adata_counts)
true_label = adata_counts.obs['group_id'].tolist()
ncomps = 30
sc.tl.pca(adata_counts, svd_solver='arpack', n_comps=ncomps)




