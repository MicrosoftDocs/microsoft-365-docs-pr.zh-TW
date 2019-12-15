---
title: 偵測並修復 Office 365 中的非法同意授權
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何識別並修正在 Office 365 中的非法同意授權。
ms.openlocfilehash: 10c03fe0370732e9cb1a10a55767648ae0ddb80b
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971721"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a><span data-ttu-id="89223-103">偵測並修復 Office 365 中的非法同意授權</span><span class="sxs-lookup"><span data-stu-id="89223-103">Detect and Remediate Illicit Consent Grants in Office 365</span></span>

<span data-ttu-id="89223-104">**摘要**了解如何識別並修正在 Office 365 中的非法同意授權。</span><span class="sxs-lookup"><span data-stu-id="89223-104">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="89223-105">什麼是 Office 365 中的非法同意授權攻擊？</span><span class="sxs-lookup"><span data-stu-id="89223-105">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="89223-106">在非法同意授權攻擊中，攻擊者會建立已註冊 Azure 的應用程式，要求存取連絡人資訊、電子郵件或文件等資料。</span><span class="sxs-lookup"><span data-stu-id="89223-106">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="89223-107">然後，攻擊者誘騙使用者授權該應用程式同意透過網路釣魚攻擊，或透過插入非法程式碼到信任的網站，來存取其資料。</span><span class="sxs-lookup"><span data-stu-id="89223-107">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="89223-108">在非法應用程式獲得授權之後，就擁有資料的帳戶層級存取權，而不需要組織帳戶。</span><span class="sxs-lookup"><span data-stu-id="89223-108">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="89223-109">一般補救步驟，例如重設遭入侵帳戶的密碼或要求帳戶的多重要素驗證 (MFA)，對這類型攻擊是無效的，因為這些是第三方應用程式，而且在組織外部。</span><span class="sxs-lookup"><span data-stu-id="89223-109">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span> <span data-ttu-id="89223-110">這些攻擊採用一種互動模型，這種模型會假正在呼叫資訊的實體是自動化，而不是人。</span><span class="sxs-lookup"><span data-stu-id="89223-110">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="89223-111">Office 365 中的非法同意授權攻擊的外觀如何？</span><span class="sxs-lookup"><span data-stu-id="89223-111">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="89223-112">您必須搜尋 Office 365 **稽核記錄**才能找到此攻擊的徵象，又名入侵標記 (IOC)。</span><span class="sxs-lookup"><span data-stu-id="89223-112">You need to search the Office 365 **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="89223-113">如果組織擁有許多 Azure 註冊應用程式和大量使用者，最佳做法就是每週檢閱您的組織同意授權。</span><span class="sxs-lookup"><span data-stu-id="89223-113">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>
### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="89223-114">尋找此攻擊徵象的步驟</span><span class="sxs-lookup"><span data-stu-id="89223-114">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="89223-115">在您的 Office 365 租用戶中開啟 [安全性與合規性中心]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89223-115">Open the **Security and Compliance Center** in your Office 365 tenant.</span></span>

2. <span data-ttu-id="89223-116">瀏覽至 [搜尋與調查]\*\*\*\* 節點，然後選取 [稽核記錄]\*\*\*\* 搜尋。</span><span class="sxs-lookup"><span data-stu-id="89223-116">Navigate to the **Search & investigation** node and select **audit log** search.</span></span>

3. <span data-ttu-id="89223-117">建立搜尋 (所有活動和所有使用者)，並篩選同意應用程式的結果，並新增 OAuth2PermissionGrant。</span><span class="sxs-lookup"><span data-stu-id="89223-117">Create a search (all activities and all users) and filter the results for Consent to application, and Add OAuth2PermissionGrant.</span></span>

4. <span data-ttu-id="89223-118">檢查擴充屬性，並檢查 IsAdminContent 是否設為 True。</span><span class="sxs-lookup"><span data-stu-id="89223-118">Examine the Extended Properties and check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
> <span data-ttu-id="89223-119">• 發生事件後，對應的稽核記錄項目最多可能需要 30 分鐘或 24 小時才會顯示在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="89223-119">It can take up to 30 minutes or up to 24 hours after an event occurs for the corresponding audit log entry to be displayed in the search results.</span></span> <br/><br/> <span data-ttu-id="89223-120">• 稽核記錄的保留時間及可在稽核記錄中搜尋的時間長度，取決於您的 Office 365 訂閱，具體來說，取決於指派給特定使用者的授權類型。</span><span class="sxs-lookup"><span data-stu-id="89223-120">The length of time that an audit record is retained (and searchable in the audit log) depends on your Office 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="89223-121">如需詳細資訊，請參閱[稽核記錄](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="89223-121">For more information, see [Export Mailbox Audit Logs](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
<span data-ttu-id="89223-122">如果這個值為 true，表示擁有全域系統管理員存取權的人員可能已獲得資料的廣泛存取權。</span><span class="sxs-lookup"><span data-stu-id="89223-122">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="89223-123">如果這是未預期的，請採取步驟以[確認攻擊](#how-to-confirm-an-attack)。</span><span class="sxs-lookup"><span data-stu-id="89223-123">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="89223-124">如何確認攻擊</span><span class="sxs-lookup"><span data-stu-id="89223-124">How to confirm an attack</span></span>

<span data-ttu-id="89223-125">如果您有上面所列的一或多個 IOC 執行個體，則必須進一步調查，以明確確認發生了攻擊。</span><span class="sxs-lookup"><span data-stu-id="89223-125">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="89223-126">您可以使用下列三種方法中的任何一種來確認攻擊。</span><span class="sxs-lookup"><span data-stu-id="89223-126">You can use any of these three methods to confirm the attack.</span></span>

- <span data-ttu-id="89223-127">使用 Azure Active Directory 入口網站來清查應用程式及其權限。</span><span class="sxs-lookup"><span data-stu-id="89223-127">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="89223-128">此方法很徹底，但是一次只能檢查一個使用者，如果要檢查的使用者很多，這會非常耗時。</span><span class="sxs-lookup"><span data-stu-id="89223-128">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="89223-129">使用 PowerShell 來清查應用程式及其權限。</span><span class="sxs-lookup"><span data-stu-id="89223-129">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="89223-130">這是最快也最徹底的方法，而且負擔最小。</span><span class="sxs-lookup"><span data-stu-id="89223-130">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="89223-131">讓您的使用者個別檢查其應用程式和授權，並將結果報告給系統管理員以進行修正。</span><span class="sxs-lookup"><span data-stu-id="89223-131">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="89223-132">使用您組織中的存取權來清查應用程式。</span><span class="sxs-lookup"><span data-stu-id="89223-132">Inventory apps with access in your organization</span></span>

<span data-ttu-id="89223-133">您可以使用 Azure Active Directory 入口網站或 PowerShell 來為您使用者執行此動作，或請您的使用者個別列舉其應用程式存取權。</span><span class="sxs-lookup"><span data-stu-id="89223-133">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="89223-134">使用 Azure Active Directory 入口網站的步驟</span><span class="sxs-lookup"><span data-stu-id="89223-134">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="89223-135">您可以使用 [Azure Active Directory 入口網站](https://portal.azure.com/)來查閱任何個人使用者已獲授權的應用程式。</span><span class="sxs-lookup"><span data-stu-id="89223-135">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="89223-136">使用系統管理權限登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="89223-136">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="89223-137">選取 [Azure Active Directory] 刀鋒視窗。</span><span class="sxs-lookup"><span data-stu-id="89223-137">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="89223-138">選取 [使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89223-138">Select **Users**.</span></span>

4. <span data-ttu-id="89223-139">選取您要檢閱的使用者。</span><span class="sxs-lookup"><span data-stu-id="89223-139">Select the user or resource that you want to delete.</span></span>

5. <span data-ttu-id="89223-140">選取 [應用程式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89223-140">Select **Applications**.</span></span>

<span data-ttu-id="89223-141">這會顯示指派給使用者的應用程式，以及應用程式所擁有的權限。</span><span class="sxs-lookup"><span data-stu-id="89223-141">This will show you the apps that are assigned to the user and what permissions the applcations have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="89223-142">請您的使用者列舉其應用程式存取權的步驟</span><span class="sxs-lookup"><span data-stu-id="89223-142">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="89223-143">請您的使用者前往 https://myapps.microsoft.com，並在那裡查看自己的應用程式存取權。</span><span class="sxs-lookup"><span data-stu-id="89223-143">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="89223-144">他們應該能夠查看具有存取權的所有應用程式、查看相關的詳細資料 (包括存取範圍)，並能夠撤銷可疑或非法應用程式的權限。</span><span class="sxs-lookup"><span data-stu-id="89223-144">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="89223-145">使用 PowerShell 執行此動作的步驟</span><span class="sxs-lookup"><span data-stu-id="89223-145">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="89223-146">驗證非法同意授權攻擊的最簡單方法是執行 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)，它會將您租用戶中所有使用者的所有 OAuth 同意授權與 OAuth 應用程式都傾印到一個 .csv 檔案中。</span><span class="sxs-lookup"><span data-stu-id="89223-146">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="89223-147">先決條件</span><span class="sxs-lookup"><span data-stu-id="89223-147">Prerequisites</span></span>

- <span data-ttu-id="89223-148">已安裝 Azure AD PowerShell 程式庫。</span><span class="sxs-lookup"><span data-stu-id="89223-148">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="89223-149">將執行指令碼的租用戶的全域系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="89223-149">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="89223-150">將執行指令碼的電腦上的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="89223-150">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89223-151">我們強烈建議您針對您的系統管理帳戶要求進行多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="89223-151">We highly recommend that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="89223-152">此指令碼支援 MFA 驗證。</span><span class="sxs-lookup"><span data-stu-id="89223-152">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="89223-153">使用本機系統管理員權限登入您將執行指令碼的電腦。</span><span class="sxs-lookup"><span data-stu-id="89223-153">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="89223-154">從 GitHub 下載或複製 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) 指令碼到您要在其中執行指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="89223-154">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the scruipt.</span></span> <span data-ttu-id="89223-155">此資料夾與寫入輸出「permissions.csv」檔案的資料夾是同一個。</span><span class="sxs-lookup"><span data-stu-id="89223-155">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="89223-156">以系統管理員身分開啟 PowerShell 執行個體，然後開啟您要儲存指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="89223-156">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="89223-157">使用 [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) Cmdlet 連線至您的目錄。</span><span class="sxs-lookup"><span data-stu-id="89223-157">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) cmdlet.</span></span>

5. <span data-ttu-id="89223-158">執行此 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="89223-158">Run this command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="89223-159">指令碼會產生一個名為「Permissions.csv」的檔案。</span><span class="sxs-lookup"><span data-stu-id="89223-159">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="89223-160">依照下列步驟尋找非法應用程式權限授權：</span><span class="sxs-lookup"><span data-stu-id="89223-160">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="89223-161">在 [ConsentType] 欄 (欄 G) 中，搜尋值「AllPrinciples」。</span><span class="sxs-lookup"><span data-stu-id="89223-161">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="89223-162">AllPrincipals 權限可允許用戶端應用程式存取租用戶內每個人的內容。</span><span class="sxs-lookup"><span data-stu-id="89223-162">The AllPrincipals permission allows the client application to access everyone’s content in the tenancy.</span></span> <span data-ttu-id="89223-163">原生的 Office 365 應用程式需要此權限才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="89223-163">Native Office 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="89223-164">必須仔細檢閱具有此權限的每一個非 Microsoft 應用程式。</span><span class="sxs-lookup"><span data-stu-id="89223-164">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="89223-165">在 [Permission] 欄 (欄 F) 中，檢閱每個委派的應用程式對內容所擁有的權限。</span><span class="sxs-lookup"><span data-stu-id="89223-165">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="89223-166">尋找「Read」和「Write」權限或「\*.All」權限，並仔細加以檢閱，因為它們可能不適當。</span><span class="sxs-lookup"><span data-stu-id="89223-166">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="89223-167">檢閱已獲同意授權的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="89223-167">Review the specific users that have consents granted.</span></span> <span data-ttu-id="89223-168">如果高設定檔或高度影響使用者擁有不適當的同意，您應進一步調查。</span><span class="sxs-lookup"><span data-stu-id="89223-168">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="89223-169">在 [ClientDisplayName] 欄 (欄 C) 中，尋找看起來可疑的應用程式。</span><span class="sxs-lookup"><span data-stu-id="89223-169">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="89223-170">應仔細檢查名稱拼錯、名稱超級簡單名稱或名稱像駭客的應用程式。</span><span class="sxs-lookup"><span data-stu-id="89223-170">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="89223-171">判斷攻擊的範圍</span><span class="sxs-lookup"><span data-stu-id="89223-171">Determine the scope of the attack</span></span>

<span data-ttu-id="89223-172">當您完成清查應用程式存取權之後，請檢閱 Office 365 **稽核記錄**，以判斷外洩的範圍。</span><span class="sxs-lookup"><span data-stu-id="89223-172">After you have finished inventorying application access, review the Office 365 **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="89223-173">搜尋受影響的使用者、非法應用程式有權存取您組織的時間範圍，以及應用程式擁有的權限。</span><span class="sxs-lookup"><span data-stu-id="89223-173">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="89223-174">您可以在 [Microsoft 365 安全性與合規性中心][](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 中搜尋**稽核記錄**。</span><span class="sxs-lookup"><span data-stu-id="89223-174">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89223-175">您必須在攻擊之前啟用 [信箱稽核][](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) 和 [系統管理員與使用者的活動稽核][](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)，才能獲得此訊息。</span><span class="sxs-lookup"><span data-stu-id="89223-175">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="89223-176">如何阻止及修復非法同意授權攻擊</span><span class="sxs-lookup"><span data-stu-id="89223-176">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="89223-177">當您識別出有非法權限的應用程式之後，有多種方式可移除該存取權。</span><span class="sxs-lookup"><span data-stu-id="89223-177">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="89223-178">您可以在 Azure Active Directory 入口網站中撤銷應用程式的權限，方法是：</span><span class="sxs-lookup"><span data-stu-id="89223-178">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="89223-179">在 [Azure Active Directory 使用者]\*\*\*\* 刀鋒視窗中瀏覽至受影響的使用者。</span><span class="sxs-lookup"><span data-stu-id="89223-179">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="89223-180">選取 [應用程式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89223-180">Select **Applications**.</span></span>

  - <span data-ttu-id="89223-181">選取非法應用程式。</span><span class="sxs-lookup"><span data-stu-id="89223-181">Select the illicit application.</span></span>

  - <span data-ttu-id="89223-182">按一下向下切入中的 [移除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89223-182">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="89223-183">您可以依照[移除-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0) 中的步驟，使用 PowerShell 撤銷 QAuth 同意授權。</span><span class="sxs-lookup"><span data-stu-id="89223-183">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0).</span></span>

- <span data-ttu-id="89223-184">您可以依照[移除-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0) 中的步驟，使用 PowerShell 撤銷服務應用程式角色指派。</span><span class="sxs-lookup"><span data-stu-id="89223-184">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0).</span></span>

- <span data-ttu-id="89223-185">您也可以完全停用受影響帳戶的登入，這將會進一步停用該帳戶中應用程式對資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="89223-185">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="89223-186">當然，這對使用者的生產力並不理想，但是如果您正努力快速限制影響，這會是可行的短期補救。</span><span class="sxs-lookup"><span data-stu-id="89223-186">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="89223-187">您可以關閉租用戶的整合式應用程式。</span><span class="sxs-lookup"><span data-stu-id="89223-187">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="89223-188">這是一項重大步驟，會在整個租用戶範圍中停用使用者授權同意的能力。</span><span class="sxs-lookup"><span data-stu-id="89223-188">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="89223-189">這可防止您的使用者不小心授權存取惡意應用程式。</span><span class="sxs-lookup"><span data-stu-id="89223-189">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="89223-190">我們不建議您這麼做，因為這會嚴重影響使用者使用使用協力廠商應用程式的生產力。</span><span class="sxs-lookup"><span data-stu-id="89223-190">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="89223-191">若要這麼做，可以依照[開啟或關閉整合式應用程式](https://docs.microsoft.com/office365/admin/misc/integrated-apps)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="89223-191">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/office365/admin/misc/integrated-apps).</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="89223-192">像網路安全專業人員一般保護 Office 365</span><span class="sxs-lookup"><span data-stu-id="89223-192">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="89223-193">您的 Office 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="89223-193">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="89223-194">使用 [Office 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Office 365 租用戶的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="89223-194">Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="89223-195">要在前 30 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="89223-195">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="89223-196">這些工作會有立即的影響，而且對您的使用者影響較低。</span><span class="sxs-lookup"><span data-stu-id="89223-196">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="89223-197">要在 90 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="89223-197">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="89223-198">這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="89223-198">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="89223-199">90 天之後。</span><span class="sxs-lookup"><span data-stu-id="89223-199">Beyond 90 days.</span></span> <span data-ttu-id="89223-200">這些增強功能會在您的前 90 天工作內建置。</span><span class="sxs-lookup"><span data-stu-id="89223-200">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="89223-201">另請參閱：</span><span class="sxs-lookup"><span data-stu-id="89223-201">See also:</span></span>

- <span data-ttu-id="89223-202">[我的應用程式清單中有未預期的應用程式](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)，在系統管理員知道有未預期應用程式具有資料存取權之後，此文章可引導系統管理員完成可能需要採取的不同動作。</span><span class="sxs-lookup"><span data-stu-id="89223-202">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="89223-203">[整合應用程式與 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) 是同意與權限的高階概觀。</span><span class="sxs-lookup"><span data-stu-id="89223-203">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="89223-204">[開發我的應用程式時發生問題](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)提供各種同意相關文章的連結。</span><span class="sxs-lookup"><span data-stu-id="89223-204">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="89223-205">[Azure Active Directory (Azure AD) 中的應用程式按服務主體物件](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)提供應用程式模型核心的應用程式和服務主體物件的概觀。</span><span class="sxs-lookup"><span data-stu-id="89223-205">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="89223-206">[管理應用程式的存取權](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)概述系統管理員用來管理使用者對應用程式的存取權的功能。</span><span class="sxs-lookup"><span data-stu-id="89223-206">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
