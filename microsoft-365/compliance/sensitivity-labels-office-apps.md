---
title: 在 Office 應用程式中使用敏感度標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 深入瞭解使用者如何使用 Office 應用程式中的敏感度標籤、適用于行動裝置的 Office 應用程式，以及適用于 web 的 Office 應用程式。 瞭解哪些應用程式支援靈敏度標籤。
ms.openlocfilehash: 858d2be23dcb3c3f2b0794e735ed8ca61d67b74d
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634211"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>在 Office 應用程式中使用敏感度標籤

當您從 Microsoft 365 規範中心或同等標籤中心[發行](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)敏感度標籤時，會開始出現在 Office 應用程式中，讓使用者在建立或編輯資料時進行分類及保護。

使用本文中的資訊，協助您在 Office app 中成功管理敏感度標籤。 例如，識別支援內建標籤所需的應用程式最少版本，並瞭解與 Azure 資訊保護整合標籤用戶端的互動，以及與其他應用程式和服務的相容性。

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>敏感度標籤的訂閱與授權需求

使用者必須至少有一個指派的下列授權：

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)或更新版本

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software)或更新版本

- [Azure 資訊保護高級 P1](https://azure.microsoft.com/pricing/details/information-protection/)或以上版本

Office 內建的標籤用戶端支援具有 Office 訂閱版本的靈敏度標籤。 這項標籤用戶端不支援獨立版本的 Office，例如 Office 2016 或 Office 2019。 若要在 Windows 電腦上使用具有這些 Office 版本的靈敏度標籤，請安裝 Azure 資訊保護統一的標籤用戶端。

若要使用自動或建議的敏感度標記，您的使用者需要下列其中一個授權：

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)或以上版本

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software)或更新版本

- [Azure 資訊保護高級 P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>支援應用程式中的靈敏度標籤功能

針對每項功能，下列各表列出該應用程式所需的最低版本，以支援使用內建標記的靈敏度標籤。 或者，如果標籤功能是公開預覽，或是未來版本的審查。

新版本的應用程式可在不同的時間用於不同的更新通道。 如需詳細資訊，包括如何設定您的更新通道，以測試您感興趣的新標記功能，請參閱[Office 365 的更新通道概述 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)。 在 [私人預覽] 中的新功能不會包含在表格中，但您可以 nominating [Microsoft 資訊保護私人預覽程式](https://aka.ms/mip-preview)的組織，以加入這些預覽。

當您安裝 Azure 資訊保護統一標籤用戶端（只在 Windows 電腦上執行）時，即可使用其他功能。 如需詳細資料，請參閱[比較 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel 及 PowerPoint 中的靈敏度標籤功能

|功能                                                                                                        |Windows 桌面 |Mac 桌面 |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[手動套用、變更或移除標籤](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | 在 [複查] 下                                                        |
|[需要調整以變更標籤](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[提供自訂 [説明] 頁面的 [說明] 連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[標記內容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[讓使用者指派權限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 預覽：[每月通道（已設定目標）](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#monthly-channel-for-office-365-proplus)            | 預覽：在[Office 有問必答](https://office.com/insider)        | 在 [複查] 下   | 在 [複查] 下         | 在 [複查] 下                                                        |
|使用標籤分析和傳送資料的系統管理員來[查看標籤使用狀況](label-analytics.md)                      | 在 [複查] 下            | 在 [複查] 下        | 在 [複查] 下   | 在 [複查] 下         | 在 [複查] 下                                                        |
|[要求使用者將標籤套用至電子郵件和檔](sensitivity-labels.md#what-label-policies-can-do)   | 在 [複查] 下            | 在 [複查] 下        | 在 [複查] 下   | 在 [複查] 下         | 在 [複查] 下                                                        |
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 預覽：在[Office 有問必答](https://office.com/insider)                                  | 在 [複查] 下 | 在 [複查] 下 | 在 [複查] 下 | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|支援標籤和受保護檔上的[AutoSave](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)和[合著](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) | 在 [複查] 下 | 在 [複查] 下 | 在 [複查] 下 | 在 [複查] 下 | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook 中的靈敏度標籤功能

|功能                                                                                                        |Windows Desktop 上的 Outlook |Mac 版 Outlook  |Outlook on iOS |Android 版 Outlook |Outlook 網頁版 |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[手動套用、變更或移除標籤](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[需要調整以變更標籤](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[提供自訂 [説明] 頁面的 [說明] 連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[標記內容](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[讓使用者指派權限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|使用標籤分析和傳送資料的系統管理員來[查看標籤使用狀況](label-analytics.md)                      | 在 [複查] 下                       | 在 [複查] 下                    | 在 [複查] 下           | 在 [複查] 下               | 在 [複查] 下               |
|[要求使用者將標籤套用至電子郵件和檔](sensitivity-labels.md#what-label-policies-can-do)   | 在 [複查] 下                       | 在 [複查] 下                    | 在 [複查] 下           | 在 [複查] 下               | 在 [複查] 下               |
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 預覽：向[Office 有問必答](https://office.com/insider)推出                       | 在 [複查] 下                    | 在 [複查] 下           | 在 [複查] 下               | 是 |
|

## <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 內建標籤用戶端和 Azure 資訊保護用戶端

Office 內建的標籤用戶端會從下列系統管理中心下載敏感度標籤和敏感度標籤原則設定：

- Microsoft 365 合規性中心
- Microsoft 365 安全性中心
- Office 365 安全性與合規性中心

若要使用 Office 內建的標籤用戶端，您必須將一個或多個[標籤原則發佈給已](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)列出系統管理中心之一的使用者。

不過，如果使用者已安裝其中一個 Azure 資訊保護用戶端（已整合的卷[標用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)或[傳統用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)），則預設會在其 Office 應用程式中關閉內建的標籤用戶端。 若要使用內建的標記，而不是 Azure 資訊保護用戶端的 Office 應用程式，請停用或卸載 Azure 資訊保護的 Office 增益集：

1. 完成下列其中一個選項：
    
    - **針對多部電腦：** 設定 [ **使用 Office 中的靈敏度功能來套用及查看敏感度標籤**] 群組原則設定。 在 [使用者設定 **/系統管理範本/Microsoft Office 2016/安全性設定**] 底下找到此設定。 透過群組原則或使用[Office 雲端原則服務](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)，部署此設定。
    
    - **針對單一電腦：** 如需如何在單一電腦上[永久停用或移除](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)Azure 資訊保護增益集的相關資訊，請參閱「在 Office 程式中查看、管理及安裝增益集」。

2. 重新啟動所有 Office 應用程式。

當您停用或卸載此 Office 增益集時，Azure 資訊保護用戶端仍會保持安裝，這樣您就可以繼續在 Office app 以外的標籤上進行標記。 例如，使用檔案瀏覽器或 PowerShell。

如需 Azure 資訊保護用戶端和 Office 內建標籤用戶端支援哪些功能的相關資訊，請參閱選擇從 Azure 資訊保護檔[使用 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)。

## <a name="protection-templates-and-sensitivity-labels"></a>保護範本和敏感度標籤

在使用內建標記時，系統管理員定義的保護範本（例如您為 Office 365 郵件加密定義的[保護範本](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)）不會顯示在 office 應用程式中。 這種簡化的經驗反映不需要選取保護範本，因為具有啟用加密功能的靈敏度標籤會包含相同的設定。

如果您需要將現有的保護範本轉換為標籤，請使用 Azure 入口網站及下列指示：[將範本轉換成標籤](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>資訊版權管理（IRM）選項和敏感度標籤

您設定用來套用加密的敏感度標籤，可移除使用者的複雜性，以指定自己的加密設定。 在許多 Office 應用程式中，使用者仍然可以使用資訊版權管理（IRM）選項手動設定這些個別的加密設定。 例如，針對 Windows 應用程式：

- 對於檔：檔案**File** > **資訊** > **保護** > 檔**限制存取權**
- 電子郵件：從 [**選項**] 索引標籤中 >**加密** 
  
當使用者最初標記檔或電子郵件時，他們會永遠使用自己的加密設定覆寫標籤設定設定。 例如：

- 使用者將 [**所有員工**] 標籤套用至檔，此標籤設定為套用加密設定給組織中的所有使用者。 然後，此使用者會手動設定 IRM 設定，以限制對組織外部使用者的存取。 最終結果是標示為「**機密 \ 所有」員工**且已加密，但組織中的使用者無法如預期的方式開啟的檔。

- 使用者將 [**機密 \**收件者] 標籤套用至電子郵件，並將此電子郵件設定為套用 [**不要轉寄**的加密] 設定。 然後，此使用者會手動設定 IRM 設定，這樣電子郵件就不會受到限制。 最終結果是，電子郵件可以由收件者轉寄，但不需要**機密**的「收件者」標籤。

- 使用者將**一般**標籤套用至檔，而且此標籤並未設定為套用加密。 然後，此使用者會手動設定 IRM 設定，以限制對檔的存取。 最終結果是一個已標示為「**一般**」但也會套用加密，因此某些使用者無法如預期的方式開啟的檔。

如果已標記檔或電子郵件，如果內容尚未加密，使用者就可以執行這些動作中的任何一項，或是[使用許可權是直接](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)匯出或完全控制的。 

為了獲得具有有意義報告的一致標籤體驗，請提供適當的標籤和指引，讓使用者只套用標籤來保護檔。 例如：

- 針對使用者必須指派其許可權的例外狀況，請提供可[讓使用者指派自己許可權](encryption-sensitivity-labels.md#let-users-assign-permissions)的標籤。 

- 在使用者需要具有相同分類的標籤但未加密時，請提供 sublabel 替代選項，而不是使用者在選取套用加密的標籤之後手動移除加密。 如：
    - **機密 \ 所有員工**
    - **機密資訊-任何人（沒有加密）**

> [!NOTE]
> 若使用者從儲存在 SharePoint 或 OneDrive 中的標籤檔中手動移除加密，而且您已[在 SharePoint 及 OneDrive 中啟用 Office 檔案的靈敏度卷](sensitivity-labels-sharepoint-onedrive-files.md)標，則會在下次存取或下載檔案時，自動還原標籤加密。 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>將敏感度標籤套用至檔案、電子郵件及附件

使用者一次只能為每個檔或電子郵件套用一個標籤。

當您標示具有附件的電子郵件時，附件不會繼承標籤，只會有一個例外：

- 附件是具有標籤的 Office 檔，其標籤不會套用加密，而且您套用至電子郵件的標籤會套用加密。 在此情況下，以電子郵件傳送的 Office 檔會以加密設定繼承電子郵件的標籤。

否則： 

- 如果附件具有標籤，則會保留其原始套用的標籤。
- 如果不使用標籤來加密附件，就會保留加密，但不會標示。
- 如果附件沒有標籤，則會保持未標記狀態。

## <a name="sensitivity-label-compatibility"></a>敏感度標籤相容性

**使用 rms-enlightened 應用**程式：如果您在不支援敏感度標籤的[RMS enlightened 應用程式](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications)中開啟標籤和加密的檔或電子郵件，該應用程式仍會強制執行加密與版權管理。

**使用 Azure 資訊保護用戶端**：您可以透過使用 Azure 資訊保護用戶端的 Office 內建標籤用戶端，查看及變更您套用至檔和電子郵件的敏感度標籤，以及另一種方式。

**使用其他版本的 office**：任何經過授權的使用者都可以開啟其他 office 版本中已標示的檔和電子郵件。 不過，您只能在支援的 Office 版本中或使用 Azure 資訊保護用戶端來查看或變更標籤。 [上一節](#support-for-sensitivity-label-capabilities-in-apps)列出支援的 Office 應用程式版本。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>支援以敏感度標籤保護 SharePoint 和 OneDrive 檔案

若要在商務用 OneDrive 商務或 SharePoint 線上的檔中，使用 office 內建的標籤用戶端與 Office 網頁版，請確定您已加入宣告預覽，以[啟用 SharePoint 和 OneDrive 中的 Office 檔案敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="when-office-365-applies-content-marking-and-encryption"></a>當 Office 365 套用內容標記和加密時

根據您使用的應用程式而定，Office 365 會以不同的敏感度標籤來套用內容標示和加密。

| 應用程式 | 內容標記 | 加密 |
| --- | --- | --- |
| 所有平台上的 Word、Excel、PowerPoint | 立即 | 立即 |
| 電腦版和 Mac 版 Outlook | Exchange Online 傳送電子郵件後 | 立即 |
| 網頁版、iOS 版和 Android 版 Outlook | Exchange Online 傳送電子郵件後 | Exchange Online 傳送電子郵件後 |
|

## <a name="end-user-documentation"></a>最終使用者檔

- [在 Office 中將敏感度標籤套用至您的文件和電子郵件](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [將敏感度標籤套用至 Office 檔案的已知問題](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
