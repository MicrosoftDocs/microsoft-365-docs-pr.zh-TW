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
description: 瞭解 Microsoft 365 eDiscovery 工具如何處理附加至電子郵件的加密檔，並儲存在 SharePoint Online 和商務用 OneDrive 中。
ms.openlocfilehash: b87d87b7b0e870d6f396d87dc693fb8f41d5826b
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750025"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 電子檔探索工具中的解密

加密是檔案保護和資訊保護原則的重要部分。 所有類型的組織都使用加密技術來保護組織內的敏感內容，並確保只有適當的人員可以存取該內容。

若要在加密內容上執行一般 eDiscovery 工作，請 ediscovery 管理員在從內容搜尋、核心 eDiscovery 案例和 Advanced eDiscovery 案例中匯出電子郵件內容時，必須加以解密。 在匯出內容之前，不會提供用 Microsoft 加密技術加密的內容供複查。

為了便於管理 eDiscovery 工作流程中的加密內容，Microsoft 365 ediscovery 工具現在會結合電子郵件所附加的加密檔案解密，並在 Exchange Online 中傳送。<sup>1</sup>此外，會在 Advanced eDiscovery 中解密 SharePoint 線上及商務用 OneDrive 中儲存的加密檔。

在此新功能之前，只會解密由 rights management (及未附加) 所保護的電子郵件內容。 在 eDiscovery 工作流程中無法解密 SharePoint 和 OneDrive 中的加密檔。 現在，使用 Microsoft 加密技術加密的檔案位於 SharePoint 或 OneDrive 帳戶，可在搜尋結果準備好預覽時進行搜尋和解密，並新增至 Advanced eDiscovery 中的審閱集，然後匯出。 此外，電子郵件所附加的 SharePoint 和 OneDrive 中的加密檔皆可供搜尋。 這項解密功能可讓 eDiscovery 管理員在預覽搜尋結果時，查看加密電子郵件附件和網站檔的內容，並在 Advanced eDiscovery 中將其新增至審閱集之後加以檢查。

## <a name="supported-encryption-technologies"></a>支援的加密技術

Microsoft eDiscovery 工具支援以 Microsoft 加密技術加密的專案。 這些技術是 Azure 版權管理和 Microsoft 資訊保護 (特別區分) 標籤。 如需 Microsoft 加密技術的相關資訊，請參閱 [encryption](encryption.md)。 不支援以協力廠商加密技術加密的內容。 例如，不支援預覽或匯出以非 Microsoft 技術加密的內容。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>支援加密專案的 eDiscovery 活動

下表識別在 SharePoint 和 OneDrive 中的電子郵件和加密檔所附加之加密檔案 Microsoft 365 eDiscovery 工具時，可執行檔支援工作。 在符合搜尋準則的加密檔上可以執行這些支援的工作。 值， `N/A` 表示在對應的 eDiscovery 工具中無法使用該功能。

|eDiscovery 任務  |內容搜尋  |核心電子文件探索  |進階電子文件探索  |
|:---------|:---------|:---------|:---------|
|在電子郵件和網站<sup>1</sup>中搜尋加密檔中的內容     |是      |是      |是      |
|預覽附加至電子郵件的加密檔     |是      |是     |是       |
|在 SharePoint 和 OneDrive 中預覽加密檔|否      |否    |是       |
|查看審閱集中的加密檔    |不適用      |不適用        | 是        |
|匯出附加至電子郵件的加密檔    |是       |是  |是    |
|在 SharePoint 和 OneDrive 中匯出加密檔    |否       |否  |是    |
|||||

> [!NOTE]
> <sup>1</sup>位於本機電腦上的加密檔案 (，但未儲存在 SharePoint 或 OneDrive 網站) 上，不會為 eDiscovery 編制索引。 這表示，如果加密的本機檔案附加至電子郵件訊息，即使檔案包含符合搜尋查詢的關鍵字，關鍵字搜尋查詢也不會傳回檔案。 不過，如果電子郵件屬性 (例如傳送日期、寄件者、收件者或主旨) 符合搜尋查詢，則 eDiscovery 搜尋可以傳回具有本機加密檔案的電子郵件。

### <a name="decryption-limitations-with-sensitivity-labels"></a>敏感度標籤的解密限制

eDiscovery 在使用下列任一設定設定套用加密的靈敏度標籤時，不支援 SharePoint 和 OneDrive 中的加密檔案：

- 使用者可以在手動將標籤套用至檔時，指派許可權。 這有時候稱為 *使用者定義的許可權*。

- 使用者對檔的存取權設定為 **永不** 超過某值的到期設定。

如需這些設定的詳細資訊，請參閱 [使用敏感度標籤來限制存取內容](encryption-sensitivity-labels.md#configure-encryption-settings)一節中的「設定加密設定」一節。

以先前的設定加密的檔仍可由 eDiscovery 搜尋傳回。 當檔案屬性 (例如標題、作者或修改日期) 符合搜尋準則時，可能會發生這種情況。 雖然這些檔可能會包含在搜尋結果中，但無法預覽或加以審閱。 在 Advanced eDiscovery 中匯出這些檔時，也會保持加密。

## <a name="requirements-for-decryption-in-ediscovery"></a>電子檔探索中解密的需求

您必須獲指派 RMS 解密角色，才能預覽、審閱及匯出使用 Microsoft 加密技術加密的檔案。 您也必須被指派此角色，以複查和查詢在 Advanced eDiscovery 中新增至審閱集的加密檔案。

預設會將此角色指派給 Office 365 安全性 & 規範中心的 [**許可權**] 頁面上的 [eDiscovery 管理員] 角色群組。 如需有關 RMS 解密角色的詳細資訊，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md#rms-decrypt)。
