**WARNING**:

Unmaintained. See [Run DBeaver outside Docker](#run-dbeaver-outside-docker).

If you find a way to use Docker, please let me know ☺️.

# Run DBeaver using Docker

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

# Run DBeaver outside Docker

1. Download the JDK and extract to, for example, `~/.local/jdk-X.X.X`
2. [Download DBeaver Community Edition](https://dbeaver.io/download/) and extract to, for example, `~/.local/dbeaver`
3. Export the ENV vars:

```shell
$ export JAVA_HOME=~/.local/jdk-X.X.X
$ export PATH=${PATH}:${JAVA_HOME}/bin
```

4. Start DBeaver: `~/.local/dbeaver/dbeaver`

## Shell script:

You need to go through steps (1) & (2) from previous section to be able to run this.

```bash
#!/bin/bash

set -xe

export JAVA_HOME=~/.local/jdk-X.X.X
export PATH=${PATH}:${JAVA_HOME}/bin
~/.local/dbeaver/dbeaver
```
