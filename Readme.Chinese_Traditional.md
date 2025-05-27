# HoYo_Versioncatcher

使用GitHub Workflows訪問米哈遊啓動器API，自動更新所有mihoyo/hoyoverse遊戲公開客戶端版本信息。  
媽媽再也不用擔心我錯過版本更新的客戶端下載鏈接啦！你說是吧，[@360NENZ](https://github.com/360NENZ) （笑  

[EN](Readme.md)|[簡體中文](Readme.Chinese_Simplified.md)|**繁體中文**  

> 注意：確保你的倉庫默認分支爲 main，否則推送時可能失敗。  

🌟 如果覺得這個項目對你有幫助，歡迎順手點個 Star 支持一下！  

---

## 功能介紹/工作流程

- GitHub Actions 會在每天 11:00（UTC+8 時間）左右自動請求米哈遊啓動器/HoYoPlay API 獲取REL遊戲客戶端信息。  
- Workflows將按照預先的設置將獲取的json信息進行分類。  
- 對比本地原始json數據,如有變化則在commit信息中顯示。  
- 添加時間戳註釋。  
- 如有異常，將會記錄至 `logs/failures.txt`。  
- 自動提交commit並推送到本倉庫。  

---

## 📂 目錄結構
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

## 📜 開源協議

本項目使用 BSD-3 License 開源。  

您可以自由地使用、複製、修改和分發本項目，前提是附帶原始許可證聲明。  

## 🚀 如需修改...

1. 直接Fork本項目（如果目標爲公開API）；或使用git clone命令/Download zip獲取源文件，創建一個私有倉庫並提交本倉庫的文件（如果目標爲私密API，或者你希望請求的數據僅自己可見。）。  
2. 前往 `.github/workflows/daily-fetch.yml` 修改目標API/json文件分類/cron觸發器。  
3. [如果你此前並未啓動過GitHub Actions功能] 進入 Actions 頁面，點擊 **Enable workflows**（啓用 GitHub Actions）。  
4. 無需其他配置，GitHub 默認的 `GITHUB_TOKEN` 權限即可推送更新。  
5. 你可以手動點擊 **Run workflow**，也可以等待每天定時自動檢查。  

---

## 📢 特別說明

- 本倉庫同步的內容均來源於米哈遊啓動器/HoYoPlay內置的官方API，不存在使用第三方掃描的情況。  
- 感謝[WatchAndyTW](https://github.com/WatchAndyTW)提供了總覽API和崩壞三API網址。  