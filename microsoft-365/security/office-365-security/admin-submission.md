---
title: Office 365 中的系統管理員報送、O365 報送、Office 365 垃圾郵件問題、O365 false 負數、在 office 365 中提交網路釣魚功能、提交電子郵件的掃描、可疑的電子郵件在 Office 365、掃描郵件、Microsoft 掃描網路釣魚詐騙、郵件、提交電子郵件，送出電子郵件，dodgy 電子郵件，不良演員郵件，可疑，不受信任的郵件，報告網路釣魚電子郵件至 microsoft，向 microsoft 報告網路，向 microsoft 報告欺詐電子郵件，並將惡意電子郵件報告給 microsoft，垃圾郵件收件匣 office 365 中的電子郵件，在電子郵件 office 365 中的病毒
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 瞭解如何將可疑的電子郵件、可疑的網路釣魚郵件、垃圾郵件和其他可能有害的郵件、URLs 和檔案從您的 Office 365 租使用者提交至 Microsoft 進行掃描。
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033611"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="494cd-103">使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="494cd-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="494cd-104">如果您是 Office 365 組織中具有 Exchange Online 信箱的系統管理員，您可以使用 Office 365 安全性 & 合規性中心內的提交入口網站，將電子郵件訊息、URLs 和附件提交給 Microsoft 以進行掃描。</span><span class="sxs-lookup"><span data-stu-id="494cd-104">If you're an admin in an Office 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Office 365 Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="494cd-105">當您提交電子郵件時，您會收到任何可能允許內送電子郵件進入租使用者的原則，以及對郵件中的任何 URLs 和附件進行檢查的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="494cd-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="494cd-106">可能允許郵件的原則包括個別使用者的安全寄件者清單，以及租使用者層級原則，例如 Exchange 郵件流程規則（也稱為傳輸規則）。</span><span class="sxs-lookup"><span data-stu-id="494cd-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="494cd-107">如需其他方式，將電子郵件訊息、URLs 和附件提交給 Microsoft，請參閱</span><span class="sxs-lookup"><span data-stu-id="494cd-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="494cd-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="494cd-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="494cd-109">您可以在<https://protection.office.com/>中開啟安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="494cd-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="494cd-110">若要直接移至**提交**頁面，請<https://protection.office.com/reportsubmission>使用。</span><span class="sxs-lookup"><span data-stu-id="494cd-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="494cd-111">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="494cd-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="494cd-112">若要連線到獨立的 Exchange Online Protection PowerShell，請參閱[connect To Exchange Online protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="494cd-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="494cd-113">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="494cd-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="494cd-114">若要新增、修改和刪除反垃圾郵件原則，您必須是「**組織管理**」、「**安全性管理員**」或「**安全性讀者**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="494cd-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="494cd-115">如需安全性 & 規範中心中角色群組的詳細資訊，請參閱[Office 365 安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="494cd-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="494cd-116">如需使用者如何將郵件和檔案提交給 Microsoft 的詳細資訊，請參閱[將報告訊息和檔案傳送給 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="494cd-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="494cd-117">如何將可疑內容引導至 Microsoft 以進行 Office 365 掃描</span><span class="sxs-lookup"><span data-stu-id="494cd-117">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="494cd-118">若要將內容提交至 Microsoft，請按一下 [提交] 頁面左上方的 [**新增提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="494cd-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="494cd-119">頁面右邊的浮出控制項顯示可供您提交電子郵件、URL 或檔案的選項。</span><span class="sxs-lookup"><span data-stu-id="494cd-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="494cd-120">將可疑的電子郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="494cd-120">Submit a questionable email to Microsoft</span></span>

![電子郵件提交範例](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="494cd-122">若要提交電子郵件，請選取 [**電子郵件**] 並指定電子郵件**網路訊息識別碼**或上傳電子郵件檔案。</span><span class="sxs-lookup"><span data-stu-id="494cd-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="494cd-123">指定您想要執行原則檢查的收件者。</span><span class="sxs-lookup"><span data-stu-id="494cd-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="494cd-124">原則檢查會決定是否因使用者或租使用者層級原則而略過掃描的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="494cd-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="494cd-125">指定是否應該封鎖電子郵件。</span><span class="sxs-lookup"><span data-stu-id="494cd-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="494cd-126">如果電子郵件應該已封鎖，請指定是否應該封鎖為垃圾郵件、網路釣魚或惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="494cd-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="494cd-127">如果您不確定可能是哪種類型，請使用您的最佳判斷。</span><span class="sxs-lookup"><span data-stu-id="494cd-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="494cd-128">如果篩選因提交原則而略過，您將會看到該原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="494cd-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="494cd-129">如果篩選器因一或多個原則而略過，掃描將會在數分鐘內完成。</span><span class="sxs-lookup"><span data-stu-id="494cd-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="494cd-130">您可以按一下 [狀態] 連結，以查看有關提交的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="494cd-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="494cd-131">這包括原則檢查的結果和重新掃描判定。</span><span class="sxs-lookup"><span data-stu-id="494cd-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="494cd-132">請注意，這不會再透過 Office 365 ATP 完整篩選棧執行電子郵件，但會根據郵件、URL 或檔案的某些屬性執行部分重新掃描。</span><span class="sxs-lookup"><span data-stu-id="494cd-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="494cd-133">按一下 [**提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="494cd-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="494cd-134">將可疑 URL 傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="494cd-134">Send a suspect URL to Microsoft</span></span>

![電子郵件提交範例](../../media/submission-url-flyout.png)

1. <span data-ttu-id="494cd-136">若要提交 URL，請選取浮出控制項的**url** 。</span><span class="sxs-lookup"><span data-stu-id="494cd-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="494cd-137">輸入完整 URL，包含通訊協定（**HTTPs://**）。</span><span class="sxs-lookup"><span data-stu-id="494cd-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="494cd-138">如果您選取 [**應該已經過篩選**]，請指定 URL 是否為網路釣魚或惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="494cd-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="494cd-139">按一下 [**提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="494cd-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="494cd-140">將可疑檔提交至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="494cd-140">Submit a suspected file to Microsoft</span></span>

![電子郵件提交範例](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="494cd-142">若**要從飛出檔中**提交檔案選取檔案，並上傳想要掃描的檔。</span><span class="sxs-lookup"><span data-stu-id="494cd-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="494cd-143">按一下 [**提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="494cd-143">Click the **Submit** button.</span></span>
