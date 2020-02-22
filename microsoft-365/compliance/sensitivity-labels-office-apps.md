---
title: 在 Office 應用程式使用敏感度標籤
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
description: 了解使用者如何使用桌面、 Office 應用程式的行動電話，以及網頁的 Office 應用程式的 Office 應用程式中使用敏感度標籤運作。 了解哪些應用程式支援敏感度標籤。
ms.openlocfilehash: 5ca3d7b68f931b7596bc61a587d5e4199aa5f70f
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225501"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>在 Office 應用程式使用敏感度標籤

當您從 Microsoft 365 合規性中心或對等標示中心[發佈](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)敏感度標籤時，便會開始來分類及保護資料，建立或編輯使用者的 Office 應用程式中會出現。

請使用本文中的資訊可協助您成功地管理 Office 相關應用程式中的敏感度標籤。 例如，找出您需要支援內建的設定標籤，應用程式的最小版本，並了解與 Azure 資訊保護整合標示用戶端之間的互動，以及與其他應用程式和服務的相容性。

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>訂閱與授權需求的敏感度標籤

使用者必須至少有一個獲派下列授權：

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)或上述

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software)或上述

- [Azure 資訊保護高階 P1](https://azure.microsoft.com/pricing/details/information-protection/)或上述

在 Office 內建標示用戶端支援與 Office 的訂閱版的敏感度標籤。 此標示的用戶端不支援獨立版本的 Office，例如 Office 2016 或 Office 2019。 若要使用敏感度標籤與 Windows 電腦上的 Office 版本，安裝 Azure 資訊保護整合標示用戶端。

若要使用自動或建議的敏感度標籤，使用者需要下列其中一個下列授權：

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)或上述

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software)或上述

- [Azure 資訊保護高階 P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>在 [應用程式敏感度標籤功能的支援

針對每個功能下, 表會列出該應用程式，才能支援使用內建的設定標籤的敏感度標籤所需的最小版本。 或者，如果標籤功能是公開預覽中或其下的未來版本的檢閱。

應用程式的新版本供在不同的更新通道的不同的時間。 如需詳細資訊，包括如何設定您的更新通道，以便您可以測試新的標示功能，您有興趣，請參閱[Office 365 專業增強版更新通道的概觀](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)。 在資料表中不包含處於私人預覽的新功能，但您或許可以加入這些預覽提出任何[Microsoft 資訊保護私人預覽程式](https://aka.ms/mip-preview)貴組織。

在您安裝 Azure 資訊保護整合標示用戶端，只有 Windows 電腦上執行時，可使用額外的功能。 這些詳細資訊，請參閱[比較標示的用戶端的 Windows 電腦](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>敏感度標籤功能的 Word、 Excel 及 PowerPoint

|功能                                                                                                        |Windows 桌面 |Mac 桌面 |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[以手動方式套用、 變更或移除標籤](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | 在 [檢閱] 下                                                        |
|[需要正當理由，若要變更標籤](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[提供自訂的技術] 頁面上的 [說明] 連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[標記內容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|[讓使用者指派權限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 預覽： 在[Office 測試人員](https://office.com/insider)            | 預覽： 在[Office 測試人員](https://office.com/insider)        | 在 [檢閱] 下   | 在 [檢閱] 下         | 在 [檢閱] 下                                                        |
|系統管理員[檢視標籤使用狀況與標籤分析](label-analytics.md)並傳送資料                      | 在 [檢閱] 下            | 在 [檢閱] 下        | 在 [檢閱] 下   | 在 [檢閱] 下         | 在 [檢閱] 下                                                        |
|[要求使用者將標籤套用至電子郵件和文件](sensitivity-labels.md#what-label-policies-can-do)   | 在 [檢閱] 下            | 在 [檢閱] 下        | 在 [檢閱] 下   | 在 [檢閱] 下         | 在 [檢閱] 下                                                        |
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 預覽： 在[Office 測試人員](https://office.com/insider)                                  | 在 [檢閱] 下 | 在 [檢閱] 下 | 在 [檢閱] 下 | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|標記和受保護的文件上支援[自動儲存](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)與[共同撰寫](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) | 在 [檢閱] 下 | 在 [檢閱] 下 | 在 [檢閱] 下 | 在 [檢閱] 下 | [預覽](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>在 Outlook 中的敏感度標籤功能

|功能                                                                                                        |在 Windows 桌面上的 outlook |在 Mac 桌面上的 outlook  |在 iOS 上的 outlook |在 Android 上的 outlook |Outlook 網頁版 |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[以手動方式套用、 變更或移除標籤](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1+         | 4.0.39+           | 是               |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1+         | 4.0.39+           | 是               |
|[需要正當理由，若要變更標籤](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1+         | 4.0.39+           | 是               |
|[提供自訂的技術] 頁面上的 [說明] 連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1+         | 4.0.39+           | 是               |
|[標記內容](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1+         | 4.0.39+           | 是               |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1+         | 4.0.39+           | 是               |
|[讓使用者指派權限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1+         | 4.0.39+           | 是               |
|系統管理員[檢視標籤使用狀況與標籤分析](label-analytics.md)並傳送資料                      | 在 [檢閱] 下                       | 在 [檢閱] 下                    | 在 [檢閱] 下           | 在 [檢閱] 下               | 在 [檢閱] 下               |
|[要求使用者將標籤套用至電子郵件和文件](sensitivity-labels.md#what-label-policies-can-do)   | 在 [檢閱] 下                       | 在 [檢閱] 下                    | 在 [檢閱] 下           | 在 [檢閱] 下               | 在 [檢閱] 下               |
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 預覽： 推行至[Office 測試人員](https://office.com/insider)                       | 在 [檢閱] 下                    | 在 [檢閱] 下           | 在 [檢閱] 下               | 是 |
|

## <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 內建的設定標籤的用戶端和 Azure 資訊保護用戶端

在 Office 內建標示用戶端會從下列系統管理中心下載敏感度標籤和敏感度標籤原則設定：

- Microsoft 365 合規性中心
- Microsoft 365 安全性中心
- Office 365 安全性與合規性中心

若要使用 Office 內建標示用戶端，您必須一或多個[發佈的標籤原則](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)的使用者從下列其中一個列出的系統管理中心。

不過，如果使用者有下列其中一個 Azure 資訊保護用戶端安裝 （[整合設定標籤的用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)或[傳統的用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)），根據預設，內建標示的用戶端已關閉其 Office 應用程式中。 若要使用內建的標籤，而不 Office 相關應用程式的 Azure 資訊保護用戶端，停用或解除安裝 Office 增益集以進行 Azure 資訊保護：

1. 完成其中一個選項：
    
    - **進行多部電腦：** 設定 **使用套用及檢視敏感度標籤的 Office 中的 [敏感度] 功能**] 群組原則設定。 找到此設定在 [**使用者設定/系統管理範本/Microsoft Office 2016/安全性設定**。 部署此設定透過群組原則，或藉由使用[Office 雲端原則服務](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)。
    
    - **的單一電腦：** 如需如何[永久停用或移除](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)的 Azure 資訊保護增益集在單一電腦上的詳細資訊，請參閱 「 檢視、 管理與 Office 程式中安裝增益集 」。

2. 重新啟動所有 Office 應用程式。

當您停用或解除安裝此 Office 增益集時，Azure 資訊保護用戶端會保留已安裝，以便您可以繼續標籤檔案超出您的 Office 應用程式。 例如，藉由使用檔案總管] 中或 PowerShell。

哪些 Azure 資訊保護用戶端和 Office 內建標示用戶端支援功能的資訊，請參閱 Azure 資訊保護文件從[選擇哪一個標示的用戶端使用的 Windows 電腦](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)。

## <a name="protection-templates-and-sensitivity-labels"></a>保護範本和敏感度標籤

系統管理員定義[保護範本](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)，例如您的 Office 365 郵件加密的定義看不到在 Office 應用程式當您使用內建的設定標籤。 此簡化的體驗反映，便不需要選取保護範本，因為相同的設定中有隨附有啟用加密的敏感度標籤。

如果您需要將現有的防護範本轉換成標籤，請使用 Azure 入口網站及下列指示：[轉換至標籤的範本](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)。

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>將敏感度標籤套用至檔案、 電子郵件及附件

使用者可以將只有一個標籤套用一次每個文件或電子郵件。

當您設定標籤具有附件的電子郵件訊息時，附件不繼承的標籤有一個例外狀況：

- 附件是 Office 文件有不會套用加密，標籤並套用至電子郵件訊息的標籤套用加密。 在此情況下，郵件的 Office 文件會繼承其加密設定的電子郵件的標籤。

否則： 

- 如果附件都有標籤，它們會保留其原本套用的標籤。
- 如果附件加密不標籤] 中，加密仍會保留，但它們不標示。
- 如果附件沒有標籤，其值維持未標示。

## <a name="sensitivity-label-compatibility"></a>敏感度標籤相容性

**與 RMS enlightened 應用程式**： 應用程式如果您不支援敏感度標籤[RMS enlightened 應用程式](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications)中開啟已標記和已加密的文件或電子郵件，仍強制加密和權限管理。

**使用 Azure 資訊保護用戶端**： 您可以檢視和變更的敏感度標籤套用至文件和電子郵件與 Office 內建標示用戶端使用 Azure 資訊保護用戶端和其他種解決方式。

**與其他版本的 Office**： 任何授權的使用者可以在其他 Office 版本中開啟已標記的文件和電子郵件。 不過，您可以僅檢視或變更在支援的 Office 版本中，或使用 Azure 資訊保護用戶端的標籤。 [前一節](#support-for-sensitivity-label-capabilities-in-apps)會列出支援的 Office 應用程式版本。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>對受保護的敏感度標籤的 SharePoint 和 OneDrive 檔案的支援

若要使用 Office 內建標示用戶端與 Office web 上的 OneDrive 文件基於商業或 SharePoint Online，請確定您已選擇集若要[啟用 SharePoint 和 OneDrive 中的 Office 檔案的敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)的預覽。

## <a name="when-office-365-applies-content-marking-and-encryption"></a>Office 365 時套用內容標示和加密

Office 365 適用於內容標示和使用敏感度標籤的加密方式，視您使用的應用程式。

| 應用程式 | 內容標記 | 加密 |
| --- | --- | --- |
| 所有平台上的 Word、Excel、PowerPoint | 立即 | 立即 |
| 電腦版和 Mac 版 Outlook | Exchange Online 會傳送電子郵件之後 | 立即 |
| 網頁版、iOS 版和 Android 版 Outlook | Exchange Online 會傳送電子郵件之後 | Exchange Online 會傳送電子郵件之後 |
|

## <a name="end-user-documentation"></a>使用者文件

- [在 Office 中將敏感度標籤套用至您的文件和電子郵件](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [將敏感度標籤套用至 Office 檔案的已知問題](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
