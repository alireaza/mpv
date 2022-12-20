# MPV

## Build
Via GitHub repository
```bash
$ docker build --tag alireaza/mpv:$(date -u +%Y%m%d) --tag alireaza/mpv:latest https://github.com/alireaza/mpv.git
```

## Run
```bash
$ docker run \
--interactive \
--tty \
--rm \
--mount="type=bind,source=/tmp/.X11-unix,target=/tmp/.X11-unix" \
--env="DISPLAY=$DISPLAY" \
--device="/dev/dri:/dev/dri" \
--env="PULSE_SERVER=unix:${XDG_RUNTIME_DIR}/pulse/native" \
--mount="type=bind,source=${XDG_RUNTIME_DIR}/pulse/native,target=${XDG_RUNTIME_DIR}/pulse/native" \
--mount="type=bind,source=$(pwd)/udocker,target=/home/udocker" \
--name="mpv" \
alireaza/mpv \
"<File/Link>"
```

