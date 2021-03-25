---
title: Windows 中的資訊保護概述
ms.reviewer: ''
description: 深入瞭解資訊保護如何在 Windows 中運作，以識別及保護機密資訊
keywords: 資訊、保護、dlp、資料、遺失、防護、保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 733f86ed48b9cc7a68fb0cd346c7b15fdcc3ce65
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187502"
---
# <a name="information-protection-in-windows-overview"></a>Windows 中的資訊保護概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

資訊保護是 Microsoft 365 企業版套件不可或缺的一部分，提供智慧防護以保持敏感性資料安全，同時在工作場所中啟用生產力。


>[!TIP]
> 閱讀我們的博客文章 [，瞭解 Microsoft DEFENDER ATP 如何與 Microsoft 資訊保護整合，以探索、保護及監視 Windows 裝置上的敏感性資料](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)。

Defender for Endpoint 套用下列方法來探索、分類及保護資料：

- **資料探索** -識別 Windows 裝置上的敏感性資料時面臨危險
- **資料分類** -根據 Office 365 安全性 & 規範中心中所管理的常見 Microsoft 資訊保護 (MIP) 原則，自動分類資料。 自動分類可讓您保護機密資料，即使使用者未手動分類也是如此。


## <a name="data-discovery-and-data-classification"></a>資料探索和資料分類

Defender for Endpoint 會自動探索具有敏感度標籤的檔案，以及包含機密資訊類型的檔案。

敏感度標籤會分類並協助保護機密內容。

Office 365 資料遺失防護中的機密資訊類型 (DLP) 實施分為兩類：

- 預設
- 自訂

預設的機密資訊類型包括銀行帳戶號碼、社會保險號碼或國內 IDs 等資訊。 如需詳細資訊，請參閱 [敏感資訊類型的外觀](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for)。

自訂類型是您定義的，其設計目的是為了保護不同類型的敏感資訊 (例如，員工 IDs 或專案編號) 。 如需詳細資訊，請參閱 [建立自訂機密資訊類型](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)。

當您在 Windows 裝置上建立或編輯檔案時，當其包含機密資訊時，資料端點的 Defender 會掃描要評估的內容。

開啟 Azure 資訊保護整合，這樣一來，當以標籤或資訊類型為端點發現包含機密資訊的檔案時，它會自動轉送到裝置的 Azure 資訊保護。

![使用 Azure 資訊保護的 [設定] 頁面的圖像](images/atp-settings-aip.png)

您可以在 Azure 資訊保護–資料探索儀表板上查看報告的信號。

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure 資訊保護-資料探索儀表板

此儀表板會顯示由 Defender for Endpoint 和 Azure 資訊保護所探索之資料的摘要探索資訊。 來自于端點的資料會以位置類型-端點標示。

![Azure 資訊保護的影像-資料探索](images/azure-data-discovery.png)

請注意，右側的 [裝置風險] 欄是指直接從 Endpoint 取得此裝置風險，指出已探索該檔案的安全性裝置風險層級，其依據是由 Defender for Endpoint 所偵測到的作用中安全性威脅。

按一下裝置以查看此裝置上所看到之檔案的清單，其靈敏度標籤和資訊類型。

>[!NOTE]
>請等待大約15-20 分鐘，Azure 資訊保護儀表板探索才能反映已發現的檔案。

## <a name="log-analytics"></a>記錄分析

您也可以在 [Azure 記錄分析](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)中使用以 Defender 做為基礎的資料探索，您可以在原始資料上執行複雜的查詢。

如需 Azure 資訊保護分析的詳細資訊，請參閱 [適用于 Azure 資訊保護的中央報告](https://docs.microsoft.com/azure/information-protection/reports-aip)。

在 Azure 入口網站中開啟 Azure 記錄分析，並在 standard 或古典) 中開啟查詢產生器 (。

若要查看 Defender 的端點資料，請執行包含下列專案的查詢：

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

**必要條件：**

- 客戶必須具備 Azure 資訊保護的訂閱。
- 在 Microsoft Defender Security Center 中啟用 Azure 資訊保護整合：
    - 移至 Microsoft Defender Security Center 中的 [**設定**]，按一下 **[一般**] 下的 [**高級設定**]。



