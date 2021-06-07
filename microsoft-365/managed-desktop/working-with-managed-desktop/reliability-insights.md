---
title: 可靠深入解析
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739765"
---
# <a name="reliability-insights"></a>可靠深入解析

此視圖提供受管理裝置的健康情況摘要。 若要查看可靠性資料，請選取 [ **可靠性** ] 索引標籤。


![可靠性窗格：左上方各裝置的可靠性、右上方的可靠性，右上方的 [最大問題] 表格。 右下方的說明和意見反應按鈕。](../../media/insights_reliability.png)

[ **各裝置的可靠性** ] 區段透過報告視為「狀況良好」的裝置百分比，以及自上次報告失敗後所觀測的平均時間，提供您部署在過去14天內的快速狀況摘要。 

 
右側的 **可靠性隨時間** 圖表會報告發生嚴重錯誤的裝置數量，以及觀測的嚴重錯誤總數。

**最上層的問題** 一節將詳細說明會影響至少5% 受管理裝置之特定偵測到的問題。 報告的詳細資料包括：

- 問題類型
    - 應用程式崩潰，應用程式停止運作或意外停止
    - 應用程式懸掛，應用程式停止回應輸入
    - 嚴重錯誤，當 Windows 發生無法復原的問題時，就會發生此錯誤。
- 受相同問題影響的裝置數目
- 代表數目的受管理裝置百分比
- 特定問題發生的總次數
- 似乎是問題來源的軟體元件
- 偵測到之問題的類別：
    - 瀏覽器 (Edge、Chrome、IE) 
    - 未知的 (非 Microsoft 元件) 
    - 驅動程式 (音訊、圖形或其他驅動程式) 
    - 生產力 (寬限時間、G-套件、Microsoft Office 及其附加元件或分機，Teams) 
    - 媒體 (影像、音樂或影片應用程式
    - 安全性 (Windows 安全性元件) 
- 目前的狀態 Microsoft 受管理的電腦作業調查並 remediates 問題

