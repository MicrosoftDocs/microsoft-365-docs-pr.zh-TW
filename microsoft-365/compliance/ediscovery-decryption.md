---
title: EDiscovery 中的解密
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解 Microsoft 365 電子檔探索工具如何處理附加至電子郵件的加密檔。
ms.openlocfilehash: 89e6457015289055c56278f5f8650ce022ecf081
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920706"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 eDiscovery tools 中的解密

組織使用加密技術來保護組織內的敏感內容，並確保只有適當的人員可以存取該內容。 組織會使用各種類型的加密，這兩種都是 Microsoft 加密技術和協力廠商的技術，以符合安全性需求及保護其機密資訊。

迄今為止，在 Microsoft 365 中的 eDiscovery 工作流程中管理加密的內容，需要根據所使用的加密類型和工作流程中的特定階段，以特殊方式處理加密的專案。 這主要是在從內容搜尋、核心 eDiscovery 案例及高級 eDiscovery 案例中匯出電子郵件內容時進行解密。 在匯出內容之前，無法預覽以 Microsoft 加密技術加密的內容。 在 [Advanced eDiscovery] 中，已使用處理錯誤來標記加密內容，這需要您下載加密的專案，解密它，然後將解密的檔案上傳至審閱集。

為了讓您更容易管理 eDiscovery 工作流程中的加密內容，Microsoft 365 eDiscovery 工具可以解密已附加到電子郵件的加密檔案，並在 Exchange Online 中傳送。 在此新功能之前，只會解密由 rights management (及未附加) 所保護的電子郵件內容。 現在，如果以 Microsoft 加密技術加密的檔案附加至符合搜尋準則的電子郵件，當搜尋結果準備好進行預覽時，就會解密加密的檔案。 這可讓 eDiscovery 管理員在預覽搜尋結果時，查看加密電子郵件附件的內容。

> [!NOTE]
> 從2021年1月開始，Microsoft 365 eDiscovery 工具將支援 SharePoint 線上和商務 OneDrive 中儲存的加密檔。

## <a name="supported-encryption-technologies"></a>支援的加密技術

Microsoft eDiscovery 工具支援以 Microsoft 加密技術加密的專案。 這些技術包括 Office 郵件加密、Microsoft 資訊保護 (敏感度標籤) 和 Azure Rights Management。 如需 Microsoft 加密技術的相關資訊，請參閱 [encryption](encryption.md)。 不支援以協力廠商加密技術加密的內容。 這包括預覽或匯出以非 Microsoft 技術加密的內容時不支援。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>支援加密專案的 eDiscovery 活動

下表列出在 Microsoft 365 eDiscovery 工具中執行的工作，這些工具可支援電子郵件 massages 所附加的加密檔案解密。 支援工作可以在附加至符合搜尋準則之電子郵件的加密檔案上執行。 "N/A" 的值表示該功能在對應的 eDiscovery 工具中不可用。

|eDiscovery 任務  |內容搜尋  |核心電子文件探索  |進階電子文件探索  |
|:---------|:---------|:---------|:---------|
|搜尋加密檔中的內容     |否      |否      |否      |
|預覽加密檔     |是      |是     |是       |
|查看審閱集中的加密檔    |不適用      |不適用        | 是        |
|匯出加密檔    |是       |是  |是    |

## <a name="requirements-for-decryption-in-ediscovery"></a>電子檔探索中解密的需求

您必須獲指派 RMS 解密角色，才能預覽、審閱及匯出以 Microsoft 加密技術加密的附加檔案。 您也必須被指派此角色，以複查和查詢在高級 eDiscovery 中新增至審閱集的加密電子郵件附件。

預設會將此角色指派給 Office 365 Security & 合規性中心內的 eDiscovery 管理員角色群組。 如需有關 RMS 解密角色的詳細資訊，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md#rms-decrypt)。
