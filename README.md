# HoYo_Versioncatcher

Accessing miHoYo launcher API using GitHub Workflows to automatically update public client version information for all miHoYo/HoYoverse games.  

**EN**|[简体中文](Readme.Chinese_Simplified.md)|[繁體中文](Readme.Chinese_Traditional.md)

> Note: Ensure your repository's default branch is `main`, otherwise pushes might fail.  

🌟 If you find this project helpful, feel free to give it a Star!  

-----

## Features/Workflow

  * GitHub Actions will automatically request REL game client information from the miHoYo launcher/HoYoPlay API daily around 11:00 AM (UTC+8 time).  
  * Workflows will categorize the fetched JSON information according to pre-settings.  
  * Changes will be displayed in the commit message if there are differences from the local raw JSON data.  
  * Timestamp comments will be added.  
  * Any anomalies will be recorded in `logs/failures.txt`.  
  * Commits will be automatically submitted and pushed to this repository.  

-----

## 📂 Directory Structure

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

-----

-----

## 📜 Open Source License

This project is open-sourced under the BSD-3 License.  

You are free to use, copy, modify, and distribute this project, provided that the original license statement is included.  

## 🚀 To Modify...

1.  Directly Fork this project (if the target is a public API); or use `git clone` command/Download zip to get the source files, create a private repository, and commit the files from this repository (if the target is a private API, or you wish the requested data to be visible only to yourself).  
2.  Go to `.github/workflows/daily-fetch.yml` to modify the target API/json file categorization/cron trigger.  
3.  [If you haven't enabled GitHub Actions before] Go to the Actions page and click **Enable workflows**.  
4.  No other configuration is needed; GitHub's default `GITHUB_TOKEN` permission is sufficient to push updates.  
5.  You can manually click **Run workflow**, or wait for the daily automatic check.  

-----

## 📢 Special Notes

  * The content synchronized in this repository originates from the official API built into miHoYo Launcher/HoYoPlay; no third-party scanning is used.  
  * Thanks to [WatchAndyTW](https://github.com/WatchAndyTW) for providing the overview API and Honkai Impact 3rd API URLs.  