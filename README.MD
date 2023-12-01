# Install Docker Engine on CentOS

## Uninstall old versions
```bash
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```

## Install using the rpm repository
```bash
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

To install a specific version, start by listing the available versions in the repository:

```bash
yum list docker-ce --showduplicates | sort -r
```

Install a specific version by its fully qualified package name, which is the package name (docker-ce) plus the version string (2nd column), separated by a hyphen (-). For example, docker-ce-3:24.0.0-1.el8.

```bash
sudo yum install docker-ce-<VERSION_STRING>
```

## Start Docker.

```bash
 sudo systemctl start docker
```

Verify that the Docker Engine installation is successful by running the hello-world image.

```bash
 sudo docker run hello-world
```

## Upgrade Docker Engine
To install a specific version, start by listing the available versions in the repository:
```bash
yum list docker-ce --showduplicates | sort -r
```
Replace <VERSION_STRING> with the desired version and then run the following command to install:

```bash
sudo yum upgrade docker-ce-<VERSION_STRING>
```

To install the latest version, run:

```bash
sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

[Watch Demo]()

# Install from a package
Go to https://download.docker.com/linux/centos/ and choose your version of CentOS. Then browse to x86_64/stable/Packages/ and download the .rpm file for the Docker version you want to install.

Install Docker Engine, changing the following path to the path where you downloaded the Docker package.

[Watch Demo for step by step guide]()

# Install using the convenience script
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh --dry-run
```

[Watch Demo for step by step guide]()
