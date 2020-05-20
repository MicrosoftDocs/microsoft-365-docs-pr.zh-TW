---
title: 傳送加密的電子郵件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 瞭解如何使用 Outlook 傳送加密的電子郵件。
ms.openlocfilehash: 5318fbe045c909e3b7f81d195a8e6b4d5eb96dc1
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322144"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>加密或標記敏感的電子郵件

您的資料和活動資訊非常重要，通常是保密的。 使用加密和敏感度標籤來協助保護此機密資訊，讓您和您的電子郵件收件者以其所需的靈敏度來處理資訊。


## <a name="best-practices"></a>最佳做法

在您傳送包含機密或機密資訊的電子郵件之前，請考慮開啟：

- **加密：** 您可以加密您的電子郵件，以保護電子郵件中資訊的隱私權。 當您加密電子郵件時，它會從可讀取的純文字轉換成亂碼的 cypher 文字。 只有具有與用來加密郵件之公開金鑰相符的私密金鑰的收件者，才能解密郵件以進行讀取。 沒有對應私密金鑰的任何收件者，但是會看到無法破譯的文字。 您的系統管理員可以定義規則，以自動加密符合特定準則的郵件。 例如，您的系統管理員可以建立一種規則，用來加密您的組織外傳送的所有郵件，或所有提及特定文字或片語的郵件。 將會自動套用任何加密規則。
- **敏感度標籤：** 您的活動也可以設定敏感度標籤，您可以將敏感度標籤套用至您的檔案和電子郵件，使其符合您的活動的資訊保護原則。 當您設定標籤時，標籤會隨電子郵件一起保留，即使傳送時也是如此; 例如，它會顯示為郵件的標頭。

![具有標籤和加密之標注的電子郵件圖表](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>進行設定

如果您想要加密的郵件不符合預先定義的規則，或系統管理員尚未設定任何規則，您可以在傳送郵件之前，套用各種不同的加密規則。 若要從 Outlook 2013 或2016（或 Outlook 2016 Mac）傳送加密的郵件，請選取 [**選項] > 許可權**]，然後選取所需的保護選項。 您也可以在 web 上的 Outlook 中選取 [**保護**] 按鈕來傳送加密的郵件。 如需詳細資訊，請參閱[在 Outlook 中傳送、查看和回復加密郵件的電腦](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)。

## <a name="admin-settings"></a>系統管理設定

您可以[在 Office 365 中瞭解如何在電子郵件加密中](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)設定電子郵件加密。

### <a name="automatically-encrypt-email-messages"></a>自動加密電子郵件

系統管理員可以建立郵件流程規則，以自動保護從您的活動中傳送及接收的電子郵件。 設定用來加密任何外寄電子郵件的規則，並從組織內部或從組織傳送的加密郵件中移除加密。 

您可以建立郵件流程規則，以使用新的 Office 365 郵件加密（OME）功能來加密電子郵件。 使用 Exchange 系統管理中心（EAC）定義郵件流程規則，以使用新的 OME 功能來觸發郵件加密。 

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登入 Office 365。 
2. 選擇 [管理] 磚。 
3. 在系統管理中心中，選擇 [系統**管理中心] > Exchange**。 

如需詳細資訊，請參閱[定義郵件流程規則，以加密 Office 365 中的電子郵件訊息](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。

### <a name="brand-your-encryption-messages"></a>標記加密郵件

您也可以套用您的行銷活動品牌，以自訂電子郵件訊息中的外觀和文字。 如需詳細資訊，請參閱[將貴組織的品牌新增至加密的郵件](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)。

