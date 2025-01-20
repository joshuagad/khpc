FROM	fedora:42

RUN	echo 'fastestmirror=true' >> /etc/dnf/dnf.conf \
&&	dnf install -y slurm slurm-slurmctld slurm-slurmd slurm-slurmdbd slurm-sackd \
&&	dnf clean all

