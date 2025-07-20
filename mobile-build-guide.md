# PAY Assistance 手機APP打包安裝指南

## 📱 完整打包步驟

### 第一步：下載並安裝Android Studio
1. 前往 https://developer.android.com/studio
2. 下載 Android Studio（免費）
3. 安裝時選擇"Standard"安裝選項
4. 等待所有組件下載完成（約2-3GB）

### 第二步：設置開發環境
1. 打開Android Studio
2. 選擇"More Actions" → "SDK Manager"
3. 確保安裝了：
   - Android SDK Platform 33 或更新版本
   - Android SDK Build-Tools
   - Android SDK Platform-Tools
   - Android SDK Command-line Tools

### 第三步：準備應用文件
在Replit中執行以下命令：
```bash
# 1. 構建Web應用
npm run build

# 2. 同步到Capacitor
npx cap sync android

# 3. 打開Android項目
npx cap open android
```

### 第四步：在Android Studio中構建APK
1. Android Studio會自動打開項目
2. 等待Gradle同步完成（可能需要幾分鐘）
3. 點擊頂部菜單 "Build" → "Build Bundle(s) / APK(s)" → "Build APK(s)"
4. 等待構建完成（約5-10分鐘）
5. 構建成功後會顯示通知，點擊"locate"找到APK文件

### 第五步：安裝到手機
**方法1：直接安裝**
1. 將APK文件複製到手機
2. 在手機上找到APK文件並點擊安裝
3. 可能需要開啟"允許安裝未知來源應用"

**方法2：通過Android Studio安裝**
1. 用USB連接手機到電腦
2. 在手機上開啟"開發者選項"和"USB調試"
3. 在Android Studio中點擊"Run"按鈕
4. 選擇你的手機設備
5. 應用會自動安裝並啟動

## 📋 應用信息
- **應用名稱**: PAY Assistance
- **包名**: com.payassistance.app
- **版本**: 1.0.0
- **最低Android版本**: 7.0 (API 24)
- **目標Android版本**: 13 (API 33)

## 🎯 主要功能
- 澳洲稅務計算系統
- 7天工作時間追蹤
- 個別日期工作/休息控制
- 臨時工加成(+25%)計算
- 加班費和節假日津貼計算
- 薪資分享功能(WhatsApp, Line, Gmail, SMS)
- 記錄保存和查看

## 🔧 故障排除

### 如果構建失敗：
1. 確保網絡連接穩定
2. 清理項目：Build → Clean Project
3. 重新構建：Build → Rebuild Project
4. 檢查Android SDK是否完整安裝

### 如果無法安裝到手機：
1. 確認手機已開啟"允許安裝未知來源應用"
2. 檢查手機存儲空間是否足夠
3. 嘗試重新下載APK文件

### 開發者選項設置：
1. 前往手機"設置" → "關於手機"
2. 連續點擊"版本號"7次
3. 返回設置，找到"開發者選項"
4. 開啟"USB調試"

## 📂 文件位置
- **APK文件位置**: `android/app/build/outputs/apk/debug/app-debug.apk`
- **項目根目錄**: 當前Replit項目文件夾
- **Android項目**: `android/` 文件夾

## 🚀 發佈準備
如果要發佈到Google Play Store：
1. 需要創建發佈版本APK（不是debug版本）
2. 需要Google Play Developer賬號（$25一次性費用）
3. 需要準備應用圖標、截圖、描述等資料
4. 需要隱私政策和使用條款