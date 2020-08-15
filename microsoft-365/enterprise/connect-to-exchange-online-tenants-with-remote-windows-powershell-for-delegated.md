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
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="158f5-103">利用適用於委派存取權限 (DAP) 合作夥伴的遠端 Windows PowerShell 連線至 Exchange Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="158f5-103">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="158f5-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="158f5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

> [!IMPORTANT]
> <span data-ttu-id="158f5-p101">本主題中的程序是僅適用於委派存取權限 (DAP) 合作夥伴。如果您不是 DAP 合作夥伴，請不要使用本主題中的程序。</span><span class="sxs-lookup"><span data-stu-id="158f5-p101">The procedures in this topic are only for Delegated Access Permission (DAP) partners. If you aren't a DAP partner, don't use the procedures in this topic.</span></span> 
  
<span data-ttu-id="158f5-107">DAP 合作夥伴是新聞訂閱方式和雲端解決方案提供者 (CSP) 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="158f5-107">DAP partners are Syndication and Cloud Solution Providers (CSP) partners.</span></span> <span data-ttu-id="158f5-108">他們通常是其他公司的網路或電信服務提供者。</span><span class="sxs-lookup"><span data-stu-id="158f5-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="158f5-109">他們會在提供給客戶的服務方案中搭售 訂閱。</span><span class="sxs-lookup"><span data-stu-id="158f5-109">They bundle subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="158f5-110">他們擁有的合作夥伴租使用者會自動授與 (AOBO 的「管理」) 許可權給其 Microsoft 365 客戶租用，讓他們能管理及報告其所有客戶租用。</span><span class="sxs-lookup"><span data-stu-id="158f5-110">They own a partner tenancy that is automatically granted Administer On Behalf Of (AOBO) permissions to their Microsoft 365 customer tenancies so they can administer and report on all of their customer tenancies.</span></span>

<span data-ttu-id="158f5-111">「合作合作夥伴」可以使用 Exchange Online PowerShell 管理客戶 Exchange Online 設定，並從命令列取得 Microsoft 365 報告。</span><span class="sxs-lookup"><span data-stu-id="158f5-111">DAP partners can use Exchange Online PowerShell to manage customer Exchange Online settings and get Microsoft 365 reports from the command line.</span></span> <span data-ttu-id="158f5-112">您可在本機電腦上使用 Windows PowerShell 建立對 Exchange Online 的遠端 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="158f5-112">You use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online.</span></span> <span data-ttu-id="158f5-113">這是一個簡單的三步驟程式，您可以在其中輸入您的認證、提供必要的連線設定，然後將 Exchange Online Cmdlet 匯入您的本機 Windows PowerShell 會話，讓您可以使用這些程式。</span><span class="sxs-lookup"><span data-stu-id="158f5-113">It's a simple three-step process where you enter your credentials, provide the required connection settings, and then import the Exchange Online cmdlets into your local Windows PowerShell session so that you can use them.</span></span>

> [!NOTE]
> <span data-ttu-id="158f5-p104">DAP 合作夥伴無法使用[使用多重要素驗證來連線到 Exchange Online PowerShell (機器翻譯)](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell)中的程序，來連線到其在 Exchange Online PowerShell 中的客戶租用戶組織。MFA 與 Exchange Online 遠端 PowerShell 模組不會使用委派的驗證。</span><span class="sxs-lookup"><span data-stu-id="158f5-p104">DAP partners can't use the procedures in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) to connect to their customer tenant organizations in Exchange Online PowerShell. MFA and the Exchange Online Remote PowerShell Module don't work with delegated authentication.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="158f5-116">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="158f5-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="158f5-117">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="158f5-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="158f5-118">您可以使用下列 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="158f5-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="158f5-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="158f5-119">Windows 10</span></span>

  - <span data-ttu-id="158f5-120">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="158f5-120">Windows 8.1</span></span>

  - <span data-ttu-id="158f5-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="158f5-121">Windows Server 2016</span></span>

  - <span data-ttu-id="158f5-122">Windows Server 2012 或 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="158f5-122">Windows Server 2012 or Windows Server 2012 R2</span></span>

  - <span data-ttu-id="158f5-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="158f5-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span></span>

  - <span data-ttu-id="158f5-124">Windows Server 2008 R2 SP1<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="158f5-124">Windows Server 2008 R2 SP1<sup>\*</sup></span></span>

    <span data-ttu-id="158f5-p105"><sup>\*</sup> 若為舊版 Windows，您需要安裝 Microsoft.NET Framework 4.5 或更新版本，然後再安裝更新版本的 Windows Management Framework：3.0、4.0 或 5.1 (只需一個)。如需詳細資訊，請參閱[安裝 the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868)、[Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757)、[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) 和 [Windows Management Framework 5.1](https://aka.ms/wmf5download)。</span><span class="sxs-lookup"><span data-stu-id="158f5-p105"><sup>\*</sup> For older versions of Windows, you need to install the Microsoft.NET Framework 4.5 or later and then an updated version of the Windows Management Framework: 3.0, 4.0, or 5.1 (only one). For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344), and [Windows Management Framework 5.1](https://aka.ms/wmf5download).</span></span>

- <span data-ttu-id="158f5-p106">Windows PowerShell 必須經過設定才能執行指令碼，不過在預設情況下它並沒有設定。當您嘗試連線時，會發生以下錯誤：</span><span class="sxs-lookup"><span data-stu-id="158f5-p106">Windows PowerShell needs to be configured to run scripts, and by default, it isn't. You'll get the following error when you try to connect:</span></span>

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  <span data-ttu-id="158f5-129">若要要求您從網際網路下載的所有 Windows PowerShell 指令碼都是由信任的發行者簽署，請在提高權限的 Windows PowerShell 視窗 (透過選取 [以系統管理員身分執行]\*\*\*\* 而開啟的 Windows PowerShell 視窗) 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="158f5-129">To require all PowerShell scripts that you download from the internet are signed by a trusted publisher, run the following command in an elevated Windows PowerShell window (a Windows PowerShell window you open by selecting **Run as administrator**):</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  <span data-ttu-id="158f5-130">您只需在電腦上設定此設定一次，而不用在每次連線時進行設定。</span><span class="sxs-lookup"><span data-stu-id="158f5-130">You need to configure this setting only once on your computer, not every time you connect.</span></span>

- <span data-ttu-id="158f5-131">如需適用於本主題之程序的鍵盤快速鍵相關資訊，請參閱 [Exchange 系統管理中心的鍵盤快速鍵](https://go.microsoft.com/fwlink/p/?LinkId=534017)。</span><span class="sxs-lookup"><span data-stu-id="158f5-131">For information about keyboard shortcuts that might apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span></span>

## <a name="connect-to-exchange-online-for-customer-organizations"></a><span data-ttu-id="158f5-132">連線到客戶組織的 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="158f5-132">Connect to Exchange Online for customer organizations</span></span>

1. <span data-ttu-id="158f5-133">在您的本機電腦上開啟 Windows PowerShell，並執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="158f5-133">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="158f5-134">在 [Windows PowerShell 認證要求]\*\*\*\* 對話方塊中，輸入您的 DAP 系統管理員使用者名稱和密碼，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="158f5-134">In the **Windows PowerShell Credential Request** dialog box, enter your DAP administrator user name and password, and then click **OK**.</span></span>
    
2. <span data-ttu-id="158f5-135">_\<customer tenant domain name\>_ 以您想要連線的租使用者功能變數名稱取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="158f5-135">Replace _\<customer tenant domain name\>_ with the name of the tenant domain that you want to connect to, and run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    <span data-ttu-id="158f5-136">此命令中的重要步驟是指定可存取報告資訊的客戶。</span><span class="sxs-lookup"><span data-stu-id="158f5-136">The key step in this command is specifying which customer to access for the reporting information.</span></span> <span data-ttu-id="158f5-137">您可以在  _ConnectionURI_ 參數中，以的值提供初始功能變數名稱的 FQDN `?DelegatedOrg=` 。</span><span class="sxs-lookup"><span data-stu-id="158f5-137">You do this in the  _ConnectionURI_ parameter, where you provide the FQDN of the initial domain name as the value for `?DelegatedOrg=`.</span></span> <span data-ttu-id="158f5-138">此值表示要連接的正確 Exchange Online PowerShell 端點。</span><span class="sxs-lookup"><span data-stu-id="158f5-138">This value indicates the correct Exchange Online PowerShell endpoint to connect to.</span></span> <span data-ttu-id="158f5-139">在每次執行報告時，遠端 PowerShell 都必須在特定客戶的內容中連接至 Microsoft 365 報告。</span><span class="sxs-lookup"><span data-stu-id="158f5-139">Remote PowerShell must connect to Microsoft 365 reporting in the context of a specific customer each time a report is run.</span></span> <span data-ttu-id="158f5-140">在您連線至 Exchange Online PowerShell 之後，所有後續命令都會在客戶的上下文中執行，讓您可以存取客戶的所有可用報告。</span><span class="sxs-lookup"><span data-stu-id="158f5-140">After you connect to Exchange Online PowerShell, all subsequent commands are run in the context of the customer, which gives you access to all of the available reports for the customer.</span></span>
    
3. <span data-ttu-id="158f5-141">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="158f5-141">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> <span data-ttu-id="158f5-p108">每個帳戶有同時執行三個工作階段的限制。完成時，請務必中斷遠端 PowerShell 工作階段連線。如果未先中斷工作階段連線即關閉 Windows PowerShell 視窗，您可能會用完您可以使用的所有遠端 PowerShell 工作階段，而需要等待這些工作階段到期。若要中斷遠端 PowerShell 工作階段連線，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="158f5-p108">There's a limit of three simultaneous sessions that can run under one account. Be sure to disconnect the remote PowerShell session when you're finished. If you close the Windows PowerShell window without disconnecting the session, you can use up all the remote PowerShell sessions available to you, and you'll need to wait for the sessions to expire. To disconnect the remote PowerShell session, run the following command:</span></span>

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="158f5-146">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="158f5-146">How do you know this worked?</span></span>

<span data-ttu-id="158f5-p109">執行步驟 3 後，Exchange Online Cmdlet 會匯入您的本機 Windows PowerShell 工作階段中，且會有進度列追蹤此作業。如果您未收到任何錯誤，便已順利連線。若要做快速測試，您可以執行一個 Exchange Online Cmdlet (例如 **Get-Mailbox** )，然後檢視結果。</span><span class="sxs-lookup"><span data-stu-id="158f5-p109">After Step 3, the Exchange Online cmdlets are imported into your local Windows PowerShell session as tracked by a progress bar. If you don't receive any errors, you connected successfully. A quick test is to run an Exchange Online cmdlet (for example, **Get-Mailbox**) and see the results.</span></span>
  
<span data-ttu-id="158f5-150">如果出現錯誤，請檢查下列需求：</span><span class="sxs-lookup"><span data-stu-id="158f5-150">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="158f5-p110">密碼錯誤是常見的問題。再次執行這三個步驟，並特別留意您在步驟 1 中輸入的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="158f5-p110">A common problem is an incorrect password. Run the three steps again and pay close attention to the user name and password you enter in Step 1.</span></span>
    
- <span data-ttu-id="158f5-p111">用來連線至 Exchange Online 的帳戶必須能夠使用遠端 PowerShell。如需詳細資訊，請參閱[啟用或停用 Exchange Online PowerShell 的存取](https://go.microsoft.com/fwlink/p/?LinkId=534018)。</span><span class="sxs-lookup"><span data-stu-id="158f5-p111">The account you use to connect to Exchange Online must be enabled for remote PowerShell. For more information, see [Enable or disable access to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span></span>
    
- <span data-ttu-id="158f5-p112">本機電腦與 Exchange Online 之間必須開啟 TCP 連接埠 80 流量。該連接埠可能已開啟，但必須考量您的組織是否有限制性網際網路存取原則。</span><span class="sxs-lookup"><span data-stu-id="158f5-p112">TCP port 80 traffic needs to be open between your local computer and Exchange Online. It's probably open, but it's something to consider if your organization has a restrictive Internet access policy.</span></span>
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a><span data-ttu-id="158f5-157">利用 Invoke-Command 直接呼叫 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="158f5-157">Call the cmdlet directly with Invoke-Command</span></span>

<span data-ttu-id="158f5-p113">匯入遠端 PowerShell 工作階段 (步驟 3) 可能會是冗長的程序，因為它會帶入_所有_ Exchange Online Cmdlet。在批次處理中這可能會造成問題 (例如，當您執行報告或針對不同租用戶進行大量變更時)。除了使用 **Import-PSSession** 之外，您還可以利用 **Invoke-Command** 直接呼叫要使用的 Cmdlet。例如，若要呼叫 **Get-Milbox** Cmdlet，請以下列語法取代步驟 3 中的 `Import-PSSession $Session` 命令：</span><span class="sxs-lookup"><span data-stu-id="158f5-p113">Importing a remote PowerShell session (Step 3) can be a lengthy process because it brings in _all_ Exchange Online cmdlets. This can be an issue in batch processing (for example, when you're running reports or making bulk changes for different tenants). As an alternative to using **Import-PSSession**, you can call cmdlets you want to use directly with **Invoke-Command**. For example, to call the **Get-Milbox** cmdlet, substitute this syntax for the `Import-PSSession $Session` command in Step 3:</span></span>
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a><span data-ttu-id="158f5-162">其他報告 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="158f5-162">More reporting cmdlets</span></span>

<span data-ttu-id="158f5-p114">本主題中所使用的 Cmdlet 是 Windows PowerShell Cmdlet。如需這些 Cmdlet 的詳細資訊，請參閱下列主題。</span><span class="sxs-lookup"><span data-stu-id="158f5-p114">The cmdlets that you used in this topic are Windows PowerShell cmdlets. For more information about these cmdlets, see the following topics:</span></span>
  
- [<span data-ttu-id="158f5-165">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="158f5-165">Get-Credential</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [<span data-ttu-id="158f5-166">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="158f5-166">New-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [<span data-ttu-id="158f5-167">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="158f5-167">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [<span data-ttu-id="158f5-168">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="158f5-168">Remove-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [<span data-ttu-id="158f5-169">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="158f5-169">Set-ExecutionPolicy</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

