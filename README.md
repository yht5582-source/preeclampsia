# 妊娠高血壓・子癲前症・子癲症｜互動學習

線上版：<https://yht5582-source.github.io/preeclampsia/>

給醫療人員的繁體中文教學頁。並列 ACOG 與 ISSHP／NICE 的診斷門檻，練習分類、急症處置、阿斯匹靈預防與分娩決策。單一 `index.html`，不需安裝；輸入的數值只在瀏覽器內計算，不會傳送。

> ⚠️ 教學摘要，不是已驗證的診斷或處方系統，不取代臨床判斷、院內方案與母胎醫學團隊。本頁不計算硫酸鎂處方。

## 單元

每個單元有自己的網址（如 `…/preeclampsia/#map`），可直接分享。

| 單元 | 網址 | 內容 |
| --- | --- | --- |
| 01 診斷分類 | `#overview` | 慢性高血壓、妊娠高血壓、子癲前症、子癲症、疊加型；ACOG 與 ISSHP／NICE 門檻對照表 |
| 02 互動評估 | `#assess` | 同一組血壓與檢驗，同時顯示兩套門檻的分類、下一步、硫酸鎂與分娩時機；空白欄位視為未知，不視為正常 |
| 03 處置 | `#treatment` | 嚴重高血壓急症、維持降壓、硫酸鎂適應症與 NICE 方案、鎂毒性、抽搐與 HELLP |
| 04 阿斯匹靈預防 | `#prevent` | 勾選風險因子，分別依 ACOG／USPSTF 與 NICE 規則判讀，兩者不同時提示原因；劑量與時程三套並列 |
| 05 分娩與產後 | `#birth` | ISSHP 任何孕週分娩適應症、ACOG 與 NICE 依孕週對照、產後追蹤與長期風險 |
| 06 病例練習 | `#cases` | 9 個原創虛構病例，每例 2 個決策點，選答後即時解析 |
| 07 自我測驗 | `#quiz` | 10 題單選，選項順序隨機，附來源與逐題回顧；重新整理會重設 |
| 08 心智圖 | `#map` | 診斷 7 支、處置 8 支，預設收合，葉節點標示出處；手機改單欄，列印時全部展開 |
| § 指引與差異 | `#sources` | 指引版本、連結與使用界線 |

頁尾的「列印學習內容」會輸出全部單元，病例與考題改為附解析的講義。

## 資料來源

核對日期：2026-10-31。

1. [NICE NG133](https://www.nice.org.uk/guidance/ng133/chapter/Recommendations)：Hypertension in pregnancy（2019；更新 2023-04-17）
2. [ISSHP 2021 recommendations](https://isshp.org/wp-content/uploads/2023/09/ISSHP-2021-guidelines.pdf)：Magee LA et al. Pregnancy Hypertens 2022;27:148–169
3. [ACOG Committee Opinion 767](https://pubmed.ncbi.nlm.nih.gov/30575639/)：Emergent therapy for acute-onset severe hypertension（2019）
4. [ACOG Practice Bulletin 222](https://www.acog.org/clinical/clinical-guidance/practice-bulletin/articles/2020/06/gestational-hypertension-and-preeclampsia)：Gestational hypertension and preeclampsia（2020）。完整 Bulletin 有存取限制，本頁以公開可核對內容為主，不聲稱逐條驗證付費全文
5. [ACOG／SMFM Practice Advisory](https://www.acog.org/clinical/clinical-guidance/practice-advisory/articles/2021/12/low-dose-aspirin-use-for-the-prevention-of-preeclampsia-and-related-morbidity-and-mortality)：Low-dose aspirin（2021）

不同指引的門檻不合併成單一標準；未涵蓋台灣健保給付或國內指引。

## 版本

- **v2.2（2026-11-02）**：新增 6 個示範病例（D–I），共 9 例，涵蓋指引門檻差異、HELLP、由穩定轉急症、雙胞胎與阿斯匹靈、氣喘與降壓、20 週前高血壓。內容依頁內既有規則撰寫，未重新核對指引原文。
- **v2.1（2026-11-02）**：新增心智圖單元與本 README。心智圖整理自頁內既有內容，未新增臨床主張，也未重新核對指引原文。
- **v2.0（2026-10-31）**：除錯與視覺重新設計；評估引擎 `PE` 並列 ACOG 與 ISSHP／NICE，新增阿斯匹靈風險檢核。

## 開發

```
index.html   單一頁面（HTML + CSS + JS）
tests.cjs    測試：引擎 /*ENGINE-START*/…/*ENGINE-END*/、心智圖資料 /*MAP-START*/…/*MAP-END*/、病例 /*CASES-START*/…/*CASES-END*/
```

```bash
node tests.cjs
```

心智圖內容不會自動同步。修改門檻或劑量時要一併更新 `MAP`；測試會檢查葉節點的數字都出現在頁面其他位置，以及主要門檻與引擎一致。

GitHub Pages 由 `main` 分支根目錄部署，推送即上線。
