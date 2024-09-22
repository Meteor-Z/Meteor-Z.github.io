# 软件清单

这是我积累的相关软件，Windows上和Linux上的软件我都用，所以都有

## Windows

安装scoop

### scoop

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```

```bash
scoop install gcc
scoop install clang clangd
scoop install gdb
scoop install git
```

- QQ 微信 企业微信 腾讯会议 聊天办公软件
- 网易云音乐
- Office
- Notepad--
- powershell, Windows Terminal 配置环境
- OpenArk 软件测试，逆向等工具集
- VS, Vscode
- Clash
- ugit: 这玩意还是非常好用的
- 彗星助手
- Windbg: 这玩意我感觉巨难用, 但是不得不用(其实还怪好用)
- 微软实用工具索引
  - Spxx: 微软调试窗口的工具, 继承在 VS 中
- api-monitor: API 监控工具
- IDA: 看汇编的

## Linux

```bash
sudo apt install zsh
sh -c "$(curl -fsSL https://gitee.com/Devkings/oh_my_zsh_install/raw/master/install.sh)"
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
plugins=(git zsh-syntax-highlighting zsh-autosuggestions sudo)
```

```bash
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
