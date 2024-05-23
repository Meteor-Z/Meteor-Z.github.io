# 软件清单

一般开发是在Linux上，但是还是有挺多软件是在Windows上的，一下是相关的软件清单

## Windows

### scoop

```shell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```

```shell
scoop install gcc
scoop install clang clangd
scoop install gdb
scoop install git
```

- powershell，Windows Terminal 配置环境
- OpenArk 软件测试，逆向等工具集
- QQ 微信 企业微信 腾讯会议 聊天办公软件
- VS，Vscode
- 网易云音乐
- Office
- Clash
- [Sysinternals实用工具集](https://learn.microsoft.com/zh-cn/sysinternals/downloads/)

### Linux

我现在使用的是Wsl，在Wsl上更加推荐 Ubuntu 24.04 LTS 版本，以下是相关软件

```shell
sudo apt install zsh
sh -c "$(curl -fsSL https://gitee.com/Devkings/oh_my_zsh_install/raw/master/install.sh)"
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
plugins=(git zsh-syntax-highlighting zsh-autosuggestions sudo)
```

```shell
sudo apt install gcc g++
sudo apt install clang clangd
sudo apt install neofetch
sudo apt install perf
sudo apt install gdb
sudo apt install cmake
sudo apt install valgrind
sudo apt install btop
sudo apt install rigrep
```
