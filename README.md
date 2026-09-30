# 9 月 30 日作业：用 Git 和 GitHub 完成一次项目协作练习
w
本次作业不考察复杂的编程内容。请通过实际操作，完成“获取项目 → 本地修改 → 提交版本 → 上传到自己的 GitHub”的过程。

教师仓库：[inspirepassion/cv_homework_09_30](https://github.com/inspirepassion/cv_homework_09_30)

## 一、你最终需要完成什么？

1. 用终端在本地创建一个文件夹；把教师仓库 Fork 到自己的 GitHub 账号，再用命令行克隆到本地文件夹中。
2. 进入克隆后的项目，创建一个以自己姓名命名的 `.py` 文件，使用 `git status`、`git add .`、`git commit`、`git push` 上传到自己的 GitHub 仓库。
3. 在“芯位蜜线”学习平台的今日作业提交处，提交**你自己 Fork 后的仓库网页链接**。

整个过程如下：

```text
教师的 GitHub 仓库
        ↓ Fork（在 GitHub 上创建自己的副本）
你自己的 GitHub 仓库
        ↓ git clone（复制到电脑）
本地项目 → 新建文件 → git add → git commit
        ↓ git push（上传提交）
你自己的 GitHub 仓库 → 复制仓库网页链接 → 提交到芯位蜜线
```

## 二、开始前的准备

### 1. 打开合适的终端

| 电脑系统 | 本文使用的命令行环境 |
| --- | --- |
| macOS | 打开“终端 / Terminal”，使用默认的 zsh 或 bash |
| Windows | 打开安装 Git for Windows 后提供的 **Git Bash** |

为便于大家使用同一套命令，Windows 同学请使用 Git Bash。本文的 `~` 路径、`ls` 和文件创建示例按上述环境编写，不要直接套用到 Windows 的 cmd 窗口。

在终端中输入：

```bash
git --version
```

如果看到 `git version ...`，说明当前终端可以使用 Git。如果提示找不到 `git`，请先完成课堂中的 Git 安装步骤，再继续作业。

### 2. 登录自己的 GitHub 账号

用浏览器登录 GitHub，确认右上角头像对应的是你自己的账号。

### 3. 阅读命令时注意

- 命令请逐行执行，执行成功后再进行下一步。
- 示例中的 `YOUR_USERNAME` 要换成你的 **GitHub 用户名**。
- 示例中的“张三”要换成你的**学生姓名**。
- GitHub 用户名和学生姓名可能不同，不要混淆。
- 命令中的引号请使用英文半角引号。本文代码框里没有 `$` 提示符，可直接复制相应命令。

## 三、任务 1：创建本地文件夹，Fork 并克隆项目

### 步骤 1：在本地创建作业存放文件夹

在终端中依次执行：

```bash
cd ~
mkdir -p git_homework_09_30
cd git_homework_09_30
pwd
```

这些命令分别在做什么：

| 命令 | 作用 |
| --- | --- |
| `cd ~` | 回到当前电脑用户的主文件夹 |
| `mkdir -p git_homework_09_30` | 创建用于存放作业的文件夹；若已存在则保留 |
| `cd git_homework_09_30` | 进入这个文件夹 |
| `pwd` | 显示当前所在的位置 |

**成功标志：** `pwd` 输出的路径最后一段是 `git_homework_09_30`。

例如，Mac 上可能是 `/Users/你的电脑用户名/git_homework_09_30`；Windows Git Bash 中可能是 `/c/Users/你的电脑用户名/git_homework_09_30`。每个人的用户名不同，路径不必完全一致。

> 为什么先看位置？接下来的 `git clone` 会在当前文件夹里创建项目目录。先确认位置，才能知道项目下载到哪里了。

### 步骤 2：把教师仓库 Fork 到自己的 GitHub

1. 在浏览器中打开[教师仓库](https://github.com/inspirepassion/cv_homework_09_30)。
2. 点击页面上的 **Fork**。
3. 将 Owner（所有者）选择为你自己的 GitHub 账号。
4. 保留仓库名称 `cv_homework_09_30`，点击 **Create fork**。
5. 创建完成后，确认页面顶部的仓库所有者已变成你的账号。

你的仓库网页地址应类似：

```text
https://github.com/YOUR_USERNAME/cv_homework_09_30
```

**成功标志：** 页面显示的是“你的账号 / cv_homework_09_30”，通常还会显示它 Fork 自教师仓库。

> Fork 在 GitHub 上创建一份属于你的仓库副本；它还没有把文件下载到你的电脑。如果之前已经 Fork 过，请打开自己的现有 Fork，不必重复创建。

### 步骤 3：复制自己仓库的克隆地址

在**自己的 Fork 页面**点击绿色的 **Code** 按钮，选择 **HTTPS**，复制其中的地址。

地址应类似：

```text
https://github.com/YOUR_USERNAME/cv_homework_09_30.git
```

请检查：网址中是你自己的 GitHub 用户名，而不是教师的 `inspirepassion`。

### 步骤 4：用命令行克隆到本地

回到刚才的终端，先确认位置：

```bash
pwd
```

确认仍在 `git_homework_09_30` 文件夹内，再执行下面的命令。请将示例网址替换成刚才复制的**自己仓库的 HTTPS 地址**：

```bash
git clone https://github.com/YOUR_USERNAME/cv_homework_09_30.git
```

完成后执行：

```bash
ls
```

**成功标志：** 可以看到新出现的 `cv_homework_09_30` 文件夹。

现在文件夹结构应为：

```text
你的主文件夹/
└── git_homework_09_30/       ← 你自己创建的存放文件夹
    └── cv_homework_09_30/   ← git clone 创建的项目文件夹
```

> `git clone` 会复制项目及其 Git 历史，并自动配置名为 `origin` 的远程地址。因此，本次作业不需要再执行 `git init` 或 `git remote add origin`。

## 四、任务 2：创建自己的文件，提交并推送

### 步骤 1：进入克隆后的项目

接着在终端中执行：

```bash
cd cv_homework_09_30
pwd
ls
git status
git remote -v
```

这里要检查三件事：

1. `pwd` 输出的最后一段是 **`cv_homework_09_30`**，说明你已经进入项目，而不是停在外层存放文件夹。
2. `git status` 能显示仓库状态，没有提示 `not a git repository`。
3. `git remote -v` 显示的 `origin` 地址指向**你自己的 GitHub 仓库**。

例如：

```text
origin  https://github.com/YOUR_USERNAME/cv_homework_09_30.git (fetch)
origin  https://github.com/YOUR_USERNAME/cv_homework_09_30.git (push)
```

> `origin` 是远程地址的简称。这里确认地址，是为了确保稍后的 `git push` 上传到你自己的仓库。

### 步骤 2：创建“学生姓名.py”文件

请在项目的最外层创建文件，与项目中的其他顶层文件放在一起。文件名统一采用：**你的学生姓名.py**。

例如，学生张三执行：

```bash
echo 'print("Hello, Git!")' > "张三.py"
```

这条命令会创建 `张三.py`，并写入一行简单的 Python 代码。请将“张三”换成自己的姓名；不要求编写复杂程序，也不要求运行这个文件。

**注意：** `>` 会覆盖同名文件。如果该文件已经存在，请直接用编辑器打开并修改，不要重复执行覆盖命令。

检查文件是否创建成功：

```bash
ls
cat "张三.py"
```

请同步替换检查命令中的姓名。`ls` 应列出你的文件，`cat` 应显示文件内容。

> `.py` 文件本身也是文本文件。本次统一使用“姓名.py”命名，不要保存成“姓名.py.txt”。如果使用编辑器创建，请使用纯文本格式并保存为 UTF-8。

### 步骤 3：查看 Git 发现了哪些变化

```bash
git status
```

通常会在 `Untracked files`（未跟踪文件）下面看到你刚创建的文件。

**你现在完成的是创建文件，还没有创建 Git 提交。** Git 需要你明确选择要记录的内容。

### 步骤 4：把改动加入暂存区

确认状态中只有自己打算提交的内容后，执行：

```bash
git add .
git status
```

`git add .` 中的 `.` 表示当前目录。它会暂存当前目录及子目录中未被忽略的新增文件，以及相关修改和删除，所以执行前要确认自己位于项目目录、改动内容也正确。

**成功标志：** `git status` 的 `Changes to be committed`（准备提交的改动）中出现你的文件，通常标注为 `new file`。

> `add` 是“选好这次要提交的内容”，此时内容仍在本地，还没有上传 GitHub。不要把密码、访问令牌或无关私人文件放进作业仓库。

### 步骤 5：创建一次提交

执行下面的命令，可以把引号中的文字换成你想写的提交说明：

```bash
git commit -m "添加张三的作业文件"
```

例如，课堂中的形式是 `git commit -m "the message I want to say"`。其中 `-m` 表示为这次提交写一段说明；说明应让别人看得懂你改了什么。

**成功标志：** 终端显示新的提交编号及文件变化摘要，没有报错。

可以进一步检查：

```bash
git log -1 --oneline
git status
```

第一条显示最近一次提交，应该能看到你写的说明；如果没有其他改动，第二条通常显示 `working tree clean`。

#### 如果首次提交提示没有姓名或邮箱

如果看到 `Author identity unknown` 或 `Please tell me who you are`，请先在当前项目内配置：

```bash
git config user.name "你的姓名"
git config user.email "你的邮箱"
```

建议邮箱使用已关联到自己 GitHub 账号的邮箱，或 GitHub 邮箱设置中提供的 noreply 邮箱。完成后重新执行上面的 `git commit` 命令。

这些命令设置的是**提交署名**，只对当前仓库生效，不是登录 GitHub，也不需要输入 GitHub 密码。

### 步骤 6：把提交推送到自己的 GitHub

```bash
git push
```

因为项目是从自己的 Fork 克隆下来的，在默认分支上操作时，通常可以直接使用 `git push`。

如果出现身份验证提示，请使用课堂配置的登录方式完成认证。如果弹出浏览器授权，请确认登录的是自己的账号。通过 HTTPS 手动输入凭证时，`Password` 提示处应使用个人访问令牌（PAT），不能填写 GitHub 网页登录密码。

> `commit` 把版本保存在本地；`push` 才把提交上传到远程。两步都要完成。

### 步骤 7：在网页上检查结果

1. 回到**自己的 GitHub Fork 页面**。
2. 刷新页面。
3. 找到“你的姓名.py”。
4. 点击文件，确认能看到刚才写入的内容。
5. 确认页面上可以找到你刚才的提交说明。

**任务 2 的成功标志：自己的 GitHub 仓库网页中，确实出现了自己的文件和内容。** 仅仅在本地 `ls` 中看到文件，或 `git status` 显示干净，都不能代替网页检查。

## 五、任务 3：在“芯位蜜线”提交仓库链接

1. 确认任务 1、任务 2 已完成。
2. 打开自己的 GitHub 仓库首页，复制浏览器地址栏中的仓库链接。
3. 进入“芯位蜜线”学习平台，找到今日作业的提交入口。
4. 在作业提交处填入该仓库链接，并完成平台要求的提交操作。

应提交的链接格式：

```text
https://github.com/YOUR_USERNAME/cv_homework_09_30
```

这里的 `YOUR_USERNAME` 必须是你自己的 GitHub 用户名。

| 链接或内容 | 是否为本次应提交的内容 |
| --- | --- |
| 你自己的 `cv_homework_09_30` 仓库首页链接 | **是** |
| 教师 `inspirepassion` 的仓库链接 | 否 |
| 你的 GitHub 个人主页 | 否 |
| 本地文件夹路径，如 `/Users/...` 或 `C:\...` | 否 |
| 仅某个 `.py` 文件的页面链接或截图 | 否，本次提交仓库首页链接 |

**本次不要求向教师仓库提交 Pull Request。** 将文件推送到自己的 Fork，并在平台提交链接即可。请确保教师能够通过链接访问你的仓库；对于公开 Fork，可以用浏览器未登录窗口打开链接检查。

## 六、提交前逐项自查

- [ ] 我用终端创建了本地作业存放文件夹。
- [ ] 我把教师仓库 Fork 到了自己的 GitHub 账号。
- [ ] 我通过 `git clone` 下载的是自己的 Fork。
- [ ] 我用 `cd` 进入了克隆后的项目文件夹。
- [ ] 项目中有一个按“我的姓名.py”命名的文件。
- [ ] 我执行了 `git status`、`git add .`、`git commit` 和 `git push`。
- [ ] 我在自己的 GitHub 网页上看到了新文件及正确内容。
- [ ] 我在“芯位蜜线”提交的是自己的仓库首页链接，并完成了平台提交操作。

## 七、遇到问题时先检查什么？

| 现象或报错 | 先检查什么 |
| --- | --- |
| `not a git repository` | 运行 `pwd`；是否还停在外层 `git_homework_09_30`？进入内层 `cv_homework_09_30` 再操作。 |
| `destination path ... already exists and is not an empty directory` | 目标目录已经存在；可能之前已成功克隆。先查看目录和 `git remote -v`，不要为了重试直接删除文件。 |
| `Author identity unknown` | 按任务 2 配置姓名和邮箱，再重新提交。 |
| `Authentication failed` | 检查当前账号与凭证；网页登录密码不能代替 HTTPS Git 操作所需的令牌。 |
| `Permission denied` 或没有推送权限 | 用 `git remote -v` 确认指向自己的 Fork，并确认认证账号正确。 |
| `Repository not found` | 检查网址、用户名、仓库是否已 Fork 成功，以及当前账号是否有访问权限。 |
| `nothing to commit` | 检查文件是否已保存、是否在正确目录、是否已经提交；也可用 `git status --short --untracked-files=all` 和 `git log -1 --oneline` 查看。 |
| GitHub 网页上看不到文件 | 确认 `commit` 和 `push` 都成功，再检查是否打开了自己的仓库及正确分支，刷新网页。 |
| `push` 提示 `rejected`、`fetch first` 或 `non-fast-forward` | 远程可能出现了本地没有的新提交。保留报错，向老师求助；本次作业不需要使用强制推送。 |

如果仍无法解决，请保留**执行的命令和完整报错**，并记录 `pwd` 的输出，方便老师判断问题发生在哪一步。不要在截图或消息中包含密码、令牌或私钥。
