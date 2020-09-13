FROM jgoerzen/dosemu
WORKDIR /root
RUN mkdir -p /usr/lib/dosemu/drive_z/pcs \
 && cd /usr/lib/dosemu/drive_z/pcs \
 && wget -nv https://misc.lassi.io/2020/pc-scheme/extracted/pcs303.zip \
 && unzip -q pcs303.zip \
 && rm pcs303.zip
RUN printf '$_layout = "us"\n' >>/etc/dosemu/dosemu.conf \
 && printf 'z:\ncd \\pcs\npcs\nexitemu\n' >>/etc/dosemu/freedos/autoexec.bat
CMD ["dosemu", "-t"]
