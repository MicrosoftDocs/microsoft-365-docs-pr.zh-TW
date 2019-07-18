---
title: 傳送加密的電子郵件
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
description: 了解如何傳送加密的電子郵件使用 Outlook。
ms.openlocfilehash: e58a69c25c00a0482d3837d9bde626ec0a54936f
ms.sourcegitcommit: 75b97d1ff617bc4b1b0ef9135dfe6a8842ea1b52
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "35772320"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>加密或標籤機密電子郵件

您的資料和活動資訊是很重要，通常機密。 協助讓您和您的電子郵件收件者的資訊則會需要區分大小寫視為使用加密和敏感度標籤來保護機密資訊。


## <a name="best-practices"></a>最佳做法

您傳送電子郵件具有敏感或機密資訊之前，請考慮開啟：

- **加密：** 您可以加密您的電子郵件保護的電子郵件中的資訊私密性。 當您將加密的電子郵件訊息時，它會從可讀取的純文字轉換成亂碼的 cypher 文字。 只有收件者具有比對的公開金鑰用來加密郵件的私密金鑰可解密讀取的郵件。 任何收件者，而不相對應之私密金鑰，不過，會看到無法解讀文字。 您的系統管理員可以定義規則以自動加密符合特定準則的郵件。 比方說，您的系統管理員可以建立傳送組織外的所有郵件都加密的規則或涵蓋特定單字或片語的所有郵件。 任何加密的郵件將會自動套用。
- **敏感度標籤：** 您可以套用到您的檔案和電子郵件，讓它們與您的行銷活動資訊保護原則相容的敏感度標籤也可以設定您的行銷活動。 當您設定標籤時，標籤保存與您的電子郵件，即使它傳送-例如，藉由讓它成為您的郵件標頭。

![含有圖說文字的標籤和加密的電子郵件的圖表](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>進行設定

如果您想要加密的郵件不符合的預先定義的規則，或您的系統管理員尚未設定任何規則，您可以在傳送郵件之前，先套用各種不同的加密的郵件。 傳送加密的郵件，從 Outlook 2013 或 2016 或 Outlook 2016 for Mac 中，選取**選項 > 權限**，然後選取您需要的保護選項。 您也可以藉由選取 [**保護**] 按鈕，網頁型 Outlook 中傳送加密的郵件。 如需詳細資訊，請參閱[傳送、 檢視和回覆加密郵件的電腦版 Outlook 中](https://support.office.com/en-us/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US)。

## <a name="admin-settings"></a>系統管理員設定

您可以了解在[Office 365 中的電子郵件加密](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption)的電子郵件加密設定。

### <a name="automatically-encrypt-email-messages"></a>會自動加密電子郵件

系統管理員可以建立郵件流程規則來自動保護的傳送和接收來自您的行銷活動的電子郵件訊息。 設定規則以加密所有外寄的電子郵件，並移除加密，從加密的郵件來自組織內部或從組織傳送加密郵件的回覆。 

建立郵件流程規則來加密與新的 Office 365 郵件加密 (OME) 功能的電子郵件。 定義郵件流程規則觸發郵件加密與新的 OME 功能使用 Exchange 系統管理中心 (EAC)。 

1. 在網頁瀏覽器中，使用已授與全域系統管理員權限的工作或學校帳戶登入 Office 365。 
2. 選擇 [管理] 磚。 
3. 在 Office 365 系統管理中心中，選擇 [**系統管理中心 > Exchange**]。 

如需詳細資訊，請參閱[定義郵件流規則以加密 Office 365 中的電子郵件](https://docs.microsoft.com/en-us/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email)。

### <a name="brand-your-encryption-messages"></a>品牌加密郵件

您也可以套用行銷活動品牌自訂外觀和電子郵件訊息中的文字。 如需詳細資訊，請參閱[新增至加密郵件的貴組織的品牌](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption)。

