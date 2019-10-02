---
title: 使用敏感度標籤中的加密來限制內容的存取
ms.author: laurawi
author: laurawi
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 當建立敏感度標籤時，您可以限制標籤將套用至其中之內容的存取。敏感度標籤可以使用加密來保護內容。
ms.openlocfilehash: be41f60f8d0210c779fb6c5a8fdc783cf23fcc19
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369444"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a><span data-ttu-id="a94c6-104">使用敏感度標籤中的加密來限制內容的存取</span><span class="sxs-lookup"><span data-stu-id="a94c6-104">Restrict access to content by using encryption in sensitivity labels</span></span>

<span data-ttu-id="a94c6-p102">當建立敏感度標籤時，您可以限制標籤將套用至其中之內容的存取。例如，使用敏感度標籤的加密設定，您可以保護內容，以便：</span><span class="sxs-lookup"><span data-stu-id="a94c6-p102">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="a94c6-107">僅您組織內的使用者才能開啟機密文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a94c6-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="a94c6-108">僅行銷部門中的使用者才能編輯和列印促銷公告文件或電子郵件，而您組織中的所有其他使用者則只能讀取它。</span><span class="sxs-lookup"><span data-stu-id="a94c6-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="a94c6-109">使用者無法轉寄電子郵件，或從中複製包含內部組織相關消息的資訊。</span><span class="sxs-lookup"><span data-stu-id="a94c6-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="a94c6-110">在指定日期之後，無法開啟傳送給商業夥伴的目前價格清單。</span><span class="sxs-lookup"><span data-stu-id="a94c6-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="a94c6-111">加密文件或電子郵件時，內容的存取會受到限制，以便：</span><span class="sxs-lookup"><span data-stu-id="a94c6-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="a94c6-112">只有標籤加密設定授權的使用者才能將其解密。</span><span class="sxs-lookup"><span data-stu-id="a94c6-112">Can be decrypted only by users authorized by the label’s encryption settings.</span></span>
- <span data-ttu-id="a94c6-113">即使檔案重新命名，無論其位於您組織內部或外部，仍保持加密狀態。</span><span class="sxs-lookup"><span data-stu-id="a94c6-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file’s renamed.</span></span>
- <span data-ttu-id="a94c6-114">同時進行靜態加密 (例如，在 OneDrive 帳戶中) 及傳輸中加密 (例如，已傳送的電子郵件)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, a sent email).</span></span>

<span data-ttu-id="a94c6-115">最後，身為系統管理員，當您建立敏感度標籤時，可以選擇以下任一動作：</span><span class="sxs-lookup"><span data-stu-id="a94c6-115">Finally, as an admin, when you create a sensitivity label, you can choose either to:</span></span>

- <span data-ttu-id="a94c6-116">**立即指派權限**，這樣您就能確實決定哪個使用者能夠存取該標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="a94c6-116">**Assign permissions now**, so that you determine exactly which users get which permissions to content with that label.</span></span>
- <span data-ttu-id="a94c6-117">當使用者將標籤套用到內容時，**讓使用者指派權限**。</span><span class="sxs-lookup"><span data-stu-id="a94c6-117">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="a94c6-118">如此一來，您就可以讓組織中的人員靈活地共同作業並完成工作。</span><span class="sxs-lookup"><span data-stu-id="a94c6-118">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span>

<span data-ttu-id="a94c6-119">當您在 Microsoft 365 合規性中心、Microsoft 365 安全性中心或是 Office 365 安全性與合規性中心中建立敏感性標籤時，可以使用加密設定。</span><span class="sxs-lookup"><span data-stu-id="a94c6-119">The encryption settings are available when you create a sensitivity label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="a94c6-120">在左側導覽中，選擇[分類] \*\*\*\* >  [敏感度標籤] \*\*\*\* >  [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a94c6-120">In the left nav, choose **Classification** > **Sensitivity label** > **Create a label**.</span></span>

## <a name="how-encryption-works"></a><span data-ttu-id="a94c6-121">加密的運作方式</span><span class="sxs-lookup"><span data-stu-id="a94c6-121">How encryption works</span></span>

<span data-ttu-id="a94c6-p105">加密會使用 Azure Rights Management (Azure RMS)。Azure RMS 會使用加密、身分識別和授權原則。若要深入了解，請參閱[什麼是 Azure Rights Management？](https://docs.microsoft.com/zh-TW/azure/information-protection/what-is-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="a94c6-p105">Encryption uses Azure Rights Management (Azure RMS). Azure RMS uses encryption, identity, and authorization policies. To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/zh-TW/azure/information-protection/what-is-azure-rms)</span></span>

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a><span data-ttu-id="a94c6-125">如何開啟敏感度標籤的加密</span><span class="sxs-lookup"><span data-stu-id="a94c6-125">How to turn on encryption for a sensitivity label</span></span>

<span data-ttu-id="a94c6-126">若要開始，只要將 [加密]\*\*\*\* 切換為 [開啟]\*\*\*\*，然後選擇以下任一動作：</span><span class="sxs-lookup"><span data-stu-id="a94c6-126">To begin, simply toggle **Encryption** to **On**, and then choose whether to:</span></span>

- <span data-ttu-id="a94c6-127">**立即指派權限**，這樣您就能確實決定哪個使用者能夠存取該標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="a94c6-127">**Assign permissions now**, so that you can determine exactly which users get which permissions to content with that label.</span></span> <span data-ttu-id="a94c6-128">如需詳細資訊，請參閱下一節的[立即指派權限](#assign-permissions-now)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-128">For more information, see the next section [Assign permissions now](#assign-permissions-now).</span></span>
- <span data-ttu-id="a94c6-129">當使用者將標籤套用到內容時，**讓使用者指派權限**。</span><span class="sxs-lookup"><span data-stu-id="a94c6-129">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="a94c6-130">如此一來，您就可以讓組織中的人員靈活地共同作業並完成工作。</span><span class="sxs-lookup"><span data-stu-id="a94c6-130">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span> <span data-ttu-id="a94c6-131">如需詳細資訊，請參閱下一節的[讓使用者指派權限](#let-users-assign-permissions)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-131">For more information, see the below section [Let users assign permissions](#let-users-assign-permissions).</span></span>

<span data-ttu-id="a94c6-132">例如，如果您有一個名為 [高度機密] \*\*\*\* 的敏感度標籤，該標籤將套用至最敏感的內容，則您可能會希望立即決定可以存取該內容。</span><span class="sxs-lookup"><span data-stu-id="a94c6-132">For example, if you have a sensitivity label named **Highly Confidential** that will be applied to your most sensitive content, you may want to decide now who gets what type of permissions to that content.</span></span>

<span data-ttu-id="a94c6-133">或者，如果您有一個名為 [商業合約]\*\*\*\* 的敏感度標籤，並且貴組織的工作流程要求人員隨機與不同人員就此內容共同作業，則您可能會希望讓使用者在指派標籤時決定可存取的人員。</span><span class="sxs-lookup"><span data-stu-id="a94c6-133">Alternatively, if you have a sensitivity label named **Business Contracts**, and your organization's workflow requires that your people collaborate on this content with different people on an ad hoc basis, you may want to allow your users to decide who gets permissions when they assign the label.</span></span> <span data-ttu-id="a94c6-134">這種靈活性既可以幫助您提高使用者的工作效率，又可以減少管理員更新或建立新敏感度標籤以滿足特定案例的要求。</span><span class="sxs-lookup"><span data-stu-id="a94c6-134">This flexibility both helps your users' productivity and reduces the requests for your admins to update or create new sensitivity labels to address specific scenarios.</span></span>

![新增使用者或系統管理員定義權限的選項](media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a><span data-ttu-id="a94c6-136">立即指派權限</span><span class="sxs-lookup"><span data-stu-id="a94c6-136">Assign permissions now</span></span>

<span data-ttu-id="a94c6-137">使用下列選項來控制誰可以存取套用此標籤的電子郵件或文件。</span><span class="sxs-lookup"><span data-stu-id="a94c6-137">To begin, simply toggle Encryption to On, and then use the options below to control who can access email or documents to which this label is applied. You can:</span></span> <span data-ttu-id="a94c6-138">您可以：</span><span class="sxs-lookup"><span data-stu-id="a94c6-138">You can:</span></span>

1. <span data-ttu-id="a94c6-p110">**允許加標籤的內容到期**，可在特定日期，或是在套用標籤之後的特定天數之後。在此時間後，使用者將無法開啟加標籤的項目。如果您指定日期，則有效時間直到您的目前時區中該日期的午夜。(請注意，某些電子郵件用戶端可能因為其快取機制而無法強制執行到期，並顯示超過期限的電子郵件。)</span><span class="sxs-lookup"><span data-stu-id="a94c6-p110">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won’t be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone. (Note that some email clients may not enforce expiration and show emails past their expiration date, due to their caching mechanisms.)</span></span>

2. <span data-ttu-id="a94c6-p111">在套用標籤之後**允許離線存取**可為從不、一律或特定天數。如果您將離線存取限制為從不或天數，則達到該閾值時，必須重新驗證使用者，並記錄其存取。如需詳細資訊，請參閱關於 Rights Management 使用授權的下一節。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p111">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

![系統管理員定義權限的設定](media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="a94c6-147">用於離線存取的 Rights Management 使用授權</span><span class="sxs-lookup"><span data-stu-id="a94c6-147">Rights Management use license for offline access</span></span>

<span data-ttu-id="a94c6-p112">當使用者離線開啟受到敏感度標籤保護的文件或電子郵件時，該內容的 Azure Rights Management 使用授權會授與使用者。此使用授權是一種憑證，其中包含使用者對文件或電子郵件的使用權，以及用來加密內容的加密金鑰。使用授權也會包含到期日 (若已設定的話)，以及使用授權的有效期限。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p112">When a user opens a document or email offline that’s been protected by a sensitivity label, an Azure Rights Management use license for that content is granted to the user. This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content. The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="a94c6-p113">如果未設定到期日，則租用戶的預設使用授權有效期間為 30 天。在這段期間，不會針對內容重新驗證或重新授權使用者。這可讓使用者在沒有網際網路連線的情況下繼續開啟受保護文件或電子郵件。使用授權有效期間到期時，下次使用者存取受保護文件或電子郵件時，必須重新驗證和重新授權使用者。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p113">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This lets the user continue to open the protected document or email without an Internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="a94c6-p114">除了重新驗證外，還會重新評估原則和使用者群組成員資格。這表示，如果上次使用者存取內容後，原則或群組成員資格發生變更，則這些使用者可能遇到相同的文件或電子郵件，卻有不同的存取結果。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p114">In addition to reauthentication, the policy and user group membership is reevaluated. This means that users could experience different access results for the same document or email if there are changes in the policy or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="a94c6-157">若要了解如何變更預設的 30 天設定，請參閱 [Rights Management 使用授權](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-management-use-license)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-157">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

### <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="a94c6-158">將權限指派給特定使用者或群組</span><span class="sxs-lookup"><span data-stu-id="a94c6-158">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="a94c6-159">您可以將權限授與特定人員，以便只有他們可與標籤內容互動。</span><span class="sxs-lookup"><span data-stu-id="a94c6-159">You can grant permissions to specific people so that only they can interact with the labeled content.</span></span>

<span data-ttu-id="a94c6-160">作法是簡單的兩步驟程序：</span><span class="sxs-lookup"><span data-stu-id="a94c6-160">Doing so is a straightforward two-step process:</span></span>

1. <span data-ttu-id="a94c6-161">首先，新增將獲指派標籤內容之權限的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="a94c6-161">First you add users or groups that will be assigned permissions to the labeled content.</span></span>
2. <span data-ttu-id="a94c6-162">接著，選擇那些使用者對標籤內容具有的權限。</span><span class="sxs-lookup"><span data-stu-id="a94c6-162">Then you choose which permissions those users have for the labeled content.</span></span>

![將權限指派給使用者的選項](media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a><span data-ttu-id="a94c6-164">新增使用者或群組</span><span class="sxs-lookup"><span data-stu-id="a94c6-164">Add users or groups</span></span>

<span data-ttu-id="a94c6-165">指派權限時，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="a94c6-165">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="a94c6-p115">組織中的所有人 (所有租用戶成員)。此設定會排除來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p115">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>
- <span data-ttu-id="a94c6-168">任何特定使用者或啟用電子郵件功能的安全性群組、通訊群組、Office 365 群組或動態通訊群組。</span><span class="sxs-lookup"><span data-stu-id="a94c6-168">Any specific user or email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span> 
- <span data-ttu-id="a94c6-169">組織外的任何電子郵件地址或網域，例如 gmail.com、hotmail.com 或 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="a94c6-169">Any email address or domain outside your organization, such as gmail.com, hotmail.com, or outlook.com.</span></span>

<span data-ttu-id="a94c6-170">當您選擇所有租用戶成員或瀏覽目錄時，使用者或群組必須具有電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a94c6-170">When you choose all tenant members or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="a94c6-p116">最佳做法是使用群組，而非使用者。此策略可讓您保持更簡單的組態。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p116">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

#### <a name="choose-permissions"></a><span data-ttu-id="a94c6-173">選擇權限</span><span class="sxs-lookup"><span data-stu-id="a94c6-173">Choose permissions</span></span>

<span data-ttu-id="a94c6-174">當您選擇要對那些使用者或群組允許的權限時，您可以選取下列任一項：</span><span class="sxs-lookup"><span data-stu-id="a94c6-174">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="a94c6-175">[預先定義的權限層級](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)，其中有一組預設的權限，例如共同作者或檢閱者。</span><span class="sxs-lookup"><span data-stu-id="a94c6-175">A [predefined permissions level](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="a94c6-176">一組自訂的權限，您可在其中選擇任何您想要的權限。</span><span class="sxs-lookup"><span data-stu-id="a94c6-176">A Custom group of rights, where you choose whichever permissions you want.</span></span>

<span data-ttu-id="a94c6-177">如需每一個特定權限的詳細資訊，請參閱[使用權限和描述](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-177">For more information on each specific permission, see [Usage rights and descriptions](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![選擇預設或自訂權限的選項](media/Sensitivity-Choose-permissions-settings.png)

<span data-ttu-id="a94c6-p117">請注意，相同標籤可將不同的權限授與不同的使用者。例如，單一標籤可將某些使用者指派為檢閱者，並將不同的使用者指派為共同作者，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p117">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown below.</span></span>

<span data-ttu-id="a94c6-p118">若要這麼做，請新增使用者或群組、將權限指派給他們，並儲存這些設定。然後，重複這些步驟，新增使用者並將權限指派給他們，每次儲存設定。您可以視需要經常執行此動作，為不同的使用者定義不同的權限。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p118">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can do this as often as necessary, to define different permissions for different users.</span></span>

![具有不同權限的不同使用者](media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="a94c6-185">Rights Management 簽發者 (套用敏感度標籤的使用者) 一律具有完全控制權</span><span class="sxs-lookup"><span data-stu-id="a94c6-185">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="a94c6-p119">敏感度標籤的加密會使用 Azure RMS。當使用者套用敏感度標籤以使用 Azure RMS 保護文件或電子郵件時，該使用者就會變成該內容的 Rights Management 簽發者。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p119">Encryption for a sensitivity label uses Azure RMS. When a user applies a sensitivity label to protect a document or email by using Azure RMS, that user becomes the Rights Management issuers for that content.</span></span>

<span data-ttu-id="a94c6-188">Rights Management 簽發者一律會被授與文件或電子郵件的完全控制權限，此外：</span><span class="sxs-lookup"><span data-stu-id="a94c6-188">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="a94c6-189">如果保護設定包括到期日，則 Rights Management 簽發者仍然可在該日期之後開啟和編輯文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a94c6-189">If the protection settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="a94c6-190">Rights Management 簽發者一律可以離線存取文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a94c6-190">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="a94c6-191">Rights Management 簽發者仍可以開啟撤銷後的文件。</span><span class="sxs-lookup"><span data-stu-id="a94c6-191">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="a94c6-192">如需詳細資訊，請參閱 [Rights Management 簽發者和 Rights Management 擁有者](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-192">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

## <a name="let-users-assign-permissions"></a><span data-ttu-id="a94c6-193">讓使用者指派權限</span><span class="sxs-lookup"><span data-stu-id="a94c6-193">Let users assign permissions</span></span>

<span data-ttu-id="a94c6-194">您可以使用這些選項讓使用者在手動將敏感度標籤套用至內容時指派權限：</span><span class="sxs-lookup"><span data-stu-id="a94c6-194">You can use these options to let users assign permissions when they manually apply a sensitivity label to content:</span></span>

- <span data-ttu-id="a94c6-195">在 Outlook 中，使用者可以強制執行與 [不可轉寄][](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) 選項同等的限制。</span><span class="sxs-lookup"><span data-stu-id="a94c6-195">In Outlook, a user can enforce restrictions equivalent to the [Do Not Forward](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) option.</span></span> <span data-ttu-id="a94c6-196">Windows 上的 Outlook 原本就支援這個選項，並且不會要求您安裝 Azure 資訊保護統一標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="a94c6-196">This option is supported natively in Outlook on Windows, and does not require you to install the Azure Information Protection unified labeling client.</span></span>
- <span data-ttu-id="a94c6-197">在 Word、PowerPoint 和 Excel 中，系統會提示使用者為特定使用者、群組或組織選取權限等級。</span><span class="sxs-lookup"><span data-stu-id="a94c6-197">In Word, PowerPoint, and Excel, a user is prompted to select a permission level for specific users, groups, or organizations.</span></span> <span data-ttu-id="a94c6-198">這些 Office 應用程式原本就不支援這個選項，因此您的使用者必須安裝 Azure 資訊保護統一標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="a94c6-198">This option is not supported natively in these Office apps, so your users must install the Azure Information Protection unified labeling client.</span></span>

<span data-ttu-id="a94c6-199">這些選項可決定敏感標籤將出現在哪些應用程式中：</span><span class="sxs-lookup"><span data-stu-id="a94c6-199">These options determine in which apps the sensitivity label will appear:</span></span>

- <span data-ttu-id="a94c6-200">如果敏感度標籤僅啟用了 Outlook 選項，則標籤只會顯示給 Outlook 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="a94c6-200">If the sensitivity label has only the Outlook option enabled, the label will appear to users only in Outlook.</span></span>
- <span data-ttu-id="a94c6-201">如果敏感度標籤僅啟用了 Word、PowerPoint 和 Excel 選項，則標籤只會顯示給這些應用程式中的使用者。</span><span class="sxs-lookup"><span data-stu-id="a94c6-201">If the sensitivity label has only the Word, PowerPoint, and Excel option enabled, the label will appear to users only in those apps.</span></span>
- <span data-ttu-id="a94c6-202">如果敏感度標籤同時啟用了這兩個選項，則標籤將顯示給所有可用應用程式中的使用者：Outlook、Word、PowerPoint 和 Excel。</span><span class="sxs-lookup"><span data-stu-id="a94c6-202">If the sensitivity label has both options enabled, the label will appear to users in all of the available apps: Outlook, Word, PowerPoint, and Excel.</span></span>

<span data-ttu-id="a94c6-203">可讓使用者指派權限的敏感度標籤只能透過使用者手動來套用至內容；它不能自動套用，也不能作為推薦標籤。</span><span class="sxs-lookup"><span data-stu-id="a94c6-203">A sensitivity label that lets users assign permissions can be applied to content only manually by users; it can't be auto-applied or used as a recommended label.</span></span>

> [!NOTE]
> <span data-ttu-id="a94c6-204">讓使用者指派權限需要訂閱 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="a94c6-204">Letting users assign permissions requires an Azure Information Protection subscription.</span></span> <span data-ttu-id="a94c6-205">若要在 Word、PowerPoint 和 Excel 中使用此功能，您必須下載並安裝 [Azure 資訊保護統一標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-205">To use this feature in Word, PowerPoint, and Excel, you must download and install the [Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> <span data-ttu-id="a94c6-206">我們正努力在這些 Office 應用程式中對此功能提供原生支援，這樣它們就不需要安裝 Azure 資訊保護用戶端。</span><span class="sxs-lookup"><span data-stu-id="a94c6-206">We're working on native support for this feature in these Office apps, so that they won't require the Azure Information Protection client.</span></span> <span data-ttu-id="a94c6-207">此外，用戶端僅能在 Windows 上執行，因此 Mac、iOS、Android 或網頁版 Office 尚不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="a94c6-207">Also, the client runs only on Windows, so this feature is not yet supported on Mac, iOS, Android, or Office for the web.</span></span>

![使用者定義權限的加密設定](media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a><span data-ttu-id="a94c6-209">Outlook 限制</span><span class="sxs-lookup"><span data-stu-id="a94c6-209">Outlook restrictions</span></span>

<span data-ttu-id="a94c6-210">在 Outlook 中，當使用者套用的敏感標籤可允許他們指派郵件的權限時，限制與 [不可轉寄] 選項相同。</span><span class="sxs-lookup"><span data-stu-id="a94c6-210">In Outlook, when a user applies a sensitivity label that lets them assign permissions to a message, the restrictions are the same as the Do Not Forward option.</span></span> <span data-ttu-id="a94c6-211">使用者會在郵件頂端看到標籤名稱和描述，指出內容已受到保護。</span><span class="sxs-lookup"><span data-stu-id="a94c6-211">The user will see the label name and description at the top of the message, which indicates the content's being protected.</span></span> <span data-ttu-id="a94c6-212">與 Word、PowerPoint 和 Excel 不同的是 (請參閱[下一節](#word-powerpoint-and-excel-permissions))，使用者不會收到選取特定權限的提示。</span><span class="sxs-lookup"><span data-stu-id="a94c6-212">Unlike Word, PowerPoint, and Excel (see the [next section](#word-powerpoint-and-excel-permissions)), users aren't prompted to select specific permissions.</span></span>

![套用至 Outlook 郵件的敏感度標籤](media/sensitivity-label-outlook-protection-applied.png)

<span data-ttu-id="a94c6-214">將 [不可轉寄] 選項套用到電子郵件時，電子郵件會加密而且收件者必須經過驗證。</span><span class="sxs-lookup"><span data-stu-id="a94c6-214">When the Do Not Forward option is applied to an email, the email is encrypted and recipients must be authenticated.</span></span> <span data-ttu-id="a94c6-215">收件者無法轉寄、列印或複製該電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a94c6-215">Then, the recipients cannot forward it, print it, or copy from it.</span></span> <span data-ttu-id="a94c6-216">例如，在 Outlook 用戶端中，無法使用 [轉寄] 按鈕、[另存新檔] 和 [列印] 功能表選項，且您無法在 [收件人]、[副本] 或 [密件副本] 方塊中新增或變更收件者。</span><span class="sxs-lookup"><span data-stu-id="a94c6-216">For example, in the Outlook client, the Forward button is not available, the Save As and Print menu options are not available, and you cannot add or change recipients in the To, Cc, or Bcc boxes.</span></span>

<span data-ttu-id="a94c6-217">附加到電子郵件的未受保護的 Office 文件會自動繼承相同的限制。</span><span class="sxs-lookup"><span data-stu-id="a94c6-217">Unprotected Office documents that are attached to the email automatically inherit the same restrictions.</span></span> <span data-ttu-id="a94c6-218">套用至這些文件的使用權限是 [編輯內容]、[編輯]；[儲存]；[檢視]、[開啟]、[讀取]；和 [允許巨集]。</span><span class="sxs-lookup"><span data-stu-id="a94c6-218">The usage rights applied to these documents are Edit Content, Edit; Save; View, Open, Read; and Allow Macros.</span></span> <span data-ttu-id="a94c6-219">如果使用者想要不同的附件使用權限，或者附件不是支援此繼承保護的 Office 文件，則使用者需要在將文件附加到電子郵件之前保護該檔案。</span><span class="sxs-lookup"><span data-stu-id="a94c6-219">If the user wants different usage rights for an attachment, or the attachment is not an Office document that supports this inherited protection, the user needs to protect the file before attaching it to the email.</span></span>

### <a name="word-powerpoint-and-excel-permissions"></a><span data-ttu-id="a94c6-220">Word、PowerPoint 和 Excel 權限</span><span class="sxs-lookup"><span data-stu-id="a94c6-220">Word, PowerPoint, and Excel permissions</span></span>

<span data-ttu-id="a94c6-221">在 Word、PowerPoint 和 Excel 中，當使用者套用可讓他們指派文件權限的敏感度標籤時，系統會提示他們保護內容，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a94c6-221">In Word, PowerPoint, and Excel, when a user applies a sensitivity label that lets them assign permissions to a document, they are prompted to protect the content as shown below.</span></span>

<span data-ttu-id="a94c6-222">使用者可以：</span><span class="sxs-lookup"><span data-stu-id="a94c6-222">The user can modify records.</span></span>

- <span data-ttu-id="a94c6-223">選取權限等級，例如檢視者 (指派 [僅檢視] 權限) 或共同作者 (指派 [檢視]、[編輯]、[複製] 和 [列印] 權限)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-223">Select a permission level, such as Viewer (which assigns View Only permission) or Co-Author (which assigns View, Edit, Copy, and Print permissions).</span></span>
- <span data-ttu-id="a94c6-224">選取使用者、群組或組織。</span><span class="sxs-lookup"><span data-stu-id="a94c6-224">Select users, groups, or organizations.</span></span> <span data-ttu-id="a94c6-225">這可能包括組織內部或外部的人員。</span><span class="sxs-lookup"><span data-stu-id="a94c6-225">This can include people both inside or outside your organizations.</span></span>
- <span data-ttu-id="a94c6-226">設定到期日，到期之後所選使用者就無法存取內容。</span><span class="sxs-lookup"><span data-stu-id="a94c6-226">Set an expiration date, after which the selected users cannot access the content.</span></span> <span data-ttu-id="a94c6-227">如需詳細資訊, 請參閱前一節的[用於離線存取的 Rights Management 使用授權](#rights-management-use-license-for-offline-access)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-227">For more information, see the above section [Rights Management use license for offline access](#rights-management-use-license-for-offline-access).</span></span>

![讓使用者以自訂權限進行保護的選項](media/sensitivity-aip-custom-permissions-dialog.png)

## <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a><span data-ttu-id="a94c6-229">套用標籤時，現有的加密會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="a94c6-229">What happens to existing encryption when a label's applied</span></span>

<span data-ttu-id="a94c6-230">將敏感度標籤套用至內容之前，使用者可能已透過套用其他的保護設定來加密內容。</span><span class="sxs-lookup"><span data-stu-id="a94c6-230">Before a sensitivity label is applied to content, it's possible that a user already encrypted the content by applying some other protection setting.</span></span> <span data-ttu-id="a94c6-231">例如，使用者可能已套用：</span><span class="sxs-lookup"><span data-stu-id="a94c6-231">For example, a user might have applied:</span></span>

- <span data-ttu-id="a94c6-232">[不可轉寄]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="a94c6-232">The **Do Not Forward** option.</span></span>
- <span data-ttu-id="a94c6-233">使用 Azure 資訊保護整合標籤用戶端的自訂保護。</span><span class="sxs-lookup"><span data-stu-id="a94c6-233">Custom protection by using the Azure Information Protection unified labeling client.</span></span>
- <span data-ttu-id="a94c6-234">會加密內容但未與標籤關聯的 Azure Rights Management Service (RMS) 範本。</span><span class="sxs-lookup"><span data-stu-id="a94c6-234">An Azure Rights Management Service (RMS) template that encrypts the content but is not associated with a label.</span></span>

<span data-ttu-id="a94c6-235">下表說明對該內容套用敏感度標籤時，現有的加密會發生的情況。</span><span class="sxs-lookup"><span data-stu-id="a94c6-235">This table describe what happens to existing encyption when a sensitivity label is applied to that content.</span></span>
<br/>
<br/>

| |<span data-ttu-id="a94c6-236">**使用者套用將加密關閉的敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="a94c6-236">**User applies a sensitivity label with encryption turned off**</span></span>|<span data-ttu-id="a94c6-237">**使用者套用將加密開啟的敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="a94c6-237">**User applies a sensitivity label with encryption turned on**</span></span>|<span data-ttu-id="a94c6-238">**使用者套用具有移除保護的標籤**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a94c6-238">**User applies a label with Remove Protection**<sup>1</sup></span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a94c6-239">**不可轉寄**</span><span class="sxs-lookup"><span data-stu-id="a94c6-239">**Do Not Forward**</span></span>|<span data-ttu-id="a94c6-240">會移除 [電子郵件 - 保護]</span><span class="sxs-lookup"><span data-stu-id="a94c6-240">Email - Protection is removed</span></span><br/><span data-ttu-id="a94c6-241">會保留 [文件 - 保護]</span><span class="sxs-lookup"><span data-stu-id="a94c6-241">Document - Protection is preserved</span></span>|<span data-ttu-id="a94c6-242">會套用標籤保護</span><span class="sxs-lookup"><span data-stu-id="a94c6-242">Label protection is applied</span></span>|<span data-ttu-id="a94c6-243">會移除 [不可轉寄]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a94c6-243">**Do Not Forward** is removed</span></span>|
|<span data-ttu-id="a94c6-244">**自訂保護**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a94c6-244">**Custom protection**<sup>1</sup></span></span>|<span data-ttu-id="a94c6-245">會保留保護</span><span class="sxs-lookup"><span data-stu-id="a94c6-245">Protection is preserved</span></span>|<span data-ttu-id="a94c6-246">會套用標籤保護</span><span class="sxs-lookup"><span data-stu-id="a94c6-246">Label protection is applied</span></span>|<span data-ttu-id="a94c6-247">會移除自訂保護</span><span class="sxs-lookup"><span data-stu-id="a94c6-247">Custom protection is removed</span></span>|
|<span data-ttu-id="a94c6-248">**Azure RMS 範本**</span><span class="sxs-lookup"><span data-stu-id="a94c6-248">**Azure RMS template**</span></span>|<span data-ttu-id="a94c6-249">會保留保護</span><span class="sxs-lookup"><span data-stu-id="a94c6-249">Protection is preserved</span></span>|<span data-ttu-id="a94c6-250">會套用標籤保護</span><span class="sxs-lookup"><span data-stu-id="a94c6-250">Label protection is applied</span></span>|<span data-ttu-id="a94c6-251">會移除自訂保護</span><span class="sxs-lookup"><span data-stu-id="a94c6-251">Custom protection is removed</span></span>|

<span data-ttu-id="a94c6-252"><sup>1</sup> 僅 Azure 資訊保護標籤用戶端中支援此功能。</span><span class="sxs-lookup"><span data-stu-id="a94c6-252"><sup>1</sup>This is supported only in the Azure Information Protection labeling client.</span></span>

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a><span data-ttu-id="a94c6-253">將加密內容儲存在 OneDrive 和 SharePoint 中</span><span class="sxs-lookup"><span data-stu-id="a94c6-253">Storing encrypted content in OneDrive and SharePoint</span></span>

<span data-ttu-id="a94c6-p129">請注意，當加密套用至 OneDrive 和 SharePoint 中儲存的檔案時，服務無法處理這些檔案的內容。這表示共同撰寫、電子文件探索、搜尋、Delve 和其他共同作業功能等這類功能無法運作。此外，資料外洩防護 (DLP) 原則只可使用中繼資料 (包括 Office 365 標籤)，但無法使用加密檔案的內容 (例如檔案內的信用卡號碼)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p129">Be aware that when encryption is applied to files stored in OneDrive and SharePoint, the service cannot process the contents of these files. This means that features such as co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. Also, data loss prevention (DLP) policies can work only with the metadata (including Office 365 labels) but not the contents of encrypted files (such as credit card numbers within files).</span></span>

<span data-ttu-id="a94c6-p130">這僅適用於 OneDrive 和 SharePoint 中儲存的內容。在 Exchange Online 中，郵件流程規則 (也稱為傳輸規則) 會使用[進階使用者帳戶](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-super-users)，讓他們可以掃描加密內容，並強制執行 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p130">This applies only to content stored in OneDrive and SharePoint. In Exchange Online, mail flow rules (also known as transport rules) use the [super user account](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-super-users) so that they can scan encrypted content and enforce DLP policies.</span></span>

## <a name="important-prerequisites"></a><span data-ttu-id="a94c6-259">重要的先決條件</span><span class="sxs-lookup"><span data-stu-id="a94c6-259">Important prerequisites</span></span>

<span data-ttu-id="a94c6-260">在可以使用加密之前，您可能需要執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="a94c6-260">Before you can use encryption, you might need to perform these tasks.</span></span>

### <a name="activating-azure-rights-management"></a><span data-ttu-id="a94c6-261">啟動 Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="a94c6-261">Activating Azure Rights Management</span></span>

<span data-ttu-id="a94c6-p131">若要使用敏感度標籤中的加密，需要在您的租用戶中啟動 Azure Rights Management 服務。在較新的租用戶中，此服務預設為開啟，但您可能需要手動啟動此服務。如需詳細資訊，請參閱[啟用 Azure Rights Management](https://docs.microsoft.com/zh-TW/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p131">To use encryption in sensitivity labels, the Azure Rights Management service needs to be activated in your tenant. In newer tenants, the service is on by default, but you might need to manually activate the service. For more information, see [Activating Azure Rights Management](https://docs.microsoft.com/zh-TW/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="a94c6-265">設定 Exchange 進行 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="a94c6-265">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="a94c6-p132">在使用者可在 Outlook 中套用標籤以保護其電子郵件之前，不必設定 Exchange 進行 Azure 資訊保護。不過，直到設定 Exchange 進行 Azure 資訊保護前，您都無法取得使用 Azure Rights Management 保護與 Exchange 搭配的完整功能。</span><span class="sxs-lookup"><span data-stu-id="a94c6-p132">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to protect their emails. However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
 
<span data-ttu-id="a94c6-268">例如，使用者無法在行動電話或 Outlook 網頁版上檢視受保護的電子郵件，無法為受保護的電子郵件編製索引進行搜尋，而且您無法設定 Exchange Online DLP 進行 Rights Management 保護。</span><span class="sxs-lookup"><span data-stu-id="a94c6-268">For example, users cannot view protected emails on mobile phones or with Outlook on the web, protected emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 

<span data-ttu-id="a94c6-269">若要確保 Exchange 可以支援這些額外情節，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="a94c6-269">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="a94c6-270">針對 Exchange Online，請參閱 [Exchange Online：IRM 設定](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-office365#exchange-online-irm-configuration)的指示。</span><span class="sxs-lookup"><span data-stu-id="a94c6-270">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-office365#exchange-online-irm-configuration).</span></span>
- <span data-ttu-id="a94c6-271">針對 Exchange 內部部署，您必須部署 [RMS 連接器和設定您的 Exchange Server](https://docs.microsoft.com/zh-TW/azure/information-protection/deploy-rms-connector)。</span><span class="sxs-lookup"><span data-stu-id="a94c6-271">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/zh-TW/azure/information-protection/deploy-rms-connector).</span></span> 
