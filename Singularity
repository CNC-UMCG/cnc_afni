Bootstrap: shub
From: CNC-UMCG/cnc_base

%post

  # afni dependencies
  apt-get install -y libmotif-common
  apt-get install -y motif
  
  # install afni
  wget https://afni.nimh.nih.gov/pub/dist/tgz/linux_ubuntu_16_64.tgz
  tar xvzf linux_ubuntu_16_64.tgz -C /usr/share/
    
  mv /usr/share/linux_ubuntu /usr/share/afni
    
