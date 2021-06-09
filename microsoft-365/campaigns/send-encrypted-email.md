---
title: 傳送加密的電子郵件
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- m365solution-smb
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
ms.openlocfilehash: 209734bd52d1d97278d5632f035723758fe2e016
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576970"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>幫您的機密電子郵件加密或加上標籤

您的資料和活動資訊非常重要，通常是保密的。 使用加密和敏感度標籤來協助保護此機密資訊，讓您和您的電子郵件收件者以其所需的靈敏度來處理資訊。

## <a name="best-practices"></a>最佳做法

在您傳送包含機密或機密資訊的電子郵件之前，請考慮開啟：

- **加密：** 您可以加密您的電子郵件，以保護電子郵件中資訊的隱私權。 當您加密電子郵件時，它會從可讀取的純文字轉換成亂碼的 cypher 文字。 只有具有與用來加密郵件之公開金鑰相符的私密金鑰的收件者，才能解密郵件以進行讀取。 沒有對應私密金鑰的任何收件者，但是會看到無法破譯的文字。 您的系統管理員可以定義規則，以自動加密符合特定準則的郵件。 例如，您的系統管理員可以建立一種規則，用來加密您的組織外傳送的所有郵件，或所有提及特定文字或片語的郵件。 將會自動套用任何加密規則。
- **敏感度標籤：** 您的活動也可以設定敏感度標籤，您可以將敏感度標籤套用至您的檔案和電子郵件，使其符合您的活動的資訊保護原則。 當您設定標籤時，標籤會隨電子郵件一起保留，即使傳送時也是如此; 例如，它會顯示為郵件的標頭。

![具有標籤和加密之標注的電子郵件圖表](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>進行設定

如果您想要加密的郵件不符合預先定義的規則，或系統管理員尚未設定任何規則，您可以在傳送郵件之前，套用各種不同的加密規則。 若要從 Outlook 2013 或2016或 Mac 版 Outlook 2016 中傳送加密的郵件，請選取 [選項] [ **> 許可權**]，然後選取所需的保護選項。 您也可以選取網頁 Outlook 中的 [**保護**] 按鈕來傳送加密的郵件。 如需詳細資訊，請參閱[Outlook 中的電腦傳送、查看和回復加密的郵件](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)。

## <a name="admin-settings"></a>系統管理員設定

您可以[在 Microsoft 365 中深入瞭解設定電子郵件加密中](../compliance/email-encryption.md)的電子郵件加密。

### <a name="automatically-encrypt-email-messages"></a>自動加密電子郵件

系統管理員可以建立郵件流程規則，以自動保護從您的活動中傳送及接收的電子郵件。 設定用來加密任何外寄電子郵件的規則，並從組織內部或從組織傳送的加密郵件中移除加密。

您可以建立郵件流程規則，以使用新 Office 365 郵件加密 (OME) 功能來加密電子郵件。 使用 Exchange 系統管理中心 (EAC) ，定義用新 OME 功能觸發郵件加密的郵件流程規則。 

1. 在網頁瀏覽器中，使用已被授與全域管理員許可權的工作或學校帳戶登入。
2. 選擇 [管理] 磚。
3. 在系統管理中心中，選擇 [系統 **管理中心] > Exchange**]。

如需詳細資訊，請參閱 [定義郵件流程規則以加密電子郵件訊息](../compliance/define-mail-flow-rules-to-encrypt-email.md)。

### <a name="brand-your-encryption-messages"></a>標記加密郵件

您也可以套用您的行銷活動品牌，以自訂電子郵件訊息中的外觀和文字。 如需詳細資訊，請參閱 [將貴組織的品牌新增至加密的郵件](../compliance/email-encryption.md)。