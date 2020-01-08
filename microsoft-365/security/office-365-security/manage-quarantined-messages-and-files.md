---
title: 以 Office 365 系統管理員身分管理隔離的郵件和檔案
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 09/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: '身為系統管理員，您可以檢視、 釋出，並報告誤判隔離的郵件在 Office 365 中。 您可以設定原則，讓 Office 365 篩選郵件，並傳送至隔離區幾個原因： 因為被判定是垃圾郵件、 大量、 網路釣魚、 惡意程式碼，或因為它們符合郵件流程規則。 '
ms.openlocfilehash: 615d88f63f738ca443b9ff377bb08fdaa97fe2dc
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40970931"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a><span data-ttu-id="aea72-104">以 Office 365 系統管理員身分管理隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="aea72-104">Manage quarantined messages and files as an administrator in Office 365</span></span>

<span data-ttu-id="aea72-105">身為系統管理員，您可以檢視、 釋出，並刪除隔離的郵件，並報告誤判隔離的郵件在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="aea72-105">As an admin, you can view, release, and delete quarantined messages, and report false positive quarantined messages in Office 365.</span></span> <span data-ttu-id="aea72-106">您也可以檢視、 下載及刪除隔離擷取藉由進階威脅防護 (ATP) 的 SharePoint Online、 OneDrive for Business 和 Microsoft Teams 的檔案。</span><span class="sxs-lookup"><span data-stu-id="aea72-106">You can also view, download, and delete quarantined files captured by Advance Threat Protection (ATP) for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="aea72-107">您可以設定原則，讓 Office 365 篩選郵件，並傳送至隔離區幾個原因： 因為被判定為垃圾郵件、 大量郵件、 網路釣魚郵件、 包含惡意程式碼，或因為它們符合郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="aea72-107">You can set up policies so that Office 365 filters messages and sends them to quarantine for several reasons: Because they were identified as spam, bulk mail, phishing mail, containing malware, or because they matched a mail flow rule.</span></span>

<span data-ttu-id="aea72-108">根據預設，Office 365 會直接將網路釣魚郵件和包含惡意程式碼的郵件傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="aea72-108">By default, Office 365 sends phishing messages and messages containing malware directly to quarantine.</span></span> <span data-ttu-id="aea72-109">其他已篩選的郵件會傳送至使用者的垃圾郵件] 資料夾中，除非您要傳送至隔離區設定的原則。</span><span class="sxs-lookup"><span data-stu-id="aea72-109">Other filtered messages are sent to users' Junk Email folder unless you set up a policy to send them to quarantine.</span></span>

<span data-ttu-id="aea72-110">您必須在 Office 365 全域系統管理員 (GA) 的權限或屬於一或多個安全性 & 合規性中心角色群組，才能使用被隔離的郵件或隔離的檔案。</span><span class="sxs-lookup"><span data-stu-id="aea72-110">You must have global administrator (GA) permissions in Office 365, or be a member of one or more Security & Compliance Center role groups, to work with quarantined messages or quarantined files.</span></span> <span data-ttu-id="aea72-111">如需詳細資訊，請參閱[Office 365 安全性 & 合規性中心的權限](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="aea72-111">See [Permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center) for more information.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aea72-112">根據預設，垃圾郵件、 大量和網路釣魚郵件會隔離區中保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="aea72-112">By default, spam, bulk and phishing messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="aea72-113">因為它們符合郵件流程規則遭到隔離的郵件會保留在隔離區 7 天。</span><span class="sxs-lookup"><span data-stu-id="aea72-113">Messages that are quarantined because they matched a mail flow rule are kept in quarantine for 7 days.</span></span> <span data-ttu-id="aea72-114">惡意程式碼的郵件會保留在隔離區 15 天。</span><span class="sxs-lookup"><span data-stu-id="aea72-114">Malware messages are kept in quarantine for 15 days.</span></span> <span data-ttu-id="aea72-115">您可以自訂安全性 & 合規性中心中的反垃圾郵件設定] 中的垃圾郵件隔離時間。</span><span class="sxs-lookup"><span data-stu-id="aea72-115">You can customize the spam quarantine time in anti-spam settings in the Security & Compliance Center.</span></span> <span data-ttu-id="aea72-116">當 Office 365 從隔離中刪除某封郵件後，您就無法復原該郵件。</span><span class="sxs-lookup"><span data-stu-id="aea72-116">When Office 365 deletes a message from quarantine, you can't get it back.</span></span> <span data-ttu-id="aea72-117">如有需要，您可以在您的反垃圾郵件篩選原則中變更隔離郵件的保留期間。</span><span class="sxs-lookup"><span data-stu-id="aea72-117">If you like, you can change the retention period for quarantined messages in your anti-spam filter policies.</span></span> <span data-ttu-id="aea72-118">如需詳細資訊，請參閱[設定隔離保留期限](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)。</span><span class="sxs-lookup"><span data-stu-id="aea72-118">For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aea72-119">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="aea72-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="aea72-120">雖然安全性 & 合規性中心位於隔離區，來管理郵件在隔離區的權限是由**Exchange Online**角色群組的成員資格所控制。</span><span class="sxs-lookup"><span data-stu-id="aea72-120">Although the quarantine is in the Security & Compliance Center, the permissions to manage messages in the quarantine are controlled by membership in **Exchange Online** role groups.</span></span> <span data-ttu-id="aea72-121">如需 Exchange Online 中的角色群組的詳細資訊，請參閱[管理角色群組在 Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="aea72-121">For more information about role groups in Exchange Online, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

<span data-ttu-id="aea72-122">授與管理隔離區檔案的權限的 Exchange Online 角色群組為：</span><span class="sxs-lookup"><span data-stu-id="aea72-122">The Exchange Online role groups that give permissions to manage quarantine files are:</span></span>

- <span data-ttu-id="aea72-123">**組織管理**： 全域系統管理員會自動這個群組的成員。</span><span class="sxs-lookup"><span data-stu-id="aea72-123">**Organization Management**: Global admins are automatically members of this group.</span></span>

- <span data-ttu-id="aea72-124">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="aea72-124">**Security Administrator**</span></span>

- <span data-ttu-id="aea72-125">**檢疫管理**</span><span class="sxs-lookup"><span data-stu-id="aea72-125">**Hygiene Management**</span></span>

<span data-ttu-id="aea72-126">若要檢視隔離區檔案的權限授與 Exchange Online 角色群組為：</span><span class="sxs-lookup"><span data-stu-id="aea72-126">The Exchange Online role groups that give permissions to view quarantine files are:</span></span>

- <span data-ttu-id="aea72-127">**View-Only Organization Management**</span><span class="sxs-lookup"><span data-stu-id="aea72-127">**View-Only Organization Management**</span></span>

- <span data-ttu-id="aea72-128">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="aea72-128">**Security Reader**</span></span>

## <a name="view-your-organizations-quarantined-messages"></a><span data-ttu-id="aea72-129">檢視您的組織已隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="aea72-129">View your organization's quarantined messages</span></span>

1. <span data-ttu-id="aea72-130">使用公司或學校帳戶具備全域系統管理員權限 （或適當的安全性 & 合規性中心角色） Office 365 組織中，登入 Office 365 並[移至安全性與合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="aea72-130">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your Office 365 organization, sign into Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="aea72-131">在左側清單中，展開 [**威脅管理**，選擇 [**檢閱**，，然後選擇 [**隔離**。</span><span class="sxs-lookup"><span data-stu-id="aea72-131">In the list on the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

    > [!TIP]
    > <span data-ttu-id="aea72-132">若要直接前往安全 & 與規範中心中的 [**隔離**] 頁面上，使用此 URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="aea72-132">To go directly to the **Quarantine** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

    <span data-ttu-id="aea72-133">根據預設，安全性 & 合規性中心會顯示已隔離的所有電子郵件為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="aea72-133">By default, the Security & Compliance Center displays all email messages that have been quarantined as spam.</span></span> <span data-ttu-id="aea72-134">郵件會依據接收的 [日期]\*\*\*\*，從最新排到最舊。</span><span class="sxs-lookup"><span data-stu-id="aea72-134">The messages are sorted from newest to oldest based on the **Date** the message was received.</span></span> <span data-ttu-id="aea72-135">系統也會顯示每封郵件的 [寄件者]\*\*\*\*、[主旨]\*\*\*\* 與到期日 (位於 [到期]\*\*\*\* 底下)。</span><span class="sxs-lookup"><span data-stu-id="aea72-135">**Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message.</span></span> <span data-ttu-id="aea72-136">您可以按一下對應的欄標題來依該欄位排序；再按一下欄標題則可將排序順序倒轉。</span><span class="sxs-lookup"><span data-stu-id="aea72-136">You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span>

3. <span data-ttu-id="aea72-137">您可以檢視清單中的所有隔離的郵件，或您可以減少設定來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="aea72-137">You can view a list of all quarantined messages, or you can reduce the result set by filtering.</span></span> <span data-ttu-id="aea72-138">您只能夠對最多 100 封郵件執行大量作業；如果您擁有的郵件超過 100 封，進行篩選也有助於減少結果集。</span><span class="sxs-lookup"><span data-stu-id="aea72-138">You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that.</span></span> <span data-ttu-id="aea72-139">您可以從頁面頂端的篩選器中選擇選項，以快速篩選單一隔離原因的郵件。</span><span class="sxs-lookup"><span data-stu-id="aea72-139">You can quickly filter messages for a single quarantine reason by choosing an option from the filter at the top of the page.</span></span> <span data-ttu-id="aea72-140">選項包括：</span><span class="sxs-lookup"><span data-stu-id="aea72-140">Options include:</span></span>

   - <span data-ttu-id="aea72-141">識別為垃圾郵件的郵件</span><span class="sxs-lookup"><span data-stu-id="aea72-141">Mail identified as spam</span></span>

   - <span data-ttu-id="aea72-142">因為它符合郵件流程規則 （也稱為傳輸規則） 來設定原則的隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="aea72-142">Mail quarantined because it matched a policy set by a mail flow rule (also known as a transport rule)</span></span>

   - <span data-ttu-id="aea72-143">郵件被識別為大宗郵件</span><span class="sxs-lookup"><span data-stu-id="aea72-143">Mail identified as bulk mail</span></span>

   - <span data-ttu-id="aea72-144">郵件被識別為網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="aea72-144">Mail identified as phishing mail</span></span>

   - <span data-ttu-id="aea72-145">因為它含有惡意程式碼隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="aea72-145">Mail quarantined because it contains malware</span></span>

<span data-ttu-id="aea72-146">此外，身為系統管理員，您可以選擇為您的組織的所有郵件，或是傳送給您的郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="aea72-146">In addition, as an admin, you can choose to filter all messages for your organization or only messages sent to you.</span></span> <span data-ttu-id="aea72-147">結束使用者可以僅檢視並處理郵件傳送給他們。</span><span class="sxs-lookup"><span data-stu-id="aea72-147">End users can only view and work with messages sent to them.</span></span>

<span data-ttu-id="aea72-148">您也可以篩選您的結果，以尋找特定的郵件。</span><span class="sxs-lookup"><span data-stu-id="aea72-148">You can also filter your results to find specific messages.</span></span> <span data-ttu-id="aea72-149">提示，請參閱[來篩選結果和尋找隔離的郵件和檔案](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)本文中。</span><span class="sxs-lookup"><span data-stu-id="aea72-149">For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span>

<span data-ttu-id="aea72-150">找到特定隔離的郵件後，按一下訊息即可檢視的詳細資訊，並採取動作，例如釋放訊息給某個人的信箱。</span><span class="sxs-lookup"><span data-stu-id="aea72-150">After you find a specific quarantined message, click the message to view details about it, and take actions, like releasing the message to someone's mailbox.</span></span>

## <a name="view-your-organizations-quarantined-files"></a><span data-ttu-id="aea72-151">檢視您的組織隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="aea72-151">View your organization's quarantined files</span></span>

1. <span data-ttu-id="aea72-152">使用 Office 365 組織中具有全域系統管理員權限 （或適當的安全性 & 合規性中心角色） 的工作或學校帳戶，登入 Office 365 並[移至安全性與合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="aea72-152">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="aea72-153">展開左側的 [威脅管理]\*\*\*\*，依序選擇 [檢閱]\*\*\*\* 與 [隔離]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aea72-153">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

   > [!TIP]
   > <span data-ttu-id="aea72-154">若要直接前往安全 & 與規範中心中的 [**隔離**] 頁面上，使用此 URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="aea72-154">To go directly to the **Quarantine** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

3. <span data-ttu-id="aea72-155">根據預設，頁面會顯示隔離區的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="aea72-155">By default, the page displays quarantined email messages.</span></span> <span data-ttu-id="aea72-156">若要檢視隔離的檔案，設定要顯示的**檔案**，因為**惡意程式碼**隔離的頁面頂端的篩選器。</span><span class="sxs-lookup"><span data-stu-id="aea72-156">To view quarantined files, set the filters at the top of the page to show **files**, quarantined due to **malware**.</span></span> <span data-ttu-id="aea72-157">若要使用隔離檔案的 Office 365 中，您必須具有系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="aea72-157">You must have admin permissions in Office 365 to work with quarantined files.</span></span>

4. <span data-ttu-id="aea72-158">檔案會以排序從最新到最舊根據隔離檔案的日期。</span><span class="sxs-lookup"><span data-stu-id="aea72-158">The files are sorted from newest to oldest based on the date the file was quarantined.</span></span> <span data-ttu-id="aea72-159">上次**使用者**修改的檔案，**服務**要張貼檔案，**檔案名稱**、**位置**、**檔案大小**，和到期日期 （**到期日**） 也會列出每個檔案。</span><span class="sxs-lookup"><span data-stu-id="aea72-159">The **User** who last modified the file, the **Service** to which the file was posted, the **File Name**, **Location**, **File Size**, and the expiration date ( **Expires**) are also listed for each file.</span></span> <span data-ttu-id="aea72-160">您可以藉由按一下標頭; 排序欄位按一下第二次欄標題以相反順序排序。</span><span class="sxs-lookup"><span data-stu-id="aea72-160">You can sort on a field by clicking a header; click a column header a second time to reverse the sort order.</span></span>

<span data-ttu-id="aea72-161">您可以檢視所有隔離檔案的清單或篩選您可以搜尋特定的檔案。</span><span class="sxs-lookup"><span data-stu-id="aea72-161">You can view a list of all quarantined files, or you can search for specific files by filtering.</span></span> <span data-ttu-id="aea72-162">就像郵件，您可以只執行大量作業最多 100 個項目。</span><span class="sxs-lookup"><span data-stu-id="aea72-162">Just like messages, you can only do bulk operations on up to 100 items.</span></span> <span data-ttu-id="aea72-163">目前，安全性 & 合規性中心可讓您檢視及管理位於隔離區，因為它們已識別為包含惡意程式碼的檔案。</span><span class="sxs-lookup"><span data-stu-id="aea72-163">Currently, the Security & Compliance Center lets you view and manage files that are in quarantine because they have been identified as containing malware.</span></span> <span data-ttu-id="aea72-164">提示，請參閱[來篩選結果和尋找隔離的郵件和檔案](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)本文中。</span><span class="sxs-lookup"><span data-stu-id="aea72-164">For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span>

## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a><span data-ttu-id="aea72-165">若要篩選結果，並找出隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="aea72-165">To filter results and find quarantined messages and files</span></span>
<span data-ttu-id="aea72-166"><a name="BKMK_AdvSearch"> </a></span><span class="sxs-lookup"><span data-stu-id="aea72-166"></span></span>

<span data-ttu-id="aea72-167">根據您的設定，可能會有很多隔離的郵件和檔案。</span><span class="sxs-lookup"><span data-stu-id="aea72-167">Depending on your settings, there may be a lot of quarantined messages and files.</span></span> <span data-ttu-id="aea72-168">若要尋找特定郵件或檔案或一組檔案或郵件，您可以篩選根據各種不同的其他資訊的隔離項目。</span><span class="sxs-lookup"><span data-stu-id="aea72-168">To find a specific message or file or set of messages or files, you can filter quarantined items based on a variety of additional information.</span></span>

1. <span data-ttu-id="aea72-169">在 [**隔離**] 頁面上，確定篩選條件的第一列設為郵件或檔案顯示為適當：</span><span class="sxs-lookup"><span data-stu-id="aea72-169">On the **Quarantine** page, ensure that the top row of filters is set to display messages or files as appropriate:</span></span>

   - <span data-ttu-id="aea72-170">若要搜尋的檔案，設定要顯示隔離因為**惡意程式碼**的**檔案**篩選。</span><span class="sxs-lookup"><span data-stu-id="aea72-170">To search for files, set the filters to show **files** quarantined due to **malware**.</span></span>

     <span data-ttu-id="aea72-171">隔離的檔案，頁面會顯示所有隔離的檔案，而不只顯示您自己，無論您的告訴 it。</span><span class="sxs-lookup"><span data-stu-id="aea72-171">For quarantined files, the page displays all quarantined files, not just your own, regardless of what you tell it to show.</span></span>

   - <span data-ttu-id="aea72-172">若要搜尋被隔離的郵件，設定 [顯示**所有**篩選器或**只有我\*\*\*\*電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="aea72-172">To search for quarantined messages, set filters to show **all** or **only my** **email**.</span></span> <span data-ttu-id="aea72-173">最後一個篩選條件選擇的隔離的郵件類型，您正在尋找。</span><span class="sxs-lookup"><span data-stu-id="aea72-173">For the last filter choose the type of quarantined message that you're looking for.</span></span> <span data-ttu-id="aea72-174">您可以搜尋隔離的郵件會被識別為**垃圾郵件**，符合郵件流程規則 （**傳輸規則**）、**大量**郵件、**網路釣魚**郵件或郵件包含**惡意程式碼**的郵件。</span><span class="sxs-lookup"><span data-stu-id="aea72-174">You can search for quarantined messages that have been identified as **spam**, for messages that matched a mail flow rule (**transport rule**), **bulk** mail, **phishing** mail, or mail that contains **malware**.</span></span>

2. <span data-ttu-id="aea72-175">[**來排序結果**，請選擇 [篩選器或您想要用來搜尋從下拉式清單的篩選器。</span><span class="sxs-lookup"><span data-stu-id="aea72-175">Under **Sort results by**, choose the filter or filters you want to use to search from the drop-down lists.</span></span> <span data-ttu-id="aea72-176">選項會依據您所搜尋的檔案或郵件而有所不同。</span><span class="sxs-lookup"><span data-stu-id="aea72-176">The options vary based on whether you are searching for files or messages.</span></span> <span data-ttu-id="aea72-177">在搜尋欄位中不支援萬用字元這一次。</span><span class="sxs-lookup"><span data-stu-id="aea72-177">Wildcards are not supported in search fields at this time.</span></span>

   <span data-ttu-id="aea72-178">檔案和訊息，您可以選擇將依日期篩選郵件或檔案已傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="aea72-178">For both files and messages, you can choose to filter by the date the message or file was sent to quarantine.</span></span> <span data-ttu-id="aea72-179">您可以指定某個日期或一個日期範圍，包括時間。</span><span class="sxs-lookup"><span data-stu-id="aea72-179">You can specify the date or a date range, including the time.</span></span> <span data-ttu-id="aea72-180">您也可以在其的檔案或郵件將會刪除從隔離區，或您可以使用篩選器的組合的到期日期篩選您的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="aea72-180">You can also filter your search results by the expiration date on which the file or message will be deleted from quarantine, or you can use a combination of filters.</span></span> <span data-ttu-id="aea72-181">若要搜尋的到期日，選擇 [**進階的篩選**]。</span><span class="sxs-lookup"><span data-stu-id="aea72-181">To search by expiration date, choose **Advanced filter**.</span></span> <span data-ttu-id="aea72-182">在 [**到期日**，您可以選取郵件將會在下一個 24 小時 （**今天**）、 一週 （**未來 7 天**）、 未來 48 小時 （**未來 2 天**）、 內從隔離區刪除，或您可以選取的自訂時間間隔。</span><span class="sxs-lookup"><span data-stu-id="aea72-182">Under **Expires**, you can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>

   <span data-ttu-id="aea72-183">對於郵件，您可以使用下列的其他選項：</span><span class="sxs-lookup"><span data-stu-id="aea72-183">For messages, you have the following additional options:</span></span>

   - <span data-ttu-id="aea72-184">**訊息識別碼**： 使用此功能來識別特定郵件，當您知道郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="aea72-184">**Message ID**: Use this to identify a specific message when you know the message ID.</span></span>

     <span data-ttu-id="aea72-185">例如，如果組織中的某位使用者傳送了特定郵件或者他是郵件的預定收件者，但郵件未到達目的地，則您可使用郵件追蹤功能搜尋郵件 (請參閱[安全性與合規性中心內的郵件追蹤](message-trace-scc.md))(英文版)。</span><span class="sxs-lookup"><span data-stu-id="aea72-185">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Message trace in the Security & Compliance Center](message-trace-scc.md)).</span></span> <span data-ttu-id="aea72-186">如果您發現郵件已傳送至隔離，可能是因為它符合郵件流程規則，或已識別為垃圾郵件，您接下來可以輕鬆地尋找此郵件隔離區中藉由指定其郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="aea72-186">If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its message ID.</span></span> <span data-ttu-id="aea72-187">請務必包括完整的郵件識別碼字串。</span><span class="sxs-lookup"><span data-stu-id="aea72-187">Be sure to include the full message ID string.</span></span> <span data-ttu-id="aea72-188">這可能包括角括號 (\<\>)，例如：</span><span class="sxs-lookup"><span data-stu-id="aea72-188">This might include angle brackets (\<\>), for example:</span></span>

     `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`

   - <span data-ttu-id="aea72-189">**寄件者電子郵件地址**：選擇依單一寄件者電子郵件地址來篩選。</span><span class="sxs-lookup"><span data-stu-id="aea72-189">**Sender email address**: Choose to filter by a single sender email address.</span></span>

   - <span data-ttu-id="aea72-190">**收件者電子郵件地址**：選擇做為篩選依據的單一收件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="aea72-190">**Recipient email address**: Choose to filter by a single recipient email address.</span></span>

   - <span data-ttu-id="aea72-191">**主旨**：輸入您要尋找之電子郵件地址的主旨。</span><span class="sxs-lookup"><span data-stu-id="aea72-191">**Subject**: Enter the subject of an email address you want to find.</span></span> <span data-ttu-id="aea72-192">由於不支援萬用字元搜尋，您必須在結果中傳回郵件搜尋順序使用整個郵件的主旨。</span><span class="sxs-lookup"><span data-stu-id="aea72-192">Since wildcard searching is not supported, you must use the entire subject of the message in order for search to return the message in the results.</span></span> <span data-ttu-id="aea72-193">搜尋不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="aea72-193">The search is not case-sensitive.</span></span>

## <a name="view-details-about-quarantined-messages-and-files"></a><span data-ttu-id="aea72-194">檢視詳細資料隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="aea72-194">View details about quarantined messages and files</span></span>

<span data-ttu-id="aea72-195">當您選取 [隔離] 清單中顯示的項目時，您會看到其**詳細資料**窗格中的屬性摘要 Security & 合規性中心的右側。</span><span class="sxs-lookup"><span data-stu-id="aea72-195">When you select an item displayed in the quarantine list, you'll see a summary of its properties in the **Details** pane on the right side of the Security & Compliance Center.</span></span>

### <a name="details-displayed-for-quarantined-messages"></a><span data-ttu-id="aea72-196">顯示隔離的郵件詳細資料</span><span class="sxs-lookup"><span data-stu-id="aea72-196">Details displayed for quarantined messages</span></span>

- <span data-ttu-id="aea72-197">**郵件識別碼**：郵件的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="aea72-197">**Message ID**: The unique identifier for the message.</span></span>

- <span data-ttu-id="aea72-198">**寄件者地址**：傳送郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="aea72-198">**Sender Address**: Who sent the message.</span></span>

- <span data-ttu-id="aea72-199">**Received**： 收到郵件的時間與日期。</span><span class="sxs-lookup"><span data-stu-id="aea72-199">**Received**: The date and time the message was received.</span></span>

- <span data-ttu-id="aea72-200">**主旨**： 郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="aea72-200">**Subject**: The text of the subject line of the message.</span></span>

- <span data-ttu-id="aea72-201">**類型**： 顯示郵件被識別為**垃圾郵件**、**大量**、**釣魚程式**，如果符合郵件流程規則 （**傳輸規則**），或被視為包含**惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="aea72-201">**Type**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="aea72-202">**到期日**： 的日期和時間時將會自動刪除郵件從隔離區。</span><span class="sxs-lookup"><span data-stu-id="aea72-202">**Expires**: The date and time when the message will automatically be deleted from quarantine.</span></span>

- <span data-ttu-id="aea72-203">**已釋出給**：該封郵件曾釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="aea72-203">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="aea72-204">**尚未發行至**： 所有電子郵件地址 （如果有的話） 給這不尚未已釋放郵件。</span><span class="sxs-lookup"><span data-stu-id="aea72-204">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="details-displayed-for-quarantined-files"></a><span data-ttu-id="aea72-205">顯示隔離檔案的詳細資料</span><span class="sxs-lookup"><span data-stu-id="aea72-205">Details displayed for quarantined files</span></span>

- <span data-ttu-id="aea72-206">**檔案名稱**隔離區中的檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="aea72-206">**File Name** The name of the file in quarantine.</span></span>

- <span data-ttu-id="aea72-207">**網站路徑**在 Office 365 中定義的檔案位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="aea72-207">**Site path** URL that defines the location of the file in Office 365.</span></span>

- <span data-ttu-id="aea72-208">**偵測到的日期 / 時間**日期和時間檔案的隔離。</span><span class="sxs-lookup"><span data-stu-id="aea72-208">**Detected Date / Time** The date and time the file was quarantined.</span></span>

- <span data-ttu-id="aea72-209">**到期**郵件從隔離區的刪除時的日期。</span><span class="sxs-lookup"><span data-stu-id="aea72-209">**Expires** The date when the message will be deleted from quarantine.</span></span>

- <span data-ttu-id="aea72-210">**藉由偵測到**用來偵測惡意程式碼檔案中的方法。</span><span class="sxs-lookup"><span data-stu-id="aea72-210">**Detected By** The method used to detect the malware in the file.</span></span> <span data-ttu-id="aea72-211">這可以是 ATP （進階威脅防護） 或 Microsoft 的反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="aea72-211">This can be either ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="aea72-212">**發行**說明檔案已釋放。</span><span class="sxs-lookup"><span data-stu-id="aea72-212">**Released** Describes whether or not the file has been released.</span></span>

- <span data-ttu-id="aea72-213">**惡意程式碼名稱**系列，檔案中偵測到惡意程式碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="aea72-213">**Malware Name** Family and name of the malware detected in the file.</span></span>

- <span data-ttu-id="aea72-214">**文件識別碼**文件的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="aea72-214">**Document ID** A unique identifier for the document.</span></span>

- <span data-ttu-id="aea72-215">**檔案大小**Kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="aea72-215">**File Size** The size of the file in KB.</span></span>

- <span data-ttu-id="aea72-216">**組織**貴組織的 Office 365 中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="aea72-216">**Organization** Your organization's unique ID in Office 365.</span></span>

- <span data-ttu-id="aea72-217">**藉由修改**最後修改檔案的使用者工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="aea72-217">**Modified By** The work or school account of the user who last modified the file.</span></span>

- <span data-ttu-id="aea72-218">**檔案大小**Kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="aea72-218">**File Size** The size of the file in KB.</span></span>

- <span data-ttu-id="aea72-219">**SHA256 雜湊**檔案的雜湊。</span><span class="sxs-lookup"><span data-stu-id="aea72-219">**SHA256 Hash** The hash of the file.</span></span> <span data-ttu-id="aea72-220">您可以使用此來查閱其他信譽存放區，您可能會有或調查的檔案在您的環境中可能的其他位置。</span><span class="sxs-lookup"><span data-stu-id="aea72-220">You can use this to look up other reputation stores you may have or investigate where else the file might be in your environment.</span></span>

## <a name="managing-messages-and-files-in-quarantine"></a><span data-ttu-id="aea72-221">管理隔離區中的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="aea72-221">Managing messages and files in quarantine</span></span>
<span data-ttu-id="aea72-222"><a name="BKMK_ManageQuarantinedItem"> </a></span><span class="sxs-lookup"><span data-stu-id="aea72-222"></span></span>

<span data-ttu-id="aea72-223">選取郵件或群組的郵件後您必須管理隔離區中的郵件數個選項。</span><span class="sxs-lookup"><span data-stu-id="aea72-223">After you select a message or group of messages you have several options for managing messages in quarantine.</span></span>

- <span data-ttu-id="aea72-224">不執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="aea72-224">Do nothing.</span></span> <span data-ttu-id="aea72-225">如果您選擇不執行任何動作，該郵件會在到期後由 Office 365 自動刪除。</span><span class="sxs-lookup"><span data-stu-id="aea72-225">If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration.</span></span> <span data-ttu-id="aea72-226">根據預設，垃圾郵件、 大量、 惡意程式碼、 網路釣魚及因為它們符合郵件流程規則的隔離郵件會保留在隔離區中 30 天。</span><span class="sxs-lookup"><span data-stu-id="aea72-226">By default, spam, bulk, malware, phishing, and messages quarantined because they matched a mail flow rule are kept in quarantine for 30 days.</span></span> <span data-ttu-id="aea72-227">當 Office 365 從隔離中刪除某封郵件後，您就無法復原該郵件。</span><span class="sxs-lookup"><span data-stu-id="aea72-227">When Office 365 deletes a message from quarantine, you can't get it back.</span></span> <span data-ttu-id="aea72-228">如有需要，您可以變更隔離郵件的保留期間 **（天） 的保留垃圾郵件**設定反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="aea72-228">If you like, you can change the retention period for quarantined messages by configuring the **Retain spam for (days)** setting in your anti-spam policies.</span></span> <span data-ttu-id="aea72-229">如需詳細資訊，請參閱本文中的[設定隔離保留期限](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)。</span><span class="sxs-lookup"><span data-stu-id="aea72-229">For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span>

- <span data-ttu-id="aea72-230">**檢視郵件標頭**： 選擇此連結以查看郵件標頭文字。</span><span class="sxs-lookup"><span data-stu-id="aea72-230">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="aea72-231">若要分析的標頭中深度，將郵件標頭文字複製到剪貼簿，，然後選擇 [ **Microsoft 郵件標頭分析器**要前往 Remote Connectivity Analyzer （以滑鼠右鍵按一下並選擇 [**開啟新的索引標籤中**，如果您不想要保留完成這項工作的 Office 365）。在郵件標頭分析器] 區段中，貼到頁面的郵件標頭，然後選擇 [**分析標頭**：</span><span class="sxs-lookup"><span data-stu-id="aea72-231">To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="aea72-232">**預覽郵件**：讓您查看郵件內文文字的原始版本或 HTML 版本。</span><span class="sxs-lookup"><span data-stu-id="aea72-232">**Preview message**: Lets you see raw or HTML versions of the message body text.</span></span> <span data-ttu-id="aea72-233">在 HTML 檢視中會停用連結。</span><span class="sxs-lookup"><span data-stu-id="aea72-233">In the HTML view, links are disabled.</span></span>

- <span data-ttu-id="aea72-234">**下載郵件**或**下載檔案**： 選擇這個選項，郵件或檔案的複本下載到您的本機裝置。</span><span class="sxs-lookup"><span data-stu-id="aea72-234">**Download message** or **Download file**: Choose this option to download a copy of the message or file to your local device.</span></span> <span data-ttu-id="aea72-235">您必須確認您了解與下載的項目從隔離區，才能將允許相關聯的風險。</span><span class="sxs-lookup"><span data-stu-id="aea72-235">You'll need to confirm that you understand the risks associated with downloading items from quarantine before you'll be allowed to do so.</span></span> <span data-ttu-id="aea72-236">郵件會儲存在.eml 格式，以指定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="aea72-236">Messages are saved in .eml format to a folder you specify.</span></span> <span data-ttu-id="aea72-237">隔離的檔案會儲存在其原始格式。</span><span class="sxs-lookup"><span data-stu-id="aea72-237">Quarantined files are saved in their original format.</span></span>

- <span data-ttu-id="aea72-238">**刪除**： 如果您想，您可以立即隔離的項目 （或刪除的項目集合） 而不是等待設定 Office 365 的到期日期。</span><span class="sxs-lookup"><span data-stu-id="aea72-238">**Delete**: If you want, you can immediately delete a quarantined item (or set of items) instead of waiting for the expiration date set by Office 365.</span></span> <span data-ttu-id="aea72-239">若要刪除的郵件或檔案，請在 [隔離] 清單中選取的項目，然後選擇 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="aea72-239">To delete a message or file, in the quarantine list, select the item and then choose **Delete**.</span></span> <span data-ttu-id="aea72-240">若要一次刪除多個項目，[隔離] 清單中選取的項目左邊的核取方塊，然後在出現 [**大量動作**] 頁面中，選擇 [**刪除選取的郵件**] 或 [**刪除選取的檔案**。</span><span class="sxs-lookup"><span data-stu-id="aea72-240">To delete multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Delete selected messages** or **Delete selected files**.</span></span>

- <span data-ttu-id="aea72-241">**版本**： 釋出隔離的項目 （或組的項目） 並向 Microsoft 報告為實隔離 （誤判） 的項目。</span><span class="sxs-lookup"><span data-stu-id="aea72-241">**Release**: Release a quarantined item (or set of items) and report the items as falsely quarantined (false positives) to Microsoft.</span></span>

  <span data-ttu-id="aea72-242">若要釋放並回報單一郵件或檔案，請在 [隔離] 清單中選取的項目中，選擇 [**釋出檔案**或**郵件釋出**。</span><span class="sxs-lookup"><span data-stu-id="aea72-242">To release and report a single message or file, in the quarantine list, select the item, choose **Release file** or **Release message**.</span></span> <span data-ttu-id="aea72-243">在 [下一步] 頁面上，確定已選取 [**報告郵件提交給 Microsoft 進行分析**或**報告給 Microsoft 進行分析的檔案**。</span><span class="sxs-lookup"><span data-stu-id="aea72-243">On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span>

  <span data-ttu-id="aea72-244">若要一次發行多個項目，[隔離] 清單中選取的項目左邊的核取方塊，然後在出現 [**大量動作**] 頁面中，選擇**發行的檔案**或**釋放郵件**。</span><span class="sxs-lookup"><span data-stu-id="aea72-244">To release multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Release files** or **Release messages**.</span></span> <span data-ttu-id="aea72-245">在 [下一步] 頁面上，確定已選取 [**報告郵件提交給 Microsoft 進行分析**或**報告給 Microsoft 進行分析的檔案**。</span><span class="sxs-lookup"><span data-stu-id="aea72-245">On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span>

<span data-ttu-id="aea72-246">當您正在釋出郵件，請注意下列：</span><span class="sxs-lookup"><span data-stu-id="aea72-246">When you're releasing messages, be aware of the following:</span></span>

- <span data-ttu-id="aea72-247">當您同時執行多個郵件大量版本時，郵件會發行至原本已識別的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="aea72-247">When you perform a bulk release of multiple messages at once, the messages are released to all originally identified recipients.</span></span> <span data-ttu-id="aea72-248">如果您只想釋放僅給特定收件者的郵件，您需要釋放郵件一次，並個別識別收件者。</span><span class="sxs-lookup"><span data-stu-id="aea72-248">If you only want to release messages only to specific recipients, you need to release the messages one at a time and identify the recipients individually.</span></span>

- <span data-ttu-id="aea72-249">郵件無法再釋出一次以上相同的收件者。</span><span class="sxs-lookup"><span data-stu-id="aea72-249">A message cannot be released more than once to the same recipient.</span></span>

- <span data-ttu-id="aea72-250">當您正在釋出給一個以上的收件者的郵件時，僅有不先前已收到郵件收件者會出現在潛在收件者清單。</span><span class="sxs-lookup"><span data-stu-id="aea72-250">When you're releasing a message to more than one recipient, only recipients who have not previously received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="aea72-251">當您選擇要報告誤判，如果郵件或您釋出的郵件為垃圾郵件、 大量、 網路釣魚，或包含惡意程式碼隔離時，也會向 Microsoft 垃圾郵件分析小組報告該郵件。</span><span class="sxs-lookup"><span data-stu-id="aea72-251">When you choose to report false positives, if the message or messages you release were quarantined as spam, bulk, phishing, or as containing malware, the message will also be reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="aea72-252">小組會評估和分析此郵件，然後根據分析結果，可能會調整全服務垃圾郵件內容篩選規則以允許郵件通過。</span><span class="sxs-lookup"><span data-stu-id="aea72-252">The team will evaluate and analyze the message, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>

## <a name="setting-the-quarantine-retention-period"></a><span data-ttu-id="aea72-253">設定隔離保留期限</span><span class="sxs-lookup"><span data-stu-id="aea72-253">Setting the quarantine retention period</span></span>
<span data-ttu-id="aea72-254"><a name="BKMK_ModQuarantineTime"> </a></span><span class="sxs-lookup"><span data-stu-id="aea72-254"></span></span>

<span data-ttu-id="aea72-255">您可以設定多久郵件和到期之前，將會保留在隔離區的檔案。</span><span class="sxs-lookup"><span data-stu-id="aea72-255">You can configure how long messages and files will remain in quarantine before they expire.</span></span> <span data-ttu-id="aea72-256">根據預設，隔離的郵件會保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="aea72-256">By default, quarantined items are kept for 30 days.</span></span> <span data-ttu-id="aea72-257">您將此設為您建立的每個原則。</span><span class="sxs-lookup"><span data-stu-id="aea72-257">You configure this setting for each policy that you create.</span></span> <span data-ttu-id="aea72-258">您也可以修改預設原則，如本文所述的值。</span><span class="sxs-lookup"><span data-stu-id="aea72-258">You can also modify the value for the default policy as described in this article.</span></span>

### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a><span data-ttu-id="aea72-259">若要在安全性與合規性中心修改預設垃圾郵件篩選器原則的隔離保留期限</span><span class="sxs-lookup"><span data-stu-id="aea72-259">To modify the quarantine retention period for the default spam filter policy in the Security and Compliance Center</span></span>

1. <span data-ttu-id="aea72-260">使用 Office 365 組織中具有全域系統管理員權限 （或適當的安全性 & 合規性中心角色） 的工作或學校帳戶，登入 Office 365 並[移至安全性與合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="aea72-260">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="aea72-261">位於左側，展開**威脅管理**，選擇 [**原則**] 中，，然後選擇 [**反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="aea72-261">On the left, expand **Threat Management**, choose **Policy**, and then choose **Anti-spam**.</span></span>

    > [!TIP]
    > <span data-ttu-id="aea72-262">若要直接前往安全 & 與規範中心中的**反垃圾郵件**] 頁面上，使用此 URL: >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span><span class="sxs-lookup"><span data-stu-id="aea72-262">To go directly to the **anti-spam** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span></span>

3. <span data-ttu-id="aea72-263">展開 [**預設垃圾郵件篩選原則 (always ON)** ] 列。</span><span class="sxs-lookup"><span data-stu-id="aea72-263">Expand the **Default spam filter policy (always ON)** row.</span></span>

4. <span data-ttu-id="aea72-264">選擇 [**編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="aea72-264">Choose **Edit policy**.</span></span> <span data-ttu-id="aea72-265">預設垃圾郵件篩選器原則的設定出現在新的頁面。</span><span class="sxs-lookup"><span data-stu-id="aea72-265">The settings for the default spam filter policy appear in a new page.</span></span>

5. <span data-ttu-id="aea72-266">依序展開 [**垃圾郵件和大量動作**。</span><span class="sxs-lookup"><span data-stu-id="aea72-266">Expand **Spam and bulk actions**.</span></span>

6. <span data-ttu-id="aea72-267">在 [**隔離**，在 [**保留垃圾郵件的 （天）** ] 文字方塊中輸入您希望 Office 365 到隔離區中保留的郵件和檔案的時間量。</span><span class="sxs-lookup"><span data-stu-id="aea72-267">Under **Quarantine**, in the **Retain spam for (days)** text box, enter the amount of time you want Office 365 to retain messages and files in quarantine.</span></span> <span data-ttu-id="aea72-268">預設值為 30 天。</span><span class="sxs-lookup"><span data-stu-id="aea72-268">The default is 30 days.</span></span> <span data-ttu-id="aea72-269">這也是最大值。</span><span class="sxs-lookup"><span data-stu-id="aea72-269">This is also the maximum.</span></span>

7. <span data-ttu-id="aea72-270">選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aea72-270">Choose **Save**.</span></span>
