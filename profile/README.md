<div align="center">

### Build Docker images fast, in the cloud.

[Turbocharge the `docker build`](https://depot.dev)

</div>

---

Depot provides cloud-hosted Docker builder machines - our builders are quick, running on native hardware. Docker caching is fully managed with no extra configuration. ⚡

## What

1. Our [`depot` CLI](https://github.com/depot/cli) supports the same CLI options as Docker Buildx:

   ```diff
   - docker buildx build -t repo/image:tag .
   + depot build -t repo/image:tag .
   ```

2. We launch a cloud builder instance with 4 CPUs, 8GB of RAM, and a persistent 50GB Docker cache, all automatically configured for your project. The builder starts in just a few seconds and already has your previous build cache ready to use.

3. Your Docker image is built remotely and the result is downloaded to your local machine.

## Why

- **For your local machine:** Docker builds won't slow down your laptop, use up your machine memory, or clog your network connection. By running the build in the cloud, it will have access to a fast low-latency network connection to download base images and build dependencies. And you won't need to pull gigabytes of unnecessary files into your local disk for cache.
- **For CI:** we fully manage a persistent Docker cache for each project builder, so no more waiting minutes for the GitHub `actions/cache` to load and save tarballs for each build. Builds also have access to more resources than GitHub Actions, with 4 CPUs to speed up and parallelize `RUN` steps, and 50GB of total Docker cache per project instead of 10GB.

## Private Beta

We're currently in private beta, but if you're interested in early access, please email [contact@depot.dev](mailto:contact@depot.dev) and mention that you found us on GitHub.
