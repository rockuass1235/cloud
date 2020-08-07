
# Dango on gcp

### 環境設定

```
# 更新
sudo apt-get update
# 安裝python依賴庫
sudo apt install python(x.x)-dev


# 安裝虛擬環
sudo apt-get -y install python3-pip
sudo pip3 install virtualenv

# 安裝git
sudo apt-get install -y git
sudo config --global user.name "user" # 請設定與github相同
sudo config --global user.email "user@gmail.com" # 請設定與github相同

```

### 請動虛擬環境

```
# 建立
virtualenv envs/web
source envs/web/bin/activate

```

### 安裝django & 設定

```
pip install django
django-admin startproject myweb
cd myweb
pip freeze > requirements.txt


# 初始化 & 上傳到 github

git init
git remote add origin https://github.com/user/my_repo.git
git add
git commit -m 'first commit'
git push origin master


# 初次django啟動
cd myweb
nano setting.py
# 修改 setting.py 內 ALLOW_HOSTS=['*',]
python manage.py runserver 0.0.0.0:8000

```
### 簡易關ssh server不關閉方法


```
nohup python manage.py runserver 0.0.0.0:8000 &
```

### 異地環境移植

```
git clone https://github.com/user/my_repo.git

# 安裝python 環境
cd myweb
pip install -r 'requirements.txt'

```

輸入ip:8000測試是否有看到django火箭
