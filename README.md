# reproducibilityTutorial
Practice/Test FOSS
    1  cd /scratch/
    2  ls
    3  git clone https://github.com/j-p-courneya/reproducibilityTutorial.git
    4  git status
    5  ls
    6  df -h
    7  clear
    8  ls
    9  wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
   10  clear
   11  bash Miniconda3-latest-Linux-x86_64.sh -b -p /opt/conda
   12  ln -s /opt/conda/pkgs/*/bin/* /bin
   13  ln -s /opt/conda/pkgs/*/lib/* /usr/lib
   14  clear
   15  /opt/conda/bin/conda install -c conda-forge -y jupyterlab=1.2.3
   16  /opt/conda/bin/conda install -c conda-forge -y nodejs=10.13.0
   17  /opt/conda/bin/pip install bash_kernel
   18  /opt/conda/bin/pip install ipykernel
   19  clear
   20  /opt/conda/bin/python3 -m bash_kernel.install
   21  clear
   22  conda search <PACKAGE NAME>
   23  conda search jupyterlab
   24  conda search <jupyterlab>
   25  /opt/conda/bin/jupyter lab --no-browser --allow-root --ip=0.0.0.0 --NotebookApp.token='' --NotebookApp.password='' --notebook-dir='/scratch/reproducibility-tutorial/'
   26  clear
   27  /opt/conda/bin/conda search -c bioconda STAR
   28  /opt/conda/bin/jupyter lab --no-browser --allow-root --ip=0.0.0.0 --NotebookApp.token='' --NotebookApp.password='' --notebook-dir='/scratch/reproducibilityTutorial/'
   29  clear
   30  /opt/conda/bin/conda search -c bioconda snakemake
   31  /opt/conda/bin/conda install -c bioconda -c conda-forge -y snakemake=5.8.1
   32  clear
   33  ln -s /opt/conda/bin/* /bin
   34  ln -s /opt/conda/lib/* /usr/lib
   35  snakemake --version
   36  sudo apt-get update
   37  sudo apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common
   38  clear
   39  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   40  sudo add-apt-repository  "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
 $(lsb_release -cs) \
 stable"
   41  sudo apt-get update
   42  clear
   43  sudo apt-get install -y docker-ce docker-ce-cli containerd.io
   44  clear
   45  docker run hello-world
   46  clear
   47  cd /scratch/reproducibilityTutorial/
   48  ls
   49  history >>README.md 
   # reproducibility-tutorial

## Computer Setup

    #download the Miniconda installer
    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

    # instal miniconda silently (-b) in path (-p) /opt/conda
    bash Miniconda3-latest-Linux-x86_64.sh -b -p /opt/conda

    #make sure all conda packages will be in path by symbolic links to /bin
    ln -s /opt/conda/pkgs/*/bin/* /bin
    ln -s /opt/conda/bin/* /bin
    ln -s /opt/conda/pkgs/*/lib/* /usr/lib

    # Install Jupyter lab version 1.2.3
    /opt/conda/bin/conda install -c conda-forge -y jupyterlab=1.2.3
    /opt/conda/bin/conda install -c conda-forge -y nodejs=10.13.0

    python3 -m pip install bash_kernel
    pip install ipykernel
    python3 -m bash_kernel.install

    #Test Jupyterlab
    jupyter lab --no-browser --allow-root --ip=0.0.0.0 --NotebookApp.token='' --NotebookApp.password='' --notebook-dir='/scratch/reproducibilityTutorial/'

    #Install Snakemake
    /opt/conda/bin/conda install -c bioconda -c conda-forge -y snakemake=5.8.1

    #install Docker
    # update ubuntu apt-get package manager
    sudo apt-get update

    # install some needed packages
    sudo apt-get install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

    # add the Docker key
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

    #add the repository
    sudo add-apt-repository \
     "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) \
     stable"

    # update apt-get with new repository information
    sudo apt-get update

    # install docker
    sudo apt-get install -y docker-ce docker-ce-cli containerd.io

    #test docker
    docker run hello-world
