---
title: 撤銷由 Office 365 進階郵件加密所加密的電子郵件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/8/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 是 Office 365 系統管理員，您可以撤銷某些使用 Office 365 進階郵件加密所加密的電子郵件。
ms.openlocfilehash: 6cbe0704d6e84282d71c37c72a45712c30f3ac61
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42070032"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a>撤銷由 Office 365 進階郵件加密所加密的電子郵件

電子郵件被撤銷被提供作為 Office 365 進階郵件加密的一部分。 Office 365 進階郵件加密隨附於[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 Office 365 E5、 Microsoft 365 E5 （非營利組織版人員價格），Office 365 企業版 E5 （非營利組織版人員價格） 和 Office 365 教育版 A5。 如果貴組織擁有不包含 Office 365 進階郵件加密的訂閱，您可以購買它與 Microsoft 365 E5 規範 SKU 附加元件的 Microsoft 365 E3，Microsoft 365 E3 （非營利組織版人員價格），或 Office 365 進階為 Microsoft 365 E3，Microsoft 365 E3 的合規性 SKU 附加元件 （非營利組織版人員價格），或 Office 365 Sku。

本文屬於較大的一連串的[Office 365 郵件加密](ome.md)的相關文章。

如果已加密郵件，使用 Office 365 進階郵件加密，並且您是 Office 365 系統管理員，您可以執行撤銷在某些情況下的訊息。 本文說明哪個撤銷可能會與執行方式] 底下的情況。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>您可以撤銷的加密電子郵件

如果收件者收到連結為基礎，品牌加密的電子郵件，您可以撤銷加密的電子郵件。 如果收件者收到的原生內嵌體驗中支援的 Outlook 用戶端，無法撤銷這些電子郵件。

收件者收到的連結為基礎的體驗還是內嵌經驗會視收件者的身分識別類型而定： Office 365 和 Microsoft 帳戶收件者 （例如，outlook.com 使用者） 中支援的 Outlook 用戶端取得內嵌體驗。 所有其他收件者類型，例如 Gmail 收件者，取得連結為基礎的體驗。

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>撤銷已加密的電子郵件的收件者體驗

當使用者透過 Office 365 郵件加密入口網站存取加密的電子郵件收件者之後已撤銷電子郵件，會收到錯誤: 「 寄件者，該訊息已被撤銷 」。

![螢幕擷取畫面顯示 [撤銷加密的電子郵件。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>若要撤銷加密的電子郵件的方式

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步驟 1。 取得電子郵件訊息識別碼

您可以撤銷加密的郵件之前會收集郵件訊息識別碼。 MessageId 通常是的格式：

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多種方式來尋找您想要撤銷的電子郵件訊息識別碼。 本小節會說明兩個選項，但您可以使用任何方法，提供識別碼。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>若要找出您想要撤銷安全性使用郵件追蹤的電子郵件訊息識別碼&amp;合規性中心

1. 搜尋由寄件者或收件者使用[新的郵件追蹤，在 Office 365 安全性 & 合規性中心中](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)的電子郵件。

2. 一旦您已經找到電子郵件，請選取帶出 [**郵件追蹤詳細資料**] 窗格。 依序展開 [**更多的資訊**來找出郵件的識別碼。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>若要找出您想要使用 Office 郵件加密報告安全性撤銷電子郵件訊息識別碼&amp;合規性中心

1. 安全性&amp;合規性中心，瀏覽至**郵件加密報告**。 這份報告的詳細資訊，請參閱[檢視電子郵件安全性報告安全性&amp;合規性中心](../security/office-365-security/view-email-security-reports.md)。

2. 選擇 [**檢視詳細資料]** 表格，並找出您想要撤銷的訊息。

3. 按兩下 [檢視詳細資料] 包含郵件識別碼訊息

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步驟 2。 確認便可撤銷之電子郵件

若要確認您是否可以撤銷一則訊息，請檢查 [撤銷狀態] 欄位是否顯示在 [加密] 報告，**詳細資料**表格中的安全性&amp;合規性中心。

若要確認是否您可以使用 Windows Powershell 撤銷將特定電子郵件，完成下列步驟。

1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 執行 Get OMEMessageStatus 指令程式，如下所示：

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   這會傳回郵件以及是否可撤銷之郵件的主旨。 For example,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>步驟 3： 撤銷郵件

一旦您知道想要撤銷，請將電子郵件訊息識別碼且已驗證的訊息是可撤銷之，您可以撤銷使用安全的電子郵件&amp;合規性中心或 Windows Powershell。

若要撤銷使用安全的郵件&amp;合規性中心

若要撤銷安全性中的電子郵件&amp;合規性中心，在 [加密] 報告中，為訊息， **Details** ] 資料表中選擇 [**撤銷訊息**。

您可以使用 Windows Powershell 設定 OMEMessageRevocation 指令程式撤銷電子郵件。

1. [連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 執行設定 OMEMessageRevocation 指令程式，如下所示：

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 若要檢查是否已撤銷電子郵件，請執行 Get OMEMessageStatus 指令程式，如下所示：

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    如果撤銷成功，cmdlet 就會傳回下列結果：  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Office 365 進階郵件加密的詳細資訊

- [Office 365 進階郵件加密](ome-advanced-message-encryption.md)

- [Office 365 進階的郵件加密]-電子郵件到期](ome-advanced-expiration.md)

- [郵件原則及符合性服務說明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
