Bootstrap: shub
From: CNC-UMCG/cnc_r

%environment
    export R_LIBS=$HOME/R
    mkdir $R_LIBS

%post

  # afni dependencies
  apt-get install -y tcsh libxp6 xfonts-base python-qt4 libmotif4 libmotif-dev motif-clients gsl-bin netpbm xvfb gnome-tweak-tool libjpeg62 xterm gedit evince

  apt-get update

  
  # install afni
  wget https://afni.nimh.nih.gov/pub/dist/tgz/linux_ubuntu_16_64.tgz
  tar xvzf linux_ubuntu_16_64.tgz -C /usr/share/
    
  mv /usr/share/linux_ubuntu /usr/share/afni
    
  echo "PATH=$PATH:/usr/share/afni" >> /etc/profile
  echo "export R_LIBS=$HOME/R" >> /etc/profile
 
  curl -O https://afni.nimh.nih.gov/pub/dist/src/scripts_src/@add_rcran_ubuntu.tcsh
  tcsh @add_rcran_ubuntu.tcsh

