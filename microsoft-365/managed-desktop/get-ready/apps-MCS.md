---
title: 使用 Microsoft 諮詢服務
description: 準備使用 MCS 以封裝應用程式的準備工作和步驟
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 7a967f5e4b2678b55ed87f2eaa68590703c55805
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840883"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="f89bf-104">使用 Microsoft 諮詢服務</span><span class="sxs-lookup"><span data-stu-id="f89bf-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="f89bf-105">您可以與 Microsoft 諮詢服務 (MCS) 接洽，以便使用 Microsoft 受管理的電腦封裝您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f89bf-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="f89bf-106">如需確切的詳細資訊，請與您的客戶代表連絡 MCS，以定義特定應用程式封裝專案範圍。</span><span class="sxs-lookup"><span data-stu-id="f89bf-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="f89bf-107">角色和責任</span><span class="sxs-lookup"><span data-stu-id="f89bf-107">Roles and responsibilities</span></span>

<span data-ttu-id="f89bf-108">若要使用 MCS 應用程式封裝，**您必須提供下列項目**：</span><span class="sxs-lookup"><span data-stu-id="f89bf-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="f89bf-109">來源 installer 檔案 (例如，setup.exe 或 .msi) 。</span><span class="sxs-lookup"><span data-stu-id="f89bf-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="f89bf-110">安裝指示，指定安裝完成的外觀詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f89bf-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="f89bf-111">例如，應用程式應該有桌面快速鍵嗎？</span><span class="sxs-lookup"><span data-stu-id="f89bf-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="f89bf-112">應用程式可見度應該為何？</span><span class="sxs-lookup"><span data-stu-id="f89bf-112">What should the app's visibility be?</span></span> <span data-ttu-id="f89bf-113">應用程式應該連線到伺服器嗎？若是如此，哪一個伺服器？</span><span class="sxs-lookup"><span data-stu-id="f89bf-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="f89bf-114">如需詳細資訊，請參閱[應用程式封裝要求範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。</span><span class="sxs-lookup"><span data-stu-id="f89bf-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="f89bf-115">您必須執行自己的接受度測試，以驗證此應用程式在您的環境中能夠正常運作。</span><span class="sxs-lookup"><span data-stu-id="f89bf-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="f89bf-116">**MCS 將處理下列動作：**</span><span class="sxs-lookup"><span data-stu-id="f89bf-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="f89bf-117">檢查此應用程式在 Microsoft 受管理的電腦環境中是否禁止或受限制。</span><span class="sxs-lookup"><span data-stu-id="f89bf-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="f89bf-118">測試安裝、啟動及解除安裝應用程式，以確保與 Windows 10 相容。</span><span class="sxs-lookup"><span data-stu-id="f89bf-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="f89bf-119">如果 MCS 發現相容性問題，將會將應用程式提交給應用程式，以 [確保](/fasttrack/products-and-capabilities#app-assure) 修復程式的執行。</span><span class="sxs-lookup"><span data-stu-id="f89bf-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="f89bf-120">以您的規格封裝應用程式，然後使用 Microsoft Intune 測試應用程式部署。</span><span class="sxs-lookup"><span data-stu-id="f89bf-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="f89bf-121">應用程式交付排程</span><span class="sxs-lookup"><span data-stu-id="f89bf-121">App delivery schedule</span></span>

<span data-ttu-id="f89bf-122">將應用程式資訊上傳到 Microsoft 受管理的電腦入口網站來啟動封裝程序。</span><span class="sxs-lookup"><span data-stu-id="f89bf-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="f89bf-123">封裝小組每星期四都會檢閱新的提交。</span><span class="sxs-lookup"><span data-stu-id="f89bf-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="f89bf-124">檢閱和封裝之後，封裝的應用程式會在下星期五交付。</span><span class="sxs-lookup"><span data-stu-id="f89bf-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="f89bf-125">一開始每週最多可以封裝五個應用程式，但能根據您的需求調整服務。</span><span class="sxs-lookup"><span data-stu-id="f89bf-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![行事曆顯示應用程式在星期四輸入 (在此範例中為 21 日)，第二天做媒體驗證，下星期一封裝 (25 日)，之後的星期五交付應用程式 (29 日)](../../media/MCS-cal.png)

<span data-ttu-id="f89bf-127">應用程式交付之後，您會收到通知。</span><span class="sxs-lookup"><span data-stu-id="f89bf-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="f89bf-128">在該點，您可以在 Microsoft 受管理的電腦入口網站中執行接受度測試並核准工作。</span><span class="sxs-lookup"><span data-stu-id="f89bf-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="f89bf-129">如果您在接受度測試期間發現應用程式有些問題，請在 Microsoft 受管理的電腦入口網站中拒絕該應用程式，您將會透過電子郵件與 MCS 封裝程式連線，以了解並解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="f89bf-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="f89bf-130">測試帳戶和環境</span><span class="sxs-lookup"><span data-stu-id="f89bf-130">Testing accounts and environment</span></span>

<span data-ttu-id="f89bf-131">為了讓打包小組完成 Microsoft Intune 的遷移，我們建議您提供某些許可權：</span><span class="sxs-lookup"><span data-stu-id="f89bf-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>

- <span data-ttu-id="f89bf-132">封裝程式的 Microsoft Intune App 部署功能的存取權，以新增並指派應用程式</span><span class="sxs-lookup"><span data-stu-id="f89bf-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span>
- <span data-ttu-id="f89bf-133">搭配封裝程式的測試群組、使用者帳戶和授權，以便能夠測試應用程式</span><span class="sxs-lookup"><span data-stu-id="f89bf-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="f89bf-134">MCS 將使用這些權限來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f89bf-134">MCS will use those permissions to perform the following actions:</span></span>

- <span data-ttu-id="f89bf-135">確保應用程式能夠在 Microsoft 受管理的電腦設定之虛擬機器上正常運作</span><span class="sxs-lookup"><span data-stu-id="f89bf-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
- <span data-ttu-id="f89bf-136">將應用程式上傳到 Microsoft Intune，以便部署至您的使用者</span><span class="sxs-lookup"><span data-stu-id="f89bf-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="f89bf-137">若沒有這些使用權限，MCS 可能會繼續進行，但無法將應用程式上傳到您的環境。</span><span class="sxs-lookup"><span data-stu-id="f89bf-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
