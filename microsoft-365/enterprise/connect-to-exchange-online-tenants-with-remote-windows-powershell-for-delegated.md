---
title: 使用適用于合作合作夥伴的遠端 Windows PowerShell，連線至 Exchange Online 承租人
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: 摘要：使用遠端 Windows PowerShell 搭配 DelegatedOrg 值連線至 Exchange Online。
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688609"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a>利用適用於委派存取權限 (DAP) 合作夥伴的遠端 Windows PowerShell 連線至 Exchange Online 租用戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

> [!IMPORTANT]
> 本主題中的程序是僅適用於委派存取權限 (DAP) 合作夥伴。如果您不是 DAP 合作夥伴，請不要使用本主題中的程序。 
  
DAP 合作夥伴是新聞訂閱方式和雲端解決方案提供者 (CSP) 合作夥伴。 他們通常是其他公司的網路或電信服務提供者。 他們會在提供給客戶的服務方案中搭售 訂閱。 他們擁有的合作夥伴租使用者會自動授與 (AOBO 的「管理」) 許可權給其 Microsoft 365 客戶租用，讓他們能管理及報告其所有客戶租用。

「合作合作夥伴」可以使用 Exchange Online PowerShell 管理客戶 Exchange Online 設定，並從命令列取得 Microsoft 365 報告。 您可在本機電腦上使用 Windows PowerShell 建立對 Exchange Online 的遠端 PowerShell 工作階段。 這是一個簡單的三步驟程式，您可以在其中輸入您的認證、提供必要的連線設定，然後將 Exchange Online Cmdlet 匯入您的本機 Windows PowerShell 會話，讓您可以使用這些程式。

> [!NOTE]
> DAP 合作夥伴無法使用[使用多重要素驗證來連線到 Exchange Online PowerShell (機器翻譯)](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell)中的程序，來連線到其在 Exchange Online PowerShell 中的客戶租用戶組織。MFA 與 Exchange Online 遠端 PowerShell 模組不會使用委派的驗證。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 預估完成時間：5 分鐘

- 您可以使用下列 Windows 版本：
    
  - Windows 10

  - Windows 8.1

  - Windows Server 2016

  - Windows Server 2012 或 Windows Server 2012 R2

  - Windows 7 Service Pack 1 (SP1)<sup>*</sup>

  - Windows Server 2008 R2 SP1<sup>*</sup>

    <sup>*</sup> 若為舊版 Windows，您需要安裝 Microsoft.NET Framework 4.5 或更新版本，然後再安裝更新版本的 Windows Management Framework：3.0、4.0 或 5.1 (只需一個)。如需詳細資訊，請參閱[安裝 the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868)、[Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757)、[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) 和 [Windows Management Framework 5.1](https://aka.ms/wmf5download)。

- Windows PowerShell 必須經過設定才能執行指令碼，不過在預設情況下它並沒有設定。當您嘗試連線時，會發生以下錯誤：

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  若要要求您從網際網路下載的所有 Windows PowerShell 指令碼都是由信任的發行者簽署，請在提高權限的 Windows PowerShell 視窗 (透過選取 [以系統管理員身分執行]**** 而開啟的 Windows PowerShell 視窗) 中執行下列命令：

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  您只需在電腦上設定此設定一次，而不用在每次連線時進行設定。

- 如需適用於本主題之程序的鍵盤快速鍵相關資訊，請參閱 [Exchange 系統管理中心的鍵盤快速鍵](https://go.microsoft.com/fwlink/p/?LinkId=534017)。

## <a name="connect-to-exchange-online-for-customer-organizations"></a>連線到客戶組織的 Exchange Online

1. 在您的本機電腦上開啟 Windows PowerShell，並執行下列命令。
    
    ```
    $UserCredential = Get-Credential
    ```

    在 [Windows PowerShell 認證要求]**** 對話方塊中，輸入您的 DAP 系統管理員使用者名稱和密碼，然後按一下 [確定]****。
    
2. _\<customer tenant domain name\>_ 以您想要連線的租使用者功能變數名稱取代，並執行下列命令：
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    此命令中的重要步驟是指定可存取報告資訊的客戶。 您可以在  _ConnectionURI_ 參數中，以的值提供初始功能變數名稱的 FQDN `?DelegatedOrg=` 。 此值表示要連接的正確 Exchange Online PowerShell 端點。 在每次執行報告時，遠端 PowerShell 都必須在特定客戶的內容中連接至 Microsoft 365 報告。 在您連線至 Exchange Online PowerShell 之後，所有後續命令都會在客戶的上下文中執行，讓您可以存取客戶的所有可用報告。
    
3. 執行下列命令。
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> 每個帳戶有同時執行三個工作階段的限制。完成時，請務必中斷遠端 PowerShell 工作階段連線。如果未先中斷工作階段連線即關閉 Windows PowerShell 視窗，您可能會用完您可以使用的所有遠端 PowerShell 工作階段，而需要等待這些工作階段到期。若要中斷遠端 PowerShell 工作階段連線，請執行下列命令：

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

執行步驟 3 後，Exchange Online Cmdlet 會匯入您的本機 Windows PowerShell 工作階段中，且會有進度列追蹤此作業。如果您未收到任何錯誤，便已順利連線。若要做快速測試，您可以執行一個 Exchange Online Cmdlet (例如 **Get-Mailbox** )，然後檢視結果。
  
如果出現錯誤，請檢查下列需求：
  
- 密碼錯誤是常見的問題。再次執行這三個步驟，並特別留意您在步驟 1 中輸入的使用者名稱和密碼。
    
- 用來連線至 Exchange Online 的帳戶必須能夠使用遠端 PowerShell。如需詳細資訊，請參閱[啟用或停用 Exchange Online PowerShell 的存取](https://go.microsoft.com/fwlink/p/?LinkId=534018)。
    
- 本機電腦與 Exchange Online 之間必須開啟 TCP 連接埠 80 流量。該連接埠可能已開啟，但必須考量您的組織是否有限制性網際網路存取原則。
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a>利用 Invoke-Command 直接呼叫 Cmdlet

匯入遠端 PowerShell 工作階段 (步驟 3) 可能會是冗長的程序，因為它會帶入_所有_ Exchange Online Cmdlet。在批次處理中這可能會造成問題 (例如，當您執行報告或針對不同租用戶進行大量變更時)。除了使用 **Import-PSSession** 之外，您還可以利用 **Invoke-Command** 直接呼叫要使用的 Cmdlet。例如，若要呼叫 **Get-Milbox** Cmdlet，請以下列語法取代步驟 3 中的 `Import-PSSession $Session` 命令：
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a>其他報告 Cmdlet

本主題中所使用的 Cmdlet 是 Windows PowerShell Cmdlet。如需這些 Cmdlet 的詳細資訊，請參閱下列主題。
  
- [Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [New-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [Import-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [Remove-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [Set-ExecutionPolicy](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

