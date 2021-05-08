---
title: 疑難排解 Microsoft Defender AV 報告工具的問題
description: 在更新規範中嘗試以 Microsoft Defender AV 保護狀態報表時，識別並解決常見問題
keywords: 疑難排解，錯誤，修正，更新規範，oms，監視器，報表，Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ca62db922a13ab2cb3226eaf0efb92bfaf8c572b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274889"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>疑難排解更新合規性中的 Microsoft Defender 防毒軟體報告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> 2020年3月31日，將會移除更新規範的 Microsoft Defender 防毒軟體報告功能。 您可以繼續使用[Microsoft 端點管理員](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)來定義及檢查安全性符合性原則，這可讓您更精細地控制安全性功能和更新。

您可以使用具有更新規範的 Microsoft Defender 防毒軟體。 您將會看到 E3、B、F1、VL 和 Pro 授權的狀態。 不過，對於 E5 授權，您必須使用 [Microsoft Defender For Endpoint 入口網站](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。 若要深入瞭解授權選項，請參閱[Windows 10 產品授權選項](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)。

當您使用 Windows Analytics 更新合規性，以在您的網路中使用 Microsoft Defender 防毒軟體[來取得裝置或端點的保護狀態](/windows/deployment/update/update-compliance-using#wdav-assessment)時，可能會發生問題或問題。

一般來說，問題最常見的指示器如下：
- 您只會看到您期望看到之所有裝置的小數位或子集
- 您沒有看到任何裝置
- 您所看到的報告和資訊已過時 (數天內) 

如需與更新規範不相關之 Microsoft Defender 防毒軟體服務相關的常見錯誤代碼和事件 IDs，請參閱[Microsoft Defender 防毒軟體事件](troubleshoot-microsoft-defender-antivirus.md)。 

針對這些問題進行疑難排解有三個步驟：

1. 確認您已符合所有必要條件
2. 檢查您與 Windows Defender 雲端架構服務的連線能力
3. 提交支援記錄檔

>[!IMPORTANT]
>裝置開始出現的3天內，會出現更新規範。


## <a name="confirm-prerequisites"></a>確認必要條件

為了讓裝置能夠正確顯示更新規範，您必須符合更新規範服務和 Microsoft Defender 防毒軟體的特定必要條件：

>[!div class="checklist"]
>- 端點使用 Microsoft Defender 防毒軟體作為獨立的防防毒保護應用程式。 [使用任何其他防病毒應用程式會使 Microsoft DEFENDER AV 自行停用](microsoft-defender-antivirus-compatibility.md) ，而且不會在更新規範中報告端點。
> - [已啟用雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)功能。
> - 端點可以 [連接至 Microsoft DEFENDER AV 雲端](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - 如果端點執行 Windows 10 版本1607或更舊版本，則[必須將 Windows 10 診斷資料設定為增強的層級](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。
> - 由於已符合所有需求，因此已完成3天

「您可以搭配更新規範使用 Microsoft Defender 防毒軟體。 您將會看到 E3、B、F1、VL 和 Pro 授權的狀態。 不過，對於 E5 授權，您必須使用 Microsoft Defender for Endpoint 入口網站 (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) 。 若要深入瞭解授權選項，請參閱 Windows 10 產品授權選項 "。

若上述必要條件皆已符合，您可能需要繼續進行下一個步驟，以收集診斷資訊並傳送給我們。

> [!div class="nextstepaction"]
> [收集診斷資料以進行更新規範疑難排解](collect-diagnostic-data.md)  

## <a name="related-topics"></a>相關主題

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
- [部署 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)