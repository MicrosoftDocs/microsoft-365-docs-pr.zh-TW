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
description: 瞭解使用者在電腦版、行動版和網頁版 Office App 中如何使用敏感度標籤，以及哪些應用程式支援敏感度標籤。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d84735cc51b26df6b4c28ffc3bf8fb99f896f1ae
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925693"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>在 Office 應用程式中使用敏感度標籤

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

當您從[](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)Microsoft 365 規範中心或同等的標籤中心發佈敏感度標籤時，這些標籤會開始顯示在 Office App 中，讓使用者在建立或編輯資料時分類及保護資料。

使用本文中的資訊可協助您成功管理 Office App 中的敏感度標籤。 例如，識別支援內建標籤所需的 App 最低版本，並瞭解與 Azure 資訊保護統一標籤用戶端的互動，以及與其他應用程式和服務相容性。

## <a name="labeling-client-for-desktop-apps"></a>桌面應用程式的標籤用戶端

若要使用 Windows 版和 Mac 版 Office 桌面應用程式內建的敏感度標籤，您必須使用 Office 訂閱版本。 此標籤用戶端不支援獨立版本的 Office，例如 Office 2016 或 Office 2019。

若要在 Windows 電腦上使用這些獨立版本的 Office 來使用敏感度標籤，請安裝 [Azure 資訊保護的一致標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)。

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>支援應用程式中的敏感度標籤功能

下錶針對每個功能列出使用內建標籤支援敏感度標籤的最低 Office 版本。 或者，如果標籤功能是在公開預覽版中，或正針對未來版本進行審查。 使用 [Microsoft 365 藍圖](https://aka.ms/MIPC/Roadmap) 來瞭解未來版本的詳細資訊。

不同更新通道會在不同的時間提供新版 Office App。 有關詳細資訊，包括如何設定更新通道，以便測試您感興趣的新標籤功能，請參閱 [Microsoft 365 應用程式更新通道概觀](https://docs.microsoft.com/DeployOffice/overview-update-channels)。 表格中不會包含私人預覽中的新功能，但您可以指定貴組織參與 Microsoft 資訊保護私人預覽計畫，以加入這些 [預覽版](https://aka.ms/mip-preview)。

> [!NOTE]
> Office 應用程式更新通道的名稱最近有變更。 例如，每月通道現在為目前通道，而 Office 測試人員現在為 Beta 通道。 詳細資訊請參閱 Microsoft [365 應用程式更新通道的變更](https://docs.microsoft.com/deployoffice/update-channels-changes)。

iOS 版 Office 和 Android 版 Office：敏感度標籤內建于[Office App。](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)

當您安裝 Azure 資訊保護統一標籤用戶端時 ，會提供其他功能，此用戶端只能在 Windows 電腦上執行。 有關這些詳細資料，請參閱 [比較 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel 和 PowerPoint 中的敏感度標籤功能

列出的數位是每項功能所需的 Office 應用程式版本最低需求。

|功能                                                                                                        |Windows |Mac |iOS    |Android      |網址                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[手動申請、變更或移除標籤](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 加入宣告](sensitivity-labels-sharepoint-onedrive-files.md) |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 加入宣告](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[需要對齊以變更標籤](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 加入宣告](sensitivity-labels-sharepoint-onedrive-files.md) |
|[提供自訂説明頁面的協助連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 加入宣告](sensitivity-labels-sharepoint-onedrive-files.md) |
|[標記內容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 加入宣告](sensitivity-labels-sharepoint-onedrive-files.md) |
|[動態標記與變數](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | 評論中 |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 加入宣告](sensitivity-labels-sharepoint-onedrive-files.md) |
|[讓使用者指派權限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | 評論中   | 評論中         | 評論中                                                        |
|[使用標籤分析來查看標籤使用方式，](label-analytics.md) 並傳送資料給系統管理員                      | 預覽 [：目前通道 (預覽) ](https://office.com/insider)            | 預覽 [：目前通道 (預覽) ](https://office.com/insider)        | 評論中   | 評論中         | 是的 <sup>\*</sup>                                                        |
|[要求使用者將標籤用於電子郵件和檔](sensitivity-labels.md#what-label-policies-can-do)   | 預覽：推出至目前 [通道 (預覽) ](https://office.com/insider)             | 預覽：推出至目前 [通道 (預覽) ](https://office.com/insider)         | 評論中   | 預覽 [：Beta 通道](https://office.com/insider)         | 評論中                                            
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 2009+                                  | 推出：16.44+ | 評論中 | 評論中 | [是 - 加入宣告](sensitivity-labels-sharepoint-onedrive-files.md) |
|支援[在已卷](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)標[](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4)和加密的檔上自動Save和共同作者 | 評論中 | 評論中 | 評論中 | 評論中 | [是 - 加入宣告](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**註腳：**

<sup>\*</sup> 目前，不包含移除標籤或降低分類層級的對齊文字

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook 中的敏感度標籤功能

列出的數位是每項功能所需的 Office 應用程式版本最低需求。

|功能                                                                                                        | Outlook for Windows |Mac 版 Outlook |iOS 上的 Outlook |Android 上的 Outlook |Outlook 網頁版 |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[手動申請、變更或移除標籤](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[套用預設標籤](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[需要對齊以變更標籤](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[提供自訂説明頁面的協助連結](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[標記內容](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[動態標記與變數](#dynamic-markings-with-variables)                                              | 評論中                     | 評論中                 | 評論中         | 評論中           | 評論中               |
|[立即指派權限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[讓使用者指派權限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[要求使用者將標籤用於電子郵件和檔](#require-users-to-apply-a-label-to-their-email-and-documents)   | 預覽[：目前通道 (預覽) ) ](https://office.com/insider)                        | 16.43+                     | 評論中            | 評論中                | 是                |
|[使用標籤分析來查看標籤使用方式，](label-analytics.md) 並傳送資料給系統管理員                      | 預覽 [：目前通道 (預覽) ](https://office.com/insider)                       | 預覽 [：目前通道 (預覽) ](https://office.com/insider)                    | 評論中           | 評論中               | 是               |
|[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+                    | 評論中           | 評論中               | 是 |
|


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 內建標籤用戶端和其他標籤解決方案

Office 內建的標籤用戶端會從下列系統管理中心下載敏感度標籤和敏感度標籤策略設定：

- Microsoft 365 合規性中心
- Microsoft 365 安全性中心
- Office 365 安全性與合規性中心

若要使用 Office 內建標籤用戶端，您必須從所列的系統管理中心[](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)和支援的[Office](#support-for-sensitivity-label-capabilities-in-apps)版本，將一或多個標籤策略發佈給使用者。

如果同時符合這兩個條件，但您需要關閉 Office 內建標籤用戶端，請使用下列群組原則設定：

1. 流覽至 **使用者設定/系統管理範本/Microsoft Office 2016/安全性設定**。

2. 在 **Office 中設定使用敏感度功能，將** 敏感度標籤套用並查看為 **0。** 
 
使用群組原則或 Office 雲端策略服務部署 [此設定](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)。 此設定在 Office App 重新開機時即生效。

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 內建標籤用戶端和 Azure 資訊保護用戶端

如果使用者已安裝其中一個 Azure 資訊保護用戶端 ([統](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) 一標籤用戶端或傳統用戶端 [) ，](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client) 則根據預設，內建的標籤用戶端會關閉其 Office App。 

若要使用內建標籤，而不是適用于 Office App 的 Azure 資訊保護用戶端，請使用上一節的指示，但將群組原則設定設為使用 **Office** 中的敏感度功能，將敏感度標籤套用及查看為 **1。** 

或者，停用或移除 Office 外掛程式 Azure **資訊保護**。 此方法適用于單一電腦和臨時測試。 有關指示，請參閱 Office 程式中的View、Manage 及 install [。](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) 

當您停用或移除此 Office 附加元件時，系統仍然會安裝 Azure 資訊保護用戶端，這樣您才能繼續為 Office 應用程式以外的檔案加上標籤。 例如，使用檔案管理器或 PowerShell。

有關 Azure 資訊保護用戶端和 Office 內建標籤用戶端支援哪些功能的資訊，請參閱 Azure 資訊保護檔中選擇要用於 [Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) 電腦的標籤用戶端。

## <a name="office-file-types-supported"></a>支援的 Office 檔案類型

具有 Word、Excel 和 PowerPoint 檔案內建標籤的 Office App 支援 Open XML 格式 (例如 .docx 和 .xlsx) ，但不支援 Microsoft Office 97-2003 格式 (例如 .doc 和 .xls) 。 如果內建標籤不支援檔案類型，Office App 中就未提供敏感度按鈕。

Azure 資訊保護統一標籤用戶端支援 Open XML 格式和 Microsoft Office 97-2003 格式。 詳細資訊請參閱該用戶端管理指南中 [Azure 資訊保護統](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) 一標籤用戶端支援的檔案類型。

有關其他標籤解決方案，請查看其檔以尋找支援的檔案類型。

## <a name="protection-templates-and-sensitivity-labels"></a>保護範本和敏感度標籤

當您 [使用內建](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)標籤時，Office App 中不會顯示系統管理員定義的保護範本，例如您為 Office 365 郵件加密定義的範本。 這種簡化的體驗反映出不需要選取保護範本，因為啟用加密的敏感度標籤包含相同的設定。

如果您需要將現有的保護範本轉換成標籤，請使用 Azure 入口網站和下列指示：將 [範本轉換為標籤](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>資訊版權管理 (IRM) 選項和敏感度標籤

您設定為使用加密的敏感度標籤會移除使用者指定自己的加密設定的複雜性。 在許多 Office App 中，使用者仍可使用資訊版權管理或 IRM 選項 (這些) 設定。 例如，Windows 應用程式：

- 檔：**檔案**  >  **資訊**  >  **保護檔限制**  >  **存取**
- 電子郵件：從 **選項或加密**>  
  
當使用者一開始為檔或電子郵件設定標籤時，他們隨時都可以使用自己的加密設定來覆蓋標籤設定。 例如：

- 使用者將機密 \ **所有員工** 標籤適用于檔，且此標籤已設定為為組織中所有使用者進行加密設定。 使用者接著手動設定 IRM 設定，以限制組織外部使用者的存取權。 結果檔會標示為機密 **\** 所有員工都經過加密，但貴組織的使用者無法如預期方式開啟檔。

- 使用者將機密 **\** 只有收件者標籤適用于電子郵件，而且此電子郵件已設定為將加密設定用於不可 **轉轉**。 使用者接著手動設定 IRM 設定，使電子郵件不受限制。 最後，即使具有機密 \ 只有收件者標籤，收件者 **還是可以轉轉** 電子郵件。

- 使用者將一般 **卷** 標應用至檔，而且未將這個標籤進行加密。 使用者接著手動設定 IRM 設定以限制檔的存取權。 最後，檔會標示為一般，但也會進行加密，讓某些使用者無法如預期般開啟檔。

如果該檔或電子郵件已標示為標籤，使用者就可以在內容尚未加密，或是其使用權為匯出或完全控制時，執行任何這些動作[](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。 

若要使用有意義的報告獲得更一致的標籤體驗，請提供適當的標籤和指南，讓使用者只貼上標籤以保護檔。 例如：

- 針對使用者必須自行指派許可權的例外情況，請提供可讓使用者 [自行指派許可權的標記](encryption-sensitivity-labels.md#let-users-assign-permissions)。 

- 當使用者需要分類相同，但沒有加密的標籤時，請提供子標籤，讓使用者不用在選取適用加密的標籤後手動移除加密。 如：
    - **機密 \ 所有員工**
    - **機密 \ 任何人 (加密)**

> [!NOTE]
> 如果使用者從 SharePoint 或 OneDrive 中儲存的標籤檔手動移除加密，而且您已啟用 SharePoint 和 [OneDrive 中 Office](sensitivity-labels-sharepoint-onedrive-files.md)檔案的敏感度標籤，標籤加密會在下次存取或下載檔案時自動還原。 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>將敏感度標籤貼到檔案、電子郵件和附件

使用者一次只能為一份檔或電子郵件申請一個標籤。

當您為包含附件的電子郵件訊息標示標籤時，附件不會繼承標籤，但例外：

- 附件是包含未加密標籤的 Office 檔，而您適用于電子郵件訊息的標籤會進行加密。 在此案例中，電子郵件的 Office 檔會繼承電子郵件的標籤及其加密設定。

否則： 

- 如果附件有標籤，它們會保留原本所貼上的標籤。
- 如果附件加密時沒有使用標籤，加密會保留，但不會標示。
- 如果附件沒有標籤，這些附件會維持未標籤。

## <a name="sensitivity-label-compatibility"></a>敏感度標籤相容性

**使用 RMS** 型應用程式：如果您在不支援敏感度標籤的 [RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 應用程式中開啟標籤和加密的檔或電子郵件，應用程式仍然會強制執行加密和版權管理。

使用 Azure 資訊保護用戶端：您可以使用 **Azure** 資訊保護用戶端和其他方式，使用 Office 內建標籤用戶端來查看及變更您用於檔和電子郵件的敏感度標籤。

**與其他版本的 Office：** 任何授權的使用者都可以在其他版本的 Office 中開啟標籤檔和電子郵件。 不過，您僅能查看或變更支援之 Office 版本中的標籤，或是使用 Azure 資訊保護用戶端。 支援的 Office App 版本會列在上 [一節](#support-for-sensitivity-label-capabilities-in-apps)。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>支援由敏感度標籤保護的 SharePoint 和 OneDrive 檔案

若要將 Office 內建標籤用戶端與 Office 網頁版本一起使用，以用於 SharePoint 或 OneDrive 中的檔，請確認您已啟用 SharePoint 和 OneDrive 中 Office 檔案的敏感度 [標籤](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="support-for-external-users-and-labeled-content"></a>支援外部使用者和標示的內容

當您為檔或電子郵件標示標籤時，標籤會儲存為中繼資料，其中包含您的租使用者和標籤 GUID。 當標籤的檔或電子郵件是由支援敏感度標籤的 Office App 開啟時，系統只會讀取此中繼資料，而且只有在使用者屬於同一個租使用者時，標籤會顯示于他們的 App 中。 例如，針對 Word、PowerPoint 和 Excel 的內建標籤，標籤名稱會顯示在狀態列上。 

這表示，如果您與使用不同標籤名稱的組織共用文件，每個組織都可以將自己的標籤應用至檔，並查看其標籤。 不過，貴組織外部的使用者可以看到所使用標籤中的下列元素：

- 內容標記。 當標籤適用于頁標題、頁腳或浮水印時，這些會直接新增到內容中，並持續顯示，直到有人修改或刪除它們。

- 來自已加密標籤之基礎保護範本的名稱和描述。 此資訊會顯示在檔頂端的訊息列，提供誰有權開啟檔及其檔使用權的資訊。

### <a name="sharing-encrypted-documents-with-external-users"></a>與外部使用者共用加密的檔

除了限制貴組織中使用者的存取權，您還可以將存取權延伸到在 Azure Active Directory 中擁有帳戶的其他使用者。 在使用者通過成功驗證後，所有 Office App 和其他 [RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 應用程式都可以開啟加密檔。

如果外部使用者沒有 Azure Active Directory 中的帳戶，他們可以使用您租使用者中的來賓帳戶進行驗證。 當您啟用 SharePoint 和 OneDrive 中 Office 檔案的敏感度標籤時，這些來賓帳戶也可以用來存取 SharePoint 或 [OneDrive 中的共用文件](sensitivity-labels-sharepoint-onedrive-files.md)：

- 其中一個選項是自己建立這些來賓帳戶。 您可以指定這些使用者已經使用的任何電子郵件地址。 例如，他們的 Gmail 位址。
    
    此選項的優點是，您可以在加密設定中指定特定使用者的電子郵件地址，以限制特定使用者的存取和許可權。 缺點是帳戶建立及與標籤組配置協調的系統管理負荷。

- 另一個選項是使用 SharePoint 和 OneDrive 與 [Azure AD B2B (Preview ](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)) 整合，這樣當使用者共用連結時，就會自動建立來賓帳戶。
    
    此選項的好處是系統管理負荷最低，因為帳戶會自動建立，而且標籤配置也比較簡單。 在此情境中，您必須選取加密選項以新增[](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users)任何已驗證的使用者，因為您事先不知道電子郵件地址。 缺點是，這項設定不會讓您將存取和使用許可權限制給特定使用者。

當外部使用者于 Windows 上使用 Microsoft 365 應用程式 (前 Office [365](https://docs.microsoft.com/deployoffice/name-change) 應用程式) ，以及新支援的 macOS (版本 16.42+) 、Android (版本 16.0.13029+) 和 iOS (版本 2.42+) 時，您也可以使用 Microsoft 帳戶加密的檔。 例如，有人與某人共用加密的檔，而加密設定會指定他們的 Gmail 電子郵件地址。 此使用者可以使用自己的 Gmail 電子郵件地址建立自己的 Microsoft 帳戶。 然後，使用這個帳戶之後，他們就可以根據針對該使用者指定的使用限制開啟並編輯檔。 有關此案例的分步範例，請參閱開啟和編輯 [受保護的檔](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)。

> [!NOTE]
> Microsoft 帳戶的電子郵件地址必須與限制加密設定存取權所指定的電子郵件地址相符。

當擁有 Microsoft 帳戶的使用者以此方法開啟加密的檔時，如果相同名稱的來賓帳戶不存在，就會自動為租使用者建立來賓帳戶。 當來賓帳戶存在時，除了從 Windows 桌面應用程式開啟加密的檔之外，您還可以使用瀏覽器 (Office 網頁版) 在 SharePoint 和 OneDrive 中開啟檔。 

不過，在此情境中，由於複寫延遲，系統不會立即建立自動來賓帳戶。 如果您在標籤加密設定中指定個人電子郵件地址，我們建議您在 Azure Active Directory 中建立對應的來賓帳戶。 然後讓這些使用者知道他們必須使用這個帳戶，從貴組織開啟加密的檔。

> [!TIP]
> 由於您不確定外部使用者會使用支援的 Office 用戶端應用程式，因此在為特定使用者建立來賓帳戶 (後，或當您針對任何已驗證的使用者使用 SharePoint 和 OneDrive 整合 Azure [AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) () 後，從 SharePoint 和 OneDrive 共用連結) 是一種更可靠的方法，可支援與外部使用者安全地共同合作。

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>當 Office 應用程式會進行內容標記和加密時

Office App 會根據您使用的 App，以不同方式使用敏感度標籤來使用內容標記和加密。

| 應用程式 | 內容標記 | 加密 |
| --- | --- | --- |
| 所有平台上的 Word、Excel、PowerPoint | 立即 | 立即 |
| 電腦版和 Mac 版 Outlook | Exchange Online 傳送電子郵件之後 | 立即 |
| 網頁版、iOS 版和 Android 版 Outlook | Exchange Online 傳送電子郵件之後 | Exchange Online 傳送電子郵件之後 |
|

將敏感度標籤適用于 Office 應用程式外部檔案的解決方案，就是將標籤中繼資料應用程式至檔案。 在此情境中，來自標籤組配置的內容標記不會插入檔案中，但會進行加密。 

在 Office 桌面應用程式中開啟這些檔案時，內容標記會自動由 Azure 資訊保護的一致標籤用戶端來申請。 當您針對桌面、行動或 Web 應用程式使用內建標籤時，內容標記並不會自動顯示。

包括將敏感度標籤適用于 Office 應用程式外部的情況包括：

- 來自 Azure 資訊保護統一標籤用戶端的掃描器、檔案管理器和 PowerShell 

- SharePoint 和 OneDrive 的自動標籤政策

- 從 Power BI 匯出標籤和加密的資料

- Microsoft Cloud App Security

在這些情況下，使用者可以使用 Office App 來使用內建標籤，暫時移除或取代目前的標籤，然後重新使用原始的標籤，以貼上標籤的內容標記。

### <a name="dynamic-markings-with-variables"></a>動態標記與變數

> [!IMPORTANT]
> 目前，並非所有平臺上所有的應用程式都支援動態內容標記，您可為頁碼、頁腳及浮水印指定這些標記。 對於不支援此功能的 App，他們會將標記以標籤配置中指定的原始文字來使用，而不是解決變數。
> 
> Azure 資訊保護統一標籤用戶端支援動態標記。 針對 Office 內建的標籤功能，請參閱本頁功能 [區段](#support-for-sensitivity-label-capabilities-in-apps) 內的資料表。

當您設定內容標記的敏感度標籤時，您可以在頁標題、頁腳或浮水印的文字字串中，使用下列變數：

| 變數 | 描述 | 已貼上標籤的範例 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 已申請標籤的標籤顯示名稱| **一般**|
| `${Item.Name}` | 標示內容的檔案名或電子郵件主題 | **Sales.docx** |
| `${Item.Location}` | 正在標示檔的路徑和檔案名，或電子郵件被標示為電子郵件的電子郵件主題 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | 使用標籤之使用者的顯示名稱| **王亞力** |
| `${User.PrincipalName}` | Azure AD 使用者主體名稱 (使用) 標籤之使用者的 UPN 名稱 | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | 內容標示的日期和時間，在使用者于當地時區中以貼上標籤 | **2020/8/10 1：30 PM** |

> [!NOTE]
> 這些變數的語法會區分大小寫。

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>為 Word、Excel、PowerPoint 和 Outlook 設定不同的視覺標記

做為額外的變數，您可以使用文字字串中的 "If.App" 變數語句，為每個 Office 應用程式類型設定視覺標記，並且使用Word、Excel、PowerPoint 或 **Outlook** 的值來識別應用程式類型。 如果您想要在同一個 If.App 語句中指定多個值，您也可以縮寫這些值。

> [!NOTE]
> 為了完整，包含 Outlook 的指示，不過目前僅支援 Azure 資訊保護統一標籤用戶端。

使用下列語法：

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

和其他動態視覺標記一樣，語法會區分大小寫。

範例：

- **只設定 Word 檔的標題文字：**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    只在 Word 檔標題中，標籤會使用標題文字「此 Word 檔有敏感」。 標題文字不會適用于其他 Office 應用程式。

- **設定 Word、Excel 和 Outlook 的頁腳文字，以及 PowerPoint 的不同頁腳文字：**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    在 Word、Excel 和 Outlook 中，標籤會使用「此內容為機密」的頁腳文字。 在 PowerPoint 中，標籤會使用頁腳文字「此簡報為機密」。

- **設定 Word 和 PowerPoint 的特定浮水印文字，然後設定 Word、Excel 和 PowerPoint 的浮水印文字：**

    `${If.App.WP}This content is ${If.End}Confidential`

    在 Word 和 PowerPoint 中，標籤會使用「此內容為機密」浮水印文字。 在 Excel 中，標籤會使用「機密」浮水印文字。 在 Outlook 中，標籤不會為任何浮水印文字顯示，因為 Outlook 不支援浮水印作為視覺標記。

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>要求使用者將標籤用於電子郵件和檔

> [!IMPORTANT]
> 也稱為強制標籤，並非所有平臺上的應用程式目前都支援要求使用者將標籤用於電子郵件和檔原則 **設定**。
> 
> [Azure 資訊保護統一標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)支援強制標籤，而且對於內建于 Office App 的標籤，請參閱[](#support-for-sensitivity-label-capabilities-in-apps)本頁功能區段內的資料表。

選取此原則設定時，指派原則的使用者必須在下列情況下選取並申請敏感度標籤：

- 針對 Azure 資訊保護統一標籤用戶端：
    - 如果檔 (Word、Excel、PowerPoint) ：儲存未標記的檔或使用者關閉檔時。
    - 針對 Outlook () ：當使用者傳送未標記的郵件時。

- 對於內建于 Office App 的標籤：
    - 對於使用 ( (Word、Excel、PowerPoint) ：開啟或儲存未標記的檔時。
    - 針對 Outlook () ：當使用者傳送未標記的電子郵件訊息時。

內建標籤的其他資訊：

- 當系統提示使用者新增敏感度標籤，因為使用者開啟未標記的檔時，可以新增標籤，或選擇以唯讀模式開啟檔。

- 當強制標籤生效時，使用者無法從檔移除敏感度標籤，但可以變更現有的標籤。

## <a name="end-user-documentation"></a>使用者檔

- [在 Office 中將敏感度標籤套用至您的文件和電子郵件](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [將敏感度標籤套用至 Office 檔案的已知問題](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
