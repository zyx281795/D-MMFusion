# OASIS 阿茲海默症分類數據集

## 數據集概述

本數據集是基於OASIS (Open Access Series of Imaging Studies) 計劃的阿茲海默症分類數據集，包含腦部MRI掃描切片圖像，用於阿茲海默症嚴重程度的分類研究。

## 數據集結構

### 目錄組織
```
.
├── MildDemented/
│   └── MildDemented/         # 輕度癡呆症圖像 (5,184張)
├── ModerateDemented/
│   └── ModerateDemented/     # 中度癡呆症圖像 (376張)
├── NonDemented (2)/
│   └── NonDemented/          # 正常無癡呆症圖像 (63,560張)
├── VeryMildDemented/
│   └── VeryMildDemented/     # 極輕度癡呆症圖像 (13,796張)
├── oasis_cross-sectional-5708aa0a98d82080 (1).xlsx    # 受試者元數據
└── DATARECORD.md                 # 本說明文件
```

### 數據集統計

| 分類標籤 | 圖像數量 | 百分比 | 濾後案例數 |
|----------|---------|--------|--------|
| 正常無癡呆 (NonDemented) | 63,560 | 76.7% | 135 |
| 極輕度癡呆 (VeryMildDemented) | 13,796 | 16.6% | 70 |
| 輕度癡呆 (MildDemented) | 5,184 | 6.3% | 28 |
| 中度癡呆 (ModerateDemented) | 376 | 0.4% | 2 |
| **總計** | **82,916** | **100%** |

## 圖像格式和命名規則

### 文件命名格式
```
OAS1_[受試者ID]_MR1_[掃描序號].nii_slice_[切片編號].png
```

**命名範例解釋:**
- `OAS1_0028_MR1_1.nii_slice_113.png`
  - `OAS1`: OASIS數據集版本1
  - `0028`: 受試者編號
  - `MR1`: 磁振造影掃描類型
  - `1`: 掃描序號
  - `113`: 腦部切片編號

### 圖像規格
- **格式**: PNG (可攜式網路圖形)
- **內容**: 腦部MRI掃描軸向切片
- **顏色**: 灰階圖像
- **用途**: 阿茲海默症病程分類

## 分類標籤說明

1. **NonDemented (正常無癡呆)**
   - CDR (Clinical Dementia Rating) = 0
   - 認知功能正常的健康個體

2. **VeryMildDemented (極輕度癡呆)**
   - CDR = 0.5
   - 輕微認知障礙或極早期阿茲海默症

3. **MildDemented (輕度癡呆)**
   - CDR = 1
   - 輕度阿茲海默症，日常生活能力受輕微影響

4. **ModerateDemented (中度癡呆)**
   - CDR = 2
   - 中度阿茲海默症，需要日常照護協助

## 數據集使用建議

### 機器學習應用
- **影像分類**: 使用深度學習模型進行四類別分類
- **特徵提取**: 分析腦部結構變化特徵
- **早期診斷**: 開發自動化診斷輔助系統

### 數據不平衡處理
由於數據集存在明顯的類別不平衡問題（正常個體占76.7%），建議採用以下策略：
- **數據重採樣**: 對少數類別進行過採樣或多數類別欠採樣
- **加權損失函數**: 調整不同類別的損失權重
- **數據增強**: 對少數類別應用更多數據增強技術
- **分層抽樣**: 訓練/驗證/測試集分割時保持類別比例

### 評估指標建議
- **準確率** (Accuracy): 整體分類性能
- **精確度** (Precision): 各類別預測精確性
- **召回率** (Recall): 各類別識別完整性
- **F1分數**: 精確度和召回率的調和平均
- **混淆矩陣**: 詳細分類錯誤分析
- **AUC-ROC**: 多類別分類性能

## 相關資源

### OASIS計劃
- **官方網站**: [oasis-brains.org](https://oasis-brains.org/)
- **數據集版本**: OASIS-1 (Cross-sectional MRI Data)
- **發布機構**: Washington University School of Medicine

### 引用資訊
如使用本數據集進行研究，請引用OASIS原始論文：

Marcus, D.S., Wang, T.H., Parker, J., Csernansky, J.G., Morris, J.C., Buckner, R.L. (2007). 
*Open Access Series of Imaging Studies (OASIS): Cross-sectional MRI Data in Young, Middle Aged, Nondemented, and Demented Older Adults*. 
Journal of Cognitive Neuroscience, 19, 1498-1507.

## 數據集限制與注意事項

### 技術限制
- **圖像品質**: 部分圖像可能存在掃描偽影
- **切片選擇**: 並非所有切片都包含診斷相關資訊
- **標註偏差**: 基於臨床評估，可能存在主觀判斷差異

### 倫理考量
- 本數據集僅供學術研究使用
- 請遵守相關的數據使用政策和隱私保護規範
- 不應用於商業診斷目的，需要臨床醫師的專業判斷

**適用**:
- 學術研究和教育
- 機器學習模型開發和驗證
- 醫學影像分析方法研究
- 阿茲海默症早期檢測技術開發

**不適用**:
- 直接臨床診斷
- 商業診斷軟體開發
- 未經授權的數據分享

## 版本資訊
- **更新日期**: 2025
- **文件建立**: 2025-08-27

---
*此DATARECORD文檔提供數據集的完整技術說明，如有疑問請參考OASIS官方文檔或聯繫數據集維護者。*