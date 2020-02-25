---
title: Windows 安全性更新深入解析
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 600491fbdd70315385587eb8cb443a1696c3bee6
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254587"
---
# <a name="windows-security-update-insights"></a>Windows 安全性更新深入解析
此檢視提供您的 Microsoft 受管理的電腦裝置概觀安全性更新的狀態。 

若要檢視流量資料，請選取 [ <strong>Windows 安全性更新</strong>] 索引標籤。

![Windows 安全性更新窗格： 長條圖的裝置狀態及更新版本，在左邊的欄中，更新經過一段時間在中心] 欄中和百分比的作用中裝置的部署] 群組中，部署進度以及採取到達 95%部署的天數在右邊欄位中的目標。](../../media/update-insights.jpg)

## <a name="device-status"></a>裝置狀態

裝置更新的 Windows 更新，它們必須連線至網際網路，不休眠至少六個小時，其中兩個必須是連續範圍。 只要裝置已連線且未休眠，它已被視為 」 中使用。 」 雖然很可能不符合這些需求的裝置將會更新，滿足它們的裝置必須要更新的最高的可能性。 

我們分類與這些字詞的 Windows 更新的內容中的裝置活動：

- <strong>作用中：</strong>您必須符合最新的安全性更新版本的最低流量準則 （六個小時，兩個連續） 和簽入 Microsoft Intune 至少每隔五天的裝置
- <strong>同步處理：</strong>最後一個 28 天內簽入 Intune 裝置
- <strong>同步處理超出</strong>– 裝置已<i>不</i>使用 Intune 簽入 28 天內




## <a name="update-version-status"></a>更新的版本狀態

Microsoft 發行月份中的每個第二個星期二的安全性更新。 每個版本會新增已知的安全性弱點的重要更新。 Microsoft 受管理的電腦可確保 95%的受管理的裝置會以最新可用的安全性更新每月更新。 在其他時候緊急地址新威脅有時發行安全性更新。 Microsoft 受管理電腦部署方式都很類似這些更新。

我們分類與這些字詞的安全性更新版本的狀態：

- <strong>目前：</strong>正在執行中的目前月份發行的更新的裝置
- <strong>先前：</strong>執行於上個月發行更新的裝置
- <strong>舊：</strong>執行前一個月之前發行任何安全性更新的裝置

您應該會看到一些裝置的<strong>較舊</strong>類別中-大型或可能得母體指出，因此我們可以調查，您應該報告至 Microsoft 受管理電腦的系統問題。


## <a name="deployment-progress"></a>部署進度

起點處的每個安全性更新發行週期，Microsoft 受管理的電腦會採用裝置母群體的快照集，並在 95%的該母體設定它的部署目標。 <strong>部署進度</strong>區域顯示的歷史趨勢，更新每日、 追蹤更新部署符合此目標，針對每個版本的程度。 此圖只會顯示作用中狀態的裝置。

您可以使用下拉式清單功能表右上角，先前的更新週期檢視此資料。 您在此功能表中選取的期間套用於所有的整個頁面上的資訊。

<strong>已更新使用中的裝置部署群組</strong>] 區域中所示的進度更新安裝 Microsoft 受管理電腦部署群組的每個提供不同的檢視。

<strong>天的時間可以達到目標</strong>區域會顯示所需的時間 95%的裝置總數以更新目前的安全性更新。 雖然部署正在進行中，此區域會顯示<strong>仍更新</strong>直到 95%目標到達所選更新。

## <a name="device-details-area"></a>裝置詳細資料] 區域

儀表板底部是表格顯示您的裝置，包括[裝置狀態](#device-status)和[更新版本狀態](#update-version-status)的詳細的資訊。 您可以搜尋這份清單或篩選所列出的任何值。


![顯示的裝置名稱、 指派的使用者、 裝置狀態、 更新版本、 作業系統版本，以及日期欄上次同步處理之裝置的裝置詳細資料表格。](../../media/security-update-insights-device-table-sterile.png)