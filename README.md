# 🚀 Spaceship Titanic - 生存預測機器學習專案

## 📘 專案簡介
本專案參與的是 Kaggle 比賽 [Spaceship Titanic](https://www.kaggle.com/competitions/spaceship-titanic)，
目的是根據太空旅客的基本資訊與消費行為，預測他們是否在神秘事故中被「Transported」到另一個維度。

---

## 🎯 專案目標
- 針對每位乘客，根據其背景與消費數據預測 `Transported`（二元分類）。
- 運用機器學習模型進行特徵工程、訓練與優化。
- 比較不同模型效能，並進行交叉驗證與提交。

---

## 📂 資料集概覽

| 資料欄位        | 說明                     |
|-----------------|--------------------------|
| PassengerId     | 乘客編號（含組別）       |
| HomePlanet      | 乘客出發星球             |
| CryoSleep       | 是否冷凍睡眠（True/False）|
| Cabin           | 艙房位置（分艙、甲板等）  |
| Destination     | 目的地行星               |
| Age             | 年齡                     |
| VIP             | 是否為貴賓               |
| RoomService、FoodCourt、ShoppingMall... | 花費紀錄 |
| Name            | 姓名（可拆解）           |
| Transported     | **目標欄位**（True/False）|

---

## 🧹 資料處理與特徵工程
- **缺失值處理**：使用多種策略（中位數、類別眾數、推測填補）
- **欄位拆解**：Cabin 拆為 Deck / Num / Side，Name 拆為 First / Last
- **類別編碼**：One-hot Encoding 與 Label Encoding
- **特徵選擇與擴充**：消費總和欄位、是否無消費者標記等

---

## 🧠 建模與實驗
### 使用的模型：
- Logistic Regression
- Random Forest
- XGBoost（最佳表現）
- LightGBM
- Voting Ensemble（提升穩定性）

### 評估指標：
- Accuracy
- Cross-validation score
- Kaggle submission accuracy

---

## 📈 最佳模型成果
- 模型：XGBoost + 調參 + 特徵工程
- 交叉驗證準確率：約 0.80+
- Kaggle Public Leaderboard 分數：`0.79900`

---

## 📁 專案結構
```bash
📦 spaceship-titanic
├── data/                     # 原始資料與前處理後資料
├── notebooks/                # EDA 與建模筆記本
│   ├── 1_EDA.ipynb
│   └── 2_Modeling.ipynb
├── src/                      # 模型訓練、工具程式碼
│   └── train.py
├── submission/               # kaggle 提交檔案
├── requirements.txt
└── README.md
