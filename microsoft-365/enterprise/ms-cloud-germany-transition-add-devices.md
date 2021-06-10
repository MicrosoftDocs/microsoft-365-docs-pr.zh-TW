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
description: 摘要：從 microsoft cloud 德國移至服務時，服務的其他裝置資訊 (Microsoft cloud Deutschland) 以 Office 365 新德文 datacenter 區域中的服務。
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861298"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="1575a-103">從 Microsoft Cloud Deutschland 遷移的其他裝置資訊</span><span class="sxs-lookup"><span data-stu-id="1575a-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="1575a-104">連接至 Microsoft 雲端 Deutschland 的 Azure AD 加入和註冊裝置必須在階段9和階段10之前遷移。</span><span class="sxs-lookup"><span data-stu-id="1575a-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="1575a-105">裝置的遷移取決於裝置類型、作業系統和 AAD 關聯。</span><span class="sxs-lookup"><span data-stu-id="1575a-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="1575a-106">常見問題集</span><span class="sxs-lookup"><span data-stu-id="1575a-106">Frequently asked questions</span></span>

<span data-ttu-id="1575a-107">**如何判斷組織是否受到影響？**</span><span class="sxs-lookup"><span data-stu-id="1575a-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="1575a-108">管理員應該檢查 `https://portal.microsoftazure.de` 是否有任何已註冊或 AZURE AD 連接的裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="1575a-109">如果您的組織已註冊裝置，您會受到影響。</span><span class="sxs-lookup"><span data-stu-id="1575a-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="1575a-110">**對我的使用者有何影響？**</span><span class="sxs-lookup"><span data-stu-id="1575a-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="1575a-111">已註冊的裝置中的使用者將無法再登入 [遷移階段 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 已完成，且已停用 Microsoft Cloud Deutschland 的端點。</span><span class="sxs-lookup"><span data-stu-id="1575a-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="1575a-112">在您的組織中斷與 Microsoft 雲端 Deutschland 的連線之前，請確定您的所有裝置都已向全球端點註冊。</span><span class="sxs-lookup"><span data-stu-id="1575a-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="1575a-113">**我的使用者何時重新註冊其裝置？**</span><span class="sxs-lookup"><span data-stu-id="1575a-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="1575a-114">您的成功必須先取消註冊，然後在 [階段 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 完成之後重新登錄裝置，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="1575a-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="1575a-115">您必須在第10階段開始之前完成重新註冊，否則您可能會失去對裝置的存取權。</span><span class="sxs-lookup"><span data-stu-id="1575a-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="1575a-116">**如何在遷移後還原我的裝置狀態？**</span><span class="sxs-lookup"><span data-stu-id="1575a-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="1575a-117">對於向 Azure AD 註冊的公司所擁有的 Windows 裝置，管理員將能夠透過遠端觸發的工作流程（會取消註冊舊的裝置狀態）來管理這些裝置的遷移。</span><span class="sxs-lookup"><span data-stu-id="1575a-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="1575a-118">對於所有其他裝置，包括在 Azure AD 中註冊的個人 Windows 裝置，使用者必須手動執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="1575a-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="1575a-119">若為已加入 Azure 的裝置，使用者必須具有本機系統管理員帳戶，才可取消註冊，然後重新登錄其裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="1575a-120">如需如何成功還原下列裝置狀態的詳細指示，請參閱詳細指示。</span><span class="sxs-lookup"><span data-stu-id="1575a-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="1575a-121">**如何知道我的所有裝置都已登錄公用雲端？**</span><span class="sxs-lookup"><span data-stu-id="1575a-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="1575a-122">若要檢查您的裝置是否已在公用雲端中註冊，您應該將裝置清單從 Azure AD 入口網站匯出並下載至 Excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="1575a-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="1575a-123">然後，使用 _registeredTime_ 欄) [不同于 Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段之後，篩選 (所註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="1575a-124">其他考量</span><span class="sxs-lookup"><span data-stu-id="1575a-124">Additional considerations</span></span>
<span data-ttu-id="1575a-125">在遷移租使用者後，裝置註冊會停用，且無法啟用或停用。</span><span class="sxs-lookup"><span data-stu-id="1575a-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="1575a-126">若未使用 Intune，請登入您的訂閱，並執行此命令以重新開機此選項：</span><span class="sxs-lookup"><span data-stu-id="1575a-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="1575a-127">**重要：** 在商務用遷移後，將會啟用 Intune 服務主體，這表示 Azure AD Device Registration 的啟用。</span><span class="sxs-lookup"><span data-stu-id="1575a-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="1575a-128">如果您在遷移之前封鎖 Azure AD 裝置註冊，您必須使用 PowerShell 停用 Intune service 主體，以使用 Azure AD 入口網站停用 Azure AD 裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="1575a-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="1575a-129">您可以在 Graph 模組的 Azure Active Directory PowerShell 中，使用此命令來停用 Intune 服務主體。</span><span class="sxs-lookup"><span data-stu-id="1575a-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="1575a-130">Azure AD 加入</span><span class="sxs-lookup"><span data-stu-id="1575a-130">Azure AD Join</span></span>
<span data-ttu-id="1575a-131">這適用于 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="1575a-132">如果裝置已加入 Azure AD，必須中斷與 Azure AD 的連線，並再次連線。</span><span class="sxs-lookup"><span data-stu-id="1575a-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="1575a-133">[![AZURE AD 裝置 Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1575a-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="1575a-134">如果使用者是 Windows 10 裝置上的系統管理員，使用者可以從 Azure AD 中登出裝置，然後重新加入。</span><span class="sxs-lookup"><span data-stu-id="1575a-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="1575a-135">如果他沒有系統管理員許可權，則使用者需要此機器上本機系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="1575a-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="1575a-136">管理員可以在此設定路徑之後的裝置上建立本機系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="1575a-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="1575a-137">*設定 > 帳戶 > 其他帳戶 > 憑證未知 > 新增沒有 Microsoft 帳戶的使用者*</span><span class="sxs-lookup"><span data-stu-id="1575a-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="1575a-138">步驟1：判斷裝置是否已加入 Azure 識別碼</span><span class="sxs-lookup"><span data-stu-id="1575a-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="1575a-139">使用使用者電子郵件和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="1575a-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="1575a-140">移至設定 > 帳戶 > 存取單位或學校。</span><span class="sxs-lookup"><span data-stu-id="1575a-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="1575a-141">在清單中尋找 [ **連線至 ...] 的使用者。的 Azure AD**。</span><span class="sxs-lookup"><span data-stu-id="1575a-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="1575a-142">如果已連線的使用者存在，請繼續進行步驟2。</span><span class="sxs-lookup"><span data-stu-id="1575a-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="1575a-143">如果不是，則不需要進一步的動作。</span><span class="sxs-lookup"><span data-stu-id="1575a-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="1575a-144">步驟2：從 Azure AD 中斷裝置連線</span><span class="sxs-lookup"><span data-stu-id="1575a-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="1575a-145">在連線的公司或學校帳戶上，按一下 [ **中斷連線]** 。</span><span class="sxs-lookup"><span data-stu-id="1575a-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="1575a-146">確認 [中斷連線] 兩次。</span><span class="sxs-lookup"><span data-stu-id="1575a-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="1575a-147">輸入本機系統管理員的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="1575a-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="1575a-148">裝置中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1575a-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="1575a-149">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="1575a-150">步驟3：將裝置加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="1575a-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="1575a-151">使用者使用本機系統管理員的認證登入</span><span class="sxs-lookup"><span data-stu-id="1575a-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="1575a-152">移至 **設定** 然後 **帳戶\*\*\*\*存取工作或學校**</span><span class="sxs-lookup"><span data-stu-id="1575a-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="1575a-153">點擊 **連線**</span><span class="sxs-lookup"><span data-stu-id="1575a-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="1575a-154">**重要** 事項：點擊 [**加入 Azure AD** ]</span><span class="sxs-lookup"><span data-stu-id="1575a-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="1575a-155">輸入使用者的電子郵件地址和密碼。</span><span class="sxs-lookup"><span data-stu-id="1575a-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="1575a-156">裝置已連線</span><span class="sxs-lookup"><span data-stu-id="1575a-156">The device is connected</span></span>
6.  <span data-ttu-id="1575a-157">重新開機裝置</span><span class="sxs-lookup"><span data-stu-id="1575a-157">Restart the device</span></span> 
7.  <span data-ttu-id="1575a-158">使用您的電子郵件地址和密碼進行簽署</span><span class="sxs-lookup"><span data-stu-id="1575a-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="1575a-159">Azure AD 已登記 (公司擁有) </span><span class="sxs-lookup"><span data-stu-id="1575a-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="1575a-160">若要判斷 Windows 10 裝置是否已登錄 Azure AD –已註冊，請在裝置上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1575a-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="1575a-161">如果裝置已註冊的是 Azure AD，您會看到下列輸出：</span><span class="sxs-lookup"><span data-stu-id="1575a-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="1575a-162">若要移除裝置上現有的 Azure AD 註冊帳戶，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1575a-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="1575a-163">若要移除裝置上的 Azure AD 註冊帳戶，請使用 CleanupWPJ （您可以從這裡下載的工具）： [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)。</span><span class="sxs-lookup"><span data-stu-id="1575a-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="1575a-164">解壓縮 ZIP 檔，並執行 **WPJCleanup。**</span><span class="sxs-lookup"><span data-stu-id="1575a-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="1575a-165">此工具會根據裝置上的 Windows 版本啟動正確的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="1575a-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="1575a-166">系統管理員可以使用像是「群組原則」這樣的機制，在裝置上任何登入之使用者的上下文中執行命令。</span><span class="sxs-lookup"><span data-stu-id="1575a-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="1575a-167">若要停用 Web 帳戶管理員在 Azure AD 中註冊裝置的提示，請新增此登錄值：</span><span class="sxs-lookup"><span data-stu-id="1575a-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="1575a-168">位置： HKLM\SOFTWARE\Policies\Microsoft\ Windows \WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="1575a-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="1575a-169">類型： DWORD (32 位) </span><span class="sxs-lookup"><span data-stu-id="1575a-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="1575a-170">名稱： BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="1575a-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="1575a-171">值資料：1</span><span class="sxs-lookup"><span data-stu-id="1575a-171">Value data: 1</span></span>

<span data-ttu-id="1575a-172">此登錄值的出現應該會封鎖 workplace join，並防止使用者看到加入裝置的提示。</span><span class="sxs-lookup"><span data-stu-id="1575a-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="1575a-173">Android</span><span class="sxs-lookup"><span data-stu-id="1575a-173">Android</span></span>

<span data-ttu-id="1575a-174">若為 Android，使用者將需要撤銷註冊並重新登錄其裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="1575a-175">這可以透過 Microsoft Authenticator 應用程式或公司入口網站應用程式來完成。</span><span class="sxs-lookup"><span data-stu-id="1575a-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="1575a-176">在 Microsoft Authenticator 應用程式中，使用者可以前往 **設定 > 裝置註冊**。</span><span class="sxs-lookup"><span data-stu-id="1575a-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="1575a-177">從這裡開始，使用者可以撤銷註冊並重新登錄其裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="1575a-178">從公司入口網站中，使用者可以移至 [**裝置**] 索引標籤並移除裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="1575a-179">之後，使用公司入口網站重新註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="1575a-180">使用者也可以從 [帳戶設定] 頁面移除帳戶，然後重新加入工作帳戶，以取消登錄和重新註冊。</span><span class="sxs-lookup"><span data-stu-id="1575a-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="1575a-181">若要使用 Microsoft Authenticator 應用程式在 Android 上撤銷登錄並重新登錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1575a-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="1575a-182">開啟 Microsoft Authenticator 應用程式，然後移至 **設定**。</span><span class="sxs-lookup"><span data-stu-id="1575a-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="1575a-183">選取 **Device registration**。</span><span class="sxs-lookup"><span data-stu-id="1575a-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="1575a-184">選取 [ **登出**] 以取消登錄裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="1575a-185">若為 **Device registration**，請輸入您的電子郵件地址，然後選取 [ **註冊**]，以重新註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="1575a-186">若要使用 Android 設定頁面來撤銷註冊並重新登錄 Android 裝置，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1575a-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="1575a-187">開啟 [**裝置設定**]，然後移至 [**帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="1575a-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="1575a-188">選取您要重新註冊的工作帳戶，然後選取 [ **移除帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="1575a-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="1575a-189">移除帳戶後，請從 [ **帳戶** ] 頁面中，選取 [ **新增帳戶 > 工作帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="1575a-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="1575a-190">在 [ **Workplace Join**] 中輸入您的電子郵件地址，然後選取 [ **加入** ] 以完成裝置的註冊。</span><span class="sxs-lookup"><span data-stu-id="1575a-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="1575a-191">若要從公司入口網站登出並重新登錄 Android 上的裝置：</span><span class="sxs-lookup"><span data-stu-id="1575a-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="1575a-192">啟動公司入口網站，然後移至 [**裝置**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1575a-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="1575a-193">選取裝置以查看裝置詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1575a-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="1575a-194">從省略號 (三點) 功能表中，選取 [ **移除裝置**]，並在對話方塊中確認以完成移除。</span><span class="sxs-lookup"><span data-stu-id="1575a-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="1575a-195">您現在應該已登出公司入口網站的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1575a-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="1575a-196">選取 [登入] 以重新 **登錄** 裝置。</span><span class="sxs-lookup"><span data-stu-id="1575a-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="1575a-197">如需此工作負載遷移階段所需之任何動作的詳細資訊，或對管理或使用的影響，請參閱 azure ad) 中 Azure Active Directory (Azure ad 的相關資訊，以[供從 Microsoft Cloud Deutschland 進行遷移的其他 azure ad 資訊中取得](ms-cloud-germany-transition-azure-ad.md)。</span><span class="sxs-lookup"><span data-stu-id="1575a-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="1575a-198">iOS</span><span class="sxs-lookup"><span data-stu-id="1575a-198">iOS</span></span>

<span data-ttu-id="1575a-199">在 iOS 裝置上，使用者將需要從 Microsoft Authenticator 手動移除任何快取的帳戶、登出裝置，然後登出裝置上的任何原生應用程式。</span><span class="sxs-lookup"><span data-stu-id="1575a-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="1575a-200">步驟1：若存在，請從 Microsoft Authenticator 應用程式中移除帳戶。</span><span class="sxs-lookup"><span data-stu-id="1575a-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="1575a-201">在 Microsoft Authenticator 應用程式中點擊帳戶。</span><span class="sxs-lookup"><span data-stu-id="1575a-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="1575a-202">按一下右上角的 **設定** 圖示。</span><span class="sxs-lookup"><span data-stu-id="1575a-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="1575a-203">如果您沒有看到 **設定** 圖示，則可能是您使用的是 Microsoft Authenticator 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="1575a-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="1575a-204">點擊 [ **移除帳戶** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1575a-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="1575a-205">點擊 [ **此裝置上的所有應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="1575a-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="1575a-206">步驟2：從 Microsoft Authenticator 應用程式中登出裝置</span><span class="sxs-lookup"><span data-stu-id="1575a-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="1575a-207">在右上角點擊功能表圖示。</span><span class="sxs-lookup"><span data-stu-id="1575a-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="1575a-208">按 **設定**，然後按 **裝置註冊**。</span><span class="sxs-lookup"><span data-stu-id="1575a-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="1575a-209">如果顯示您的帳戶，請點擊 [ **登出裝置** ]，然後在對話方塊中 **繼續** 。</span><span class="sxs-lookup"><span data-stu-id="1575a-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="1575a-210">之後，您就不會看到任何帳戶。</span><span class="sxs-lookup"><span data-stu-id="1575a-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="1575a-211">步驟3：必要時登出個別應用程式</span><span class="sxs-lookup"><span data-stu-id="1575a-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="1575a-212">使用者可以移至個別應用程式，例如 Outlook、Teams 及 OneDrive，以及從這些應用程式中移除帳戶。</span><span class="sxs-lookup"><span data-stu-id="1575a-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="1575a-213">其他資訊</span><span class="sxs-lookup"><span data-stu-id="1575a-213">More information</span></span>

<span data-ttu-id="1575a-214">開始：</span><span class="sxs-lookup"><span data-stu-id="1575a-214">Getting started:</span></span>

- [<span data-ttu-id="1575a-215">從 Microsoft Cloud Deutschland 遷移至新德國資料中心區域的 Office 365 服務</span><span class="sxs-lookup"><span data-stu-id="1575a-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="1575a-216">Microsoft Cloud Deutschland 移轉協助</span><span class="sxs-lookup"><span data-stu-id="1575a-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="1575a-217">如何選擇加入移轉</span><span class="sxs-lookup"><span data-stu-id="1575a-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="1575a-218">遷移期間的客戶體驗</span><span class="sxs-lookup"><span data-stu-id="1575a-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="1575a-219">在轉換中移動：</span><span class="sxs-lookup"><span data-stu-id="1575a-219">Moving through the transition:</span></span>

- [<span data-ttu-id="1575a-220">移轉階段的動作與影響</span><span class="sxs-lookup"><span data-stu-id="1575a-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="1575a-221">其他預備工作</span><span class="sxs-lookup"><span data-stu-id="1575a-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="1575a-222">[AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="1575a-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="1575a-223">雲端應用程式：</span><span class="sxs-lookup"><span data-stu-id="1575a-223">Cloud apps:</span></span>

- [<span data-ttu-id="1575a-224">Dynamics 365 的移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="1575a-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="1575a-225">Power BI 移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="1575a-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="1575a-226">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1575a-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)