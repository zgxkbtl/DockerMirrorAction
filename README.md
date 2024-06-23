# DockerMirrorAction

本项目是一个 Github Action，用于将 Docker 镜像推送到阿里云镜像仓库。
copy docker mirror to aluyun registry

## 如何使用

可以直接在本项目的 [Issue](https://github.com/zgxkbtl/DockerMirrorAction/issues) 中提出需要同步的镜像。
例如，如果你需要同步 `uozi/nginx-ui:v2.0.0-beta.25` 镜像，可以在 Issue 中提出请求。
直接将镜像名称写在 Issue 的标题中即可。同步完成后，会在 Issue 中回复。


也可以 Fork 本项目，在 [setting](https://docs.github.com/en/actions/learn-github-actions/variables#creating-configuration-variables-for-a-repository) 添加 `.github/workflows/main.yml` 文件中的变量，自行同步镜像。
具体来说，需要修改以下几个变量：
- Repository secrets
    - `DOCKER_REGISTRY_PASSWORD`：阿里云镜像仓库的密码
- Repository variables
    - `ALIYUN_DOCKER_ADDRESS`：阿里云镜像仓库地址，例如 `registry.cn-hangzhou.aliyuncs.com`
    - `ALIYUN_REGISTRY_USERNAME`：阿里云镜像仓库命名空间，例如 `zgxkbtl`
    - `MIRROR_NAMESPACE`：同步到阿里云镜像仓库的命名空间，例如 `mirrors`

## 如何工作

本项目使用 Github Actions 来同步 Docker 镜像。当有新的 Issue 提出时，会触发 Github Actions，将镜像同步到阿里云镜像仓库。
由于每月 Github Actions 有免费的 2000 分钟，可以 Fork 本项目，自行同步镜像。

阿里云的个人镜像仓库有免费的 300 个镜像仓库，可以用来同步镜像。如果需要更多的镜像仓库，可以购买企业镜像仓库。
也可以使用其他的镜像仓库，只需要修改对应的变量即可。