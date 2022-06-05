# 一、git submodule的用处
如果你的代码仓库对第三方库有依赖，可以使用package manager工具进行代码的下载和安装，如果package manager工具无法安装第三方依赖，可以直接将第三方依赖包含到当前仓库内，作为一个子模块存在
```
git submodule add https://github.com/codexuhy/git-submodule
```

# 二、git clone 之后的使用方法

包含submodule的代码仓库，git clone 后 查看 submodule目录下为空
需要在代码仓库目录下输入如下命令来获取submodule 的依赖
```
git submodule update --init --recursive 
```
此时若查看submodule状态
```
git submodule status

4bb799e41e70642003136b401466fbec70d3076c git-submodule (4bb799e)

```

之后若submodule需要更新时，使用如下命令：
```
git submodule update --remote

git submodule status

+84b404e7c5b98f0da981b11ee1382e050c2ba0f0 git-submodule (heads/master)

```
commit 由 4bb799e 转变为 84b404e ，表示最新的submodule更新成功。