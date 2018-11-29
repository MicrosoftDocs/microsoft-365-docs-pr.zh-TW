---
title: GDPR
description: Microsoft 技術指導方針 - 提交刪除要求的 FASTTRACK 移轉工具組
keywords: FastTrack 移轉、Microsoft 365 教育版、Microsoft 365 文件、GDPR
author: MohitKumar
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 9b129b7bbc1ffdcfa2dd4ac7bc0d70d09f3fb2a6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866316"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="61606-104">提交刪除要求的 FASTTRACK 移轉工具組</span><span class="sxs-lookup"><span data-stu-id="61606-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="61606-105">工具組的用途</span><span class="sxs-lookup"><span data-stu-id="61606-105">Toolset purpose</span></span>

<span data-ttu-id="61606-p101">若您是目前正在進行 FastTrack 移轉的客戶，刪除 Office 365 的使用者帳戶並不會將 Microsoft FastTrack 小組所保留的資料副本刪除，其保留之目的僅為完成移轉。如果在移轉期間，您想要 Microsoft FastTrack 小組也一併刪除資料副本，請透過此工具組提交要求。在一般的業務過程中，完成移轉之後，Microsoft FastTrack 會刪除所有資料副本。</span><span class="sxs-lookup"><span data-stu-id="61606-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the Office 365 user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If, during the migration, you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this toolset. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span> 

### <a name="supported-platforms"></a><span data-ttu-id="61606-109">支援的平台</span><span class="sxs-lookup"><span data-stu-id="61606-109">Supported platforms</span></span>
<span data-ttu-id="61606-p102">Microsoft 在 Windows 平台和 PowerShell 主控台支援此工具組的最初版本。此工具組支援下列已知平台：</span><span class="sxs-lookup"><span data-stu-id="61606-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>
 
<span data-ttu-id="61606-112">***表格 1 - 此工具組支援的平台***</span><span class="sxs-lookup"><span data-stu-id="61606-112">***Table 1 - Platforms supported by this toolset***</span></span>
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |<span data-ttu-id="61606-113">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="61606-113">**Windows 7**</span></span>|<span data-ttu-id="61606-114">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="61606-114">**Windows 8**</span></span>|<span data-ttu-id="61606-115">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="61606-115">**Windows 10**</span></span>|<span data-ttu-id="61606-116">**Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="61606-116">**Windows Server 2012**</span></span>|<span data-ttu-id="61606-117">**Windows Server 2016**</span><span class="sxs-lookup"><span data-stu-id="61606-117">**Windows Server 2016**</span></span>|
|<span data-ttu-id="61606-118">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="61606-118">PS 5.0</span></span>|<span data-ttu-id="61606-119">不</span><span class="sxs-lookup"><span data-stu-id="61606-119">Not</span></span><br/><span data-ttu-id="61606-120">支援</span><span class="sxs-lookup"><span data-stu-id="61606-120">Supported</span></span>|<span data-ttu-id="61606-121">支援</span><span class="sxs-lookup"><span data-stu-id="61606-121">Supported</span></span>|<span data-ttu-id="61606-122">支援</span><span class="sxs-lookup"><span data-stu-id="61606-122">Supported</span></span>|<span data-ttu-id="61606-123">支援</span><span class="sxs-lookup"><span data-stu-id="61606-123">Supported</span></span>|<span data-ttu-id="61606-124">支援</span><span class="sxs-lookup"><span data-stu-id="61606-124">Supported</span></span>|
|<span data-ttu-id="61606-125">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="61606-125">PS 5.1</span></span>|<span data-ttu-id="61606-126">不</span><span class="sxs-lookup"><span data-stu-id="61606-126">Not</span></span><br/><span data-ttu-id="61606-127">支援</span><span class="sxs-lookup"><span data-stu-id="61606-127">Supported</span></span>|<span data-ttu-id="61606-128">支援</span><span class="sxs-lookup"><span data-stu-id="61606-128">Supported</span></span>|<span data-ttu-id="61606-129">支援</span><span class="sxs-lookup"><span data-stu-id="61606-129">Supported</span></span>|<span data-ttu-id="61606-130">支援</span><span class="sxs-lookup"><span data-stu-id="61606-130">Supported</span></span>|<span data-ttu-id="61606-131">支援</span><span class="sxs-lookup"><span data-stu-id="61606-131">Supported</span></span>|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a><span data-ttu-id="61606-132">取得工具組</span><span class="sxs-lookup"><span data-stu-id="61606-132">Obtaining the toolset</span></span>

<span data-ttu-id="61606-p103">PowerShell 主控台應用程式的 PowerShell 資源庫中提供此工具組。若要找出並載入此 cmdlet 模組，請先在系統管理員模式中開啟 PowerShell，以讓它具有適當的權限可安裝模組。若您先前尚未使用過 PowerShell，請移至您的 Windows 工作列，然後在搜尋方塊中輸入 “PowerShell”。使用滑鼠右鍵選取主控台應用程式，然後選擇 [以系統管理員身分執行]\*\*\*\*，然後按一下 [是]\*\*\*\* 來執行 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="61606-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell - 以系統管理員身分執行](media/fasttrack-powershell_image.png)

![PowerShell - 允許應用程式進行變更](media/fasttrack-run-powershell_image.png)

<span data-ttu-id="61606-p104">現在主控台已開啟，您必須設定權限來執行指令碼。請輸入下列命令，以允許執行指令碼：‘Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope:Process’</span><span class="sxs-lookup"><span data-stu-id="61606-p104">Now that the console is open, you need to set permissions for script execution. Type the following command to allow the scripts to run: ‘Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope:Process’</span></span>

<span data-ttu-id="61606-141">系統會提示您確認執行此動作，因為系統管理員可以隨時變更範圍。</span><span class="sxs-lookup"><span data-stu-id="61606-141">You will be prompted to confirm this action, as the administrator can change the scope at their discretion..</span></span>

<span data-ttu-id="61606-142">***設定執行原則***</span><span class="sxs-lookup"><span data-stu-id="61606-142">***Set Execution Policy***</span></span>

![在 PowerShell 中設定執行原則變更](media/powershell-set-execution-policy_image.png)

<span data-ttu-id="61606-144">現在您已將主控台設定為允許指令碼，請執行下一個命令來安裝這項模組：</span><span class="sxs-lookup"><span data-stu-id="61606-144">Now that the console is set to allow the script,  run this next command to install the module:</span></span>

><span data-ttu-id="61606-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span><span class="sxs-lookup"><span data-stu-id="61606-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span></span>
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a><span data-ttu-id="61606-146">模組的必要條件</span><span class="sxs-lookup"><span data-stu-id="61606-146">Prerequisites for module</span></span>
<span data-ttu-id="61606-p105">若要順利執行此模組，您可能必須安裝相關模組，以便在尚未安裝這些模組時可供使用。您可能必須重新啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="61606-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>  

<span data-ttu-id="61606-149">若要提交 DSR，您必須先使用 Office 365 認證登入，輸入適當的認證會驗證您的全域系統管理員狀態，並收集租用資訊。</span><span class="sxs-lookup"><span data-stu-id="61606-149">In order to submit a DSR, you must first login using your Office 365 credentials – entering the proper credentials will validate your global administrator status and collect tenant information.</span></span> 

<span data-ttu-id="61606-150">**Login-FastTrackAccount -ApiKey：\<FastTrack MVM 所提供的 API 金鑰\>**</span><span class="sxs-lookup"><span data-stu-id="61606-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span></span>

<span data-ttu-id="61606-151">一旦順利登入後，系統會儲存認證和金鑰，以供與目前 PowerShell 工作階段其餘部分的 FastTrack 模組搭配使用。</span><span class="sxs-lookup"><span data-stu-id="61606-151">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="61606-152">如果您需要連線到雲端環境，而不是商業環境，必須在下列其中一個有效的環境中，將 -Environment\*\* 新增至 Login\*\* 命令：</span><span class="sxs-lookup"><span data-stu-id="61606-152">If you need to connect to a cloud environment, other than commercial, *-Environment* will needed to be added to *Login* command with one of the following valid environments:</span></span>
- <span data-ttu-id="61606-153">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="61606-153">AzureCloud</span></span>
- <span data-ttu-id="61606-154">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="61606-154">AzureChinaCloud</span></span>
- <span data-ttu-id="61606-155">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="61606-155">AzureGermanCloud</span></span>
- <span data-ttu-id="61606-156">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="61606-156">AzureUSGovernmentCloud</span></span>

<span data-ttu-id="61606-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span><span class="sxs-lookup"><span data-stu-id="61606-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span></span>

<span data-ttu-id="61606-158">若要提交 DSR 要求，請執行下列命令：Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span><span class="sxs-lookup"><span data-stu-id="61606-158">To submit a DSR request, run the following command: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span></span>

<span data-ttu-id="61606-p106">一旦成功後 – cmdlet 就會傳回交易識別碼物件。請保留交易識別碼。</span><span class="sxs-lookup"><span data-stu-id="61606-p106">On success – the cmdlet will return a Transaction ID object. Please retain the Transaction ID.</span></span>


#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="61606-161">檢查要求交易的狀態</span><span class="sxs-lookup"><span data-stu-id="61606-161">Checking the status of a request transaction</span></span>

<span data-ttu-id="61606-162">使用先前取得的交易識別碼執行下列函式：Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span><span class="sxs-lookup"><span data-stu-id="61606-162">Run the following function using the previously obtained Transaction ID: Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span></span>

#### <a name="transaction-status-codes"></a><span data-ttu-id="61606-163">交易狀態碼</span><span class="sxs-lookup"><span data-stu-id="61606-163">Transaction Status Codes</span></span>
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|<span data-ttu-id="61606-164">**交易**</span><span class="sxs-lookup"><span data-stu-id="61606-164">**Transaction**</span></span> |<span data-ttu-id="61606-165">**狀態**</span><span class="sxs-lookup"><span data-stu-id="61606-165">**Status**</span></span>|
|<span data-ttu-id="61606-166">**建立於**</span><span class="sxs-lookup"><span data-stu-id="61606-166">**Created**</span></span> |<span data-ttu-id="61606-167">已建立要求</span><span class="sxs-lookup"><span data-stu-id="61606-167">Request has been created</span></span>|
|<span data-ttu-id="61606-168">**失敗**</span><span class="sxs-lookup"><span data-stu-id="61606-168">**Failed**</span></span>|<span data-ttu-id="61606-169">要求無法建立，請重新提交，或連絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="61606-169">Request failed to create, please resubmit, or contact support</span></span>|
|<span data-ttu-id="61606-170">**完成**</span><span class="sxs-lookup"><span data-stu-id="61606-170">**Completed**</span></span>|<span data-ttu-id="61606-171">要求已完成並加以清理</span><span class="sxs-lookup"><span data-stu-id="61606-171">Request has been completed and sanitized</span></span>|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a><span data-ttu-id="61606-172">深入了解</span><span class="sxs-lookup"><span data-stu-id="61606-172">Learn more</span></span>
[<span data-ttu-id="61606-173">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="61606-173">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)