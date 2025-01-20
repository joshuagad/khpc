FROM	joshuagad/hpc-base:2.0

RUN	dnf install -y slurm-slurmdbd \
&&	dnf clean all \
&&	sed -i s/User=slurm/User=root/ /usr/lib/systemd/system/slurmdbd.service \
&&	sed -i s/Group=slurm/Group=root/ /usr/lib/systemd/system/slurmdbd.service 

RUN	systemctl enable slurmdbd
