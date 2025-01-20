FROM	joshuagad/hpc-base:2.0

RUN	dnf install -y slurm-slurmd singularity-ce htop \
&&	dnf clean all

RUN	systemctl enable slurmd
