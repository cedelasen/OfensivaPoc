FROM ubuntu:18.04

RUN apt update -y
RUN apt install python3-pip python3-venv iputils-ping git ruby-full -y

RUN python3 -m pip install virtualenv

RUN gem install winrm winrm-fs stringio

WORKDIR /root

RUN git clone https://github.com/SecuraBV/CVE-2020-1472.git SecuraBV && \
    git clone https://github.com/dirkjanm/CVE-2020-1472.git dirkjanm && \
    git clone https://github.com/bb00/zer0dump.git zer0dump && \
    git clone https://github.com/Hackplayers/evil-winrm.git evil-winrm

RUN chmod +x ./*/*.py

ENV VIRTUAL_ENV=/opt/venv
RUN python3 -m venv $VIRTUAL_ENV
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

COPY requirements.txt .
RUN pip3 install -r requirements.txt

ENTRYPOINT  ["/bin/bash"]
