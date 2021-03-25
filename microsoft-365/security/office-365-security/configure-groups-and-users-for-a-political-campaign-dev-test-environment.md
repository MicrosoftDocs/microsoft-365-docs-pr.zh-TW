---
title: 設定群組和使用者 - 政治活動開發/測試環境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 摘要：為政治活動開發/測試環境建立具備使用者與群組的 Office 365 和 Enterprise Mobility + Security (EMS) 之試用訂閱。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2e21cdfb0aabbdb10397d6d16c879756449a498e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203421"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="8bcee-103">設定政治活動開發/測試環境的群組和使用者</span><span class="sxs-lookup"><span data-stu-id="8bcee-103">Configure groups and users for a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8bcee-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="8bcee-104">**Applies to**</span></span>
- [<span data-ttu-id="8bcee-105">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="8bcee-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="8bcee-106">**摘要：** 為政治活動開發/測試環境建立具備使用者與群組的 Office 365 和 Enterprise Mobility + Security (EMS) 之試用訂閱。</span><span class="sxs-lookup"><span data-stu-id="8bcee-106">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="8bcee-107">使用本文中的指示來建立開發/測試環境，其中包括簡化使用者帳戶和群組，其適用於 [ Microsoft 安全性指導方針的政治活動、非營利組織，以及其他靈活組織](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)解決方法。</span><span class="sxs-lookup"><span data-stu-id="8bcee-107">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="8bcee-108">階段 1：建立 Office 365 開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="8bcee-108">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="8bcee-109">在這個階段中，您會為代表政治活動的虛構組織取得 Office 365 E5 與 Enterprise Mobility + Security (EMS) E5 試用訂閱。</span><span class="sxs-lookup"><span data-stu-id="8bcee-109">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="8bcee-110">首先，請依照[輕量型基本組態](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)中「第 2 階段」的指示進行。</span><span class="sxs-lookup"><span data-stu-id="8bcee-110">First, follow the instructions in **Phase 2** of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="8bcee-111">接著，註冊 EMS E5 試用訂閱，並將它新增至與試用訂閱相同的組織。</span><span class="sxs-lookup"><span data-stu-id="8bcee-111">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="8bcee-112">如果需要，請使用試用訂閱的全域管理員帳戶認證登入系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="8bcee-112">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="8bcee-113">如需說明，請參閱[在何處登入](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="8bcee-113">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="8bcee-114">按一下 [管理] 磚。</span><span class="sxs-lookup"><span data-stu-id="8bcee-114">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="8bcee-115">在瀏覽器的 [Microsoft 365 系統管理中心] 索引標籤上，按一下左導覽中的 [計費] > [購買服務]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-115">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="8bcee-p102">在 [購買服務] 頁面上，尋找 **Enterprise Mobility + Security E5** 項目。將滑鼠指標停留在上面，並且按一下 [開始免費試用]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-p102">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="8bcee-118">在 [確認訂單] 頁面上，按一下 [立即試用]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-118">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="8bcee-119">在 [訂單收據] 頁面上，按一下 [繼續]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-119">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="8bcee-120">接下來，啟用全域管理員帳戶的 EMS E5 授權。</span><span class="sxs-lookup"><span data-stu-id="8bcee-120">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="8bcee-121">在瀏覽器的 [Microsoft 365 系統管理中心] 索引標籤上，按一下左導覽中的 [使用者] > [作用中使用者]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-121">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="8bcee-122">按一下您的全域系統管理員帳戶，然後按一下 [產品授權] 的 [編輯]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-122">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="8bcee-123">在 [產品授權] 窗格中，將 Enterprise Mobility + Security E5 的產品授權設為 [開啟]\*\*，按一下 [儲存]，然後按兩次 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-123">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="8bcee-124">階段 2：建立和設定 Azure Active Directory (AD) 群組</span><span class="sxs-lookup"><span data-stu-id="8bcee-124">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="8bcee-125">在這個階段中，您會為活動建立和設定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8bcee-125">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="8bcee-126">首先，利用 Azure 入口網站建立一組典型政治活動的群組。</span><span class="sxs-lookup"><span data-stu-id="8bcee-126">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="8bcee-127">在瀏覽器的個別索引標籤中，移至 Azure 入口網站 (網址為 <https://portal.azure.com>)。</span><span class="sxs-lookup"><span data-stu-id="8bcee-127">On a separate tab in your browser, go to the Azure portal at <https://portal.azure.com>.</span></span> <span data-ttu-id="8bcee-128">如果需要，請使用 Office 365 E5 試用訂閱的全域管理員帳戶認證登入。</span><span class="sxs-lookup"><span data-stu-id="8bcee-128">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="8bcee-129">在 Azure 入口網站中，按一下 [Azure Active Directory] > [使用者和群組] > [所有群組]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-129">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="8bcee-130">針對此清單中的每個群組名稱執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8bcee-130">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="8bcee-131">資深和策略人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-131">Senior and strategic staff</span></span>

   - <span data-ttu-id="8bcee-132">IT 人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-132">IT staff</span></span>

   - <span data-ttu-id="8bcee-133">分析人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-133">Analytics staff</span></span>

   - <span data-ttu-id="8bcee-134">一般的核心人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-134">Regular core staff</span></span>

   - <span data-ttu-id="8bcee-135">作業人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-135">Operations staff</span></span>

   - <span data-ttu-id="8bcee-136">現場人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-136">Field staff</span></span>

1. <span data-ttu-id="8bcee-137">在 [所有群組] 刀鋒視窗中，按一下 [+ 新增群組]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-137">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="8bcee-138">從 **名稱** 中的清單輸入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="8bcee-138">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="8bcee-139">選取在 [成員資格] 中的 [動態使用者]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-139">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="8bcee-140">對 [啟用 Office 功能] 按一下 [是]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-140">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="8bcee-141">按一下 [新增動態查詢]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-141">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="8bcee-142">在 [新增使用者位置]，請選取 [部門]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-142">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="8bcee-143">在下一個欄位中，選取 [等於]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-143">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="8bcee-144">從下一個欄位中，從該清單中輸入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="8bcee-144">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="8bcee-145">按一下 [新增查詢]，然後按一下 [建立]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-145">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="8bcee-146">按一下 [使用者和群組 - 所有群組]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-146">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="8bcee-147">接下來，設定群組，以讓系統自動為成員指派 Office 365 E5 和 EMS E5 授權。</span><span class="sxs-lookup"><span data-stu-id="8bcee-147">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="8bcee-148">在 Azure 入口網站中，按一下 [Azure Active Directory] > [授權] > [所有產品]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-148">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="8bcee-149">在清單中，選取 [Enterprise Mobility + Security E5] 和 [Office 365 企業版 E5]，然後按一下 [+ 指派]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-149">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="8bcee-150">在 [指派授權] 刀鋒視窗中，按一下 [使用者和群組]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-150">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="8bcee-151">在群組清單中，選取下列項目：</span><span class="sxs-lookup"><span data-stu-id="8bcee-151">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="8bcee-152">分析人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-152">Analytics staff</span></span>

   - <span data-ttu-id="8bcee-153">現場人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-153">Field staff</span></span>

   - <span data-ttu-id="8bcee-154">IT 人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-154">IT staff</span></span>

   - <span data-ttu-id="8bcee-155">作業人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-155">Operations staff</span></span>

   - <span data-ttu-id="8bcee-156">一般的核心人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-156">Regular core staff</span></span>

   - <span data-ttu-id="8bcee-157">資深和策略人員</span><span class="sxs-lookup"><span data-stu-id="8bcee-157">Senior and strategic staff</span></span>

5. <span data-ttu-id="8bcee-158">按一下 [選取]，然後按一下 [指派]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-158">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="8bcee-159">關閉瀏覽器的 Azure 入口網站索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8bcee-159">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="8bcee-160">階段 3：新增使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="8bcee-160">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="8bcee-161">在這個階段，您可以為政治活動新增範例使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8bcee-161">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="8bcee-162">首先，[與 Azure Active Directory PowerShell for Graph 模組連線](../../enterprise/connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="8bcee-162">First, you [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="8bcee-163">接下來，填寫您的組織名稱、位置及常見的密碼，並從 PowerShell 命令提示字元或整合式指令碼環境 (ISE) 執行這些命令：</span><span class="sxs-lookup"><span data-stu-id="8bcee-163">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> <span data-ttu-id="8bcee-p104">此處常見密碼的使用是為自動化開發/測試環境且讓您方便進行設定而提供。建議您不要將此類密碼用於產品訂閱。當您使用這些新使用者帳戶登入時，系統會提示您變更密碼。</span><span class="sxs-lookup"><span data-stu-id="8bcee-p104">The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="8bcee-167">使用這些步驟來確認動態群組成員資格和以群組為基礎之授權是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="8bcee-167">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="8bcee-168">從瀏覽器的 [Microsoft Office 的首頁] 索引標籤中，按一下 [管理] 磚。</span><span class="sxs-lookup"><span data-stu-id="8bcee-168">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="8bcee-169">從瀏覽器的新 [Microsoft 365 系統管理中心] 索引標籤中，按一下 [使用者]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-169">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="8bcee-170">在使用者清單中，按一下 [應徵者]。</span><span class="sxs-lookup"><span data-stu-id="8bcee-170">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="8bcee-171">在列出 [應徵者] 使用者帳戶之內容的窗格中，請確認：</span><span class="sxs-lookup"><span data-stu-id="8bcee-171">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="8bcee-172">它屬於 **資深和策略的人員** 群組 (在 **群組成員資格**)。</span><span class="sxs-lookup"><span data-stu-id="8bcee-172">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="8bcee-173">他獲派 **Enterprise Mobility + Security E5** 與 **Office 365 企業版 E5** 授權 (在 **產品授權** 中)。</span><span class="sxs-lookup"><span data-stu-id="8bcee-173">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="8bcee-174">關閉 [應徵者] 使用者帳戶窗格。</span><span class="sxs-lookup"><span data-stu-id="8bcee-174">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="8bcee-175">記錄值，以便日後參考</span><span class="sxs-lookup"><span data-stu-id="8bcee-175">Record values for future reference</span></span>

<span data-ttu-id="8bcee-176">記錄這些值以與 Office 365 和 EMS 試用訂閱在此開發/測試環境中搭配使用：</span><span class="sxs-lookup"><span data-stu-id="8bcee-176">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="8bcee-177">您的試用訂閱組織名稱：</span><span class="sxs-lookup"><span data-stu-id="8bcee-177">Your trial subscription organization name:</span></span> ![底線](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="8bcee-179">例如，針對 contoso.onmicrosoft.com 的試用訂閱網域名稱，組織名稱為「contoso」。</span><span class="sxs-lookup"><span data-stu-id="8bcee-179">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="8bcee-180">全域系統管理員名稱：</span><span class="sxs-lookup"><span data-stu-id="8bcee-180">The global administrator name:</span></span> ![底線](../../media/Common-Images/TableLine.png)<span data-ttu-id="8bcee-182">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8bcee-182">.onmicrosoft.com</span></span>

  <span data-ttu-id="8bcee-183">在安全位置記錄此帳戶的密碼以及其他使用者帳戶的常見初始密碼。</span><span class="sxs-lookup"><span data-stu-id="8bcee-183">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="8bcee-184">下一步</span><span class="sxs-lookup"><span data-stu-id="8bcee-184">Next step</span></span>

<span data-ttu-id="8bcee-185">透過[在政治活動開發/測試環境中建立小組網站](create-team-sites-in-a-political-campaign-dev-test-environment.md)，在此開發/測試環境中建置四種不同類型的 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="8bcee-185">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8bcee-186">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8bcee-186">See also</span></span>

[<span data-ttu-id="8bcee-187">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="8bcee-187">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="8bcee-188">在政治活動開發/測試環境中建立小組網站</span><span class="sxs-lookup"><span data-stu-id="8bcee-188">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="8bcee-189">雲端採用測試實驗室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="8bcee-189">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="8bcee-190">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="8bcee-190">Cloud adoption and hybrid solutions</span></span>](/office365/enterprise/cloud-adoption-and-hybrid-solutions)