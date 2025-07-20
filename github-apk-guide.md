# GitHub 自動構建 APK 完整教學

## 🚀 第一步：創建 GitHub 帳號和倉庫

### 1.1 註冊 GitHub 帳號
- 前往 https://github.com
- 點擊 "Sign up"
- 填寫用戶名、郵箱、密碼
- 驗證帳號

### 1.2 創建新倉庫
- 登錄後點擊右上角 "+" → "New repository"
- 倉庫名稱：`pay-assistance-app`
- 設為 Public（免費帳號需要公開才能使用 Actions）
- 勾選 "Add a README file"
- 點擊 "Create repository"

## 📂 第二步：上傳項目文件

### 2.1 下載項目文件
從 Replit 下載所有文件：
- 點擊左上角三條線菜單
- 選擇 "Download as zip"
- 解壓縮到你的電腦

### 2.2 上傳到 GitHub
**方法1：網頁上傳**
- 在你的倉庫頁面點擊 "uploading an existing file"
- 拖拽所有項目文件到頁面
- 輸入提交信息："Initial project upload"
- 點擊 "Commit changes"

**方法2：Git 命令行**
```bash
git clone https://github.com/你的用戶名/pay-assistance-app.git
cd pay-assistance-app
# 複製所有項目文件到這個文件夾
git add .
git commit -m "Initial project upload"
git push origin main
```

## ⚙️ 第三步：啟用 GitHub Actions

### 3.1 確認 Actions 文件
確保項目包含以下文件：
```
.github/
  workflows/
    build-apk.yml
```

### 3.2 觸發構建
- 上傳完成後，GitHub 會自動檢測到 workflow 文件
- 前往倉庫的 "Actions" 標籤頁
- 你會看到 "Build Android APK" 工作流程
- 點擊工作流程名稱查看構建進度

## 📱 第四步：下載 APK

### 4.1 等待構建完成
- 構建通常需要 10-15 分鐘
- 你可以實時查看構建日誌
- 成功時會顯示綠色勾號

### 4.2 下載 APK 文件
- 構建完成後，在 Actions 頁面找到你的構建
- 點擊構建名稱
- 在頁面底部找到 "Artifacts" 部分
- 點擊 "pay-assistance-apk" 下載

### 4.3 安裝到手機
- 解壓縮下載的文件
- 將 `app-debug.apk` 複製到手機
- 在手機上點擊安裝
- 開啟"允許未知來源應用"（如果需要）

## 🔧 故障排除

### 常見問題：
1. **Actions 無法運行**
   - 確保倉庫是 Public
   - 檢查 `.github/workflows/build-apk.yml` 文件是否存在

2. **構建失敗**
   - 查看 Actions 日誌找到具體錯誤
   - 通常是依賴安裝問題，會自動重試

3. **找不到 APK**
   - 確認構建狀態為成功（綠色勾號）
   - 在 Artifacts 部分尋找下載鏈接

## 📋 需要的文件清單
確保上傳以下文件：
- `package.json`
- `package-lock.json`
- `client/` 文件夾
- `server/` 文件夾
- `android/` 文件夾
- `capacitor.config.ts`
- `.github/workflows/build-apk.yml`
- 其他配置文件

## 🎯 完成後你會得到
- 一個可安裝的 Android APK 文件
- 自動化的構建流程
- 每次代碼更新都會自動構建新版本