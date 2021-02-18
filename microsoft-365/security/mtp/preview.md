---
title: Microsoft 365 Defender 中的預覽功能
description: 了解 Microsoft 365 安全性中心的新功能。
keywords: 預覽、全新、m365 安全性、安全性、365、功能
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1636b1deb5f35d8286b33238a8f4bbfff0b33521
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288122"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender 預覽功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> 預覽版本不會提供任何服務等級協定，不建議用於實際執行工作負載。 某些功能可能不受支援，或可能具有有限的功能。

適用於：
- Microsoft 365 Defender

Microsoft 365 Defender 服務會不斷更新，以包含新功能增強功能及功能。

深入瞭解 Microsoft 365 Defender preview 版中的新功能，並透過開啟預覽體驗，以嘗試即將推出的功能。

如需一般可用之新功能的詳細資訊，請參閱 [Microsoft 365 Defender 的新](whats-new.md)功能。

## <a name="required-permissions"></a>必要的權限

指派給下列 Azure Active Directory 的帳戶 (Azure AD) 角色可以開啟 Microsoft 365 Defender 預覽功能：

- 全域管理員
- 安全性系統管理員
- 安全性操作員

## <a name="turn-on-preview-features"></a>開啟預覽功能

您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。

開啟預覽體驗設定，成為第一批嘗試即將推出的功能的人。

1. 在功能窗格中，選取 **[設定]**。
2. 選取 [ **Microsoft 365 Defender**]。
3. 選取 **預覽功能** > **開啟預覽功能**。 
4. 選取 **[儲存]**。

當您看到 **[開啟預覽功能]** 核取方塊已選取時，您就會知道您已開啟預覽功能。 

## <a name="preview-features"></a>預覽功能

目前預覽版提供下列功能和增強功能：

### <a name="improved-microsoft-365-security-center"></a>改進的 Microsoft 365 安全中心
改良的 [Microsoft 365 安全性中心](https://security.microsoft.com)現在可供公開預覽。 這種新的經驗會將 Defender、Office 365 的 Defender、Microsoft 365 Defender 等，帶入 Microsoft 365 的安全性中心。 這是管理安全性控制的新家用。 [了解新功能](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。

- **[Microsoft 365 Defender 威脅分析報告](threat-analytics.md)** -威脅分析可協助您回應並將主動攻擊的影響降至最低。 您也可以瞭解 Microsoft 365 Defender 解決方案所封鎖的攻擊嘗試，並採取預防措施，緩解進一步披露及提高恢復的風險。 在統一的安全性體驗中，威脅分析現在可用於 Microsoft Defender for Endpoint 和 Microsoft Defender for Office E5 授權持有者。
- **[Microsoft 365 Defender APIs](api-overview.md)** -最上層的 Microsoft 365 Defender APIs 可讓您根據共用的事件和高級搜尋表格來自動化工作流程。 
- **[在高級搜尋中採取動作](advanced-hunting-take-action.md)**：快速包含威脅或您在 [ [高級搜尋](advanced-hunting-overview.md)] 中找到的受損資產。
- **[In 入口架構參考](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**-直接在「安全性中心」中取得高級搜尋架構表格的相關資訊。 除了資料表和欄描述之外，此參考還包含支援的事件種類 (`ActionType` 值) 和範例查詢。
- **[DeviceFromIP () 函數](advanced-hunting-devicefromip-function.md)**-取得在指定的時間範圍內，哪些裝置已被指派特定的 IP 位址或位址的相關資訊。
