---
title: 從 Microsoft Cloud Deutschland 遷移的其他裝置資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：從 Microsoft Cloud (德國移至 Microsoft cloud Deutschland 時，服務的其他裝置資訊) 新德文 datacenter 區域中的 Office 365 服務。
ms.openlocfilehash: 1bbb4bf39db61a93844c21cd6062a70699b5d6d7
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688650"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="58c2f-103">從 Microsoft Cloud Deutschland 遷移的其他裝置資訊</span><span class="sxs-lookup"><span data-stu-id="58c2f-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="58c2f-104">常見問題集</span><span class="sxs-lookup"><span data-stu-id="58c2f-104">Frequently asked questions</span></span>

<span data-ttu-id="58c2f-105">**如何判斷組織是否受到影響？**</span><span class="sxs-lookup"><span data-stu-id="58c2f-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="58c2f-106">管理員應該檢查 `https://portal.microsoftazure.de` 是否有任何已註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="58c2f-107">如果您的組織已註冊裝置，您會受到影響。</span><span class="sxs-lookup"><span data-stu-id="58c2f-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="58c2f-108">**對我的使用者有何影響？**</span><span class="sxs-lookup"><span data-stu-id="58c2f-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="58c2f-109">在您的遷移進入 [Finalize AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段後，已登錄裝置的使用者將無法再登入。</span><span class="sxs-lookup"><span data-stu-id="58c2f-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="58c2f-110">在您的組織中斷與 Microsoft 雲端 Deutschland 的連線之前，請確定您的所有裝置都已向全球端點註冊。</span><span class="sxs-lookup"><span data-stu-id="58c2f-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="58c2f-111">**我的使用者何時重新註冊其裝置？**</span><span class="sxs-lookup"><span data-stu-id="58c2f-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="58c2f-112">您的成功必須先取消註冊，然後在 [不同的 Microsoft 雲端 Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段重新登錄裝置，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="58c2f-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="58c2f-113">**如何在遷移後還原我的裝置狀態？**</span><span class="sxs-lookup"><span data-stu-id="58c2f-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="58c2f-114">對於以 Azure AD 註冊的混合式 Azure AD （已加入及公司所擁有的 Windows 裝置），管理員將能夠透過遠端觸發的工作流程（會取消註冊舊的裝置狀態）來管理這些裝置的遷移。</span><span class="sxs-lookup"><span data-stu-id="58c2f-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="58c2f-115">對於所有其他裝置，包括在 Azure AD 中註冊的個人 Windows 裝置，使用者必須手動執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="58c2f-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="58c2f-116">若為已加入 Azure 的裝置，使用者必須具有本機系統管理員帳戶，才可取消註冊，然後重新登錄其裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="58c2f-117">Microsoft 會發佈有關如何成功還原裝置狀態的指示。</span><span class="sxs-lookup"><span data-stu-id="58c2f-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="58c2f-118">**如何知道我的所有裝置都已登錄公用雲端？**</span><span class="sxs-lookup"><span data-stu-id="58c2f-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="58c2f-119">若要檢查您的裝置是否已在公用雲端中註冊，您應該將裝置清單從 Azure AD 入口網站匯出並下載至 Excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="58c2f-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="58c2f-120">然後，使用 _registeredTime_ 欄) [不同于 Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段之後，篩選 (所註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="58c2f-121">在遷移租使用者後，裝置註冊會停用，且無法啟用或停用。</span><span class="sxs-lookup"><span data-stu-id="58c2f-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="58c2f-122">若未使用 Intune，請登入您的訂閱，並執行此命令以重新開機此選項：</span><span class="sxs-lookup"><span data-stu-id="58c2f-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="58c2f-123">Windows 混合式 Azure AD 聯結</span><span class="sxs-lookup"><span data-stu-id="58c2f-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="58c2f-124">Windows 低層級</span><span class="sxs-lookup"><span data-stu-id="58c2f-124">Windows down-level</span></span>

<span data-ttu-id="58c2f-125">_Windows 下層裝置_ 是目前執行舊版 Windows 的 windows 裝置 (例如 windows 8.1 或 windows 7) ，或執行2019和2016之前的 windows Server 版本。</span><span class="sxs-lookup"><span data-stu-id="58c2f-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="58c2f-126">如果這些裝置在註冊之前已註冊，您必須撤銷註冊並重新登錄這些裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="58c2f-127">若要判斷 Windows 下層裝置先前是否加入 Azure AD，請在裝置上使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="58c2f-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="58c2f-128">如果裝置先前已加入 Azure AD，而且裝置具有與全域 Azure AD 端點的網路連線，您會看到下列輸出：</span><span class="sxs-lookup"><span data-stu-id="58c2f-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="58c2f-129">受影響裝置的「裝置狀態」會具有值為 "Unknown"。</span><span class="sxs-lookup"><span data-stu-id="58c2f-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="58c2f-130">若輸出為 "裝置未加入" 或 "Device state" 值為 "Ok"，請忽略下列指導方針。</span><span class="sxs-lookup"><span data-stu-id="58c2f-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="58c2f-131">僅限顯示裝置已通過 deviceId、指紋等等)  (加入，且其「裝置狀態」值為「未知」的裝置，管理員應該在此類下層裝置的網域使用者登入上下文中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="58c2f-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="58c2f-132">在 Windows 下層裝置上，針對每個網域使用者登入，上述命令只需執行一次。</span><span class="sxs-lookup"><span data-stu-id="58c2f-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="58c2f-133">這個命令應該在網域使用者登入的內容中執行。</span><span class="sxs-lookup"><span data-stu-id="58c2f-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="58c2f-134">在使用者後續登入時，您必須採取足夠的護理，才可執行此命令。</span><span class="sxs-lookup"><span data-stu-id="58c2f-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="58c2f-135">當先前的命令執行時，它會為登入的使用者清除本機混合式 Azure AD –加入的電腦的已加入狀態。</span><span class="sxs-lookup"><span data-stu-id="58c2f-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="58c2f-136">而且，如果電腦仍設定為在租使用者中加入混合式 Azure AD，它會在使用者重新登入時嘗試加入。</span><span class="sxs-lookup"><span data-stu-id="58c2f-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="58c2f-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="58c2f-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="58c2f-138">脫離</span><span class="sxs-lookup"><span data-stu-id="58c2f-138">Unjoin</span></span>

<span data-ttu-id="58c2f-139">若要判斷 Windows 10 裝置先前是否加入 Azure AD，請在裝置上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="58c2f-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="58c2f-140">如果裝置為混合式 Azure AD-已加入，系統管理員會看到下列輸出：</span><span class="sxs-lookup"><span data-stu-id="58c2f-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="58c2f-141">如果輸出為 "AzureAdJoined：否"，請忽略下列指導方針。</span><span class="sxs-lookup"><span data-stu-id="58c2f-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="58c2f-142">僅限顯示裝置加入 Azure AD 的裝置，以系統管理員身分執行下列命令，以移除裝置的已加入狀態。</span><span class="sxs-lookup"><span data-stu-id="58c2f-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="58c2f-143">上述命令只需要在 Windows 裝置的系統管理內容中執行一次。</span><span class="sxs-lookup"><span data-stu-id="58c2f-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="58c2f-144">混合式 AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="58c2f-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="58c2f-145">只要裝置具有與全域 Azure AD 端點的網路連線，裝置就會自動加入至 Azure AD （無使用者或系統管理員干預）。</span><span class="sxs-lookup"><span data-stu-id="58c2f-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="58c2f-146">Windows Azure AD 加入</span><span class="sxs-lookup"><span data-stu-id="58c2f-146">Windows Azure AD Join</span></span>

<span data-ttu-id="58c2f-147">**重要：** 在商務用遷移後，將會啟用 Intune 服務主體，這表示 Azure AD Device Registration 的啟用。</span><span class="sxs-lookup"><span data-stu-id="58c2f-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="58c2f-148">如果您在遷移之前封鎖 Azure AD 裝置註冊，您必須使用 PowerShell 停用 Intune service 主體，以使用 Azure AD 入口網站停用 Azure AD 裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="58c2f-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="58c2f-149">您可以在 [Graph] 模組的 [Azure Active Directory PowerShell 中使用此命令來停用 Intune 服務主體。</span><span class="sxs-lookup"><span data-stu-id="58c2f-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="58c2f-150">脫離</span><span class="sxs-lookup"><span data-stu-id="58c2f-150">Unjoin</span></span>

<span data-ttu-id="58c2f-151">若要判斷 Windows 10 裝置先前是否加入 Azure AD，使用者或系統管理員可以在裝置上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="58c2f-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="58c2f-152">如果裝置加入 Azure AD，則使用者或系統管理員會看到下列輸出：</span><span class="sxs-lookup"><span data-stu-id="58c2f-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="58c2f-153">如果輸出為 "AzureAdJoined：否"，請忽略下列指導方針。</span><span class="sxs-lookup"><span data-stu-id="58c2f-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="58c2f-154">使用者：如果裝置已加入 Azure AD，使用者可以從設定中脫離裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="58c2f-155">在從 Azure AD unjoining 裝置之前，請確認裝置上具有本機系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="58c2f-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="58c2f-156">需要有本機系統管理員帳戶，才可重新登入裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="58c2f-157">Admin：如果組織的系統管理員想要將已加入 Azure AD 的使用者裝置，可在每個裝置上執行下列命令，以使用群組原則等機制來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="58c2f-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="58c2f-158">管理員在從 Azure AD unjoining 裝置之前，必須先確認裝置上具有本機系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="58c2f-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="58c2f-159">需要有本機系統管理員帳戶，才可重新登入裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="58c2f-160">上述命令只需要在 Windows 裝置的系統管理內容中執行一次。</span><span class="sxs-lookup"><span data-stu-id="58c2f-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="58c2f-161">Azure AD 加入/重新註冊</span><span class="sxs-lookup"><span data-stu-id="58c2f-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="58c2f-162">使用者可以從 [Windows 設定] 將裝置加入 Azure AD： **設定 > 帳戶 > 存取工作或學校 >** 連線。</span><span class="sxs-lookup"><span data-stu-id="58c2f-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="58c2f-163">Windows Azure AD 已登記 (公司擁有) </span><span class="sxs-lookup"><span data-stu-id="58c2f-163">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="58c2f-164">若要判斷 Windows 10 裝置是否已登錄 Azure AD，請在裝置上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="58c2f-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="58c2f-165">如果裝置已註冊的是 Azure AD，您會看到下列輸出：</span><span class="sxs-lookup"><span data-stu-id="58c2f-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="58c2f-166">若要移除裝置上現有的 Azure AD 註冊帳戶，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="58c2f-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="58c2f-167">若要移除裝置上的 Azure AD 註冊帳戶，請使用 CleanupWPJ （您可以從這裡下載的工具）： [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)。</span><span class="sxs-lookup"><span data-stu-id="58c2f-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="58c2f-168">解壓縮 ZIP 檔，並執行 **WPJCleanup。**</span><span class="sxs-lookup"><span data-stu-id="58c2f-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="58c2f-169">此工具會根據裝置上的 Windows 版本啟動正確的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="58c2f-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="58c2f-170">系統管理員可以使用像是「群組原則」這樣的機制，在裝置上任何登入之使用者的上下文中執行命令。</span><span class="sxs-lookup"><span data-stu-id="58c2f-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="58c2f-171">若要停用 Web 帳戶管理員在 Azure AD 中註冊裝置的提示，請新增此登錄值：</span><span class="sxs-lookup"><span data-stu-id="58c2f-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="58c2f-172">位置： HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="58c2f-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="58c2f-173">類型： DWORD (32 位) </span><span class="sxs-lookup"><span data-stu-id="58c2f-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="58c2f-174">名稱： BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="58c2f-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="58c2f-175">值資料：1</span><span class="sxs-lookup"><span data-stu-id="58c2f-175">Value data: 1</span></span>

<span data-ttu-id="58c2f-176">此登錄值的出現應該會封鎖 workplace join，並防止使用者看到加入裝置的提示。</span><span class="sxs-lookup"><span data-stu-id="58c2f-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="58c2f-177">Android</span><span class="sxs-lookup"><span data-stu-id="58c2f-177">Android</span></span>

<span data-ttu-id="58c2f-178">若為 Android，使用者將需要撤銷註冊並重新登錄其裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="58c2f-179">這可以透過 Microsoft 驗證器應用程式或公司入口網站應用程式來完成。</span><span class="sxs-lookup"><span data-stu-id="58c2f-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="58c2f-180">使用者可以從 Microsoft 驗證器應用程式移至 [ **設定] > Device Registration**。</span><span class="sxs-lookup"><span data-stu-id="58c2f-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="58c2f-181">從這裡開始，使用者可以撤銷註冊並重新登錄其裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="58c2f-182">在公司入口網站中，使用者可以移至 [ **裝置** ] 索引標籤並移除裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="58c2f-183">之後，使用公司入口網站重新註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="58c2f-184">使用者也可以從 [帳戶設定] 頁面移除帳戶，然後重新加入工作帳戶，以取消登錄和重新註冊。</span><span class="sxs-lookup"><span data-stu-id="58c2f-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="58c2f-185">若要使用 Microsoft 驗證器應用程式，在 Android 上撤銷登錄並重新註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="58c2f-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="58c2f-186">開啟 Microsoft 驗證器應用程式，然後移至 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="58c2f-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="58c2f-187">選取 **Device registration**。</span><span class="sxs-lookup"><span data-stu-id="58c2f-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="58c2f-188">選取 [ **登出**] 以取消登錄裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="58c2f-189">若為 **Device registration**，請輸入您的電子郵件地址，然後選取 [ **註冊**]，以重新註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="58c2f-190">若要使用 [Android 設定] 頁面撤銷註冊並重新登錄 Android 裝置，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="58c2f-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="58c2f-191">開啟 [ **裝置設定** ]，然後移至 [ **帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="58c2f-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="58c2f-192">選取您要重新註冊的工作帳戶，然後選取 [ **移除帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="58c2f-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="58c2f-193">移除帳戶後，請從 [ **帳戶** ] 頁面中，選取 [ **新增帳戶 > 工作帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="58c2f-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="58c2f-194">在 [ **Workplace Join**] 中輸入您的電子郵件地址，然後選取 [ **加入** ] 以完成裝置的註冊。</span><span class="sxs-lookup"><span data-stu-id="58c2f-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="58c2f-195">若要從公司入口網站上登出並重新登錄 Android 上的裝置：</span><span class="sxs-lookup"><span data-stu-id="58c2f-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="58c2f-196">啟動公司入口網站，然後移至 [ **裝置** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="58c2f-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="58c2f-197">選取裝置以查看裝置詳細資料。</span><span class="sxs-lookup"><span data-stu-id="58c2f-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="58c2f-198">從省略號 (三點) 功能表中，選取 [ **移除裝置**]，並在對話方塊中確認以完成移除。</span><span class="sxs-lookup"><span data-stu-id="58c2f-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="58c2f-199">您現在應該已登出公司入口網站應用程式。</span><span class="sxs-lookup"><span data-stu-id="58c2f-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="58c2f-200">選取 [登入] 以重新 **登錄** 裝置。</span><span class="sxs-lookup"><span data-stu-id="58c2f-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="58c2f-201">如需此工作負載遷移階段所需之任何動作的詳細資訊，或對管理或使用的影響，請參閱其他 Azure AD information for the Azure Active Directory (Azure AD) 中的相關資訊，以 [供從 Microsoft Cloud Deutschland 進行遷移](ms-cloud-germany-transition-azure-ad.md)。</span><span class="sxs-lookup"><span data-stu-id="58c2f-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="58c2f-202">iOS</span><span class="sxs-lookup"><span data-stu-id="58c2f-202">iOS</span></span>

<span data-ttu-id="58c2f-203">在 iOS 裝置上，使用者將需要從 Microsoft 驗證者手動移除任何快取的帳戶、登出裝置，然後登出裝置上的任何原生應用程式。</span><span class="sxs-lookup"><span data-stu-id="58c2f-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="58c2f-204">步驟1：若存在，請從 Microsoft 驗證器應用程式中移除帳戶</span><span class="sxs-lookup"><span data-stu-id="58c2f-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="58c2f-205">點擊 Microsoft 驗證應用程式中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="58c2f-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="58c2f-206">按一下右上角的 [ **設定** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="58c2f-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="58c2f-207">如果您看不到 [ **設定** ] 圖示，表示您可能並未使用最新版的 Microsoft 驗證者。</span><span class="sxs-lookup"><span data-stu-id="58c2f-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="58c2f-208">點擊 [ **移除帳戶** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="58c2f-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="58c2f-209">點擊 [ **此裝置上的所有應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="58c2f-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="58c2f-210">步驟2：從 Microsoft 驗證器應用程式登出裝置</span><span class="sxs-lookup"><span data-stu-id="58c2f-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="58c2f-211">在右上角點擊功能表圖示。</span><span class="sxs-lookup"><span data-stu-id="58c2f-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="58c2f-212">點擊 [ **設定** ]，然後按 **裝置註冊**。</span><span class="sxs-lookup"><span data-stu-id="58c2f-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="58c2f-213">如果顯示您的帳戶，請點擊 [ **登出裝置** ]，然後在對話方塊中 **繼續** 。</span><span class="sxs-lookup"><span data-stu-id="58c2f-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="58c2f-214">之後，您就不會看到任何帳戶。</span><span class="sxs-lookup"><span data-stu-id="58c2f-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="58c2f-215">步驟3：必要時登出個別應用程式</span><span class="sxs-lookup"><span data-stu-id="58c2f-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="58c2f-216">使用者可以移至個別應用程式，例如 Outlook、小組和 OneDrive，以及從這些應用程式中移除帳戶。</span><span class="sxs-lookup"><span data-stu-id="58c2f-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="58c2f-217">其他資訊</span><span class="sxs-lookup"><span data-stu-id="58c2f-217">More information</span></span>

<span data-ttu-id="58c2f-218">開始：</span><span class="sxs-lookup"><span data-stu-id="58c2f-218">Getting started:</span></span>

- [<span data-ttu-id="58c2f-219">從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務</span><span class="sxs-lookup"><span data-stu-id="58c2f-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="58c2f-220">Microsoft Cloud Deutschland 移轉協助</span><span class="sxs-lookup"><span data-stu-id="58c2f-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="58c2f-221">如何選擇加入移轉</span><span class="sxs-lookup"><span data-stu-id="58c2f-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="58c2f-222">遷移期間的客戶體驗</span><span class="sxs-lookup"><span data-stu-id="58c2f-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="58c2f-223">在轉換中移動：</span><span class="sxs-lookup"><span data-stu-id="58c2f-223">Moving through the transition:</span></span>

- [<span data-ttu-id="58c2f-224">移轉階段的動作與影響</span><span class="sxs-lookup"><span data-stu-id="58c2f-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="58c2f-225">其他預備工作</span><span class="sxs-lookup"><span data-stu-id="58c2f-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="58c2f-226">[AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="58c2f-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="58c2f-227">雲端應用程式：</span><span class="sxs-lookup"><span data-stu-id="58c2f-227">Cloud apps:</span></span>

- [<span data-ttu-id="58c2f-228">Dynamics 365 的移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="58c2f-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="58c2f-229">Power BI 移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="58c2f-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="58c2f-230">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58c2f-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
