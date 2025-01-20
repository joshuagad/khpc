FROM	fedora:42

RUN	echo 'fastestmirror=true' >> /etc/dnf/dnf.conf

RUN	dnf install -y freeipa-client \
&&	dnf clean all

ADD	ipa-client-install.service /usr/lib/systemd/system/ipa-client-install.service

RUN	systemctl enable ipa-client-install

RUN	adduser slurm --system --no-create-home --home-dir /run/slurm --shell /sbin/nologin

CMD	/usr/lib/systemd/systemd --system
