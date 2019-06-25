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
description: 瞭解如何使用 Outlook 傳送加密的電子郵件。
ms.openlocfilehash: 16e6a6977d7cd8ec4d6bf59adbcd196b14995752
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183251"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>加密或標記您的機密電子郵件

您的資料和活動資訊非常重要且常常是機密資訊。 使用加密和敏感度標籤來協助保護這個敏感資訊, 讓您和您的電子郵件收件者將資訊視為所需的敏感度。


## <a name="best-practices"></a>最佳做法

在您使用機密或敏感資訊傳送電子郵件之前, 請考慮開啟:

- **加密:** 您可以加密您的電子郵件, 以保護電子郵件中資訊的隱私權。 當您加密電子郵件時, 它會從可讀取的純文字轉換成已被打亂的 cypher 文字。 只有具有與用來加密郵件之公開金鑰相符的私密金鑰的收件者, 才可以解密郵件以進行讀取。 但沒有對應私密金鑰的任何收件者, 但是會看到無法解讀的文字。 您的系統管理員可以定義規則, 以自動加密符合特定準則的郵件。 例如, 您的系統管理員可以建立規則, 以加密在組織外部傳送的所有郵件, 或提及特定單字或片語的所有郵件。 系統會自動套用任何加密規則。
- **敏感度標籤:** 您的市場活動也可以設定可套用至檔案和電子郵件的敏感度標籤, 以保持其符合您的行銷活動資訊保護原則。 當您設定標籤時, 標籤會與您的電子郵件保持聯繫, 即使傳送時也是如此, 例如, 在郵件中顯示為標頭。

![包含標籤和加密之注解的電子郵件圖表](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>進行設定

如果您想要加密不符合預先定義規則的郵件, 或您的系統管理員尚未設定任何規則, 您可以在傳送郵件之前套用各種不同的加密規則。 若要從 Outlook 2013 或 2016 (或 Outlook 2016 Mac) 傳送加密的郵件, 請選取 [選項] [ **> 許可權**], 然後選取您需要的保護選項。 您也可以在 web 上的 Outlook 中選取 [**保護**] 按鈕, 傳送加密的郵件。 如需詳細資訊, 請參閱[在 Outlook 中傳送、查看和回復加密郵件的電腦](https://support.office.com/en-us/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US)。

## <a name="admin-settings"></a>系統管理設定

您可以在[Office 365 中瞭解如何在電子郵件加密中](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption)設定電子郵件加密。

### <a name="automatically-encrypt-email-messages"></a>自動加密電子郵件

系統管理員可以建立郵件流程規則, 以自動保護從您的市場活動傳送和接收的電子郵件。 設定規則以加密任何外寄的電子郵件, 並從您組織內部的加密郵件中移除加密, 或從您的組織傳送的加密郵件回復。 

您可以建立郵件流程規則, 以使用新的 Office 365 郵件加密 (OME) 功能來加密電子郵件。 使用 Exchange 系統管理中心 (EAC), 定義使用新 OME 功能觸發郵件加密的郵件流程規則。 

1. 在網頁瀏覽器中, 使用已被授與全域系統管理員許可權的公司或學校帳戶, 登入 Office 365。 
2. 選擇 [系統管理] 磚。 
3. 在 Office 365 系統管理中心, 選擇 [系統**管理中心] > Exchange**]。 

如需詳細資訊, 請參閱[定義郵件流程規則以加密 Office 365 中的電子](https://docs.microsoft.com/en-us/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email)郵件。

### <a name="brand-your-encryption-messages"></a>署名您的加密郵件

您也可以套用您的行銷活動品牌, 以自訂電子郵件訊息中的外觀和文字。 如需詳細資訊, 請參閱[將貴組織的品牌新增至加密的郵件](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption)。

