---
title: 在 Microsoft 365 Defender 中對進一步搜尋查詢結果採取行動
description: 在進位搜尋查詢結果中快速處理威脅和受影響的資產
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、採取行動
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932175"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>進一步搜尋查詢結果採取行動

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

您可以使用強大且完整的動作選項，快速包含威脅或位址在進[](advanced-hunting-overview.md)一步搜尋時發現被入侵的資產。 使用這些選項，您可以：

- 在裝置上採取各種動作
- 隔離檔案

## <a name="required-permissions"></a>必要的權限
為了能夠透過進一步搜尋採取行動，您需要 Microsoft Defender for Endpoint 中具有許可權的角色，以在裝置上提交 [補救動作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。 如果您無法採取行動，請聯絡全域系統管理員以取得下列許可權：

*威脅和>管理的行動補救動作 - 補救處理*

## <a name="take-various-actions-on-devices"></a>在裝置上採取各種動作
您可以在查詢結果中欄所識別的裝置 `DeviceId` 上執行下列動作：

- 隔離受影響的裝置以包含感染，或防止攻擊之後移動
- 收集調查套件以取得更多的資訊
- 使用最新的安全性智慧更新執行防毒軟體掃描來尋找和移除威脅
- 啟動自動化調查以檢查並修復裝置上的威脅，以及可能的其他受影響的裝置
- 將應用程式執行限制為只有 Microsoft 簽署的可執行檔，透過惡意程式碼或其他不受信任的可執行檔防止後續的威脅活動

若要進一步瞭解如何透過 Microsoft Defender for Endpoint 執行這些回應動作，請閱讀 [有關裝置上回應動作的資訊](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。
   
## <a name="quarantine-files"></a>隔離檔案
您可以對檔案 *部署* 隔離動作，讓檔案在遇到時自動隔離。 選取此動作時，您可以選擇下列兩欄以識別要隔離查詢結果中的哪些檔案：

- `SHA1` — 在大部分進一步搜尋資料表中，這是受到錄製動作影響之檔案的 SHA-1。 例如，如果複製了檔案，這會是複製的檔案。
- `InitiatingProcessSHA1` — 在大部分進步搜尋資料表中，這個檔案負責啟動錄製的動作。 例如，如果啟動副程式，則此為父程式。 
- `SHA256` — 這是資料行所識別之檔案的 SHA-256 相等 `SHA1` 值。
- `InitiatingProcessSHA256` — 這是資料行所識別之檔案的 SHA-256 相等 `InitiatingProcessSHA1` 值。

若要深入瞭解如何執行隔離動作及如何還原檔案，請閱讀[有關檔案的回應動作。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>若要找出檔案並隔離這些檔案，查詢結果也應包含值 `DeviceId` 做為裝置識別碼。  

## <a name="take-action"></a>採取行動
若要執行任何描述的動作，請在查詢結果中選取一或多則記錄，然後選取執行 **動作**。 精靈會引導您完成選取並提交您偏好的動作。

![選取的記錄影像，以及用於檢查記錄的面板](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>已執行審查動作
每個動作會個別記錄在控制中心的控制中心 [](mtp-action-center.md)的歷程記錄  >  **** [ (security.microsoft.com/action-center/history) 。](https://security.microsoft.com/action-center/history) 請前往控制中心，檢查每個動作的狀態。
 
## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [控制中心概觀](mtp-action-center.md)
