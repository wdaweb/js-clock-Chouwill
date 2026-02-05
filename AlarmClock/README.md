# 時鐘鬧鐘專案

一個用原生 JavaScript 寫的時鐘和鬧鐘應用，主要練習 DOM 操作、時間處理和 CSS 動畫。

## 功能

- 類比時鐘顯示（時針、分針、秒針會動）
- 數位時間顯示
- 鬧鐘設定（會存在 localStorage）
- 鬧鐘響鈴時會有熊跳出來（這個是後來加的，覺得很有趣）

## 技術

- HTML/CSS/JavaScript（原生，沒用框架）
- Day.js（處理時間，用 CDN）
- localStorage（存鬧鐘設定）

## 檔案結構

```
AlarmClock/
├── AlarmClock.html    # 全部寫在一起（單檔專案）
├── imgs/              # 圖片
│   ├── clock-bg.png
│   ├── forest-bg.jpg
│   ├── Bear.png       # 鬧鐘響鈴會跳出來的熊
│   └── hammer.png     # 目前沒用到
└── README.md
```

## 怎麼用

1. 直接用瀏覽器開 `AlarmClock.html`
2. 看時鐘跑
3. 選個時間設定鬧鐘
4. 時間到了會看到熊跳出來，時鐘會震動

## 開發過程遇到的問題

### 時針不準

一開始時針計算沒考慮分鐘數，所以時針不會隨著分鐘慢慢移動。後來改成 `hours12 * 30 + minutes * 0.5` 才對。

### 鬧鐘重複觸發

原本用字串比對時間，有時候會在同一分鐘內觸發好幾次。後來加了 `alarmRinging` 標記來防止重複。

### 熊的動畫

熊的出現動畫試了幾種方式，最後用 CSS keyframes + JavaScript 控制 class，比較好控制時機。
