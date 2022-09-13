# ELK_stack_on_docker

This project deploys ELK stack automatically
and represents as opensource SIEM solution.

Prerequesites:
  you will need to have virtualbox, vagrant installed on your system

Technologies:
  - vagrant (virtualisation management)
  - docker (containerization)
  - dcoker-compose 
  - Elasticsearch
  - Logstash
  - Kibana
  - Elastalert
  - SIGMA

#TODOs:
  - make two separate boxes (done)
  - make one box manage another via ansible_local
  - docker install via ansible (done)
  - deploy elk stack and configure via ansible
  - make new dockerimage or use existing elastalert image
  - *EXPERIMENTAL CI|CD pull SIGMA FROM REPO every 7days
    - auto deploy rules to elastalert
