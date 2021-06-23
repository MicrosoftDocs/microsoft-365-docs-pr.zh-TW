---
title: 偵測並修正違法的同意授與
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 瞭解如何辨識和修正非法同意授與 Microsoft 365 中的攻擊。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb3ccfbb921c106b671c4409bb95bd200f0efb55
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083005"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="6d3fc-103">偵測並修正違法的同意授與</span><span class="sxs-lookup"><span data-stu-id="6d3fc-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6d3fc-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="6d3fc-104">**Applies to**</span></span>
- [<span data-ttu-id="6d3fc-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="6d3fc-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6d3fc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d3fc-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6d3fc-107">**摘要** 瞭解如何辨識和修正非法同意授與 Microsoft 365 中的攻擊。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Microsoft 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-microsoft-365"></a><span data-ttu-id="6d3fc-108">非法的同意授與 Microsoft 365 中的攻擊是什麼？</span><span class="sxs-lookup"><span data-stu-id="6d3fc-108">What is the illicit consent grant attack in Microsoft 365?</span></span>

<span data-ttu-id="6d3fc-109">在非法同意授權攻擊中，攻擊者會建立已註冊 Azure 的應用程式，要求存取連絡人資訊、電子郵件或文件等資料。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="6d3fc-110">然後，攻擊者誘騙使用者授權該應用程式同意透過網路釣魚攻擊，或透過插入非法程式碼到信任的網站，來存取其資料。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="6d3fc-111">在非法應用程式獲得授權之後，就擁有資料的帳戶層級存取權，而不需要組織帳戶。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="6d3fc-112">一般補救步驟，例如重設遭入侵帳戶的密碼或要求帳戶的多重要素驗證 (MFA)，對這類型攻擊是無效的，因為這些是第三方應用程式，而且在組織外部。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="6d3fc-113">這些攻擊採用一種互動模型，這種模型會假正在呼叫資訊的實體是自動化，而不是人。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d3fc-114">您是否懷疑遇到違法的同意問題-從應用程式授與的許可權？</span><span class="sxs-lookup"><span data-stu-id="6d3fc-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="6d3fc-115">Microsoft Cloud App Security (MCAS) 具有偵測、調查和修正 OAuth 應用程式的工具。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="6d3fc-116">此 MCAS 文章包含的教學課程，說明如何 [調查 OAuth 應用程式的風險](/cloud-app-security/investigate-risky-oauth)。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="6d3fc-117">您也可以設定 [OAuth 的應用程式原則](/cloud-app-security/app-permission-policy) ，以調查應用程式要求的許可權，這些許可權是使用者授權這些應用程式，並廣泛核准或禁止這些許可權要求。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-117">You can also set [OAuth app policies](/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-microsoft-365"></a><span data-ttu-id="6d3fc-118">非法同意授與 Microsoft 365 的攻擊外觀。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-118">What does an illicit consent grant attack look like in Microsoft 365?</span></span>

<span data-ttu-id="6d3fc-119">您必須搜尋「 **審計記錄** 檔」，以尋找此攻擊的簽署，也稱為折衷 (IOC) 。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="6d3fc-120">如果組織擁有許多 Azure 註冊應用程式和大量使用者，最佳做法就是每週檢閱您的組織同意授權。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="6d3fc-121">尋找此攻擊徵象的步驟</span><span class="sxs-lookup"><span data-stu-id="6d3fc-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="6d3fc-122">在中開啟 **Microsoft 365 Defender 入口網站** <https://security.microsoft.com> ，然後選取 [**審計**]。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-122">Open the **Microsoft 365 Defender portal** at <https://security.microsoft.com> and then select **Audit**.</span></span> <span data-ttu-id="6d3fc-123">或者，若要直接移至 [ **審計** ] 頁面，請使用 <https://security.microsoft.com/auditlogsearch> 。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-123">Or, to go directly to the **Audit** page, use <https://security.microsoft.com/auditlogsearch>.</span></span>

2. <span data-ttu-id="6d3fc-124">在 [ **審計** ] 頁面上，確認已選取 [ **搜尋] 索引** 標籤，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="6d3fc-124">On the **Audit** page, verify that the **Search** tab is selected, and then configure the following settings:</span></span>
   - <span data-ttu-id="6d3fc-125">**日期和時間範圍**</span><span class="sxs-lookup"><span data-stu-id="6d3fc-125">**Date and time range**</span></span>
   - <span data-ttu-id="6d3fc-126">**活動**：確認已選取 [ **顯示所有活動的結果** ]。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-126">**Activities**: Verify that **Show results for all activities** is selected.</span></span>

   <span data-ttu-id="6d3fc-127">完成後，請按一下 [ **搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-127">When you're finished, click **Search**.</span></span>

3. <span data-ttu-id="6d3fc-128">按一下 [ **活動** ] 欄，排序結果，並尋找 **同意應用程式**。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-128">Click the **Activity** column to sort the results and look for **Consent to application**.</span></span>

4. <span data-ttu-id="6d3fc-129">從清單中選取一個專案，以查看活動的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-129">Select an entry from the list to see the details of the activity.</span></span> <span data-ttu-id="6d3fc-130">請檢查 IsAdminContent 是否設定為 True。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-130">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="6d3fc-131">在發生事件後，可在搜尋結果中顯示對應的審計記錄專案，最多可花30分鐘到24小時的時間。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-131">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="6d3fc-132">在審核記錄中保留及可搜尋的審計記錄的時間長度取決於您的 Microsoft 365 訂閱，並特別是指派給特定使用者的授權類型。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-132">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="6d3fc-133">如需詳細資訊，請參閱[稽核記錄](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-133">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="6d3fc-134">如果這個值為 true，表示擁有全域系統管理員存取權的人員可能已獲得資料的廣泛存取權。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-134">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="6d3fc-135">如果這是未預期的，請採取步驟以[確認攻擊](#how-to-confirm-an-attack)。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-135">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="6d3fc-136">如何確認攻擊</span><span class="sxs-lookup"><span data-stu-id="6d3fc-136">How to confirm an attack</span></span>

<span data-ttu-id="6d3fc-137">如果您有上面所列的一或多個 IOC 執行個體，則必須進一步調查，以明確確認發生了攻擊。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-137">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="6d3fc-138">您可以使用下列三種方法中的任何一種來確認攻擊：</span><span class="sxs-lookup"><span data-stu-id="6d3fc-138">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="6d3fc-139">使用 Azure Active Directory 入口網站來清查應用程式及其權限。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-139">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="6d3fc-140">此方法很徹底，但是一次只能檢查一個使用者，如果要檢查的使用者很多，這會非常耗時。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-140">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>
- <span data-ttu-id="6d3fc-141">使用 PowerShell 來清查應用程式及其權限。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-141">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="6d3fc-142">這是最快也最徹底的方法，而且負擔最小。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-142">This is the fastest and most thorough method, with the least amount of overhead.</span></span>
- <span data-ttu-id="6d3fc-143">讓您的使用者個別檢查其應用程式和授權，並將結果報告給系統管理員以進行修正。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-143">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="6d3fc-144">使用您組織中的存取權來清查應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-144">Inventory apps with access in your organization</span></span>

<span data-ttu-id="6d3fc-145">您可以使用 Azure Active Directory 入口網站或 PowerShell 來為您使用者執行此動作，或請您的使用者個別列舉其應用程式存取權。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-145">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="6d3fc-146">使用 Azure Active Directory 入口網站的步驟</span><span class="sxs-lookup"><span data-stu-id="6d3fc-146">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="6d3fc-147">您可以使用 Azure Active Directory 入口網站，查看任何個別使用者已授與許可權的應用程式 <https://portal.azure.com> 。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-147">You can look up the applications to which any individual user has granted permissions by using the Azure Active Directory Portal at <https://portal.azure.com>.</span></span>

1. <span data-ttu-id="6d3fc-148">使用系統管理許可權登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-148">Sign in to the Azure portal with administrative rights.</span></span>
2. <span data-ttu-id="6d3fc-149">選取 [Azure Active Directory] 刀鋒視窗。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-149">Select the Azure Active Directory blade.</span></span>
3. <span data-ttu-id="6d3fc-150">選取 [使用者]。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-150">Select **Users**.</span></span>
4. <span data-ttu-id="6d3fc-151">選取您要檢閱的使用者。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-151">Select the user that you want to review.</span></span>
5. <span data-ttu-id="6d3fc-152">選取 [應用程式]。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-152">Select **Applications**.</span></span>

<span data-ttu-id="6d3fc-153">這會顯示指派給使用者的應用程式，以及應用程式的許可權。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-153">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="6d3fc-154">請您的使用者列舉其應用程式存取權的步驟</span><span class="sxs-lookup"><span data-stu-id="6d3fc-154">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="6d3fc-155">請您的使用者前往 <https://myapps.microsoft.com>，並在那裡查看自己的應用程式存取權。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-155">Have your users go to <https://myapps.microsoft.com> and review their own application access there.</span></span> <span data-ttu-id="6d3fc-156">他們應該能夠查看具有存取權的所有應用程式、查看相關的詳細資料 (包括存取範圍)，並能夠撤銷可疑或非法應用程式的權限。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-156">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="6d3fc-157">使用 PowerShell 執行此動作的步驟</span><span class="sxs-lookup"><span data-stu-id="6d3fc-157">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="6d3fc-158">驗證非法同意授權攻擊的最簡單方法是執行 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)，它會將您租用戶中所有使用者的所有 OAuth 同意授權與 OAuth 應用程式都傾印到一個 .csv 檔案中。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-158">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="6d3fc-159">先決條件</span><span class="sxs-lookup"><span data-stu-id="6d3fc-159">Pre-requisites</span></span>

- <span data-ttu-id="6d3fc-160">已安裝 Azure AD PowerShell 程式庫。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-160">The Azure AD PowerShell library installed.</span></span>
- <span data-ttu-id="6d3fc-161">將執行指令碼的租用戶的全域系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-161">Global administrator rights on the tenant that the script will be run against.</span></span>
- <span data-ttu-id="6d3fc-162">將執行指令碼的電腦上的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-162">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d3fc-163">***強烈建議*** 您在您的管理帳戶上需要多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-163">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="6d3fc-164">此指令碼支援 MFA 驗證。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-164">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="6d3fc-165">使用本機系統管理員權限登入您將執行指令碼的電腦。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-165">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="6d3fc-166">將[Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)腳本從 GitHub 下載或複製到您要執行腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-166">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="6d3fc-167">此資料夾與寫入輸出「permissions.csv」檔案的資料夾是同一個。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-167">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="6d3fc-168">以系統管理員身分開啟 PowerShell 會話，並開啟您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-168">Open a PowerShell session as an administrator and open to the folder where you saved the script to.</span></span>

4. <span data-ttu-id="6d3fc-169">使用 [Connect-AzureAD](/powershell/module/azuread/connect-azuread) Cmdlet 連線至您的目錄。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-169">Connect to your directory using the [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="6d3fc-170">執行此 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="6d3fc-170">Run this PowerShell command:</span></span>

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="6d3fc-171">指令碼會產生一個名為「Permissions.csv」的檔案。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-171">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="6d3fc-172">依照下列步驟尋找非法應用程式權限授權：</span><span class="sxs-lookup"><span data-stu-id="6d3fc-172">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="6d3fc-173">在 [ConsentType] 欄 (欄 G) 中，搜尋值「AllPrinciples」。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-173">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="6d3fc-174">AllPrincipals 許可權可讓用戶端應用程式存取租使用者的所有人內容。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-174">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="6d3fc-175">原生 Microsoft 365 應用程式需要此許可權才能正確運作。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-175">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="6d3fc-176">必須仔細檢閱具有此權限的每一個非 Microsoft 應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-176">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="6d3fc-177">在 [Permission] 欄 (欄 F) 中，檢閱每個委派的應用程式對內容所擁有的權限。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-177">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="6d3fc-178">尋找「Read」和「Write」權限或「\*.All」權限，並仔細加以檢閱，因為它們可能不適當。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-178">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="6d3fc-179">檢閱已獲同意授權的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-179">Review the specific users that have consents granted.</span></span> <span data-ttu-id="6d3fc-180">如果高設定檔或高度影響使用者擁有不適當的同意，您應進一步調查。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-180">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="6d3fc-181">在 [ClientDisplayName] 欄 (欄 C) 中，尋找看起來可疑的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-181">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="6d3fc-182">應仔細檢查名稱拼錯、名稱超級簡單名稱或名稱像駭客的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-182">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="6d3fc-183">判斷攻擊的範圍</span><span class="sxs-lookup"><span data-stu-id="6d3fc-183">Determine the scope of the attack</span></span>

<span data-ttu-id="6d3fc-184">當您完成清查應用程式存取之後，請複查 **審核記錄** 以判斷破壞的完整範圍。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-184">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="6d3fc-185">搜尋受影響的使用者、非法應用程式有權存取您組織的時間範圍，以及應用程式擁有的權限。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-185">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="6d3fc-186">您可以在 [Microsoft 365 Defender 入口網站](../../compliance/search-the-audit-log-in-security-and-compliance.md)中搜尋 **審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-186">You can search the **audit log** in the [Microsoft 365 Defender portal](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d3fc-187">您必須在攻擊之前啟用 [信箱稽核][](../../compliance/enable-mailbox-auditing.md) 和 [系統管理員與使用者的活動稽核][](../../compliance/turn-audit-log-search-on-or-off.md)，才能獲得此訊息。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-187">[Mailbox auditing](../../compliance/enable-mailbox-auditing.md) and [Activity auditing for admins and users](../../compliance/turn-audit-log-search-on-or-off.md) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="6d3fc-188">如何阻止及修復非法同意授權攻擊</span><span class="sxs-lookup"><span data-stu-id="6d3fc-188">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="6d3fc-189">當您識別出有非法權限的應用程式之後，有多種方式可移除該存取權。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-189">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="6d3fc-190">您可以在 Azure Active Directory 入口網站中撤銷應用程式的權限，方法是：</span><span class="sxs-lookup"><span data-stu-id="6d3fc-190">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>
  1. <span data-ttu-id="6d3fc-191">在 [Azure Active Directory 使用者] 刀鋒視窗中瀏覽至受影響的使用者。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-191">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>
  2. <span data-ttu-id="6d3fc-192">選取 [應用程式]。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-192">Select **Applications**.</span></span>
  3. <span data-ttu-id="6d3fc-193">選取非法應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-193">Select the illicit application.</span></span>
  4. <span data-ttu-id="6d3fc-194">按一下向下切入中的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-194">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="6d3fc-195">您可以依照[移除-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant) 中的步驟，使用 PowerShell 撤銷 QAuth 同意授權。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-195">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="6d3fc-196">您可以依照[移除-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment) 中的步驟，使用 PowerShell 撤銷服務應用程式角色指派。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-196">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="6d3fc-197">您也可以完全停用受影響帳戶的登入，這將會進一步停用該帳戶中應用程式對資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-197">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="6d3fc-198">當然，這對使用者的生產力並不理想，但是如果您正努力快速限制影響，這會是可行的短期補救。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-198">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="6d3fc-199">您可以關閉租用戶的整合式應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-199">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="6d3fc-200">這是一項重大步驟，會在整個租用戶範圍中停用使用者授權同意的能力。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-200">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="6d3fc-201">這可防止您的使用者不小心授權存取惡意應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-201">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="6d3fc-202">我們不建議您這麼做，因為這會嚴重影響使用者使用使用協力廠商應用程式的生產力。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-202">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="6d3fc-203">若要這麼做，可以依照[開啟或關閉整合式應用程式](../../admin/misc/user-consent.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-203">You can do this by following the steps in [Turning Integrated Apps on or off](../../admin/misc/user-consent.md).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="6d3fc-204">像網路安全專業人員一般保護 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d3fc-204">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="6d3fc-205">您的 Microsoft 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-205">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="6d3fc-206">使用 [Microsoft 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Microsoft 365 租用戶的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-206">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="6d3fc-207">要在前 30 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-207">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="6d3fc-208">這些工作會有立即的影響，而且對您的使用者影響較低。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-208">These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="6d3fc-p124">工作要 90 天後完成。這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-p124">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>
- <span data-ttu-id="6d3fc-p125">超過 90 天。這些增強功能會在您的前 90 天工作內建置。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-p125">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d3fc-213">請參閱</span><span class="sxs-lookup"><span data-stu-id="6d3fc-213">See also</span></span>

- <span data-ttu-id="6d3fc-214">[我的應用程式清單中有未預期的應用程式](/azure/active-directory/application-access-unexpected-application)，在系統管理員知道有未預期應用程式具有資料存取權之後，此文章可引導系統管理員完成可能需要採取的不同動作。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-214">[Unexpected application in my applications list](/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>
- <span data-ttu-id="6d3fc-215">[整合應用程式與 Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) 是同意與權限的高階概觀。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-215">[Integrating applications with Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>
- <span data-ttu-id="6d3fc-216">[開發我的應用程式時發生問題](/azure/active-directory/active-directory-application-dev-development-content-map)提供各種同意相關文章的連結。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-216">[Problems developing my application](/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>
- <span data-ttu-id="6d3fc-217">[Azure Active Directory (Azure AD) 中的應用程式按服務主體物件](/azure/active-directory/develop/active-directory-application-objects)提供應用程式模型核心的應用程式和服務主體物件的概觀。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-217">[Application and service principal objects in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>
- <span data-ttu-id="6d3fc-218">[管理應用程式的存取權](/azure/active-directory/active-directory-managing-access-to-apps)概述系統管理員用來管理使用者對應用程式的存取權的功能。</span><span class="sxs-lookup"><span data-stu-id="6d3fc-218">[Manage access to apps](/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
