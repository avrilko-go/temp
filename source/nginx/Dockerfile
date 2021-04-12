FROM nginx
RUN useradd --create-home --no-log-init --shell /bin/bash avrilko && adduser avrilko sudo && echo 'avrilko:123456' | chpasswd && echo 'root:123456' | chpasswd
