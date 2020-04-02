---
title: 自動將敏感度標籤套用到內容
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
search.appverid:
- MOE150
- MET150
description: 建立敏感度標籤時，您可以自動為文件或電子郵件指派標籤，或者也可以提示使用者選取您建議的標籤。
ms.openlocfilehash: a087d142843ce74de3a930aea9286034b8617db6
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106069"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>自動將敏感度標籤套用到內容

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

建立敏感度標籤時，您可以自動將該標籤指派給包含敏感性資訊的內容，或者也可以提示使用者套用您建議的標籤。

自動將敏感度標籤套用到內容很重要，因為：

- 您不需要訓練您的使用者記下所有分類。

- 您不需要仰賴使用者正確地將所有內容分類。

- 使用者不再需要了解原則，而是可以專心於工作。

在 Windows 版 Office 應用程式中的自動標籤，是由 Azure 資訊保護整合標籤用戶端支援。 針對在 Office 應用程式中的內建標籤功能，在[某些應用程式為預覽](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

當您[建立或編輯敏感度標籤時，可使用適用於 Office 應用程式的自動加上標籤設定](create-sensitivity-labels.md)：

![敏感度標籤的自動標籤選項](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>如何設定適用於 Office 應用程式的自動加上標籤

敏感度標籤最實用的功能之一，是將標籤自動套用至符合特定條件的內容。 在此情況下，貴組織中的人員不必親自套用敏感度標籤，Office 365 會完成相關作業。

當內容包含特定類型的敏感資訊時，您可以選擇自動將敏感度標籤套用到內容。 從敏感度資訊類型或分類器清單中選擇：

![在 Office 應用程式中自動加上標籤的標籤條件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> 目前，[分類器]**** 的選項在限制預覽中，您必須將表單提交給 Microsoft，才能為您的租用戶啟用這項功能。 如需詳細資訊，請參閱[宣佈在 Office 應用程式中使用內建分類器自動加上標籤 - 限制預覽](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889) (英文)。

自動套用此敏感度標籤時，使用者會在其 Office 應用程式中看到通知。 例如：

![文件已自動套用標籤的通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>設定標籤的敏感度資訊類型

當您選取 [敏感度資訊類型]**** 選項時，會看到與在建立資料外洩防護 (DLP) 原則時相同的敏感度資訊類型清單。 例如，您可以自動將 [高度機密] 標籤套用至任何包含客戶個人身分識別資訊 (PII) 的內容，例如信用卡號碼或身分證號碼：

![在 Office 應用程式中自動加上標記的敏感資訊類型](../media/sensitivity-labels-sensitive-info-types.png)

選取敏感度資訊類型之後，您可以變更執行個體計數或比對精確度來調整條件。 如需詳細資訊，請參閱[調整規則，讓規則更容易或更難相符](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。

此外，您可以選擇條件是必須偵測所有敏感性資訊類型，還是只偵測其中一種。 若要讓您的條件更靈活或更複雜，您可以新增群組，並使用群組之間的邏輯運算子。 如需詳細資訊，請參閱[群組和邏輯運算子](data-loss-prevention-policies.md#grouping-and-logical-operators)。

![執行個體計數和比對精確度的選項](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a>為標籤設定分類器

當您選取 [分類器]**** 選項時，請選取一或多個內建分類器：

![分類器和敏感度標籤的選項](../media/sensitivity-labels-classifers.png)

如需這些分類器的詳細資訊，請參閱[開始使用可訓練的分類器 (預覽)](classifier-getting-started-with.md) (部分機器翻譯)。

在預覽期間，下列應用程式支援靈敏度標籤的分類器：

- 來自 [Office 測試人員](https://office.com/insider)的 Windows 版 Office 365 專業增強版傳統型應用程式：
    - Word
    - Excel
    - PowerPoint

- 當您[在 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md) 時的 Office Web 應用程式：
    - Word
    - Excel
    - PowerPoint
    - Outlook

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a>建議使用者套用敏感度標籤

您可以視需要建議使用者套用標籤。 如果您使用此選項，您的使用者就可以接受分類和任何相關的保護，或者當標籤不適合內容時，可以取消建議。

![向使用者建議敏感度標籤的選項](../media/Sensitivity-labels-Recommended-label-option.png)

以下舉例說明當您設定條件而將套用標籤作為建議動作 (含自訂原則提示) 時，來自 Azure 資訊保護整合標籤用戶端的提示。 您可以選擇要在原則提示中顯示的文字。

![套用建議標籤的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a>如何套用自動或建議標籤

是否會在 Office 應用程式中實作自動化的建議標籤功能，取決於您使用的是 Office 內建的標籤功能，還是 Azure 資訊保護的整合標籤用戶端。 不過，在這兩種情況下：

- 您不能對之前已手動加上標籤，或之前已自動加上較高敏感性標籤的文件和電子郵件，自動加上標籤。 請記住，您只能將單一敏感度標籤套用至文件或電子郵件 (除了單一保留標籤之外)。

- 您無法針對之前已加上較高敏感性標籤的文件或電子郵件使用建議標籤。 如果內容已加上較高敏感性標籤，使用者將不會看到含有建議和原則提示的提示。

專用於內建標籤：

- 並非所有的 Office 應用程式都支援自動化 (建議) 標籤。 如需詳細資訊，請參閱[在應用程式中支援敏感度標籤功能](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

- 若為電腦版 Word 中的建議標籤，系統會標示觸發了建議的敏感性內容，讓使用者可以檢閱和移除敏感性內容，而不是套用建議的敏感度標籤。

- 如需這些標籤在 Office 應用程式中的套用方式、範例螢幕擷取畫面，以及系統如何偵測到敏感性資訊的詳細資訊，請參閱[在 Office 中自動套用或建議敏感度標籤至您的檔案和電子郵件](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)。

專用於 Azure 資訊保護的整合標籤用戶端：

-  自動化的建議標籤功能適用於您儲存文件時所使用的 Word、Excel 和 PowerPoint，以及傳送電子郵件時的 Outlook。

- 若要讓 Outlook 支援建議標籤，您必須先設定[進階原則設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)。

- 系統可於文件和電子郵件的本文，以及頁首及頁尾中偵測到敏感性資訊，但無法在電子郵件的主旨列或附件中偵測到敏感性資訊。

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>將多個條件套用到多個標籤時的評估方式

標籤會根據您在原則中指定的標籤位置，針對評估進行排序：位於第一個位置的標籤具有最低的位置 (敏感度最低)，而位於最後一個位置的標籤具有最高的位置 (敏感度最高)。如需有關原則的詳細資訊，請參閱[標籤優先順序 (排序事項)](sensitivity-labels.md#label-priority-order-matters)。

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>請勿設定將上層標籤設定為自動套用或建議選項

請記得，您無法將上層標籤 (具有子標籤的標籤) 套用至內容。 請確定未將上層標籤設定為自動套用或建議選項，因為上層標籤無法套用到使用 Azure 資訊保護統一標籤用戶端的 Office 應用程式中的內容。 如需上層標籤和子標籤的詳細資訊，請參閱[子標籤 (分組標籤)](sensitivity-labels.md#sublabels-grouping-labels)。
