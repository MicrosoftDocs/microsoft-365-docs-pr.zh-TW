---
title: 在 Office 應用程式中管理敏感度標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 適用於 IT 系統管理員的資訊，用於在傳統型、行動裝置和網頁版 Office 應用程式中管理敏感度標籤。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3aa5c8065b882dff670d6b829141955bf615d933
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599838"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>在 Office 應用程式中管理敏感度標籤

>*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

當您從 Microsoft 365 合規性中心[發佈](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)敏感度標籤後，這些標籤會開始顯示在 Office 應用程式中，讓使用者在建立或編輯資料時分類及保護資料。

使用本文的資訊，協助您成功在 Office 應用程式中管理敏感度標籤。 例如，找出支援內建標籤所需的應用程式最低版本，並了解與 Azure 資訊保護統一標籤用戶端的互動，以及與其他應用程式與服務的相容性。

## <a name="labeling-client-for-desktop-apps"></a>適用於傳統型應用程式的標籤用戶端

若要使用 Windows 和 Mac 版 Office 桌面應用程式內建的敏感度標籤，您必須使用 Office 訂閱版本。 此標籤用戶端不支援獨立版本的 Office，例如 Office 2016 或 Office 2019。

若要使用 Windows 電腦上這些獨立版 Office 的敏感度標籤，請安裝[Azure 資訊保護統一標籤用戶端](/azure/information-protection/rms-client/aip-clientv2) (部分機器翻譯)。

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>在應用程式中支援敏感度標籤功能

針對每個功能，下表列出使用內建標籤支援敏感度標籤所需的最低 Office 版本。 或者，如果標籤功能為公開預覽，或正在審查中以用於將來版本。 請使用 [Microsoft 365 藍圖](https://aka.ms/MIPC/Roadmap)，以取得有關未來版本的詳細資料。

新版 Office 應用程式會在不同時間提供給不同的更新通道使用。 如需詳細資訊，包括如何設定更新通道，以便測試您感興趣的新標籤功能，請參閱 [Microsoft 365 Apps更新通道的概觀](/DeployOffice/overview-update-channels)。 表格中不包含個人預覽版的新功能，但您可以提名您的組織參加 [Microsoft 資訊保護個人預覽版計畫](https://aka.ms/mip-preview)，以加入這些預覽。

> [!NOTE]
> Office 應用程式的更新通道名稱最近已變更。 例如，每月通道現在稱為目前通道，而 Office 測試人員現在稱為 Beta 版通道。 如需詳細資訊，請參閱 [Microsoft 365 Apps 更新通道的變更](/deployoffice/update-channels-changes) (部分機器翻譯)。

iOS 版 Office 和 Android 版 Office：敏感度標籤內建於 [Office 應用程式](https://www.microsoft.com/zh-TW/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)中。

當您安裝 Azure 資訊保護統一標籤用戶端 (僅在 Windows 電腦上執行) 後，可以使用其他功能。 如需詳細資訊，請參閱[比較 Windows 電腦的標籤用戶端](/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers) (部分機器翻譯)。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel 和 PowerPoint 中的敏感度標籤功能

列出的數字是每個功能所需的最低 Office 應用程式版本。

|功能                                                                                                        |Windows |Mac |iOS    |Android      |網頁版                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[手動套用、變更或移除標籤](https://support.microsoft.com/zh-TW/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 選擇加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 選擇加入](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[要求變更標籤的理由](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 選擇加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[提供自訂說明頁面的說明連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 選擇加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[標記內容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 選擇加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[使用變數動態標記](#dynamic-markings-with-variables)                                              | 2010           | 16.42+     | 2.42+ | 16.0.13328+ | 審查中 |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 選擇加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[讓使用者指派權限：<br /> - 提示使用者](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | 審查中   | 審查中         | 審查中                                                        |
|[稽核標籤相關的使用者活動](data-classification-activity-explorer.md)                      | 2011+ | 16.43+ | 2.46+ | 逐步推出：16.0.13628+ | 是 <sup>\*</sup>                                                        |
|[要求使用者在電子郵件和文件中套用標籤](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+             | 逐步推出：16.45+         | 預覽：[Beta 版通道](https://office.com/insider) | 逐步推出：16.0.13628+ | 審查中                                            
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 2009+                                  | 逐步推出：16.44+ | 審查中 | 審查中 | [是 - 選擇加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|針對已標籤和已加密的文件[支援共同撰寫和自動儲存](sensitivity-labels-coauthoring.md) | 預覽：[目前通道 (預覽)](https://office.com/insider) | 預覽：[Beta 版通道](https://office.com/insider) | 審查中 | 審查中 | [是 - 選擇加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**註腳：**

<sup>\*</sup> 目前，不包含移除標籤或降低分類層級的理由文字

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook 中的敏感度標籤功能

列出的數字是每個功能所需的最低 Office 應用程式版本。

|功能                                                                                                        |Windows 版 Outlook |Mac 版 Outlook |iOS 版 Outlook |Android 版 Outlook |Outlook 網頁版 |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[手動套用、變更或移除標籤](https://support.microsoft.com/zh-TW/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[要求變更標籤的理由](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[提供自訂說明頁面的說明連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[標記內容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[使用變數動態標記](#dynamic-markings-with-variables) <sup>1</sup>                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[讓使用者指派權限：<br /> - 不可轉寄](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[讓使用者指派權限：<br /> - 僅加密](encryption-sensitivity-labels.md#let-users-assign-permissions)  |2011+ | 審查中 | 審查中  | 審查中 | 推出中 |
|[要求使用者在電子郵件和文件中套用標籤](#require-users-to-apply-a-label-to-their-email-and-documents)   | 逐步推出：2101+                        | 16.43+ <sup>2</sup>                    | 審查中            | 審查中                | 是                |
|[稽核標籤相關的使用者活動](data-classification-activity-explorer.md) | 2011+ | 審查中 | 審查中           | 審查中               | 審查中 |
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+ <sup>2</sup>                    | 審查中           | 審查中               | 是 |
|

**註腳：**

<sup>1</sup> 目前僅支援 [Item.Label 和 If.App 變數](#dynamic-markings-with-variables)
<br />
<sup>2</sup> 需要[新的 Mac 版 Outlook](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 內建標籤用戶端和其他標籤解決方案

Office 內建標籤用戶端會從下列系統管理中心下載敏感度標籤和敏感度標籤原則設定：

- Microsoft 365 合規性中心
- Microsoft 365 安全性中心
- Office 365 安全性與合規性中心

若要使用 Office 內建的標籤用戶端，您必須將一或多個[標籤原則](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)從其中一個列出的系統管理中心和[支援的 Office 版本](#support-for-sensitivity-label-capabilities-in-apps)發佈給使用者。

如果這兩個條件都符合，但您需要關閉 Office 內建標籤用戶端，請使用下列群組原則設定：

1. 瀏覽至 **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**。

2. 將 **[在 Office 中使用 [敏感度] 功能以套用並檢視敏感度標籤]** 設為 **[0]**。 
 
使用群組原則或使用 [Office 雲端原則服務](/DeployOffice/overview-office-cloud-policy-service)來部署此設定。 Office 應用程式重新啟動後，此設定即會生效。

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 內建標籤用戶端和 Azure 資訊保護用戶端

如果使用者[已安裝 Azure 資訊保護用戶端](/azure/information-protection/rms-client/aip-clientv2)，預設會關閉其 Office 應用程式中的內建標籤用戶端。 

若要使用內建標籤，而非適用於 Office 應用程式的 Azure 資訊保護用戶端，建議您使用群組原則設定 **受控增益集清單**，如同 [由於 Office 2013 和 Office 2016 程式的群組原則設定而未載入任何增益集](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off)所記載。

針對 Microsoft Word 2016、Excel 2016、PowerPoint 2016 和 Outlook 2016，為 Azure 資訊保護用戶端指定下列程式設計識別碼 (ProgID)，並且將選項設定為 [**0：增益集一律停用 (封鎖)**]

|應用程式  |ProgID  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 

使用群組原則或使用 [Office 雲端原則服務](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)來部署此設定。

> [!NOTE]
> 如果您使用群組原則設定 [**在 Office 中使用敏感性功能以套用並檢視敏感性標籤**]，並且將這個選項設定為 [**1**]，有時候 Azure 資訊保護用戶端可能仍然會在 Office 應用程式中載入。 防止增益集在每個應用程式中載入，以防止發生這種情況。

或者，您可以從 Word、Excel、PowerPoint 和 Outlook 互動地停用或移除 **Microsoft Azure 資訊保護** Office 增益集。 此方法適用於單一電腦和臨機測試。 如需指示，請參閱[在 Office 程式中檢視、管理及安裝增益集](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)。 

無論您選擇哪種方法，變更都是在 Office 應用程式重新啟動時生效。 藉由停用或移除此 Office 增益集後，Azure 資訊保護用戶端會在電腦上維持安裝狀態，以便您可以繼續在 Office 應用程式外為檔案套用標籤。 例如，使用 [檔案總管] 或 PowerShell。

有關 Azure 資訊保護用戶端和 Office 內建標籤用戶端支援哪些功能的詳細資訊，請參閱 Azure 資訊保護文件中的[選擇您的 Windows 標籤解決方案](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) (部分機器翻譯)。

## <a name="office-file-types-supported"></a>支援的 Office 檔案類型

具有 Word、Excel 和 PowerPoint 檔案內建標籤的 Office 應用程式支援 Open XML 格式 (例如 .docx 和 .xlsx)，但不支援 Microsoft Office 97-2003 格式 (例如 .doc 和 .xls)、Open Document 格式 (例如 .odt 和 .ods) 或其他格式。 當內建標籤不支援檔案類型時，在 Office 應用程式中就無法使用 **[敏感度]** 按鈕。

Azure 資訊保護統一標籤用戶端支援 Open XML 格式和 Microsoft Office 97-2003 格式。 如需詳細資訊，請參閱該用戶端系統管理指南中的 [Azure 資訊保護統一標籤用戶端支援的檔案類型](/azure/information-protection/rms-client/clientv2-admin-guide-file-types) (部分機器翻譯)。

若為其他標籤解決方案，請查看支援檔案類型的文件。

## <a name="protection-templates-and-sensitivity-labels"></a>保護範本和敏感度標籤

當您使用內建標籤時，在 Office 應用程式中看不到系統管理員定義的[保護範本](/azure/information-protection/configure-policy-templates)，例如您為 Office 365 郵件加密定義的範本。 這種簡化的體驗反映出，不需要選取保護範本，因為已啟用加密的敏感度標籤會包含相同的設定。

如果您需要將現有的保護範本轉換為標籤，請使用 Azure 入口網站並遵照下列指示：[將範本轉換為標籤](/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels) (部分機器翻譯)。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>資訊版權管理 (IRM) 選項和敏感度標籤

您設定要套用加密的敏感度標籤消除了使用者指定自己的加密設定的複雜性。 在許多 Office 應用程式中，使用者仍可以使用資訊版權管理 (IRM) 選項手動設定這些個別加密設定。 例如，針對 Windows 應用程式：

- 針對文件：**[檔案]** > **[資訊]** > **[保護文件]** > **[限制存取]**
- 針對電子郵件：從 **[選項]** 索引標籤 > **[加密]** 
  
當使用者開始標籤文件或電子郵件後，他們隨時都可以使用自己的加密設定來覆寫您的標籤設定。 例如：

- 使用者將 **機密\所有員工** 標籤套用至文件，且此標籤已設定為，為組織中所有使用者套用加密設定。 然後，此使用者手動設定 IRM 設定，以限制對組織外部使用者的存取。 結果是，文件會標籤為 **機密\所有員工** 並加密，但貴組織的使用者無法如預期開啟文件。

- 使用者將 **機密\僅收件者** 標籤套用至電子郵件，且此電子郵件已設定為套用 **不要轉寄** 加密設定。 然後，此使用者手動設定 IRM 設定，讓電子郵件不受限制。 結果是，儘管套用了 **機密\僅收件者** 標籤，收件者還是可以轉寄電子郵件。

- 使用者將 **一般** 標籤套用至文件，且此標籤未設定為套用加密。 然後，此使用者手動設定 IRM 設定，以限制文件的存取。 結果是，文件雖標籤為 **一般**，但也套用了加密，因此某些使用者無法如預期開啟該文件。

如果文件或電子郵件已套用標籤，但內容尚未加密，則使用者可以執行任何這些動作，或者使用者擁有匯出或完全控制的[使用權限](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。 

為了獲得更一致的標籤體驗以及有意義的報告，請提供適當的標籤和指引，讓使用者只透過套用標籤來保護文件。 例如：

- 在使用者必須指派自己的權限的例外案例中，請提供[可讓使用者指派自己的權限](encryption-sensitivity-labels.md#let-users-assign-permissions)的標籤。 

- 當使用者需要具有相同分類但無加密的標籤時，請提供子標籤替代方法，而不是在選取套用加密的標籤之後手動移除加密。 例如：
    - **機密\所有員工**
    - **機密\任何人 (無加密)**

> [!NOTE]
> 如果使用者手動移除儲存在 SharePoint 或 OneDrive 中的標籤文件上的加密，並且您已[為 SharePoint 和 OneDrive 中的 Office 檔案啟用了敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)，則下次存取或下載該文件時，標籤加密將自動還原。 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>將敏感度標籤套用到檔案、電子郵件和附件

使用者一次只能針對每個文件或電子郵件套用一個標籤。

當您為包含附件的電子郵件套用標籤時，僅當您套用到電子郵件的標籤套用了加密並且附件是尚未加密的 Office 文件時，附件才會繼承標籤。 因為繼承的標籤會套用加密，所以附件會成為新加密。

當套用到電子郵件的標籤未套用加密或附件已加密時，附件不會繼承電子郵件的標籤。

標籤繼承的範例，其中 **機密** 標籤套用了加密，而 **一般** 標籤則未套用加密：

- 使用者建立新電子郵件，並將 **機密** 標籤套用至此電子郵件。 然後他們新增未套用標籤或加密的 Word 文件。 因為繼承，文件會新套用 **機密** 標籤，並且現在從該標籤套用加密。

- 使用者建立新電子郵件，並將 **機密** 標籤套用至此電子郵件。 然後，他們新增具有 **一般** 標籤的 Word 檔案，且此檔案未加密。 因為繼承，文件會重新套用 **機密** 標籤，並且現在從該標籤套用加密。

## <a name="sensitivity-label-compatibility"></a>敏感度標籤相容性

**使用 RMS 啟發式應用程式**：如果您在不支援敏感度標籤的 [RMS 啟發式應用程式](/azure/information-protection/requirements-applications#rms-enlightened-applications)中開啟已套用標籤和加密的文件或電子郵件，該應用程式仍然會強制執行加密和版權管理。

**使用 Azure 資訊保護用戶端**：您可以使用 Azure 資訊保護用戶端，來檢視和變更您使用 Office 內建標籤用戶端套用到文件和電子郵件的敏感度標籤，反之亦然。

**使用其他版本 Office**：任何授權使用者都可以在其他版本的 Office 中開啟已套用標籤的文件和電子郵件。 不過，您僅能使用 Azure 資訊保護用戶端，在支援的 Office 版本中檢視或變更標籤。 支援的 Office 應用程式版本列在[上一節](#support-for-sensitivity-label-capabilities-in-apps)。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>支援受敏感度標籤保護的 SharePoint 和 OneDrive 檔案

若要針對 SharePoint 或 OneDrive 中的文件搭配使用 Office 內建標籤用戶端與 Office 網頁版，請確定您[已在 SharePoint 和 OneDrive 中啟用 Office 檔案的敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="support-for-external-users-and-labeled-content"></a>支援外部使用者和已套用標籤的內容

當您為文件或電子郵件套用標籤後，標籤會儲存為中繼資料，其中包含您的租用戶和標籤 GUID。 當支援敏感度標籤的 Office 應用程式開啟已套用標籤的文件或電子郵件時，系統只會讀取此中繼資料，且只有當使用者屬於相同的租用戶，標籤才會顯示在他們的應用程式中。 例如，針對 Word、PowerPoint 和 Excel 的內建標籤，標籤名稱會顯示在狀態列上。 

這表示，如果您與使用不同標籤名稱的另一個組織共用文件，每個組織都可以將自己的標籤套用至文件，並看到自己的標籤。 不過，組織外部的使用者可以看到來自已套用標籤的下列元素：

- 內容標記。 當標籤套用頁頁首、頁尾或浮水印時，這些會直接新增到內容中，並持續顯示，直到有人修改或刪除它們。

- 來自已套用加密之標籤的基礎保護範本的名稱和描述。 此資訊會顯示在文件頂端的訊息列，提供有權開啟文件的人員，以及該文件的使用權相關資訊。

### <a name="sharing-encrypted-documents-with-external-users"></a>與外部用戶共用加密文件

除了限制貴組織中使用者的存取權之外，您還可以將存取權延伸至在 Azure Active Directory 中擁有帳戶的其他使用者。 不過，如果您的組織使用條件式存取原則，請參閱[下一節](#conditional-access-policies)了解其他考量事項。

使用者成功驗證後，所有 Office 應用程式和其他[RMS 啟發式應用程式](/azure/information-protection/requirements-applications#rms-enlightened-applications)就可以開啟加密的文件。 

如果外部使用者在 Azure Active Directory 中沒有帳戶，他們可以使用您租用戶中的來賓帳戶進行驗證。 當您[在 SharePoint 和 OneDrive 中啟用 Office 檔案的敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)，這些來賓帳戶也可以用來存取 SharePoint 或 OneDrive 中的共用文件：

- 其中一個選項是自己建立這些來賓帳戶。 您可以指定這些使用者已經使用的任何電子郵件地址。 例如，他們的 Gmail 地址。
    
    此選項的優點是您可以在加密設定中指定特定使用者的電子郵件地址，以限制特定使用者的存取權和權限。 缺點是會有帳戶建立與標籤設定協調的系統管理額外負荷。

- 另一個選項是使用 [SharePoint 和 OneDrive 與 Azure AD B2B (預覽) 整合](/sharepoint/sharepoint-azureb2b-integration-preview)，讓使用者在共用連結時自動建立來賓帳戶。
    
    此選項的優點是系統管理額外負荷最低，因為帳戶會自動建立，而且標籤設定更簡單。 針對此案例，您必須選取 [[新增任何驗證使用者]](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) 加密選項，因為您事先不會知道電子郵件地址。 缺點是此設定無法讓您限制特定使用者的存取和使用權。

當外部使用者使用 Windows 和 Microsoft 365 Apps ([之前稱為 Office 365 應用程式](/deployoffice/name-change)) 或 Office 2019 獨立版本時，也可以使用 Microsoft 帳戶開啟加密的文件。 最近也支援其他平台，因此也支援在 macOS (Microsoft 365 Apps 版本 16.42+)、Android (版本 16.0.13029+) 和 iOS (版本 2.42+) 上使用 Microsoft 帳戶開啟加密文件。 例如，貴組織的使用者與組織外部的使用者共用加密文件，而加密設定指定外部使用者的 Gmail 電子郵件地址。 此外部使用者可以使用其 Gmail 電子郵件地址建立自己的 Microsoft 帳戶。 然後，使用這個帳戶登入之後，他們就可以根據指定的使用限制開啟並編輯文件。 如需此案例的逐步指示範例，請參閱[開啟及編輯受保護的文件](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document) (部分機器翻譯)。

> [!NOTE]
> Microsoft 帳戶的電子郵件地址必須與指定來限制加密設定存取權限的電子郵件地址相符。

當擁有 Microsoft 帳戶的使用者以這種方式開啟加密文件時，如果系統不存在相同名稱的來賓帳戶，就會自動為租用戶建立來賓帳戶。 若來賓帳戶存在，則可以使用該來賓帳戶並使用 Office 網頁版在 SharePoint 和 OneDrive 中開啟文件，以及從支援的桌上型電腦與行動裝置 Office 應用程式開啟加密文件。

不過，由於複寫延遲，在此案例不會立即建立自動來賓帳戶。 如果您在標籤加密設定中指定個人電子郵件地址，建議您在 Azure Active Directory 中建立對應的來賓帳戶。 然後讓這些使用者知道他們必須使用這個帳戶才能開啟貴組織的加密文件。

> [!TIP]
> 因為您不確定外部使用者是否會使用支援的 Office 用戶端應用程式，所以在建立來賓帳戶 (針對特定使用者) 之後或使用 [SharePoint 和 OneDrive 與 Azure AD B2B 整合](/sharepoint/sharepoint-azureb2b-integration-preview) (針對任何已驗證的使用者) 時，從 SharePoint 和 OneDrive 共用連結，是支援與外部使用者安全共同作業更可靠的方法。

### <a name="conditional-access-policies"></a>條件式存取原則

如果貴組織已實作 [Azure Active Directory 條件式存取原則](/azure/active-directory/conditional-access/overview)，請檢查那些原則的設定。 如果原則包含 **Microsoft Azure 資訊保護** 且該原則延伸至外部使用者，則這些外部使用者必須在您的租用戶中擁有來賓帳戶，即使他們在自己的租用戶中擁有 Azure AD 帳戶也是如此。

如果沒有這個來賓帳戶，他們無法開啟加密文件並會看到錯誤訊息。 訊息文字可能會通知他們，需要在租用戶中將他們的帳戶新增為外部使用者，此案例的錯誤指示是 **登出並使用其他 Azure Active Directory 使用者戶帳戶重新登入**。

如果您無法為需要開啟文件 (該文件使用您的標籤加密) 的外部使用者，在租用戶中建立和設定來賓帳戶，您必須從條件式存取原則移除 Azure 資訊保護，或將外部使用者從該原則中排除。

如需條件式存取和 Azure 資訊保護、敏感度標籤所使用的加密服務的詳細資訊，請參閱常見問題集：[我發現 Azure 資訊保護是列為條件式存取的可用雲端應用程式，這是怎麼運作的呢？](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work) (部分機器翻譯)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office 應用程式何時套用內容標記和加密

Office 應用程式會根據您使用的應用程式，以不同方式使用敏感度標籤來套用內容標記和加密。

| 應用程式 | 內容標記 | 加密 |
| --- | --- | --- |
| 所有平台上的 Word、Excel、PowerPoint | 立即 | 立即 |
| 電腦版和 Mac 版 Outlook | Exchange Online 傳送電子郵件之後 | 立即 |
| 網頁版、iOS 版和 Android 版 Outlook | Exchange Online 傳送電子郵件之後 | Exchange Online 傳送電子郵件之後 |
|

將敏感度標籤套用至 Office 應用程式外部檔案的解決方案，是藉由將標籤中繼資料套用到檔案來完成。 在此案例中，標籤設定的內容標記不會插入檔案中，但會套用加密。 

當在 Office 傳統型應用程式中開啟這些檔案時，Azure 資訊保護統一標籤用戶端會自動套用內容標記。 當您針對傳統型、行動裝置或網頁版應用程式使用內建標籤時，不會自動套用內容標記。

將敏感度標籤套用在 Office 應用程式外的情況包括：

- Azure 資訊保護統一標籤用戶端的掃描器、檔案總管和 PowerShell 

- SharePoint 和 OneDrive 自動套用標籤原則

- 從 Power BI 匯出的標籤和加密資料

- Microsoft 雲端 App 安全性

針對這些案例，具有內建標籤的使用者可以使用 Office 應用程式，透過暫時移除或取代目前的標籤，然後重新套用原始標籤來套用標籤的內容標記。

### <a name="dynamic-markings-with-variables"></a>使用變數動態標記

> [!IMPORTANT]
> 目前，並非所有平台上的應用程式都支援您可以為頁首、頁尾及浮水印指定的動態內容標記。 對於不支援此功能的應用程式，它們會以標籤設定中指定的原始文字來套用標記，而不是解析變數。
> 
> Azure 資訊保護統一標籤用戶端支援動態標記以及所有列出的變數。 針對 Office 內建的標籤，請參閱此頁面上[功能](#support-for-sensitivity-label-capabilities-in-apps)一節中的表格，以了解最低版本，然後請參閱下表找出支援的變數。

當您設定內容標記的敏感度標籤時，您可以在文字字串中針對頁首、頁尾或浮水印使用下列變數：

| 變數 | 描述 | 套用標籤後的範例 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 套用標籤的標籤顯示名稱 <br /><br> 內建標籤：Word、Excel、PowerPoint 和 Outlook 支援 | **一般**|
| `${Item.Name}` | 要套用標籤之內容的檔案名稱或電子郵件主旨 <br /><br> 內建標籤：Word、Excel、PowerPoint 支援 | **Sales.docx** |
| `${Item.Location}` | 要套用標籤之文件的路徑和檔案名稱，或要套用標籤之電子郵件的電子郵件主旨 <br /><br> 內建標籤：Word、Excel、PowerPoint 支援 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | 正在套用標籤之使用者的顯示名稱 <br /><br> 內建標籤：Word、Excel、PowerPoint 支援 | **Richard Simone** |
| `${User.PrincipalName}` | 正在套用標籤之使用者的 Azure AD 使用者主體名稱 (UPN) <br /><br> 內建標籤：Word、Excel、PowerPoint 支援  | **rsimone\@contoso.com** |
| `${Event.DateTime}` | 內容套用標籤的日期和時間，位於套用標籤之使用者的本地時區 <br /><br> 內建標籤：Word、Excel、PowerPoint 支援  | **8/10/2020 1:30 PM** |

> [!NOTE]
> 這些變數的語法區分大小寫。

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>為 Word、Excel、PowerPoint 和 Outlook 設定不同的視覺標記

做為額外的變數，您可以在文字字串中使用 "If.App" 變數陳述式來設定每個 Office 應用程式類型的視覺標記，以及使用 **Word**、**Excel**、**PowerPoint** 或 **Outlook** 值來識別應用程式類型。 如果您想要在同一個 If.App 陳述式中指定多個值，也可以將這些值縮寫。

使用下列語法：

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

與其他動態視覺標記一樣，語法區分大小寫。

範例：

- **僅設定 Word 文件的頁首文字：**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    僅在 Word 文件頁首中，標籤會套用「此 Word 文件為機密」頁首文字。 不會將頁首文字套用到其他 Office 應用程式。

- **為 Word、Excel 和 Outlook 設定頁尾文字，並為 PowerPoint 設定不同頁尾文字：**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    在 Word、Excel 和 Outlook 中，標籤會套用「此內容為機密」頁尾文字。 在 PowerPoint 中，標籤會套用「此簡報為機密」頁尾文字。

- **為 Word 和 PowerPoint 設定特定浮水印文字，然後為 Word、Excel 和 PowerPoint 設定浮水印文字：**

    `${If.App.WP}This content is ${If.End}Confidential`

    在 Word 和 PowerPoint 中，標籤會套用「此內容為機密」浮水印文字。 在 Excel 中，標籤會套用「機密」浮水印文字。 在 Outlook 中，標籤不會套用任何浮水印文字，因為 Outlook 不支援浮水印視覺標記。

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>要求使用者在電子郵件和文件中套用標籤

> [!IMPORTANT]
> 也稱為強制套用標籤，並非所有平台上的所有應用程式目前都支援 **要求使用者在電子郵件和文件中套用標籤** 原則設定。
> 
> [Azure 資訊保護統一標籤用戶端](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)支援強制套用標籤，且適用於 Office 應用程式內建的標籤，請參閱本頁[功能](#support-for-sensitivity-label-capabilities-in-apps)章節中的表格。

選取此原則設定時，獲派原則的使用者必須在下列情況下選取並套用敏感度標籤：

- 針對 Azure 資訊保護統一標籤用戶端：
    - 針對文件 (Word、Excel、PowerPoint)：儲存未套用標籤的文件或使用者關閉文件時。
    - 針對電子郵件 (Outlook)：當使用者傳送未套用標籤的郵件時。

- 針對 Office 應用程式內建的標籤：
    - 針對文件 (Word、Excel、PowerPoint)：開啟或儲存未套用標籤的文件時。
    - 針對電子郵件 (Outlook)：當使用者傳送未套用標籤的電子郵件時。

內建標籤的其他資訊：

- 當使用者因為開啟未套用標籤的文件，而系統提示他們新增敏感度標籤時，他們可以新增標籤，或選擇以唯讀模式開啟文件。

- 當強制套用標籤生效時，使用者無法從文件移除敏感度標籤，但可以變更現有的標籤。

如需何時使用此設定的指導方針，請參閱[原則設定](sensitivity-labels.md#what-label-policies-can-do)的相關資訊。

> [!NOTE]
> 如果您除了強制標籤之外，還針對文件和電子郵件使用預設標籤原則設定： 
>
> 預設標籤一律優先於強制標籤。 不過，針對文件，Azure 資訊保護統一標籤用戶端會針對所有未標籤的文件套用預設標籤，而內建標籤會對新文件而非針對未標籤的現有文件套用預設標籤。 此行為差異表示，當您使用強制標籤搭配預設標籤時，當使用者使用內建標籤時，系統會較使用 Azure 資訊保護統一標籤用戶端時，更常提示使用者套用敏感度標籤。

## <a name="end-user-documentation"></a>使用者文件

- [在 Office 中將敏感度標籤套用至您的文件和電子郵件](https://support.microsoft.com/zh-TW/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [將敏感度標籤套用至 Office 檔案的已知問題](https://support.microsoft.com/zh-TW/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)