---
title: 可靠深入解析
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634030"
---
# <a name="reliability-insights"></a>可靠深入解析

此檢視為您提供您受管理的裝置健全狀況摘要。 若要檢視可靠性資料，請選取 [**可靠性**] 索引標籤。


![可靠性窗格](images/insights_reliability.png)

**跨裝置的可靠性**] 區段中會提供快速的健全狀況摘要。 您過去 14 天的部署所報告的裝置會被認為是 「 良好 」 並觀察到自上次報告失敗後平均時間百分比。 

 
**經過一段時間的可靠性**圖形右邊報告發生嚴重錯誤的裝置數目和觀察到的重大錯誤的總數，經過一段時間。

[**熱門問題**] 區段中詳細說明特定偵測到的問題會影響，至少有 5%的受管理的裝置。 報告的詳細資料包括：

- 此類型的問題
    - 應用程式損毀，應用程式會停止運作或意外停止
    - 應用程式停止回應，其中的應用程式停止回應輸入
    - 嚴重錯誤，就會發生當發生此問題： 無法復原從 Windows。
- 受影響的同一個問題的裝置數目
- 數字代表的受管理裝置的百分比
- 特定問題數總計
- 問題的來源看起來軟體元件
- 偵測到問題的類別：
    - 瀏覽器 (Edge、 Chrome IE)
    - 未知 （非 Microsoft 元件）
    - 驅動程式 （音訊、 圖形或其他驅動程式）
    - 產能 （寬限時間，G Suite、 Microsoft Office 和其附加元件或擴充功能、 Teams）
    - 媒體 （影像、 等候音樂或視訊的應用程式
    - 安全性 （Windows 安全性元件）
- 為 Microsoft 受管理的桌上型電腦作業的目前狀態，進行調查和 remediates 問題

