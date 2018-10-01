FROM python:3.6

RUN echo "deb http://deb.debian.org/debian buster main" >> /etc/apt/sources.list && \
    echo "deb http://security.debian.org/debian-security buster/updates main" >> /etc/apt/sources.list && \
    echo "deb http://deb.debian.org/debian buster-updates main" >> /etc/apt/sources.list && \
    echo "deb-src http://deb.debian.org/debian buster main" >> /etc/apt/sources.list && \
    echo "deb-src http://security.debian.org/debian-security buster/updates main" >> /etc/apt/sources.list && \
    echo "deb-src http://deb.debian.org/debian buster-updates main" >> /etc/apt/sources.list && \
    apt-get update && \
    apt-get build-dep -y blender && \
    apt-get install -y python3-all python3-all-dev libpython3-all-dev && \
    \
    git clone http://git.blender.org/blender.git /opt/blender && \
    cd /opt/blender && \
    git submodule init && \
    git submodule update && \
    \
    WITH_PYTHON_INSTALL=OFF WITH_PLAYER=OFF WITH_PYTHON_MODULE=ON make bpy && \
    cp /usr/local/PYTHON_SITE_PACKAGES-NOTFOUND/bpy.so /usr/local/lib/python3.6/site-packages && \
    cp -R /usr/local/PYTHON_SITE_PACKAGES-NOTFOUND/2.79 /usr/local/lib/python3.6/site-packages && \
    \
    cd / && \
    rm -rf /opt/blender
