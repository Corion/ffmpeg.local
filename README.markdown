Follow

https://docs.nvidia.com/video-technologies/video-codec-sdk/ffmpeg-with-nvidia-gpu/

# Clone headers
    git clone https://git.videolan.org/git/ffmpeg/nv-codec-headers.git
    cd nv-codec-headers && sudo make install && cd -

# Install all Debian source prerequisites for ffmpeg

    apt build-dep ffmpeg
    # These may not be needed anymore
    # apt install libnuma1 libnuma-dev nasm frei0r-plugins-dev libchromaprint-dev libavresample-dev libgnutls28-dev ladspa-sdk-dev libaom-dev liblilv-dev libavc1394-dev libiec61883-dev libass-dev libbluray-dev libbs2b-dev libcaca-dev libcodec2-dev libdav1d-dev libdc1394-22-dev libdrm-dev flite1-dev

# Get current ffmpeg config for comparison with the shell script:
    ffmpeg 2>&1 |grep configuration:

    # --prefix=/usr --extra-version=0+deb11u1 --toolchain=hardened --libdir=/usr/lib/x86_64-linux-gnu --incdir=/usr/include/x86_64-linux-gnu --arch=amd64 --enable-gpl --disable-stripping --enable-avresample --disable-filter=resample --enable-gnutls --enable-ladspa --enable-libaom --enable-libass --enable-libbluray --enable-libbs2b --enable-libcaca --enable-libcdio --enable-libcodec2 --enable-libdav1d --enable-libflite --enable-libfontconfig --enable-libfreetype --enable-libfribidi --enable-libgme --enable-libgsm --enable-libjack --enable-libmp3lame --enable-libmysofa --enable-libopenjpeg --enable-libopenmpt --enable-libopus --enable-libpulse --enable-librabbitmq --enable-librsvg --enable-librubberband --enable-libshine --enable-libsnappy --enable-libsoxr --enable-libspeex --enable-libsrt --enable-libssh --enable-libtheora --enable-libtwolame --enable-libvidstab --enable-libvorbis --enable-libvpx --enable-libwavpack --enable-libwebp --enable-libx265 --enable-libxml2 --enable-libxvid --enable-libzmq --enable-libzvbi --enable-lv2 --enable-omx --enable-openal --enable-opencl --enable-opengl --enable-sdl2 --enable-pocketsphinx --enable-libmfx --enable-libdc1394 --enable-libdrm --enable-libiec61883 --enable-chromaprint --enable-frei0r --enable-libx264 --enable-shared

# Build ffmpeg and install locally

    git clone https://git.ffmpeg.org/ffmpeg.git ffmpeg/
    ./ffmpeg.configure

