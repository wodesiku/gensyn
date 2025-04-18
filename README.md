RL Swarm 是一个开源系统，用于在互联网上进行点对点强化学习。运行 Swarm 节点可以让您利用群体智能训练您的个人模型。每个 Swarm 以群体为单位进行强化学习推理，并通过一个 Gossiping 系统 (Hivemind) 实现模型间的协作改进。您还可以将您的节点连接到 Gensyn 测试网，以获得一个链上身份，用于跟踪您的进度。
要求
CUDA 设备（官方支持）：
RTX 3090
RTX 4070
RTX 4090
A100
H100
教程：
1--服务器更新
sudo apt-get update && sudo apt-get upgrade -y

2--安装软件包
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y

3--安装 Python
sudo apt-get install python3 python3-pip python3-venv python3-dev -y

4--安装节点
sudo apt-get update

curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -

sudo apt-get install -y nodejs

node -v

sudo npm install -g yarn

yarn -v



5--安装 Yarn
curl -o- -L https://yarnpkg.com/install.sh | bash

export PATH="$HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH"

source ~/.bashrc

5.1--克隆存储库

git clone https://github.com/gensyn-ai/rl-swarm.git
cd rl-swarm

（可选）----假如有之前备份的swarm.pem文件，请使用WinSCP工具把文件拷贝到workspace/rl-swarm目录下

6--创建屏幕
screen -S gensyn

cd //workspace/rl-swarm

7--安装及运行   Swarm
python3 -m venv .venv
source .venv/bin/activate
./run_rl_swarm.sh

Y , enter

8--电脑端打开Powershell  输入以下命令放开3000端口
ssh -L 3000:localhost:3000 root@你的服务器ip -p 端口
例如：
    ssh -L 3000:localhost:3000 root@ssh4.vast.ai -p 27172


8.1--访问电脑浏览器打开这个网站
http://localhost:3000/
登录进去

9--提示上传HuggingFace 
N , Enter


10--观察服务器端的进度
0/20 说明当前轮有 20 个训练 step，你刚刚开始第一步，很快你会看到
出现后可以挂起了
CTRL A + D  

11--保存swarm.pem文件到本地备份
/workspace/rl-swarm
swarm.pem





