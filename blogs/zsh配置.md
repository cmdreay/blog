# ZSH


`zsh` `shell` 

轻量级的工具控，必须要知道zsh这个shell。

## 安装

### mac下安装
mac下自带有zsh `/bin/zsh`

### linux下安装
* 如果你用 Redhat Linux，执行：sudo yum install zsh
* 如果你用 Ubuntu Linux，执行：sudo apt-get install zsh

### windows下安装 
就看你用什么虚拟机了:simple_smile:

接下去就是安装`oh my zsh`
* 自动安装：
```
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```
* 手动安装：
```
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
chsh -s /bin/zsh
```
然后重启你的terminal就可以了

### 配置
zsh 的厉害之处在于不仅可以设置通用别名，还能针对文件类型设置对应的打开程序，比如：

`alias -s html=mate`
意思就是你在命令行输入 `hello.html`，zsh会为你自动打开 TextMat 并读取 hello.html； 

`alias -s gz='tar -xzvf'`，表示自动解压后缀为 gz 的压缩包。

### 修改theme
```
ZSH_THEME=”robbyrussell”
```
### 修改plugin
```
plugins=(git textmate ruby autojump osx mvn gradle)
```


##关于history
如果是从bash切换到zsh后，history是不会共享的，也就是说`ctr+R`、`history`,或者`!cmd`都不起作用
从bash_history到zsh_history 有很多方法，下面给出一个node版本的
```javascript
// $ node bash-history-to-zsh-history.js >> ~/.zsh_history

var fs = require("fs");
var a = fs.readFileSync(".bash_history");
var time = Date.now();
a.toString().split("\n").forEach(function(line){
  console.log(": "+ (time++) + ":0;"+line);
});
```

## 参考
* http://macshuo.com/?p=676
* https://gist.github.com/ycarmel/9660351