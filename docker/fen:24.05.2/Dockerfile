FROM	fedora:42

RUN	echo 'fastestmirror=true' >> /etc/dnf/dnf.conf \
&&	dnf install -y bzip2 htop tree unzip xz sssd-common tmux screen vim nano procps-ng findutils bash-completion rsync openssh-clients ftp iputils less git wget squashfs-tools \
&&	dnf clean all

RUN	echo 'fastestmirror=true' >> /etc/dnf/dnf.conf \
&&	dnf install -y singularity-ce \
&&	dnf clean all

RUN	echo 'fastestmirror=true' >> /etc/dnf/dnf.conf \
&&	dnf install -y slurm slurm-contribs slurm-sackd openssh-server openssh-ldap-authkeys nss-pam-ldapd \
&&	dnf clean all

RUN	systemctl enable sshd

COPY	sackd.service /usr/lib/systemd/system/sackd.service
RUN	systemctl enable sackd

RUN	dnf install -y sssd sssd-ldap \
&&	dnf clean all

RUN	systemctl enable sssd

#RUN	dnf install -y freeipa-client \
#&&	dnf clean all

#COPY	ipa-client-install.service /usr/lib/systemd/system/ipa-client-install.service
#RUN	systemctl enable ipa-client-install

CMD	/usr/lib/systemd/systemd --system
