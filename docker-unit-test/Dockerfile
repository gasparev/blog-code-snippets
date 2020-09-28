FROM ubuntu:bionic

RUN apt-get update \
  && apt-get install -y curl gnupg \
  && curl -fsSL https://bazel.build/bazel-release.pub.gpg | gpg --dearmor > bazel.gpg \
  && mv bazel.gpg /etc/apt/trusted.gpg.d/ \
  && echo "deb [arch=amd64] https://storage.googleapis.com/bazel-apt stable jdk1.8" > /etc/apt/sources.list.d/bazel.list \
  && apt-get update \
  && apt-get install -y bazel \
  && rm -rf /var/lib/apt/lists/*

RUN groupadd -g 1000 user \
  && useradd -d /home/user -m -u 1000 -g 1000 user \
  && chown -R user:user /home/user \
  && mkdir -p /bazel/cache \
  && chown -R user:user /bazel

RUN echo "build --repository_cache=/bazel/cache">/home/user/.bazelrc