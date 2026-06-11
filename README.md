# CCF 2026 期刊与会议查询工具

这是一个用于查询 CCF 2026 推荐国际学术会议和期刊目录的轻量工具，支持本地命令行运行，也支持通过 GitHub Pages 静态网站访问。

在线访问地址：

```text
https://gengshuochn.github.io/CCF_search_2026/
```

## 功能

- 支持按缩写、全名、关键词查询，不区分大小写。
- 支持缩写模糊查询，例如 `infcom` 可匹配 `INFOCOM`，`neurip` 可匹配 `NeurIPS`。
- 支持缩写符号归一化，例如 `sp`、`s-p` 可匹配 `S&P`。
- 查询结果展示全名、缩写、类型、CCF 评级、所属领域，并提供 DBLP 搜索入口。
- 提供本地命令行版本和纯静态网页版本。

## 文件说明

- `ccf_search.py`：本地命令行查询程序。
- `ccf_search.bat`：Windows 本地快捷启动脚本，用于运行 `ccf_search.py`。
- `ccf_search_web.py`：用于生成或导出前端静态数据的辅助脚本。
- `ccf search/`：GitHub Pages 静态网页目录，包含 `index.html` 和 `ccf_data.js`。

## 本地运行

### 方式一：使用 bat 快捷启动

在 Windows 中双击运行：

```text
ccf_search.bat
```

也可以在 PowerShell 中运行：

```powershell
.\ccf_search.bat
```

注意：`ccf_search.bat` 中包含项目目录路径。如果项目目录发生变化，需要同步修改 bat 文件中的 `cd /d ...` 路径。

### 方式二：直接运行 Python 脚本

```powershell
py ccf_search.py
```

进入查询界面后，输入会议或期刊的缩写、全名或关键词即可查询。输入 `quit`、`exit` 或 `q` 退出。

示例查询：

```text
INFOCOM
infcom
SIGMOD
sigmod
security
computer communications
```

## GitHub 静态网站访问

本项目的静态网页已托管在 GitHub Pages：

```text
https://gengshuochn.github.io/CCF_search_2026/
```

静态网页版本不需要后端服务，浏览器会直接加载 `ccf search/index.html` 和 `ccf search/ccf_data.js` 中的数据完成查询。

如果修改了网页或数据，需要进入静态网页仓库目录后提交并推送：

```powershell
cd "D:\1_Projects\Interest_Projects\CCF_search\ccf search"
git status
git add index.html ccf_data.js
git commit -m "更新 CCF 查询页面"
git push origin main
```

推送后 GitHub Pages 通常会在几十秒到几分钟内更新。如果浏览器仍显示旧页面，可以使用 `Ctrl + F5` 强制刷新缓存。

## 本地预览静态网页

也可以直接打开：

```text
ccf search/index.html
```

或在项目根目录启动一个简单静态服务器：

```powershell
py -m http.server 8000
```

然后访问：

```text
http://localhost:8000/ccf%20search/index.html
```

## 数据来源

数据来源于中国计算机学会 CCF 推荐国际学术会议和期刊目录第七版（2026 年更新）。
