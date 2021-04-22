---
title: 為適用於端點的 Microsoft Defender 服務問題疑難排解
description: 尋找已知問題（如嘗試存取服務時的伺服器錯誤）的解決方案和解決方法。
keywords: 疑難排解 Microsoft Defender 的端點、伺服器錯誤、存取權被拒絕、不正確認證、沒有資料、儀表板入口網站、允許、事件檢視器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 81f1b4154de25f6186679adc5b1f24f78f302415
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933754"
---
# <a name="troubleshoot-service-issues"></a>為服務問題疑難排解

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


本節說明當您使用 Microsoft Defender Advanced 威脅服務時可能會發生的問題。

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>伺服器錯誤-存取因認證無效而遭到拒絕
如果您嘗試存取服務時發生伺服器錯誤，您必須變更瀏覽器 cookie 設定。
設定您的瀏覽器以允許 cookie。

## <a name="elements-or-data-missing-on-the-portal"></a>入口網站上遺失的元素或資料
如果 Microsoft Defender Security Center 上的某些元素或資料遺失，表示 proxy 設定可以封鎖。

請確定 `*.securitycenter.windows.com` 已包含 proxy allowlist。


> [!NOTE]
> 新增下列端點時，您必須使用 HTTPS 通訊協定。

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Microsoft Defender for Endpoint service 會在事件檢視器中顯示事件或錯誤記錄檔

請參閱 [使用事件檢視器查看事件與錯誤](event-error-codes.md) ，以取得 Microsoft Defender for Endpoint service 所報告的事件 IDs 清單。 本文也包含事件錯誤的疑難排解步驟。

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>重新開機後，Microsoft Defender for Endpoint service 無法啟動，並顯示錯誤577

如果已成功完成上架裝置，但是在重新開機後，Microsoft Defender for Endpoint 不會啟動，並顯示錯誤577，請檢查 Windows Defender 未由原則停用。

如需詳細資訊，請參閱 [確定原則未停用 Microsoft Defender 防病毒](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。

## <a name="known-issues-with-regional-formats"></a>地區格式的已知問題

**日期和時間格式**<br>
時間和日期格式有一些已知的問題。 

支援下列日期格式：
- MM/dd/yyyy
- dd/MM/yyyy

目前不支援下列日期和時間格式：
- 日期格式 yyyy/MM/dd
- 日期格式 dd/MM/yy
- 日期格式（yy）。 只會顯示 yyyy。
- 時間格式不支援 HH： mm： ss (12 小時 AM/PM 格式不受支援) 。 只支援24小時格式。

**使用逗號表示千位數**<br>
不支援使用逗點做為數位中的分隔符號。 當地區以逗號隔開以表示一千時，將只會看到使用點做為分隔字元。 例如，15，「15.5 K」會顯示為 K。

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>已在歐洲自動建立 Microsoft Defender for Endpoint 租使用者
當您使用 Azure Defender 監視伺服器時，會自動建立 Microsoft Defender for Endpoint 租使用者。 Microsoft Defender for Endpoint data 預設會儲存在歐洲。





## <a name="related-topics"></a>相關主題
- [疑難排解 Microsoft Defender 的端點上架問題](troubleshoot-onboarding.md)
- [使用事件檢視器審閱事件和錯誤](event-error-codes.md)
