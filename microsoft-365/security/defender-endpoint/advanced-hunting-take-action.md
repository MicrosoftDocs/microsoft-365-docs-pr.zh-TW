---
title: 在 Microsoft 威脅防護中對高級搜尋查詢結果採取動作
description: 在您的高級搜尋查詢結果中快速處理威脅與受影響的資產
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、自訂偵測、架構、kusto、避免超時、命令列、進程識別碼
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: d1dbe226cef5e94b36fcd6c35b839118b200f85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500528"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>對高級搜尋查詢結果採取動作

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

您可以使用強大且全面的動作選項，快速包含威脅或使用您在 [高級搜尋](advanced-hunting-overview.md) 中所發現的受損資產。 使用這些選項，您可以：

- 在裝置上執行各種動作
- 隔離檔

## <a name="required-permissions"></a>必要權限

若要透過「高級搜尋」採取行動，您需要具有在 [裝置上提交修正動作之許可權](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options)的「在 Defender」中的角色。 如果您無法採取行動，請洽詢全域管理員以取得下列許可權：

*使用中修復的動作 > 威脅和弱點管理-修正處理*

## <a name="take-various-actions-on-devices"></a>在裝置上執行各種動作

您可以在查詢結果中對欄所識別的裝置採取下列動作 `DeviceId` ：

- 隔離受影響的裝置以包含感染或防止攻擊移動橫向
- 收集調查套件以取得更多鑒證資訊
- 執行防病毒掃描，以利用最新的安全性情報更新來尋找並移除威脅
- 啟動自動調查以檢查和修正裝置上的威脅，以及可能受影響的裝置
- 將應用程式執行限制為僅限 Microsoft 簽署的可執行檔，以透過惡意程式碼或其他不可信的可執行檔進行後續的威脅

若要深入瞭解如何透過 Defender for Endpoint 執行這些回應動作，請 [閱讀裝置上的回應動作](respond-machine-alerts.md)。

## <a name="quarantine-files"></a>隔離檔

您可以在檔案上部署 *隔離* 動作，使其在遇到時自動隔離。 選取此動作時，您可以選擇下列各欄，以識別要隔離的查詢結果中的檔案：

- `SHA1` —在大多數高級搜尋表格中，這是受錄製動作所影響的檔案 SHA-1。 例如，如果複製檔案，這會是複製的檔案。
- `InitiatingProcessSHA1` —在大多數高級搜尋表格中，這是負責初始化錄製的動作的檔案。 例如，如果子流程已啟動，這會是父進程。 
- `SHA256` -這是欄所識別之檔案的 SHA-256 對等專案 `SHA1` 。
- `InitiatingProcessSHA256` -這是欄所識別之檔案的 SHA-256 對等專案 `InitiatingProcessSHA1` 。

若要深入瞭解如何採取隔離動作和還原檔案，請 [參閱檔案的回應動作](respond-file-alerts.md)。

>[!NOTE]
>若要尋找並隔離檔案，查詢結果也應包含 `DeviceId` 設備識別碼的值。  

## <a name="take-action"></a>採取動作

若要採取任何說明的動作，請在查詢結果中選取一或多筆記錄，然後選取 [ **採取動作**]。 嚮導會引導您完成選取及提交您偏好動作的程式。

![具有檢查記錄之面板之選取記錄的影像](images/ah-take-actions.png)

## <a name="review-actions-taken"></a>審閱採取的動作

每個動作會個別記錄在 [動作中心] 的 [**動作 (中心**]  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)) 中。 移至 [行動中心]，檢查每個動作的狀態。
 
## <a name="related-topics"></a>相關主題

- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [自訂偵測概觀](overview-custom-detections.md)
