# 网络问题

1. 换一个好一点的梯子，
2. `utools`上搜重置网络进行重置
3. 关闭网络代理，在cmd上直接`ipconfig /flushdns`刷新dns缓存，这个很奏效

4. 将git从22端口切换到443端口

在`~/.ssh/config`里面加入下面的话让443代理22端口就行了

```shell
Host github.com
    Hostname ssh.github.com
    Port 443
    User git
```

然后进行验证

```shell
ssh -T -p 443 git@ssh.github.com # 这是先用443端口来测试是否连接的通
ssh -T git@github.com # 修改之后，用默认端口是否可以联通过去
```
