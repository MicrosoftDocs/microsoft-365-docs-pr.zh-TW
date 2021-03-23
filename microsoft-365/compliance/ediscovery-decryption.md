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
description: 瞭解 Microsoft 365 電子檔探索工具如何處理附加至電子郵件的加密檔，並儲存在 SharePoint 線上和商務 OneDrive 中。
ms.openlocfilehash: ad7ee9816e83caa49e437e1723655162a44c93fa
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034066"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 eDiscovery tools 中的解密

加密是檔案保護和資訊保護原則的重要部分。 所有類型的組織都使用加密技術來保護組織內的敏感內容，並確保只有適當的人員可以存取該內容。

若要在加密內容上執行一般 eDiscovery 工作，請 eDiscovery 管理員在從內容搜尋、核心 eDiscovery 案例及高級 eDiscovery 案例中匯出電子郵件內容時，必須加以解密。 在匯出內容之前，不會提供用 Microsoft 加密技術加密的內容供複查。

為了讓您更容易管理 eDiscovery 工作流程中的加密內容，Microsoft 365 eDiscovery 工具現在整合了附加至電子郵件訊息並在 Exchange Online 中傳送的加密檔解密。 此外，儲存在 SharePoint 線上和商務 OneDrive 中的加密檔會在「高級 eDiscovery」中解密。

在此新功能之前，只會解密由 rights management (及未附加) 所保護的電子郵件內容。 在 eDiscovery 工作流程中無法解密 SharePoint 和 OneDrive 中的加密檔。 現在，如果以 Microsoft 加密技術加密的檔案是附加到電子郵件訊息或是位於 SharePoint 或 OneDrive 帳戶上，當搜尋結果準備好供預覽時，就會解密這些加密的專案，並將其新增至高級 eDiscovery 中的審閱集，然後匯出。 這可讓 eDiscovery 管理員在預覽搜尋結果時，查看加密電子郵件附件和網站檔的內容，並在將其新增至高級 eDiscovery 中的審閱集之後加以複查。

## <a name="supported-encryption-technologies"></a>支援的加密技術

Microsoft eDiscovery 工具支援以 Microsoft 加密技術加密的專案。 這些技術是 Azure 版權管理和 Microsoft 資訊保護 (特別區分) 標籤。 如需 Microsoft 加密技術的相關資訊，請參閱 [encryption](encryption.md)。 不支援以協力廠商加密技術加密的內容。 例如，不支援預覽或匯出以非 Microsoft 技術加密的內容。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>支援加密專案的 eDiscovery 活動

下表識別可在 Microsoft 365 eDiscovery tools 中對電子郵件和加密檔（SharePoint 和 OneDrive 中的加密檔）所執行的支援工作。 在符合搜尋準則的加密檔上可以執行這些支援的工作。 值， `N/A` 表示在對應的 eDiscovery 工具中無法使用該功能。

|eDiscovery 任務  |內容搜尋  |核心電子文件探索  |進階電子文件探索  |
|:---------|:---------|:---------|:---------|
|在電子郵件和網站中搜尋加密檔中的內容     |是      |是      |是      |
|預覽附加至電子郵件的加密檔     |是      |是     |是       |
|在 SharePoint 和 OneDrive 中預覽加密檔|否      |否    |是       |
|查看審閱集中的加密檔    |不適用      |不適用        | 是        |
|匯出附加至電子郵件的加密檔    |是       |是  |是    |
|在 SharePoint 和 OneDrive 中匯出加密檔    |否       |否  |是    |
|||||

**附注：** eDiscovery 不支援 SharePoint 和 OneDrive 中的加密檔案，當套用加密的靈敏度標籤是以下列任一設定進行設定時：

- 使用者可以在手動將標籤套用至檔時，指派許可權。 這有時候稱為 *使用者定義的許可權*。<br/>

- 使用者對檔的存取權設定為 **永不** 超過某值的到期設定。

如需這些設定的詳細資訊，請參閱 [使用敏感度標籤來限制存取內容](encryption-sensitivity-labels.md#configure-encryption-settings)一節中的「設定加密設定」一節。

以先前的設定加密的檔仍可由 eDiscovery 搜尋傳回。 當檔案屬性 (例如標題、作者或修改日期) 符合搜尋準則時，可能會發生這種情況。 雖然這些檔可能會包含在搜尋結果中，但無法預覽或加以審閱。 在 [高級 eDiscovery] 中匯出這些檔時，這些檔也會保持加密。

## <a name="requirements-for-decryption-in-ediscovery"></a>電子檔探索中解密的需求

您必須獲指派 RMS 解密角色，才能預覽、審閱及匯出使用 Microsoft 加密技術加密的檔案。 您也必須被指派此角色，以複查和查詢在高級 eDiscovery 中新增至審閱集的加密檔。

預設會將此角色指派給 Office 365 Security & 合規性中心的 [ **許可權** ] 頁面上的 [eDiscovery 管理員] 角色群組。 如需有關 RMS 解密角色的詳細資訊，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md#rms-decrypt)。
