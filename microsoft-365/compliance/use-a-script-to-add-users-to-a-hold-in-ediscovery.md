---
title: 使用腳本將使用者新增至核心 eDiscovery 案例中的保留
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: 瞭解如何執行腳本，將商務網站的信箱 & OneDrive 新增至與 Microsoft 365 規範中心內的 eDiscovery 案例相關聯的新保留。
ms.openlocfilehash: 278e8e051165eca906e9b454268068cbbe6aef05
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175572"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="e41d5-103">使用腳本將使用者新增至核心 eDiscovery 案例中的保留</span><span class="sxs-lookup"><span data-stu-id="e41d5-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="e41d5-104">安全性 & 合規性中心 PowerShell 提供 Cmdlet，可讓您自動化與建立及管理 eDiscovery 案例相關的耗時工作。</span><span class="sxs-lookup"><span data-stu-id="e41d5-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="e41d5-105">目前，使用安全性 & 合規性中心內的核心 eDiscovery 案例，將大量的保管人內容位置保留在暫止狀態，並準備好。</span><span class="sxs-lookup"><span data-stu-id="e41d5-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="e41d5-106">例如，在您建立保留之前，您必須為想要保留的商務網站收集每個 OneDrive 的 URL。</span><span class="sxs-lookup"><span data-stu-id="e41d5-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="e41d5-107">然後，針對您想要保留的每位使用者，您必須將其信箱和其 OneDrive 的商務網站新增至保留狀態。</span><span class="sxs-lookup"><span data-stu-id="e41d5-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="e41d5-108">您可以使用本文中的腳本來自動化此程式。</span><span class="sxs-lookup"><span data-stu-id="e41d5-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="e41d5-109">腳本會提示您組織之「我的網站」網域的名稱 (例如， `contoso` 在 URL 中 https://contoso-my.sharepoint.com) ，現有 eDiscovery 案例的名稱、與案例關聯的新保留名稱、您想要保留之使用者的電子郵件地址清單，以及您想要建立查詢式保留的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="e41d5-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="e41d5-110">然後，腳本會為清單中的每位使用者取得商務用網站 OneDrive 的 URL，並建立新的保留，然後針對清單中的每一位使用者，新增信箱及 OneDrive 的商務用網站。</span><span class="sxs-lookup"><span data-stu-id="e41d5-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="e41d5-111">腳本也會產生包含新保留相關資訊的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="e41d5-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="e41d5-112">以下是進行這種動作的步驟：</span><span class="sxs-lookup"><span data-stu-id="e41d5-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="e41d5-113">步驟 1：安裝 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="e41d5-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="e41d5-114">步驟2：產生使用者清單</span><span class="sxs-lookup"><span data-stu-id="e41d5-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="e41d5-115">步驟3：執行腳本以建立保留並新增使用者</span><span class="sxs-lookup"><span data-stu-id="e41d5-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="e41d5-116">將使用者新增至保留之前</span><span class="sxs-lookup"><span data-stu-id="e41d5-116">Before you add users to a hold</span></span>

- <span data-ttu-id="e41d5-117">您必須是 Security & 合規性中心內的 eDiscovery Manager 角色群組成員，以及 SharePoint Online 系統管理員執行步驟3中的腳本。</span><span class="sxs-lookup"><span data-stu-id="e41d5-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="e41d5-118">如需詳細資訊，請參閱 [在 Office 365 安全性 & 規範中心指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e41d5-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="e41d5-119">最多可將1000個信箱和100網站新增至與安全性 & 合規性中心內的 eDiscovery 案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="e41d5-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="e41d5-120">假設您要置於保留狀態的每一位使用者都有商務網站的 OneDrive，您可以使用本文中的腳本，將最多100個使用者新增至保留。</span><span class="sxs-lookup"><span data-stu-id="e41d5-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="e41d5-121">請務必將您在步驟2中建立的使用者清單和步驟3中的腳本儲存在相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="e41d5-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="e41d5-122">這樣會使執行腳本變得更容易。</span><span class="sxs-lookup"><span data-stu-id="e41d5-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="e41d5-123">腳本會將使用者清單新增至與現有案例關聯的新保留。</span><span class="sxs-lookup"><span data-stu-id="e41d5-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="e41d5-124">在執行腳本之前，請確定您要建立保留的大小寫與所建立的專案。</span><span class="sxs-lookup"><span data-stu-id="e41d5-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="e41d5-125">本文中的腳本可在連線至安全性 & 合規性中心 PowerShell 及 SharePoint 線上管理命令介面時，支援新式驗證。</span><span class="sxs-lookup"><span data-stu-id="e41d5-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="e41d5-126">如果您是 Microsoft 365 或 Microsoft 365 GCC 組織，您可以將腳本當做-。</span><span class="sxs-lookup"><span data-stu-id="e41d5-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="e41d5-127">如果您是 Office 365 德國組織、Microsoft 365 GCC 高組織或 Microsoft 365 DoD 組織，您必須編輯腳本，以順利執行它。</span><span class="sxs-lookup"><span data-stu-id="e41d5-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="e41d5-128">具體而言，您必須編輯該行 `Connect-IPPSSession` 並使用 *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 參數 (以及組織類型的適當值) 才能連線至安全性 & 規範中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e41d5-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="e41d5-129">如需詳細資訊，請參閱 [Connect To Security & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)中的範例。</span><span class="sxs-lookup"><span data-stu-id="e41d5-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="e41d5-130">腳本會自動中斷與安全性 & 合規性中心的連線 PowerShell 和 SharePoint 線上管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="e41d5-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="e41d5-131">腳本包含最低的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="e41d5-131">The script includes minimal error handling.</span></span> <span data-ttu-id="e41d5-132">其主要用途是快速而輕鬆地將每位使用者的信箱和 OneDrive 用於保留的商務網站。</span><span class="sxs-lookup"><span data-stu-id="e41d5-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="e41d5-p109">在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。</span><span class="sxs-lookup"><span data-stu-id="e41d5-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="e41d5-138">步驟 1：安裝 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="e41d5-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="e41d5-139">第一步是安裝本機電腦上的 SharePoint Online 管理命令介面（如果尚未安裝）。</span><span class="sxs-lookup"><span data-stu-id="e41d5-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="e41d5-140">您不需要在此程式中使用命令介面，但必須安裝它，因為它包含您在步驟3中執行之腳本所需的必要條件。</span><span class="sxs-lookup"><span data-stu-id="e41d5-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="e41d5-141">這些必要條件允許腳本與 SharePoint Online 進行通訊，以取得商務網站 OneDrive 的 URLs。</span><span class="sxs-lookup"><span data-stu-id="e41d5-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="e41d5-142">移至 [設定 SharePoint 線上管理命令介面 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318) ，並執行步驟1和步驟2，在您的本機電腦上安裝 SharePoint 的線上管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="e41d5-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="e41d5-143">步驟2：產生使用者清單</span><span class="sxs-lookup"><span data-stu-id="e41d5-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="e41d5-144">步驟3中的腳本會建立與 eDiscovery 案例相關聯的保留，並新增要保留之使用者清單的信箱和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="e41d5-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="e41d5-145">您可以只輸入文字檔中的電子郵件地址，也可以在 Windows PowerShell 中執行命令，以取得電子郵件地址的清單，並將其儲存至相同資料夾中的檔案 (，您將在步驟 3) 中儲存腳本。</span><span class="sxs-lookup"><span data-stu-id="e41d5-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="e41d5-146">以下是您使用連線至 Exchange Online 組織的遠端 PowerShell 所執行的 PowerShell 命令 () 以取得組織中所有使用者的電子郵件地址清單，並將其儲存至名為 HoldUsers.txt 的文字檔。</span><span class="sxs-lookup"><span data-stu-id="e41d5-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="e41d5-147">在您執行此命令之後，請開啟文字檔，並移除包含屬性名稱的標頭  `PrimarySmtpAddress` 。</span><span class="sxs-lookup"><span data-stu-id="e41d5-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="e41d5-148">然後針對您想要新增至您在步驟3中建立之保留的使用者，移除所有的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e41d5-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="e41d5-149">請確定電子郵件地址清單前面或後面沒有任何空白列。</span><span class="sxs-lookup"><span data-stu-id="e41d5-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="e41d5-150">步驟3：執行腳本以建立保留並新增使用者</span><span class="sxs-lookup"><span data-stu-id="e41d5-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="e41d5-151">當您在此步驟中執行腳本時，它會提示您輸入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="e41d5-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="e41d5-152">在執行腳本之前，請務必準備好此資訊。</span><span class="sxs-lookup"><span data-stu-id="e41d5-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="e41d5-153">**您的使用者認證：** 腳本會使用您的認證，以使用 PowerShell 與安全性 & 合規性中心相連。</span><span class="sxs-lookup"><span data-stu-id="e41d5-153">**Your user credentials:** The script will use your credentials to connect to Security & Compliance Center with PowerShell.</span></span> <span data-ttu-id="e41d5-154">它也會使用這些認證來存取 SharePoint 線上，以取得使用者清單的商務用 OneDrive URLs。</span><span class="sxs-lookup"><span data-stu-id="e41d5-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="e41d5-155">**SharePoint 網域的名稱：** 腳本會提示您輸入此名稱，以便連接至 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e41d5-155">**Name of your SharePoint domain:** The script prompts you to enter this name so it can connect to the SharePoint admin center.</span></span> <span data-ttu-id="e41d5-156">它也會在您的組織中使用 OneDrive URLs 的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="e41d5-156">It also uses the domain name for the OneDrive URLs in your organization.</span></span> <span data-ttu-id="e41d5-157">例如，如果系統管理中心的 URL 是 `https://contoso-admin.sharepoint.com` 和 OneDrive 的 url `https://contoso-my.sharepoint.com` ，則 `contoso` 當腳本提示您輸入功能變數名稱時，就會輸入該 url。</span><span class="sxs-lookup"><span data-stu-id="e41d5-157">For example, if the URL for your admin center is `https://contoso-admin.sharepoint.com` and the URL for OneDrive is `https://contoso-my.sharepoint.com`, then you would enter `contoso` when the script prompts you for your domain name.</span></span>

- <span data-ttu-id="e41d5-158">**案例名稱：** 現有案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="e41d5-158">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="e41d5-159">此腳本會建立與此案例相關聯的新保留。</span><span class="sxs-lookup"><span data-stu-id="e41d5-159">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="e41d5-160">**保留的名稱：** 腳本將要建立並與指定之案例產生關聯的保留名稱。</span><span class="sxs-lookup"><span data-stu-id="e41d5-160">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="e41d5-161">**查詢型保留的搜尋查詢：** 您可以建立以查詢為基礎的保留，使只保留符合指定之搜尋準則的內容。</span><span class="sxs-lookup"><span data-stu-id="e41d5-161">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="e41d5-162">若要將所有內容保留，只要在提示搜尋查詢時按下 **enter** 鍵。</span><span class="sxs-lookup"><span data-stu-id="e41d5-162">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="e41d5-163">**開啟暫止狀態：** 您可以讓腳本在建立保留後將其開啟，也可以讓腳本建立保留，但不加以啟用。</span><span class="sxs-lookup"><span data-stu-id="e41d5-163">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="e41d5-164">如果您未啟用 [保留] 的腳本，您可以稍後在安全性 & 合規性中心或執行下列 PowerShell 命令進行開啟：</span><span class="sxs-lookup"><span data-stu-id="e41d5-164">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="e41d5-165">**具有使用者清單之文字檔的名稱** -步驟2中包含要新增至保留之使用者清單的文字檔名稱。</span><span class="sxs-lookup"><span data-stu-id="e41d5-165">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="e41d5-166">如果此檔案與腳本位於相同的資料夾中，只要輸入檔案名 (例如，HoldUsers.txt) 。</span><span class="sxs-lookup"><span data-stu-id="e41d5-166">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="e41d5-167">如果文字檔位於另一個資料夾中，請輸入完整的檔案名。</span><span class="sxs-lookup"><span data-stu-id="e41d5-167">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="e41d5-168">在您收集腳本將會提示您的資訊後，最後一步是執行腳本以建立新的保留，並新增使用者。</span><span class="sxs-lookup"><span data-stu-id="e41d5-168">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="e41d5-169">使用檔案名尾碼，將下列文字儲存至 Windows PowerShell 腳本檔案 `.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="e41d5-169">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="e41d5-170">例如，`AddUsersToHold.ps1`。</span><span class="sxs-lookup"><span data-stu-id="e41d5-170">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="e41d5-171">在您的本機電腦上，開啟 [Windows PowerShell]，然後移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="e41d5-171">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="e41d5-172">執行腳本;例如：</span><span class="sxs-lookup"><span data-stu-id="e41d5-172">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="e41d5-173">輸入腳本提示您的資訊。</span><span class="sxs-lookup"><span data-stu-id="e41d5-173">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="e41d5-174">腳本會連線至安全性 & 合規性中心 PowerShell，然後在 eDiscovery 案例中建立新的保留，然後在清單中為使用者新增信箱和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="e41d5-174">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="e41d5-175">您可以移至安全性 & 合規性中心的 [ **eDiscovery** ] 頁面上的案例，以查看新的保留。</span><span class="sxs-lookup"><span data-stu-id="e41d5-175">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="e41d5-176">在腳本執行完畢後，它會建立下列記錄檔，並將其儲存至腳本所在的資料夾。</span><span class="sxs-lookup"><span data-stu-id="e41d5-176">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="e41d5-177">**LocationsOnHold.txt：** 包含腳本成功放置之商務網站的信箱和 OneDrive 清單。</span><span class="sxs-lookup"><span data-stu-id="e41d5-177">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="e41d5-178">**LocationsNotOnHold.txt：** 包含未保留腳本之商務網站的信箱和 OneDrive 清單。</span><span class="sxs-lookup"><span data-stu-id="e41d5-178">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="e41d5-179">如果使用者有信箱，但不是商務網站的 OneDrive，該使用者將會包含在未保留之商務網站的 OneDrive 清單中。</span><span class="sxs-lookup"><span data-stu-id="e41d5-179">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="e41d5-180">**GetCaseHoldPolicy.txt：** 包含新保留的 **Get-CaseHoldPolicy** Cmdlet 的輸出，腳本會在建立新的保留後執行。</span><span class="sxs-lookup"><span data-stu-id="e41d5-180">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="e41d5-181">此指令程式傳回的資訊包含使用者清單，以及其信箱和 OneDrive 商務網站保留，以及是否已啟用或停用保留。</span><span class="sxs-lookup"><span data-stu-id="e41d5-181">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="e41d5-182">**GetCaseHoldRule.txt：** 包含新保留的 **Get-CaseHoldRule** Cmdlet 的輸出，腳本會在建立新的保留後執行。</span><span class="sxs-lookup"><span data-stu-id="e41d5-182">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="e41d5-183">如果您使用腳本來建立查詢型保留，則此 Cmdlet 傳回的資訊會包含搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="e41d5-183">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
