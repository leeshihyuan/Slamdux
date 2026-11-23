# Slamdux
Dux of SLAM




台灣自編大學教科書　@prof　

《地圖建構與同步定位》　

第 23 章　ORB-SLAM3 與 Visual-Inertial SLAM

---

## 23.1　ORB-SLAM3 的系統特色

ORB-SLAM3 由 Campos、Elvira、Rodríguez、Montiel 與 Tardós 於 2021 年發表，是第 7.7 節已初步介紹過的系統。它是特徵法 SLAM 這條血脈的集大成之作，從 PTAM、ORB-SLAM、ORB-SLAM2 一路演進而來，發布時是當時最完整、最精確的開源 SLAM 函式庫。

### 三項核心突破

- 緊耦合的視覺慣性 SLAM：第一個以最大後驗估測（MAP）為基礎、連 IMU 初始化階段也建立在 MAP 之上的緊耦合系統（第 7.7 節）。這解決了單目的尺度問題與快速運動下的穩健度。
- 多地圖系統（Atlas）：跟丟時不再崩潰，而是開啟新地圖繼續運作，日後重回舊區域時再無縫合併。這解決了 ORB-SLAM2「跟丟即結束」的致命弱點。
- 四種資料關聯的全面運用：這是最根本的架構創新。ORB-SLAM3 是第一個在所有演算法階段都運用短期、中期、長期與多地圖資料關聯的系統。
