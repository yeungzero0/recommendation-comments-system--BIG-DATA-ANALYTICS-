# Amazon Reviews Helpfulness Prediction  
**Recommendation Comments System (Big Data Analytics)**

[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-orange)](https://scikit-learn.org/)
[![Sentence-Transformers](https://img.shields.io/badge/BERT-embeddings-green)](https://www.sbert.net/)

一個基於 **Amazon 商品評論** 的「有用性預測系統」（Helpfulness Prediction），使用機器學習與深度學習模型判斷評論是否值得被信任，並透過後處理機制（demotion）把誤導性評論往下排，讓真正有價值的評論優先顯示，提升使用者購物體驗。

---

## ⚠️ 免責聲明 (Disclaimer)

**本專案純粹用於學習與個人/課程用途**。

- 此專案是 **POLYU CS 學生** 的學習專案，主要目的是練習 NLP、特徵工程、模型整合（Ensemble）、資料視覺化及後處理邏輯。
- **嚴禁商業使用**：本專案**不得**用於任何商業活動、產品開發、盈利目的或生產環境。
- **僅供參考與教育**：所有產出的結果（包含 result.csv）僅供學習、測試之用。
- **無任何保證**：作者不對使用本專案所產生的任何輸出、結果、版權問題或後果承擔任何責任。
- 如有任何疑問，請勿用於正式用途。

> **總之：這只是我在 POLYU 學習 Big Data 與 Machine Learning 的練習專案，不是專業推薦系統，也不是商業解決方案。**

---

## 專案特色

- **目標**：預測 Amazon 評論是否有用（useful = 1 / useless = 0）
- 使用 **TF-IDF + Logistic Regression** 作為 Baseline，並與 **BERT embeddings + RandomForest / GradientBoosting** 進行 Ensemble
- 提供豐富的**資料視覺化**：
  - Unigrams / Bigrams / Top-10 關鍵詞
  - 原星級分佈與二元標籤分佈
  - Confusion Matrix、ROC、PR Curve、預測機率直方圖、Top-10 misclassified words 等
- **後處理機制**（Demotion）：
  - 預測為有用但星級很低（1-2 星）的評論 → trust_score × 0.3
  - 包含 misclassified 高頻詞的評論 → trust_score × 0.75
- 最終輸出 `result.csv` 包含 trust_score、is_misleading、matched_misclassified_words 等欄位
- **最終最佳成績**：Ensemble (LR-Tuned + RF-BERT + GBT-BERT) → **(F1 + AUC)/2 = 0.9079**


## Result
![image](https://github.com/yeungzero0/recommendation-comments-system--BIG-DATA-ANALYTICS-/blob/main/img/1.png)  
![image](https://github.com/yeungzero0/recommendation-comments-system--BIG-DATA-ANALYTICS-/blob/main/img/2.png)  
![image](https://github.com/yeungzero0/recommendation-comments-system--BIG-DATA-ANALYTICS-/blob/main/img/3.png)  
![image](https://github.com/yeungzero0/recommendation-comments-system--BIG-DATA-ANALYTICS-/blob/main/img/4.png)  
![image](https://github.com/yeungzero0/recommendation-comments-system--BIG-DATA-ANALYTICS-/blob/main/img/5.png)  

# Top 10 comments demo
![image](https://github.com/yeungzero0/recommendation-comments-system--BIG-DATA-ANALYTICS-/blob/main/img/0.png)

---
