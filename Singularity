Bootstrap: shub
From: CNC-UMCG/cnc_r

%environment
    export R_LIBS=$HOME/R
    mkdir $R_LIBS

%post

  # afni dependencies
  ## apt-get install -y libmotif4 libmotif-dev motif-clients gsl-bin netpbm xvfb gnome-tweak-tool libjpeg62 xterm gedit evince
  
  echo "deb http://security.ubuntu.com/ubuntu precise-security main" >> /etc/apt/sources.list
  apt-get update
  
  apt-get install -y libxp6 tcsh
  apt-get install -y python-qt4 r-base
  
  # install afni
  wget https://afni.nimh.nih.gov/pub/dist/tgz/linux_ubuntu_16_64.tgz
  tar xvzf linux_ubuntu_16_64.tgz -C /usr/share/
    
  mv /usr/share/linux_ubuntu_16_64 /usr/share/afni
    
  echo "PATH=$PATH:/usr/share/afni" >> /etc/profile
  echo "export R_LIBS=$HOME/R" >> /etc/profile
 
  curl -O https://afni.nimh.nih.gov/pub/dist/src/scripts_src/@add_rcran_ubuntu.tcsh
  tcsh @add_rcran_ubuntu.tcsh

  rPkgsInstall -pkgs ALL

  afni_system_check.py -check_all > out.afni_system_check.txt
