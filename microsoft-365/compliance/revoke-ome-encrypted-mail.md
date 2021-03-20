---
title: 撤銷由高級郵件加密所加密的電子郵件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 以系統管理員和郵件寄件者的身分，您可以撤銷使用 Office 365 高級郵件加密所加密的特定電子郵件。
ms.openlocfilehash: b49915b6ef72d366a4b2718319150d2d5b640b9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917195"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>撤銷由高級郵件加密所加密的電子郵件

電子郵件吊銷是以 Office 365 Advanced Message Encryption 的一部分提供。 Office 365 Advanced Message Encryption 包含在 [Microsoft 365 企業版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非盈利性員工定價) 、Office 365 企業版 E5 (非盈利性員工定價) 和 Office 365 教育版 A5。 如果您的組織中有未包含 Office 365 Advanced Message Encryption 的訂閱，您可以使用 microsoft 365 E5 相容性 SKU 附加元件（適用于 Microsoft 365 E3）購買它; microsoft 365 E3 (非盈利性員工定價) ，或 Office 365 的高級合規性 SKU 附加元件（適用于 Microsoft 365 E3），Microsoft 365 E3 (非盈利性員工定價) 或 Office 365 SKUs。

本文是有關 [Office 365 郵件加密](ome.md)的更多系列文章的一部分。

如果郵件是使用 Office 365 高級郵件加密進行加密，而且您是 Microsoft 365 系統管理員或您是郵件的寄件者，您可以在特定條件下撤銷郵件。 系統管理員會使用 PowerShell 來撤銷郵件。 作為寄件者，您可以撤銷從網頁 Outlook 直接傳送的郵件。 本文說明可進行撤銷的情形及其執行方式。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>您可以撤銷的加密電子郵件

如果收件者收到連結型、署名加密的電子郵件，系統管理員和郵件寄件者可以撤銷加密的電子郵件。 如果收件者在支援的 Outlook 用戶端收到原生內嵌經驗，則您無法撤銷該郵件。

收件者是否收到連結型體驗或內嵌經驗取決於收件者身分識別類型： Office 365 和 Microsoft 帳戶收件者 (例如，outlook.com 使用者) 在支援的 Outlook 用戶端中取得內嵌經驗。 所有其他收件者類型，例如 Gmail 和 Yahoo 收件者，會取得連結型經驗。

系統管理員和郵件寄件者可以吊銷以直接從網頁上 Outlook 套用的加密來加密的郵件。 例如，使用 [只加密] 選項加密的郵件。

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="螢幕擷取畫面顯示 Outlook 網頁版中的 [僅加密] 選項。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>已撤銷的加密電子郵件收件者經驗

一旦電子郵件遭到吊銷，當收件者透過 Office 365 郵件加密入口網站存取加密的電子郵件時，收件者會收到錯誤訊息：「郵件已由寄件者撤銷」。

![顯示已撤銷加密之電子郵件的螢幕擷取畫面。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>操作方法：撤銷您傳送的加密郵件

您可以撤銷您傳送給單一收件者的郵件，該郵件使用社會帳戶，例如 gmail.com 或 yahoo.com。 換句話說，您可以撤銷傳送到單一收件者的電子郵件，該收件者會收到連結型經驗。

您無法撤銷傳送給收件者的郵件，該收件者使用 Office 365 或 Microsoft 365 中的工作或學校帳戶，例如 outlook.com 帳戶。 

若要撤銷您傳送的加密郵件，請完成下列步驟：

1. 在網頁的 Outlook 中，流覽至 **您要** 撤銷的郵件。

   如果郵件是可吊銷的，您會在郵件頂端看到 [移除外部存取] 連結。

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="螢幕擷取畫面顯示您想要在 Outlook 網頁版中撤銷的加密郵件。":::

2. 按一下 [ **移除外部存取** ] 以撤銷郵件。

   郵件顯示其狀態為 [已撤銷]。

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="螢幕擷取畫面顯示 Outlook 網頁版中已撤銷的加密郵件。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>如何以系統管理員身分撤銷加密郵件

Microsoft 365 系統管理員請遵循下列一般步驟來撤銷合格的加密電子郵件：

- 取得電子郵件的郵件識別碼。
- 確認您可以撤銷郵件。
- 撤銷郵件。

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步驟 1. 取得電子郵件的郵件識別碼

在您可以撤銷加密的郵件之前，請先收集郵件的郵件識別碼。 MessageId 的格式通常如下：

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多種方式可尋找您要撤銷之電子郵件的郵件識別碼。 本節說明一些選項，但是您可以使用任何提供識別碼的方法。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>若要使用安全性與 &amp; 合規性中心的郵件追蹤，識別您想要吊銷之電子郵件的郵件識別碼。

1. [在安全性 & 規範中心內，以新郵件追蹤](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)方式，搜尋寄件者或收件者的電子郵件。

2. 找到電子郵件之後，請選取它以顯示 **郵件追蹤詳細資料** 窗格。 展開 **其他資訊** 以找出郵件識別碼。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>若要在安全性與 &amp; 合規性中心使用 Office 郵件加密報告識別您想要吊銷之電子郵件的郵件識別碼

1. 在 [安全性與 &amp; 合規性中心] 中，流覽至 [ **郵件加密] 報告**。 如需此報告的詳細資訊，請參閱 [在安全性與 &amp; 規範中心中查看電子郵件安全性報告](../security/office-365-security/view-email-security-reports.md)。

2. 選擇 [ **查看詳細資料** ] 表格，並識別您要撤銷的郵件。

3. 按兩下郵件，以查看包含郵件識別碼的詳細資料。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步驟 2. 確認郵件是可吊銷的

若要確認您是否可以吊銷郵件，請在 [安全性與規範中心] 的 [ **詳細資料** ] 表格中，檢查 [吊銷狀態] 欄位是否顯示在加密報告中 &amp; 。

若要確認您是否可以使用 Windows PowerShell 撤銷特定的電子郵件訊息，請完成下列步驟。

1. 使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 依下列方式執行 Get-OMEMessageStatus Cmdlet：

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   這個命令會傳回郵件的主旨，以及郵件是否可吊銷。 例如：

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>步驟 3. 撤銷郵件

知道您要吊銷之電子郵件的郵件識別碼，並確認該郵件可吊銷後，您就可以使用安全性與 &amp; 合規性中心或 Windows PowerShell 撤銷電子郵件。

使用安全性與 &amp; 合規性中心撤銷郵件

1. 使用組織中具有全域系統管理員許可權的公司或學校帳戶，連接至安全性 & 合規性中心。

2. 在 **加密報告** 中，于郵件的 [ **詳細資料** ] 表格中，選擇 **[撤銷郵件]**。

若要使用 Windows PowerShell 撤銷電子郵件，請使用 Set-OMEMessageRevocation Cmdlet。

1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 依下列方式執行 Set-OMEMessageRevocation Cmdlet：

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 若要檢查電子郵件是否已撤銷，請執行 Get-OMEMessageStatus Cmdlet，如下所示：

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    如果撤銷成功，Cmdlet 會傳回下列結果：  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有關 Office 365 Advanced Message Encryption 的詳細資訊

- [Office 365 進階郵件加密](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption-電子郵件到期](ome-advanced-expiration.md)

- [郵件原則及合規性服務說明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)