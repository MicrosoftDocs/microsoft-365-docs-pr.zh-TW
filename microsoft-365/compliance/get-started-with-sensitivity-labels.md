---
title: 開始使用敏感度標籤
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 準備開始實作敏感度標籤來協助保護貴組織的資料，但不確定從何處著手？ 閱讀一些實用的指導方針，以協助您開始套用標籤的旅程。
ms.openlocfilehash: efb0d8401cca8fd0e8c2450a5d35788015f37dad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073173"
---
# <a name="get-started-with-sensitivity-labels"></a>開始使用敏感度標籤

如需敏感度標籤為何及其如何可協助您保護組織資料的相關資訊，請參閱[了解敏感度標籤](sensitivity-labels.md)。

如果您有 [Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)，請判斷是否需要將標籤移轉至統一標籤平台，以及要使用的標籤用戶端：
- [如何判斷我的租用戶是否在統一標籤平台上？](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [選擇要用於 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

當您準備好要開始使用敏感度標籤來保護組織的資料時：

1. **建立標籤。** 根據貴組織用於不同內容敏感度層級的分類法，建立您的敏感度標籤並加以命名。 使用對您的使用者有意義的一般名稱或字詞。 如果您還沒有建立分類法，請考慮從 [個人]、[公用]、[一般]、[機密] 和 [高度機密] 等標籤名稱著手。 您可以接著使用子標籤，依類別將類似的標籤群組。 當您建立標籤時，請使用工具提示文字來協助使用者選取適當的標籤。

2. **定義每個標籤的功能。** 設定您想要與每個標籤相關聯的保護設定。 例如，您可能希望較低敏感度內容 (如「一般」標籤) 只有套用頁首或頁尾，而較高敏感度內容 (如「機密」標籤) 則應套用浮水印、加密及端點保護。

3. **發佈標籤。** 設定好敏感度標籤之後，請使用標籤原則加以發佈。 決定哪些使用者和群組應具有標籤，以及所要使用的原則設定。 單一標籤可重複使用；您只要定義一次，就可以將它納入指派給不同使用者的數個標籤原則中。 例如，您可以將標籤原則指派給少數幾個使用者來試驗您的敏感度標籤。 當您準備好在整個組織推出標籤時，您可以為標籤建立新的標籤原則，而這次指定所有使用者。

系統管理員、使用者和 Office 應用程式和服務執行項目以讓敏感度標籤運作的基本流程：

![顯示敏感度標籤的工作流程圖](../media/Sensitivity-label-flow.png)

## <a name="common-scenarios-for-sensitivity-labels"></a>敏感度標籤的常見案例

使用下列文件來支援您的敏感度標籤部署：

|我想要...|文件|
|----------------|---------------|
|建立及發佈將協助保護我的組織資料的敏感度標籤|[建立及設定敏感度標籤及其原則](create-sensitivity-labels.md)|
|使用敏感度標籤加密文件和電子郵件，並限制能夠存取的人員及其使用該內容的方式 |[使用敏感度標籤來套用加密以限制存取內容](encryption-sensitivity-labels.md)|
|在 SharePoint (和 OneDrive) 中針對具有加密標籤的文件啟用共同作業功能 | [對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md)
|管理 Office 應用程式的敏感度標籤，讓內容標示為已建立 |[在 Office 應用程式使用敏感度標籤](sensitivity-labels-office-apps.md)|
|建立內容時自動套用敏感度標籤或向使用者建議標籤 | [自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)|
|使用敏感度標籤來保護 Teams 和 SharePoint 中的內容 |[對 Microsoft Teams、Office 365 群組和 SharePoint 網站使用敏感度標籤 (公開預覽)](sensitivity-labels-teams-groups-sites.md)|
|探索、標記和保護儲存在內部部署資料儲存區中的檔案 |[部署 Azure 資訊保護掃描器以自動分類和保護檔案](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|探索、標記和保護儲存在雲端資料儲存區中的檔案 |[探索、分類、標記及保護儲存在雲端的管制資料及敏感性資料](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|將敏感度標籤的使用情況視覺化，以報告部署狀態和微調標籤組態|[利用標籤分析檢視標籤使用量](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a>敏感度標籤的使用者文件

- [在 Office 中將敏感度標籤套用至您的檔案和電子郵件](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Office 敏感度標籤的已知問題](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [在 Office 中自動套用或建議敏感度標籤至您的檔案和電子郵件](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)

- [自動套用或建議敏感度標籤的已知問題](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)


