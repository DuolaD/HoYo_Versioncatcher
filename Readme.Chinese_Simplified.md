# HoYo_Versioncatcher

使用GitHub Workflows访问米哈游启动器API，自动更新所有mihoyo/hoyoverse游戏公开客户端版本信息。  
妈妈再也不用担心我错过版本更新的客户端下载链接啦！你说是吧，[@360NENZ](https://github.com/360NENZ) （笑  

[EN](Readme.md)|**简体中文**|[繁體中文](Readme.Chinese_Traditional.md) 

> 注意：确保你的仓库默认分支为 main，否则推送时可能失败。  

🌟 如果觉得这个项目对你有帮助，欢迎顺手点个 Star 支持一下！  

---

## 功能介绍/工作流程

- GitHub Actions 会在每天 11:00（UTC+8 时间）左右自动请求米哈游启动器/HoYoPlay API 获取REL游戏客户端信息。  
- Workflows将按照预先的设置将获取的json信息进行分类。  
- 对比本地原始json数据,如有变化则在commit信息中显示。  
- 添加时间戳注释。  
- 如有异常，将会记录至 `logs/failures.txt`。  
- 自动提交commit并推送到本仓库。  

---

## 📂 目录结构
```
/       
├── LICENSE                  
├── Readme.md
├── Readme.Chinese_Simplified.md
├── Readme.Chinese_Traditional.md
├── summarizing_cn.json
├── summarizing_os.json
└── GI/
    └── CN.json
    └── OS.json
    └── BiliBili.json
└── BH3/
    └── CN.json
    └── OS.json
└── HSR/
    └── CN.json
    └── OS.json
    └── BiliBili.json
└── ZZZ/
    └── CN.json
    └── OS.json
└── logs/
    └── failures.txt/
└── .github/
    └── workflows/
        └── daily-fetch.yml
```

---

---

## 📜 开源协议

本项目使用 BSD-3 License 开源。  

您可以自由地使用、复制、修改和分发本项目，前提是附带原始许可证声明。  

## 🚀 如需修改...

1. 直接Fork本项目（如果目标为公开API）；或使用git clone命令/Download zip获取源文件，创建一个私有仓库并提交本仓库的文件（如果目标为私密API，或者你希望请求的数据仅自己可见。）。  
2. 前往 `.github/workflows/daily-fetch.yml` 修改目标API/json文件分类/cron触发器。  
3. [如果你此前并未启动过GitHub Actions功能] 进入 Actions 页面，点击 **Enable workflows**（启用 GitHub Actions）。  
4. 无需其他配置，GitHub 默认的 `GITHUB_TOKEN` 权限即可推送更新。  
5. 你可以手动点击 **Run workflow**，也可以等待每天定时自动检查。  

---

## 📢 特别说明

- 本仓库同步的内容均来源于米哈游启动器/HoYoPlay内置的官方API，不存在使用第三方扫描的情况。  
- 感谢[WatchAndyTW](https://github.com/WatchAndyTW)提供了总览API和崩坏三API网址。  