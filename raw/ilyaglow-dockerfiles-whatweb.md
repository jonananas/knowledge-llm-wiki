# ilyaglow/dockerfiles: WhatWeb Dockerfile

Source URL: https://github.com/ilyaglow/dockerfiles/tree/master
Relevant path: https://github.com/ilyaglow/dockerfiles/tree/master/whatweb
Related Docker image: https://hub.docker.com/r/ilyaglow/whatweb
Captured: 2026-08-26

The `ilyaglow/dockerfiles` repository is a collection of Dockerfiles for tools used by the maintainer. The repository includes a `whatweb/` directory containing a Dockerfile for running WhatWeb in a container.

The related Docker Hub image is `ilyaglow/whatweb`, described as "WhatWeb dockerized". Docker Hub lists the image as updated over 5 years ago and gives this usage example:

```sh
docker run -it --rm ilyaglow/whatweb -v https://github.com
```

## Main Points

- The repository link supplied by the user contains a WhatWeb Dockerfile under `whatweb/`.
- Docker Hub publishes the corresponding image as `ilyaglow/whatweb`.
- The Docker Hub example passes normal WhatWeb CLI arguments after the image name, implying the image entrypoint is WhatWeb itself.
- Because Docker Hub reports the image as updated over 5 years ago, it should be treated as a convenience reference rather than assumed current security tooling.
- For outdated-software checks, the containerized equivalent of the existing WhatWeb note is:

```sh
docker run -it --rm ilyaglow/whatweb -v -a 3 yourdomain.com
```

Use this kind of scan only on domains and systems you own or have permission to assess.

## Notable Links

- Dockerfiles repository: https://github.com/ilyaglow/dockerfiles/tree/master
- WhatWeb Dockerfile directory: https://github.com/ilyaglow/dockerfiles/tree/master/whatweb
- Docker Hub image: https://hub.docker.com/r/ilyaglow/whatweb
- Upstream WhatWeb: https://github.com/urbanadventurer/WhatWeb
