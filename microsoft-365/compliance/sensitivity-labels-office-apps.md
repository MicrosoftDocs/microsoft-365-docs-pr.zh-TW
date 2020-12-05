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
description: 深入瞭解使用者如何在 Office 應用程式中使用敏感度標籤，以用於桌面、行動裝置及網路，以及哪些應用程式支援靈敏度標籤。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 685228823c87eff975fabd2dd398c1b67be8eeef
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580736"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>在 Office 應用程式中使用敏感度標籤

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

當您從 Microsoft 365 規範中心或同等標籤中心 [發行](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 敏感度標籤時，會開始出現在 Office 應用程式中，讓使用者在建立或編輯資料時進行分類及保護。

使用本文中的資訊，協助您在 Office app 中成功管理敏感度標籤。 例如，識別支援內建標籤所需的應用程式最少版本，並瞭解與 Azure 資訊保護整合標籤用戶端的互動，以及與其他應用程式和服務的相容性。

## <a name="labeling-client-for-desktop-apps"></a>用於桌面應用程式的標籤用戶端

若要使用內置於 Windows 和 Mac Office 桌面應用程式的敏感度標籤，您必須使用 Office 的訂閱版本。 這項標籤用戶端不支援獨立版本的 Office，例如 Office 2016 或 Office 2019。

若要在 Windows 電腦上使用具有這些獨立版本 Office 的靈敏度標籤，請安裝 [Azure 資訊保護統一的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)。

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>支援應用程式中的靈敏度標籤功能

針對每項功能，下列各表列出該應用程式所需的 Office 版本，以支援使用內建標記的靈敏度標籤。 或者，如果標籤功能是公開預覽，或是未來版本的審查。 使用 [Microsoft 365 藍圖](https://aka.ms/MIPC/Roadmap) 以取得未來版本的詳細資訊。

新版本的 Office app 可在不同的時間用於不同的更新通道。 如需詳細資訊，包括如何設定您的更新通道，以測試您所感興趣的新標記功能，請參閱 [Microsoft 365 應用程式的更新通道概述](https://docs.microsoft.com/DeployOffice/overview-update-channels)。 在 [私人預覽] 中的新功能不會包含在表格中，但您可以 nominating [Microsoft 資訊保護私人預覽程式](https://aka.ms/mip-preview)的組織，以加入這些預覽。

> [!NOTE]
> 最近變更了 Office 應用程式的更新通道名稱。 例如，每月通道現在是目前通道，而 Office 有問必答現在是 Beta 通道。 如需詳細資訊，請參閱 [Microsoft 365 應用程式的更新通道變更](https://docs.microsoft.com/deployoffice/update-channels-changes)。

當您安裝 Azure 資訊保護統一標籤用戶端（只在 Windows 電腦上執行）時，即可使用其他功能。 如需詳細資料，請參閱 [比較 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel 及 PowerPoint 中的靈敏度標籤功能

若為 iOS 和 Android：其中列出了最低的版本，則 [Office 應用程式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)也支援敏感性標籤功能。

|功能                                                                                                        |Windows 桌面 |Mac 桌面 |iOS    |Android      |網址                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[手動套用、變更或移除標籤](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Yes-自願加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Yes-自願加入](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[需要調整以變更標籤](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Yes-自願加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[提供自訂 [説明] 頁面的 [說明] 連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Yes-自願加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[標記內容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Yes-自願加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[包含變數的動態標記](#dynamic-markings-with-variables)                                              | 2010 +           | 16.42 +     | 2.42 + | 16.0.13328 + | 在 [複查] 下 |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Yes-自願加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[讓使用者指派權限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004 + | 16.35 +   | 在 [複查] 下   | 在 [複查] 下         | 在 [複查] 下                                                        |
|使用標籤分析和傳送資料的系統管理員來[查看標籤使用狀況](label-analytics.md)                      | 在 [複查] 下            | 在 [複查] 下        | 在 [複查] 下   | 在 [複查] 下         | 是的 <sup>\*</sup>                                                        |
|[要求使用者將標籤套用至電子郵件和檔](sensitivity-labels.md#what-label-policies-can-do)   | 預覽： [Beta 通道](https://office.com/insider)             | 預覽： [Beta 通道](https://office.com/insider)         | 在 [複查] 下   | 在 [複查] 下         | 在 [複查] 下                                            
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 2009 +                                  | Word 和 PowerPoint 的預覽：向裡 [ (預覽的現有頻道) ](https://office.com/insider) | 在 [複查] 下 | 在 [複查] 下 | [Yes-自願加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|支援標籤和受保護檔上的[AutoSave](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)和[合著](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) | 在 [複查] 下 | 在 [複查] 下 | 在 [複查] 下 | 在 [複查] 下 | [Yes-自願加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**註腳：**

<sup>\*</sup> 目前不包含調整文字可移除標籤或降低分類層級

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook 中的靈敏度標籤功能

|功能                                                                                                        |Windows Desktop 上的 Outlook |Mac 版 Outlook  |Outlook on iOS |Android 版 Outlook |Outlook 網頁版 |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[手動套用、變更或移除標籤](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[需要調整以變更標籤](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[提供自訂 [説明] 頁面的 [說明] 連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[標記內容](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[包含變數的動態標記](#dynamic-markings-with-variables)                                              | 在 [複查] 下                     | 在 [複查] 下                 | 在 [複查] 下         | 在 [複查] 下           | 在 [複查] 下               |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[讓使用者指派權限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[要求使用者將標籤套用至電子郵件和檔](#require-users-to-apply-a-label-to-their-email-and-documents)   | 預覽： [Beta 通道](https://office.com/insider)                        | 16.43 +                     | 4.57.0 +            | 4.2037.4 +                | 是                |
|使用標籤分析和傳送資料的系統管理員來[查看標籤使用狀況](label-analytics.md)                      | 在 [複查] 下                       | 在 [複查] 下                    | 在 [複查] 下           | 在 [複查] 下               | 是               |
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 2009 +                      | 在 [複查] 下                    | 在 [複查] 下           | 在 [複查] 下               | 是 |
|


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 內建標籤用戶端和其他標記解決方案

Office 內建的標籤用戶端會從下列系統管理中心下載敏感度標籤和敏感度標籤原則設定：

- Microsoft 365 合規性中心
- Microsoft 365 安全性中心
- Office 365 安全性與合規性中心

若要使用 Office 內建的標籤用戶端，您必須將一個或多個 [標籤原則發佈給已](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 列出系統管理中心的使用者，以及 [支援的 Office 版本](#support-for-sensitivity-label-capabilities-in-apps)。

如果同時滿足這兩種條件，但您需要關閉 Office 內建標籤用戶端，請使用下列群組原則設定：

1. 流覽至 [ **使用者設定/系統管理範本/Microsoft Office 2016/安全性設定**]。

2. Set **使用 Office 中的靈敏度功能，套用敏感度標籤並將其顯示** 為 **0**。 
 
使用群組原則或使用 [Office 雲端原則服務](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)，部署此設定。 設定會在 Office 應用程式重新開機時生效。

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 內建標籤用戶端和 Azure 資訊保護用戶端

如果使用者已安裝其中一個 Azure 資訊保護用戶端 (的 [整合標籤客戶](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) 端或 [傳統用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)) 上，預設會在其 Office 應用程式中關閉內建的標記用戶端。 

若要使用內建的標記，而不是 Azure 資訊保護用戶端的 Office 應用程式，請使用上一節中的指示，但設定群組原則設定 **使用 Office 中的靈敏度功能，將敏感度標籤** 套用至 **1**。 

或者，停用或移除 Office 增益集（ **Azure 資訊保護**）。 這種方法適用于單一電腦和特殊的測試。 如需相關指示，請參閱 [在 Office 程式中查看、管理及安裝增益集](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)。 

當您停用或移除此 Office 增益集時，Azure 資訊保護用戶端仍會保持安裝，這樣您就可以繼續在 Office app 以外的標籤上進行標記。 例如，使用檔案瀏覽器或 PowerShell。

如需 Azure 資訊保護用戶端和 Office 內建標籤用戶端支援哪些功能的相關資訊，請參閱選擇從 Azure 資訊保護檔 [使用 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) 。

## <a name="office-file-types-supported"></a>支援的 Office 檔案類型

在 Word、Excel 及 PowerPoint 檔內建內建標籤的 Office 應用程式支援 Open XML 格式 (如 .docx 和 .xlsx) ，但不是 Microsoft Office 97-2003 格式 (例如 .doc 及 .xls) 。 當內建標籤不支援檔案類型時，[ **敏感度** ] 按鈕無法在 Office 應用程式中使用。

Azure 資訊保護整合標籤用戶端支援 Open XML 格式和 Microsoft Office 97-2003 格式。 如需詳細資訊，請參閱由該用戶端的系統管理指南之 [Azure 資訊保護統一標籤用戶端支援的檔案類型](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) 。

如需其他的標籤方案，請檢查其檔是否有支援的檔案類型。

## <a name="protection-templates-and-sensitivity-labels"></a>保護範本和敏感度標籤

在使用內建標記時，系統管理員定義的保護範本（例如您為 Office 365 郵件加密定義的 [保護範本](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)）不會顯示在 office 應用程式中。 這種簡化的經驗反映不需要選取保護範本，因為具有啟用加密功能的靈敏度標籤會包含相同的設定。

如果您需要將現有的保護範本轉換為標籤，請使用 Azure 入口網站及下列指示： [將範本轉換成標籤](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>資訊版權管理 (IRM) 選項和敏感度標籤

您設定用來套用加密的敏感度標籤，可移除使用者的複雜性，以指定自己的加密設定。 在許多 Office 應用程式中，使用者仍然可以使用資訊版權管理 (IRM) 選項，手動設定這些個別加密設定。 例如，針對 Windows 應用程式：

- 對於檔：檔案 **File**  >  **資訊**  >  **保護** 檔  >  **限制存取權**
- 電子郵件：從 [ **選項** ] 索引標籤中 > **加密** 
  
當使用者最初標記檔或電子郵件時，他們會永遠使用自己的加密設定覆寫標籤設定設定。 例如：

- 使用者將 [ **所有員工** ] 標籤套用至檔，此標籤設定為套用加密設定給組織中的所有使用者。 然後，此使用者會手動設定 IRM 設定，以限制對組織外部使用者的存取。 最終結果是標示為「 **機密 \ 所有」員工** 且已加密，但組織中的使用者無法如預期的方式開啟的檔。

- 使用者將 [ **機密 \** 收件者] 標籤套用至電子郵件，並將此電子郵件設定為套用 [ **不要轉寄** 的加密] 設定。 然後，此使用者會手動設定 IRM 設定，這樣電子郵件就不會受到限制。 最終結果是，電子郵件可以由收件者轉寄，但不需要 **機密** 的「收件者」標籤。

- 使用者將 **一般** 標籤套用至檔，而且此標籤並未設定為套用加密。 然後，此使用者會手動設定 IRM 設定，以限制對檔的存取。 最終結果是一個已標示為「 **一般** 」但也會套用加密，因此某些使用者無法如預期的方式開啟的檔。

如果已標記檔或電子郵件，如果內容尚未加密，使用者就可以執行這些動作中的任何一項，或是 [使用許可權是直接](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) 匯出或完全控制的。 

為了獲得具有有意義報告的一致標籤體驗，請提供適當的標籤和指引，讓使用者只套用標籤來保護檔。 例如：

- 針對使用者必須指派其許可權的例外狀況，請提供可 [讓使用者指派自己許可權](encryption-sensitivity-labels.md#let-users-assign-permissions)的標籤。 

- 在使用者需要具有相同分類的標籤但未加密時，請提供 sublabel 替代選項，而不是使用者在選取套用加密的標籤之後手動移除加密。 如：
    - **機密 \ 所有員工**
    - **機密 \ 個人 (無加密)**

> [!NOTE]
> 若使用者從儲存在 SharePoint 或 OneDrive 中的標籤檔中手動移除加密，而且您已 [在 SharePoint 及 OneDrive 中啟用 Office 檔案的靈敏度卷](sensitivity-labels-sharepoint-onedrive-files.md)標，則會在下次存取或下載檔案時，自動還原標籤加密。 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>將敏感度標籤套用至檔案、電子郵件及附件

使用者一次只能為每個檔或電子郵件套用一個標籤。

當您標示具有附件的電子郵件時，附件不會繼承標籤，只會有一個例外：

- 附件是具有標籤的 Office 檔，其標籤不會套用加密，而且您套用至電子郵件的標籤會套用加密。 在此情況下，以電子郵件傳送的 Office 檔會以加密設定繼承電子郵件的標籤。

否則： 

- 如果附件具有標籤，則會保留其原始套用的標籤。
- 如果不使用標籤來加密附件，就會保留加密，但不會標示。
- 如果附件沒有標籤，則會保持未標記狀態。

## <a name="sensitivity-label-compatibility"></a>敏感度標籤相容性

**使用 rms-enlightened 應用** 程式：如果您在不支援敏感度標籤的 [RMS enlightened 應用程式](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 中開啟標籤和加密的檔或電子郵件，該應用程式仍會強制執行加密與版權管理。

**使用 Azure 資訊保護用戶端**：您可以透過使用 Azure 資訊保護用戶端的 Office 內建標籤用戶端，查看及變更您套用至檔和電子郵件的敏感度標籤，以及另一種方式。

**使用其他版本的 office**：任何經過授權的使用者都可以開啟其他 office 版本中已標示的檔和電子郵件。 不過，您只能在支援的 Office 版本中或使用 Azure 資訊保護用戶端來查看或變更標籤。 [上一節](#support-for-sensitivity-label-capabilities-in-apps)列出支援的 Office 應用程式版本。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>支援以敏感度標籤保護 SharePoint 和 OneDrive 檔案

若要在 SharePoint 或 OneDrive 中的檔上使用 office 內建的 Office 內建標籤用戶端，請確定您已 [在 SharePoint 及 OneDrive 中啟用 office 檔案的靈敏度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="support-for-external-users-and-labeled-content"></a>支援外部使用者和標示的內容

當您標示檔或電子郵件時，標籤會儲存為包含您租使用者和標籤 GUID 的中繼資料。 當支援敏感度標籤的 Office 應用程式開啟已標示的檔或電子郵件時，此中繼資料是唯讀的，而且只有在使用者屬於相同租使用者時，標籤會顯示在其應用程式中。 例如，針對 Word、PowerPoint 及 Excel 內建的標籤，標籤名稱會顯示在狀態列上。 

這表示，如果您與另一個使用不同標籤名稱的組織共用檔，則每個組織都可以套用並查看其自己的標籤套用至檔。 不過，組織外部的使用者看不見已套用標籤的下列元素：

- 內容標記。 當標籤套用頁首、頁尾或浮水印時，這些內容會直接新增至內容並保持可見，直到有人修改或刪除。

- 來自套用加密之標籤的基礎保護範本名稱和描述。 這項資訊會顯示在檔頂端的訊息列中，以提供授權誰開啟檔的相關資訊，以及該檔的使用許可權。

### <a name="sharing-encrypted-documents-with-external-users"></a>與外部使用者共用加密檔

除了限制存取您自己組織中的使用者之外，您還可以將存取權擴充至在 Azure Active Directory 中具有帳戶的任何其他使用者。 在使用者成功驗證之後，所有 Office 應用程式和其他 [RMS enlightened 應用程式](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 都可以開啟加密檔。

如果外部使用者在 Azure Active Directory 中沒有帳戶，您可以在租使用者中為這些使用者建立來賓帳戶。 若為其電子郵件地址，您可以指定任何已使用的電子郵件地址。 例如，其 Gmail 位址。 您也可以使用此來賓帳戶，存取 SharePoint 或 OneDrive 中的共用檔，以 [SharePoint 和 OneDrive 中的 Office 檔案已啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。

外部使用者也可以使用 microsoft 帳戶來加密檔，當其使用 Microsoft 365 (應用程式時，在 Windows 上) 舊版本的 [Office 365 應用程式](https://docs.microsoft.com/deployoffice/name-change) ，以及 macOS (版本 16.42 +) ，Android (版本 16.0.13029 +) ，以及 iOS (版本 2.42 +) 。 例如，某人與他們共用加密檔，加密設定會指定其 Gmail 電子郵件地址。 此使用者可建立其自己的 Microsoft 帳戶，其使用 Gmail 電子郵件地址。 然後，使用此帳戶登入後，他們就可以開啟檔，並根據為該使用者指定的使用限制來進行編輯。 如需此案例的逐步範例，請參閱 [開啟和編輯受保護的檔](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)。

> [!NOTE]
> Microsoft 帳戶的電子郵件地址必須符合所指定的電子郵件地址，以限制加密設定的存取權。

當使用 Microsoft 帳戶的使用者以這種方式開啟加密檔時，如果不存在具有相同名稱的來賓帳戶，它會自動為租使用者建立來賓帳戶。 當來賓帳戶存在時，您可以使用網頁) 上的瀏覽器 (Office 來開啟 SharePoint 和 OneDrive 中的檔，以及從 Windows 桌面應用程式中開啟加密的檔。 

不過，因為複寫延遲，所以不會立即建立自動來賓帳戶。 如果您指定個人電子郵件地址做為標籤加密設定的一部分，我們建議您在 Azure Active Directory 中建立對應的來賓帳戶。 然後，讓這些使用者知道他們必須使用此帳戶來開啟組織中的加密檔。

> [!TIP]
> 因為您無法確定外部使用者將使用受支援的 Office 用戶端應用程式，所以在建立來賓帳戶後，從 SharePoint 和 OneDrive 共用連結是比較可靠的方法，可支援與外部使用者的安全共同作業。

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office 應用程式何時套用內容標示和加密

根據您使用的應用程式而定，Office 應用程式會以不同的敏感度標籤來套用內容標示和加密。

| 應用程式 | 內容標記 | 加密 |
| --- | --- | --- |
| 所有平台上的 Word、Excel、PowerPoint | 立即 | 立即 |
| 電腦版和 Mac 版 Outlook | Exchange Online 傳送電子郵件後 | 立即 |
| 網頁版、iOS 版和 Android 版 Outlook | Exchange Online 傳送電子郵件後 | Exchange Online 傳送電子郵件後 |
|

將敏感度標籤套用至 Office app 以外檔案的解決方案，可將標記中繼資料套用至檔案。 在此案例中，標籤設定中的內容標示不會插入檔案，但會套用加密。 

在 Office 桌面應用程式中開啟這些檔案時，Azure 資訊保護統一標記用戶端會自動套用內容標記。 當您使用用於桌面、行動裝置或 web 應用程式的內建標記時，不會自動套用內容標記。

在 Office app 外部套用敏感度標籤的案例包括：

- 來自 Azure 資訊保護統一標籤用戶端的掃描器、檔案瀏覽器和 PowerShell 

- SharePoint 和 OneDrive 的自動標記原則

- 從 Power BI 匯出已標示及已加密的資料

- Microsoft 雲端 App 安全性

針對這些案例，使用內建標籤的使用者可以暫時移除或取代目前的標籤，然後重新應用原始標籤，以套用標籤的內容標記。

### <a name="dynamic-markings-with-variables"></a>包含變數的動態標記

> [!IMPORTANT]
> 目前，並非所有平臺上的所有應用程式都支援您可以為頁首、頁尾和浮水印指定的動態內容標記。 針對不支援此功能的應用程式，它們會將標記套用為標籤設定中指定的原始文字，而不是解析變數。
> 
> Azure 資訊保護統一的標籤用戶端支援動態標記。 若要在 Office 內建標記，請參閱此頁面上 [ [功能](#support-for-sensitivity-label-capabilities-in-apps) ] 區段中的表格。

當您為內容標記設定敏感度標籤時，您可以在您的頁首、頁尾或浮水印的文字字串中使用下列變數：

| 變數 | 描述 | 套用標籤的範例 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 目前的標籤顯示名稱 | **一般**|
| `${Item.Name}` | 目前的檔案名或電子郵件主題 | **Sales.docx** |
| `${Item.Location}` | 檔的目前路徑和檔案名，或電子郵件的電子郵件主題 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | 目前的使用者顯示名稱  | **Richard Simone** |
| `${User.PrincipalName}` | 目前的使用者 Azure AD 使用者主體名稱 (UPN)  | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | 本機時區的目前日期和時間 | **8/10/2020 1:30 PM** |

> [!NOTE]
> 這些變數的語法是區分大小寫的。

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>要求使用者將標籤套用至電子郵件和檔

> [!IMPORTANT]
> 也稱為必要標籤，並非所有平臺上的所有應用程式目前都支援 **要求使用者將標籤套用至電子郵件和檔** 的原則設定。
> 
> [Azure 資訊保護整合的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)支援必要的標記，以及針對 Office 應用程式內建的標記，請參閱此頁面上 [[功能](#support-for-sensitivity-label-capabilities-in-apps)] 區段中的表格。

選取此原則設定時，已指派該原則的使用者必須在下列情況下選取並套用靈敏度標籤：

- 針對 Azure 資訊保護的整合標籤用戶端：
    - 若為檔 (Word、Excel PowerPoint) ：儲存未標記的檔時，或使用者關閉檔時。
    - 電子郵件 (Outlook) ：在使用者傳送未標記的郵件時。

- 針對內建至 Office app 的標籤：
    - 若為檔 ( # B1 Word、Excel PowerPoint) ：開啟或儲存未標記的檔時。
    - 電子郵件 (Outlook) ：在使用者傳送未標記的電子郵件訊息時。

內建標示標籤的其他資訊：

- 當使用者在開啟未標記的檔時，系統會提示使用者新增敏感度標籤，他們可以新增標籤，或選擇以唯讀模式開啟檔。

- 當必要的標籤生效時，使用者就無法從檔中移除敏感度標籤，但是可以變更現有的標籤。

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>為 Word、Excel、PowerPoint 和 Outlook 設定不同的視覺標記

做為其他變數，您可以在文字字串中使用 "If. App" variable 語句來設定每個 Office 應用程式類型的視覺標記，並使用 [ **Word**]、[ **Excel**]、[ **PowerPoint**] 或 [ **Outlook**] 的值來識別應用程式類型。 您也可以縮寫這些值，如果您想要在相同的 If App 語句中指定多個值，則這是必要的。

> [!NOTE]
> 為了完整，Outlook 的指示會包含在內，但目前只有 Azure 資訊保護整合的標籤用戶端支援。

使用下列語法：

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

與其他動態視覺標記一樣，語法也是區分大小寫的。

範例：

- **只為 Word 檔設定標頭文字：**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    只有在 Word 檔標題中，標籤會套用標頭文字「這個 Word 檔是保密的」。 沒有標頭文字會套用至其他 Office 應用程式。

- **設定 Word、Excel 和 Outlook 的頁尾文字，以及 PowerPoint 的不同頁腳文字的頁腳文字：**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    在 Word、Excel 和 Outlook 中，標籤會套用頁腳文字「此內容是機密」。 在 PowerPoint 中，標籤會套用註腳文字「本簡報是機密」。

- **設定 Word 和 PowerPoint 的特定浮水印文字，然後為 Word、Excel 及 PowerPoint 設定浮水印文字：**

    `${If.App.WP}This content is ${If.End}Confidential`

    在 Word 和 PowerPoint 中，標籤會套用浮水印文字「此內容是機密」。 在 Excel 中，標籤會套用浮水印文字「機密」。 在 Outlook 中，標籤不會套用任何浮水印文字，因為浮水印是不支援 Outlook 的視覺標記。
>>>>>>> a51fef4b19dc23a23a161de3e8333dcd7527540b

## <a name="end-user-documentation"></a>最終使用者檔

- [在 Office 中將敏感度標籤套用至您的文件和電子郵件](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [將敏感度標籤套用至 Office 檔案的已知問題](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
