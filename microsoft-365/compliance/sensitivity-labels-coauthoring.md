---
title: 在 Microsoft 365 中啟用由敏感度標籤加密的檔案共同撰寫
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
description: 開啟可在桌面應用程式中針對 SharePoint 和 OneDrive 中已標記和加密的檔案啟用共同撰寫和自動儲存的設定。
ms.openlocfilehash: 990ab13508565fb910abe0d5e759a93e54766915
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245717"
---
# <a name="enable-co-authoring-for-files-encrypted-with-sensitivity-labels"></a>針對使用敏感度標籤加密的檔案啟用共同撰寫

>*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

> [!NOTE]
> 此功能處於預覽階段，可能會有所變更。 
>
> 在測試租用戶而非生產租用戶中啟用此功能，原因是：
> - 這項功能會變更標記中繼資料，並非所有平台上的所有應用程式目前都支援這項變更
> - 啟用此功能後，您無法自己停用此功能

啟用此設定以支援 Office 桌面應用程式 [共同撰寫](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) ，如此一來，當 [敏感度標籤](sensitivity-labels.md) 標記和加密檔案時，多個使用者可以同時編輯這些檔案。

未針對您的租用戶啟用此設定，使用者必須在使用 Office 桌面應用程式時，查看儲存在 SharePoint 或 OneDrive 中的加密檔案。 因此，他們無法即時共同合作。 或者，當 [SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度](sensitivity-labels-sharepoint-onedrive-files.md) 時，他們必須使用 Office 網頁。

此外，啟用此功能會導致這些已標記和加密的檔案支援 [自動儲存](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 功能。

若要閱讀發行公告，請參閱這篇部落格文章：[宣佈在 Microsoft 資訊保護加密的文件上共同撰寫並標示更新](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-co-authoring-on-microsoft-information-protection/ba-p/2164162)。

## <a name="metadata-changes-for-sensitivity-labels"></a>敏感度標籤的中繼資料變更

> [!IMPORTANT]
> 啟用共同撰寫的設定之後，未加密檔案的標籤資訊將不再儲存於自訂屬性中。
> 
> 如果使用任何將標籤中繼資料讀取或寫入舊位置的應用程式、服務、指令碼或工具，請勿啟用此設定。

在啟用設定以支援 Office 桌面應用程式共同撰寫之前，必須了解此動作會變更儲存至 Office 檔案和從 Office 檔案讀取的標籤中繼資料。

標籤中繼資料包含可識別租用戶和已套用敏感度標籤的資訊。 此設定所變更的是 Word、Excel 和 PowerPoint 未加密檔案的中繼資料格式和位置。 加密檔案或電子郵件沒有標籤中繼資料變更。

此變更會影響新標記的檔案和已標記的檔案。 當您使用支援共同撰寫設定的應用程式和服務時：
- 對於新標記的檔案，只會使用新的格式和位置來標記中繼資料。
- 對於已標記的檔案，下次開啟和儲存檔案時，如果檔案有舊格式和位置的中繼資料，它會複製到新的格式和位置。

您可以在下列資源中，閱讀有關此中繼資料變更的詳情：

- 部落格文章：[Microsoft 資訊保護中繼資料儲存空間的近期變更](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)

- 開啟規格：[2.6.3 LabelInfo 與自訂檔案屬性](/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)

由於這些變更，如果您的組織中有任何將標籤中繼資料讀取或寫入舊位置的應用程式、服務、指令碼或工具，請勿啟用此設定：

- 已標記的檔案會向使用者顯示為未標記

- 檔案向使用者顯示過期的標籤

- 如果其他使用者在不支援新標籤中繼資料的 Office 桌面應用程式中開啟已標記和加密的檔案，共同撰寫和自動儲存將無法用於該檔案

- 有一個 [將 Office 附件中的標籤識別為自訂屬性](/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) 的 Exchange Online 郵件流程規則，其無法加密電子郵件和附件，或不正確地加密它們

請查看下一節，以尋找支援此設定的應用程式和服務清單，以及標籤中繼資料的變更。

## <a name="prerequisites"></a>必要條件

開啟此功能之前，請確定您了解下列必要條件。

- 您必須使用測試租用戶來進行此預覽。

- 您必須是全域系統管理員才能開啟此功能。

- 必須為租用戶啟用 [SharePoint 和 OneDrive 中 Office 檔案](sensitivity-labels-sharepoint-onedrive-files.md) 的敏感度標記。 如果此功能尚未啟用，當您選取設定以開啟具有敏感度標籤的檔案共同撰寫時，就會自動啟用此功能。

- Microsoft 365 Apps 企業版：
    - **Windows**：預覽：[目前通道 (預覽)](https://office.com/insider)
    - **macOS**：預覽：[Beta 版通道](https://office.com/insider)
    - **iOS**：尚未支援
    - **Android**：尚未支援

- 您租用戶中所有的應用程式、服務和作業工具都必須支援新的應用程式 [標籤中繼資料](#metadata-changes-for-sensitivity-labels)。 如果您使用下列任何一項，請檢查所需的最低版本：
    
    - **Azure 資訊保護統一標籤用戶端和掃描：**
        - 可從 [Microsoft 下載中心](https://www.microsoft.com/en-us/download/details.aspx?id=53018)安裝的公開預覽版本 (AzInfoProtection_2.10.46_CoAuthoring_PublicPreview.exe 的安裝名稱)
    
    - **適用於 Windows 或 macOS 的 OneDrive 同步處理應用程式：**
        - 最低版本 19.002.0121.0008
    
    - **端點資料外洩防護 (端點 DLP)：**
        - Windows 10 1809 搭配 KB 4601383
        - Windows 10 1903 和 1909 搭配 KB 4601380
        - Windows 10 2004 搭配 KB 4601382
    
    - **使用 Microsoft 資訊保護 SDK 的應用程式和服務：** 
        - 最低版本 1.7 

當您開啟此功能時，Microsoft 365 服務會自動支援新的標籤中繼資料。例如：

- [自動標籤原則](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)
- [使用敏感度標籤作為條件的 DLP 原則](dlp-sensitivity-label-as-condition.md)
- [Microsoft Cloud App Security 已設為套用敏感度標籤](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)

## <a name="limitations"></a>限制

在針對使用敏感度標籤加密的檔案啟用共同撰寫的租用戶設定之前，請確定您了解此功能的下列限制。

- 由於 [標籤中繼資料變更](#metadata-changes-for-sensitivity-labels)，您租用戶中所有的應用程式、服務和作業工具都必須支援新的標籤中繼資料，以得到一致且可靠的標籤體驗。
    
    Excel 專用：如果有人使用不支援敏感度標籤中繼資料變更的 Excel 版本來編輯並保存該檔案，則不應用加密的敏感度標籤中繼資料可以從檔案中刪除。

- 不支援共同撰寫和自動儲存，且無法用於使用下列任何 [加密設定](encryption-sensitivity-labels.md#configure-encryption-settings) 的已標記和加密的 Office 檔案：
    - **讓使用者在套用標籤時指派權限**，且核取方塊 **在 Word、PowerPoint 與 Excel 中提示使用者指定權限** 為選取狀態。 此設定有時稱為「使用者定義的權限」。
    - **使用者的內容存取權到期日** 設定為 **永不** 以外的值。
    - **使用雙重金鑰加密** 已選取。
    
    對於具有這些加密設定的標籤，標籤會顯示在 Office 應用程式中。 不過，當使用者選取這些標籤，且沒有其他人在編輯檔案時，系統會警告他們共同撰寫和自動儲存將無法使用。 如果有其他人在編輯文件，使用者會看到「無法套用這些標籤」的訊息。

- 如果您使用 Azure 資訊保護統一標籤用戶端：請查看此標籤用戶端的文件，以取得[更多需求或限制](/azure/information-protection/known-issues#known-issues-for-co-authoring-public-preview)。

## <a name="known-issues-for-this-preview"></a>此預覽的已知問題

此預覽版使用敏感度標籤加密的檔案共同撰寫有下列已知問題：

- 使用者無法針對大於 300 MB 的 Word、Excel 和 PowerPoint 檔案，在 Office 網頁版中為任何的檔案套用任何標籤。 對於這些檔案，您可以使用 Office 桌面應用程式來套用標籤，但您必須是唯一開啟檔案的人。

- 當您使用 [將敏感度標籤作為條件的 DLP](dlp-sensitivity-label-as-condition.md) 時，電子郵件的未加密附件不受支援。

- 某些文件由於 [密碼保護](https://support.microsoft.com/office/require-a-password-to-open-or-modify-a-workbook-10579f0e-b2d9-4c05-b9f8-4109a6bce643)、 [共用活頁簿](https://support.microsoft.com/office/about-the-shared-workbook-feature-49b833c0-873b-48d8-8bf2-c1c59a628534)，或包含 ActiveX 控制項內容等功能，而與敏感度標籤不相容。 其他原因會記錄在 [在 Office 中共同撰寫的疑難排解](https://support.microsoft.com/office/troubleshoot-co-authoring-in-office-bd481512-3f3a-4b6d-b7eb-ebf9d3626ae7)。 針對這些文件，您會看到 **[上傳失敗]** 訊息，且應選取 **[捨棄變更]** 選項。 在解決此問題之前，請勿標記這些以此失敗訊息識別的文件。

- 不支援 iOS 版和 Android 版 Office 應用程式。

## <a name="how-to-enable-co-authoring-for-files-with-sensitivity-labels"></a>如何啟用具有敏感度標籤的檔案共同撰寫

> [!CAUTION]
> 開啟此設定是單向動作。此功能為預覽版時，請只在非實際執行環境中進行測試，且只有在您閱讀並了解中繼資料變更、必要條件、限制，以及此頁面上記錄的任何已知問題之後，再進行測試。

在預覽期間，您必須使用特定的 URL，以在 Microsoft 365 合規性中心存取此設定。

1. 使用下列連結，以測試租用戶全域系統管理員的身分登入 Microsoft 365 合規性中心：
    
    ```http
    https://compliance.microsoft.com/co-authoring_for_files_with_sensitivity_labels
    ```
    此連結會直接將您帶至租用戶設定，**共同撰寫具有敏感度標記的檔案**。

    > [!IMPORTANT]
    > 在您繼續之前，請檢查您是否已登入不會影響您的使用者的測試租用戶： 
    >
    > 選取合規性中心右上方具有您帳戶縮寫的圓圈，並確認租用戶名稱確實顯示您預期的測試租用戶。
    
2. 閱讀摘要描述、必要條件、預期項目，以及開啟此設定後無法關閉的警告。 然後依序選取 **開啟具有敏感度標籤的檔案共同撰寫** 以及 **套用**：
    
    ![開啟具有敏感度標籤之檔案共同撰寫的選項](../media/co-authoring-tenant-option-for-sensitivity-labels.png)

3. 在您測試這項新功能進行共同撰寫之前，請等候 24 小時，讓此設定在整個環境中進行複製。

## <a name="contact-support-if-you-need-to-disable-this-feature"></a>如果您需要停用此功能，請聯絡客戶支援

> [!IMPORTANT]
> 如果您需要停用此功能，請注意標籤資訊可能會遺失。

為租用戶啟用具有敏感度標籤的檔案共同撰寫之後，您無法自己停用此設定。 這就是為什麼在啟用此設定之前，務必先查看並了解必要條件、結果和限制。 這也是我們建議您使用測試租用戶而非生產租用戶來測試此功能的原因。

![顯示已針對敏感度標籤開啟共同撰寫的選項](../media/co-authoring-tenant-option-set-for-sensitivity-labels.png)

正如您在此設定開啟時從螢幕擷取畫面中所看到的一樣，您可以聯絡 [Microsoft 支援服務](/office365/admin/contact-support-for-business-products) 並要求關閉此設定。 此要求可能需要數天的時間，您必須證明您為租用戶全域系統管理員。 預期需要支付一般支援費用。 

如果支援工程師針對您的租用戶停用此設定：

- 對於支援新標籤中繼資料的應用程式和服務，現在當讀取或儲存標籤時，它們會還原為原始的中繼資料格式和位置。

- 啟用設定時所使用的 Office 檔的新中繼資料格式和位置將不會複製到原始格式和位置。 因此，未加密 Word、Excel 和 PowerPoint 檔案的此標籤資訊將會遺失。

- 對於已標籤和已加密的文件，共同撰寫和自動儲存無法再於您的租用戶中使用。

- 在 OneDrive 和 SharePoint 中，Office 檔案的敏感度標籤仍維持啟用。