<div align="center">

### The fastest place to build Docker images

[Turbocharge the `docker build`](https://depot.dev)

</div>

---

Depot is a remote container build service that builds container images up to **20x faster**, from your terminal or existing CI provider. Our builders are quick, run on native hardware, and fully managed persistent caching with no extra configuration. ⚡

## What is Depot?

1. Our [`depot` CLI](https://github.com/depot/cli) supports the same CLI options as Docker Buildx:

   ```diff
   - docker buildx build -t repo/image:tag .
   + depot build -t repo/image:tag .
   ```

2. We launch a cloud builder instance with 16 CPUs, 32GB of RAM, and a persistent 50GB build cache (with the option to select large cache sizes if you need it), all automatically configured for your project. We launch builders with native CPUs for every platform, so you can enjoy **emulation-free** builds for AWS Graviton and Apple Silicon.

3. Your container image is built remotely on a builder that starts in just a few seconds with your previous build cache ready to use. When the build is finished, the result can be downloaded to your local machine or pushed to a registry of your choosing.

## Why should I use it?

- **For your local machine:** builds won't slow down your laptop, use up your machine memory, or clog your network connection. By running the build in the cloud, it will have access to a fast low-latency network connection to download base images and build dependencies. And you won't need to pull gigabytes of unnecessary files into your local disk for cache.
- **For CI:** we fully manage a persistent cache for each builder, so no more waiting minutes for the GitHub `actions/cache` to load and save tarballs for each build. Builds also have access to more resources than GitHub Actions, with 16 CPUs to speed up and parallelize `RUN` steps, 32GB of RAM, and 50GB of total cache per project instead of 10GB.
- **For teams:** the entire build cache is centralized and shared with anyone who is building the same project. By running the `docker build` via Depot, the build cache can be accessed and used by anyone on a team making for faster iteration cycles.
