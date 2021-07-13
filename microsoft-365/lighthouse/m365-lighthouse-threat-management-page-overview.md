---
title: Microsoft 365 Lighthouse威脅管理頁面概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 針對受管理的服務提供者 (MSPs) 使用 Microsoft 365 Lighthouse，瞭解 [威脅管理] 頁面。
ms.openlocfilehash: 10f39737bb69f4a5080b343cfbe6c6cfe5908d72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395046"
---
# <a name="microsoft-365-lighthouse-threat-management-page-overview"></a>Microsoft 365 Lighthouse威脅管理頁面概述 

> [!NOTE]
> 本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。 如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

**適用於：**

- Windows 10

Microsoft Defender 防毒軟體保護租使用者和裝置免受軟體威脅（包括病毒、惡意程式碼和間諜軟體威脅）。 它是強大且持續進行的保護，可納入 Windows 10 並包含 Microsoft 365 商務進階版中。  
  
若要存取 Microsoft 365 Lighthouse 中的 [威脅管理] 頁面，請選取左導覽窗格中的 [**威脅管理**]，以查看承租人對威脅的安全性狀態。 您將會看到需要您注意的承租人、使用者和裝置，以及可協助您降低風險的建議。  
  
## <a name="overview-tab"></a>概覽] 索引標籤  
  
在 [威脅管理] 頁面的 [一覽] 索引標籤上，您可以監視所有承租人的防病毒狀態，以找出需要注意的區域。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="[一覽] 索引標籤的螢幕擷取畫面。 >。":::

## <a name="threats-tab"></a>威脅] 索引標籤

在 [威脅管理] 頁面的 [威脅] 索引標籤上，您可以查看所有承租人的作用中、已緩解、已解決及允許的威脅。 您也可以透過篩選並深入查看每個威脅，以瞭解影響哪些裝置、使用者或租使用者，以在所有承租人間同時修復多個威脅。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="預設基線頁面的螢幕擷取畫面。 >。":::
  
您可以依下列方式篩選威脅：

- 威脅狀態
- 威脅嚴重性
- 威脅類型
- 日期範圍

下表列出不同威脅狀態及其定義：<br><br>

| 威脅狀態 | 定義 |
|--|--|
| 作用中 | 裝置上的威脅為作用中狀態。 |
| 無狀態 | 威脅狀態無法使用。 在裝置上執行完整掃描，使 Microsoft Defender 防毒軟體重新檢查威脅。 |
| 動作失敗 | 裝置沒有危險。 動作失敗，但裝置上的潛在威脅已停止，且未在使用中狀態。 在裝置上執行完整掃描。 |
| 需要手動步驟 | 威脅已停止，但需要手動步驟完成，例如完整掃描或裝置重新開機。 |
| 需要完整掃描 | 需要完整掃描裝置。 |
| 需要重新開機 | 需要重新開機裝置。 |
| 修正非嚴重失敗 | 威脅已經修正，不需要進行進一步的動作。 |
| 隔離 | 已隔離威脅。 不需要進一步的動作。 |
| 已移除 | 已從裝置成功移除威脅。 不需要進一步的動作。 |
| 打掃 | Microsoft Defender 防毒軟體已復原和 disinfected 檔案。 不需要進一步的動作。 |
| 允許 | 系統管理員可以在裝置上保留威脅。 | 

## <a name="antivirus-protection-tab"></a>防防毒保護] 索引標籤

[威脅管理] 頁面上的 [防病毒防護] 索引標籤會顯示所有承租人和其 Microsoft Defender 防毒軟體保護狀態中的裝置。 您可以評估狀態，並對一或多個可能易受到攻擊的裝置採取動作。 您也可以選取裝置以查看詳細資訊，例如裝置概述、目前的威脅和裝置動作狀態。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="[防病毒] 索引標籤的螢幕擷取畫面。":::

## <a name="related-content"></a>相關內容

 (文章[部署 Microsoft 365 Lighthouse 基線](m365-lighthouse-deploy-baselines.md)) 
[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) 
