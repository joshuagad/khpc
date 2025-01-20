FROM	joshuagad/hpc-base:2.0

RUN	dnf install -y slurm-slurmctld \
&&	dnf clean all \
&&	sed -i s/User=slurm/User=root/ /usr/lib/systemd/system/slurmctld.service \
&&	sed -i s/Group=slurm/Group=root/ /usr/lib/systemd/system/slurmctld.service

RUN	systemctl enable slurmctld
