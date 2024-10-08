An extremely fast Python package and project manager, written in Rust.
一个用 Rust 编写的速度极快的 Python 包和项目管理器。

[GitHub Pages](https://github.com/astral-sh/uv)

# 基本使用
## 1、安装 
略
## 2、基本命令
### python版本管理
```
uv python install：安装 Python 版本。
uv python list：查看可用的 Python 版本。
uv python find：查找已安装的 Python 版本。
uv python pin：固定当前项目以使用特定的 Python 版本。
uv python uninstall：卸载 Python 版本。
```
### 项目基本使用
```
uv init：创建新的 Python 项目。
uv add：向项目添加依赖项。
uv remove：从项目中删除依赖项。
uv sync：将项目的依赖项与环境同步。
uv lock：为项目的依赖项创建一个 lockfile。
uv run：在项目环境中执行命令。
uv tree：查看项目的依赖关系树。
uv build：将项目构建到分发存档中。
uv publish：将项目发布到包索引。
```
### uv自身命令
```
uv cache clean：删除缓存条目。
uv cache prune：删除过时的缓存条目。
uv cache dir：显示 uv 缓存目录路径。
uv tool dir：显示 uv 工具目录路径。
uv python dir：显示 uv 安装的 Python 版本路径。
uv self update：将 UV 更新到最新版本。
```
### uv 兼容pip命令
只需要在想执行的pip命令前加上uv即可，例如
```
uv pip install
```
## 3、在项目中使用UV

可以使用 uv init 命令创建新的 Python 项目：
```
uv init hello-world
cd hello-world
```
或者可以在 working directory 中初始化一个项目：
```
mkdir hello-world
cd hello-world
uv init
```
添加依赖
```
# 直接添加版本依赖
uv add 'requests==2.31.0'
# 添加仓库依赖
uv add git+https://github.com/psf/requests
```

删除依赖
```
uv remove requests
```
升级依赖
```
uv lock --upgrade-package requests
--upgrade-package 标志将尝试将指定的包更新到最新的 compatibleversion，同时保持锁定文件的其余部分不变。
```

## 源配置
### 在项目中修改

找到项目中的pyproject.toml配置
uv源码配置需要添加：
```
[tool.uv]
index-url = "https://test.pypi.org/simple"
```
pip源配置
```
[tool.uv.pip]
index-url = "https://test.pypi.org/simple"
```
### uv配置
mac或Linux
在下面的路中文件中添加内容
~/.config/uv/uv.toml
```
index-url = "https://test.pypi.org/simple"
```
### 在项目中配置uv.toml文件
```
index-url = "https://test.pypi.org/simple"
```
uv.toml 文件优先于 pyproject.toml 文件，因此如果目录中同时存在 uv.toml 和pyproject.toml 文件，则将从 uv.toml 中读取配置，并且将忽略随附的 pyproject.toml 中的 [tool.uv] 部分。
