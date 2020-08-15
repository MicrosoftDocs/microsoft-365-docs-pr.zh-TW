---
title: 修正 Microsoft 365 的目錄同步處理問題
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: 說明 Office 365 中目錄同步處理問題的常見原因，並提供一些協助疑難排解並解決問題的方法。
ms.openlocfilehash: 80b4a88e91230a8736f209ecd65c58b2882c25d6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688791"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="d2429-103">修正 Microsoft 365 的目錄同步處理問題</span><span class="sxs-lookup"><span data-stu-id="d2429-103">Fixing problems with directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="d2429-104">您可以使用目錄同步處理繼續透過內部部署方式管理使用者和群組，以及同步處理雲端的新增、刪除和變更。</span><span class="sxs-lookup"><span data-stu-id="d2429-104">With directory synchronization, you can continue to manage users and groups on-premises and synchronize additions, deletions, and changes to the cloud.</span></span> <span data-ttu-id="d2429-105">但是，安裝程式有些複雜，而且有時很難找出問題來源。</span><span class="sxs-lookup"><span data-stu-id="d2429-105">But setup is a little complicated and it can sometimes be difficult to identify the source of problems.</span></span> <span data-ttu-id="d2429-106">我們有資源可以協助您辨別潛在問題並加以修正。</span><span class="sxs-lookup"><span data-stu-id="d2429-106">We have resources to help you identify potential issues and fix them.</span></span>
  
## <a name="how-do-i-know-if-something-is-wrong"></a><span data-ttu-id="d2429-107">要如何知道發生問題了？</span><span class="sxs-lookup"><span data-stu-id="d2429-107">How do I know if something is wrong?</span></span>

<span data-ttu-id="d2429-108">發生問題時，Microsoft 365 系統管理中心中的 [DirSync 狀態] 磚會在第一時間表示有問題發生。</span><span class="sxs-lookup"><span data-stu-id="d2429-108">The first indication that something is wrong is when the DirSync Status tile in the Microsoft 365 admin center indicates there is a problem.</span></span>
  
<span data-ttu-id="d2429-109">您也會收到 Microsoft 365 寄送的郵件通知 (會傳送到備用電子郵件與您的系統管理員電子郵件)，指出您的租用戶目前發生目錄同步處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="d2429-109">You will also receive a mail (to the alternate email and to your admin email) from Microsoft 365 that indicates your tenant has encountered directory synchronization errors.</span></span> <span data-ttu-id="d2429-110">如需詳細資料，請參閱[識別 Microsoft 365 中的目錄同步處理錯誤](identify-directory-synchronization-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="d2429-110">For details see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a><span data-ttu-id="d2429-111">如何獲取 Azure Active Directory Connect 工具?</span><span class="sxs-lookup"><span data-stu-id="d2429-111">How do I get Azure Active Directory Connect tool?</span></span>

<span data-ttu-id="d2429-112">在 [Microsoft 365 系統管理中心](https://admin.microsoft.com)中，瀏覽至 **[使用者]** \> **[作用中使用者]**。</span><span class="sxs-lookup"><span data-stu-id="d2429-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), navigate to **Users** \> **Active users**.</span></span> <span data-ttu-id="d2429-113">按一下 **[其他]** 功能表 (三個點) 並選取 **[目錄同步處理]**。</span><span class="sxs-lookup"><span data-stu-id="d2429-113">Click the **More** menu (three dots) and select **Directory synchronization**.</span></span> 
  
<span data-ttu-id="d2429-114">請遵循[精靈中的指示](set-up-directory-synchronization.md)以下載 Aure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="d2429-114">Follow the [instructions in the wizard](set-up-directory-synchronization.md) to download Azure AD Connect.</span></span> 
  
<span data-ttu-id="d2429-115">如果您仍在使用 Azure Active Directory (Azure AD) 同步處理 (DirSync)，請參閱[如何疑難排解 Microsoft 365 中的 Azure Active Directory 同步處理工具安裝和設定精靈錯誤訊息](https://go.microsoft.com/fwlink/p/?LinkId=396717)，以取得安裝同步處理的系統需求、所需的權限及如何疑難排解常見錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d2429-115">If you are still using Azure Active Directory (Azure AD) Sync (DirSync), take a look at [How to troubleshoot Azure Active Directory Sync Tool installation and Configuration Wizard error messages in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=396717) for information about the system requirements to install dirsync, the permissions you need, and how to troubleshoot common errors.</span></span> 
  
<span data-ttu-id="d2429-116">若要從 Azure AD 同步服務更新至 Azure AD Connect，請參閱 [[升級指示]](https://go.microsoft.com/fwlink/p/?LinkId=733240)。</span><span class="sxs-lookup"><span data-stu-id="d2429-116">To update from Azure AD Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span>
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a><span data-ttu-id="d2429-117">解決 Microsoft 365 中目錄同步處理問題的常見原因</span><span class="sxs-lookup"><span data-stu-id="d2429-117">Resolving common causes of problems with directory synchronization in Microsoft 365</span></span>

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a><span data-ttu-id="d2429-118">已同步處理的物件並未出現或在線上更新，或從服務收到同步處理錯誤報告。</span><span class="sxs-lookup"><span data-stu-id="d2429-118">Synchronized objects aren't appearing or updating online, or I'm getting synchronization error reports from the Service.</span></span>

- [<span data-ttu-id="d2429-119">身分識別同步及重複屬性復原</span><span class="sxs-lookup"><span data-stu-id="d2429-119">Identity synchronization and duplicate attribute resiliency</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a><span data-ttu-id="d2429-120">我的系統管理中心出現警示，或收到最近未進行同步處理事件的自動發送電子郵件</span><span class="sxs-lookup"><span data-stu-id="d2429-120">I have an alert in the admin center, or am receiving automated emails that there hasn't been a recent synchronization event</span></span>
- [<span data-ttu-id="d2429-121">針對 Azure AD Connect 的連線問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="d2429-121">Troubleshoot connectivity issues with Azure AD Connect</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [<span data-ttu-id="d2429-122">Azure AD Connect 帳戶和權限</span><span class="sxs-lookup"><span data-stu-id="d2429-122">Azure AD Connect Accounts and permissions</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=820598)
- [<span data-ttu-id="d2429-123">Azure AD Connect 同步：如何管理 Azure AD 服務帳戶</span><span class="sxs-lookup"><span data-stu-id="d2429-123">Azure AD Connect sync: How to manage the Azure AD service account</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [<span data-ttu-id="d2429-124">Azure Active Directory 目錄同步處理停止，或者系統警告您超過一天未登錄同步處理</span><span class="sxs-lookup"><span data-stu-id="d2429-124">Directory synchronization to Azure Active Directory stops or you're warned that sync hasn't registered in more than a day</span></span>](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a><span data-ttu-id="d2429-125">密碼雜湊未同步處理，或我在系統管理中心看到最近未進行同步處理密碼雜湊的警示</span><span class="sxs-lookup"><span data-stu-id="d2429-125">Password hashes aren't synchronizing, or I'm seeing an alert in the admin center that there hasn't been a recent password hash synchronization</span></span>
- [<span data-ttu-id="d2429-126">使用 Azure AD Connect 同步處理來實作密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="d2429-126">Implementing password hash synchronization with Azure AD Connect sync</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a><span data-ttu-id="d2429-127">我看到超過物件配額的警示</span><span class="sxs-lookup"><span data-stu-id="d2429-127">I'm seeing an alert that Object quota exceeded</span></span>
- <span data-ttu-id="d2429-128">我們有內建物件配額可協助保護服務。</span><span class="sxs-lookup"><span data-stu-id="d2429-128">We have a built-in object quota to help protect the service.</span></span> <span data-ttu-id="d2429-129">如果您的目錄中有太多需要同步處理至 Microsoft 365 的物件，則必須 [連絡商務產品的客戶支援](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)以增加您的配額。</span><span class="sxs-lookup"><span data-stu-id="d2429-129">If you have too many objects in your directory that need to sync to Microsoft 365, you'll have to [Contact support for business products](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to increase your quota.</span></span>

### <a name="i-need-to-know-which-attributes-are-synchronized"></a><span data-ttu-id="d2429-130">我需要知道哪些屬性已同步處理</span><span class="sxs-lookup"><span data-stu-id="d2429-130">I need to know which attributes are synchronized</span></span>
- <span data-ttu-id="d2429-131">您可以在 [[這裡]](https://go.microsoft.com/fwlink/p/?LinkId=396719) 找到內部部署與雲端之間同步處理的所有屬性清單。</span><span class="sxs-lookup"><span data-stu-id="d2429-131">You can find a list of all the attributes that are synced between on-premises and the cloud [right here](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a><span data-ttu-id="d2429-132">我無法管理或移除已同步處理到雲端的物件</span><span class="sxs-lookup"><span data-stu-id="d2429-132">I can't manage or remove objects that were synchronized to the cloud</span></span>
- <span data-ttu-id="d2429-133">您是否準備好僅管理雲端中的物件？</span><span class="sxs-lookup"><span data-stu-id="d2429-133">Are you ready to manage objects in the cloud only?</span></span> <span data-ttu-id="d2429-134">或者，是否有透過內部部署刪除但卡在雲端中的物件？</span><span class="sxs-lookup"><span data-stu-id="d2429-134">Or is there an object that was deleted on-premises, but is stuck in the cloud?</span></span> <span data-ttu-id="d2429-135">請參閱此 [在同步處理期間進行疑難排解錯誤](https://go.microsoft.com/fwlink/p/?linkid=842044) 和 [支援文章](https://go.microsoft.com/fwlink/p/?LinkId=396720)以獲取解決這些問題的指南。</span><span class="sxs-lookup"><span data-stu-id="d2429-135">Take a look at this [Troubleshooting Errors during synchronization](https://go.microsoft.com/fwlink/p/?linkid=842044) and [support article](https://go.microsoft.com/fwlink/p/?LinkId=396720) for guidance on how to resolve these issues.</span></span>

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a><span data-ttu-id="d2429-136">我收到公司超出可同步處理之物件數目的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="d2429-136">I got an error message that my company has exceeded the number of objects that can be synchronized</span></span>
- <span data-ttu-id="d2429-137">如需此問題的詳細資訊，請參閱 [[這裡]](https://go.microsoft.com/fwlink/p/?LinkId=396721)。</span><span class="sxs-lookup"><span data-stu-id="d2429-137">You can read more about this issue [here](https://go.microsoft.com/fwlink/p/?LinkId=396721).</span></span>
   
## <a name="other-resources"></a><span data-ttu-id="d2429-138">其他資源</span><span class="sxs-lookup"><span data-stu-id="d2429-138">Other resources</span></span>

- [<span data-ttu-id="d2429-139">修正使用者主要名稱重複問題的腳本</span><span class="sxs-lookup"><span data-stu-id="d2429-139">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
    
- [<span data-ttu-id="d2429-140">如何準備無法路由傳送的網域 (例如.local 網域) 以用於目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="d2429-140">How to prepare a non-routable domain (such as .local domain) for directory synchronization</span></span>](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [<span data-ttu-id="d2429-141">計算已同步處理物件之總數的腳本</span><span class="sxs-lookup"><span data-stu-id="d2429-141">Script to count total synchronized objects</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396726)
    
- [<span data-ttu-id="d2429-142">疑難排解 AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="d2429-142">Troubleshoot AD FS 2.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [<span data-ttu-id="d2429-143">針對已啟用郵件功能的群組，使用 PowerShell 修正空的 DisplayName 屬性</span><span class="sxs-lookup"><span data-stu-id="d2429-143">Use PowerShell to fix empty DisplayName attributes for mail-enabled groups</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [<span data-ttu-id="d2429-144">使用 PowerShell 修正 UPN 重複的問題</span><span class="sxs-lookup"><span data-stu-id="d2429-144">Use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [<span data-ttu-id="d2429-145">使用 PowerShell 修正電子郵件地址重複的問題</span><span class="sxs-lookup"><span data-stu-id="d2429-145">Use PowerShell to fix duplicate email addresses</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396731)
    
