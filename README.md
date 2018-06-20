# Run DBeaver using docker

Run:

```terminal
$ docker run --rm \
  -e DISPLAY=unix$DISPLAY \
  -e GDK_DPI_SCALE \
  -e GDK_SCALE \
  -v /etc/localtime:/etc/localtime:ro \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  --net host \
  dmitryrck/dbeaver dbeaver
```

If you want to save your configs add `-v dbeaver_home:/root` to the list.
