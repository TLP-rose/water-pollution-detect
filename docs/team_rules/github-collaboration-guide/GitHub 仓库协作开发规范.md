# GitHub 仓库协作开发规范
######  识纤 2026年4月12日
## 前置检查

请先确认已安装 **Git**（代码版本管理工具），安装成功后再执行后续步骤。
![alt text](<../屏幕截图 2026-04-12 224534.png>)

## 一、首次配置流程（仅第一次操作）

### 1. 接受仓库邀请

打开 GitHub 邀请链接，接受权限邀请。

### 2. 复制仓库地址

进入 GitHub 仓库页面 → 点击 **Code** → 复制仓库链接：
![alt text](../image.png)

```Plain Text

https://github.com/TLP-rose/water-pollution-detect.git
```
后面的链接就是我刚刚让你们复制的仓库链接，你们可以直接用我这条口令也没有关系只是想让你们熟悉一下流程 。
### 3. 克隆仓库到本地

打开电脑终端（CMD），执行以下命令：

```Bash

# 1. 进入本地项目文件夹（先自行创建文件夹）
cd D:\projects

# 2. 克隆远程仓库到本地
git clone https://github.com/TLP-rose/water-pollution-detect.git
```

### 4. 进入项目目录

```Bash

cd water-pollution-detect
```

### 5. 创建个人开发分支

**严禁直接在 main 分支开发**，每人创建独立分支：

```Bash

# 连冰月 执行
git checkout -b dev-lianbingyue

# 肖昱虹 执行
git checkout -b dev-xiaoyuhong
```

命令说明：`git checkout -b` = 创建新分支 + 立即切换到该分支，而`git checkout`表示切换到自己的分支

### 6. 用 IDE 打开项目
* （我是用Pycharm，连冰月是两个的可以选一个使用，肖玉红两个都可以选但是肖玉红建议选VScode更方便前端后端开发）

#### 方式1：VS Code 打开

1. 打开 VS Code → 点击 **File** → **Open Folder**

2. 选择 `water-pollution-detect` 文件夹

3. 验证目录：左侧需看到 `algorithm`/`data`/`docs`/`system`

4. 打开终端：点击 **Terminal** → **New Terminal**

5. 检查当前分支：

```Bash

git branch
```

前面带 `*` 的分支即为当前所在分支

#### 方式2：PyCharm 打开

1. 打开 PyCharm → 点击 **Open**

2. 选择 `water-pollution-detect` 文件夹

3. 打开底部 **Terminal** 终端

4. 检查当前分支：

```Bash

git branch
```

---

## 二、日常开发流程（每次写代码必做）

1. 打开 IDE，进入项目文件夹 `water-pollution-detect`

2. 打开终端，执行命令：

```Bash

# 1. 确认当前分支
git branch

# 2. 切换到自己的分支（不在自己分支的情况下执行）
# 连冰月
git checkout dev-lianbingyue
# 肖昱虹
git checkout dev-xiaoyuhong

# 3. 拉取远程最新代码（同步 GitHub 最新内容）
git pull
```

**特殊同步（队长更新 main 分支后）**

！！！注意还有一个情况是整个main的内容我都进行了合并或者更改的话我会告知你们，然后你们就需要在工作之前执行：

```Bash

# 1. 切换到主分支
git checkout main

# 2. 拉取主分支最新代码
git pull origin main

# 3. 切回自己的分支
git checkout dev-lianbingyue  # 连冰月
git checkout dev-xiaoyuhong  # 肖昱虹

# 4. 合并主分支代码到自己分支
git merge main
```

⚠️ 若出现 `conflict`（代码冲突），**禁止自行修改删除**，立即截图发送给队长处理。

---

## 三、代码提交推送流程（写完代码后）
也就是怎么把自己的分支推到 GitHub

在 IDE 终端执行以下命令：

```Bash

# 1. 查看修改内容
git status

# 2. 添加所有改动到提交区
git add .

# 3. 本地提交（备注修改内容）
git commit -m "修改说明：例如完成湖面污染识别算法"

# 4. 推送到 GitHub
# 首次推送执行（带 -u origin）
#origin：远程仓库名字 默认指的就是 GitHub 上那个仓库。
#-u表示“以后记住这个对应关系”。

git push -u origin dev-lianbingyue  # 连冰月
git push -u origin dev-xiaoyuhong  # 肖昱虹

# 以后续推送直接执行
git push
```

---

## 四、提交 PR 审核（推送后）

代码推送到 GitHub 后，前往仓库页面提交 **Pull Request（合并请求）**，由队长审核通过后合并到主分支。
图中说明已经比较清楚，看图按步骤来即可


![alt text](<../屏幕截图 2026-04-12 230956.png>)
![alt text](<../屏幕截图 2026-04-12 231037.png>)
![alt text](<../屏幕截图 2026-04-12 231058.png>)
---

## 🔴 核心注意事项（必须遵守）

1. **绝对禁止**直接修改 `main` 主分支代码

2. 所有开发仅在**自己的个人分支**进行

3. 每次开发前：确认分支 → 执行 `git pull`

4. 每次提交必须编写清晰的修改说明

5. 代码完成后必须通过 **PR** 提交，等待队长审核合并
