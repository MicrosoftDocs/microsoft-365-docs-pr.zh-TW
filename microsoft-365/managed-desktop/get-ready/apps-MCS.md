---
title: 使用 Microsoft 諮詢服務
description: 準備與步驟遵循以搭配使用 MCS 来封裝您的應用程式
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 應用程式，MCS，封裝
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 39a5102d045d9ed79b631a3b477bd1c72dea76de
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/12/2019
ms.locfileid: "34918720"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="63ad4-104">使用 Microsoft 諮詢服務</span><span class="sxs-lookup"><span data-stu-id="63ad4-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="63ad4-105">您可以邀請與 Microsoft 諮詢服務 (MCS) 若要取得您封裝搭配 Microsoft 受管理的電腦使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="63ad4-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="63ad4-106">確切詳細資料，使用您的帳戶代表連絡 MCS 和您的特定應用程式封裝專案的範圍。</span><span class="sxs-lookup"><span data-stu-id="63ad4-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="63ad4-107">角色和責任</span><span class="sxs-lookup"><span data-stu-id="63ad4-107">Roles and responsibilities</span></span>

<span data-ttu-id="63ad4-108">若要搭配 MCS 應用程式封裝，**您必須提供下列項目**：</span><span class="sxs-lookup"><span data-stu-id="63ad4-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="63ad4-109">來源安裝程式檔案 （例如，setup.exe 或.msi）。</span><span class="sxs-lookup"><span data-stu-id="63ad4-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="63ad4-110">指定詳細資料的最終安裝應該看起來大概安裝指示。</span><span class="sxs-lookup"><span data-stu-id="63ad4-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="63ad4-111">例如，應該會有應用程式的桌面捷徑嗎？</span><span class="sxs-lookup"><span data-stu-id="63ad4-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="63ad4-112">應用程式的可見性為何？</span><span class="sxs-lookup"><span data-stu-id="63ad4-112">What should the app's visibility be?</span></span> <span data-ttu-id="63ad4-113">應用程式連線至伺服器，並若是如此，哪一種？</span><span class="sxs-lookup"><span data-stu-id="63ad4-113">Should the app connect to a server and if so, which one?</span></span> <!--For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx). -->
- <span data-ttu-id="63ad4-114">您必須執行您自己的接受度測試來確認應用程式在您的環境中的需要般運作。</span><span class="sxs-lookup"><span data-stu-id="63ad4-114">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="63ad4-115">**這些動作會負責 MCS:**</span><span class="sxs-lookup"><span data-stu-id="63ad4-115">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="63ad4-116">檢查應用程式會禁止或限制 Microsoft 受管理電腦環境中。</span><span class="sxs-lookup"><span data-stu-id="63ad4-116">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="63ad4-117">測試安裝、 啟動和解除安裝的應用程式，以確保與 Windows 10 相容性。</span><span class="sxs-lookup"><span data-stu-id="63ad4-117">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="63ad4-118">如果 MCS 」 會探索的相容性問題，他們會交給修復的[桌面應用程式保證](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure)程式應用程式。</span><span class="sxs-lookup"><span data-stu-id="63ad4-118">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="63ad4-119">封裝您的規格的應用程式，然後藉由使用 Microsoft Intune 來測試應用程式部署。</span><span class="sxs-lookup"><span data-stu-id="63ad4-119">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="63ad4-120">應用程式傳遞排程</span><span class="sxs-lookup"><span data-stu-id="63ad4-120">App delivery schedule</span></span>

<span data-ttu-id="63ad4-121">啟動封裝程序將應用程式資訊上傳至 Microsoft 受管理電腦入口網站。</span><span class="sxs-lookup"><span data-stu-id="63ad4-121">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="63ad4-122">封裝小組會檢閱新的提交每個星期四。</span><span class="sxs-lookup"><span data-stu-id="63ad4-122">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="63ad4-123">檢閱並封裝之後, 的封裝應用程式會傳遞下列星期五。</span><span class="sxs-lookup"><span data-stu-id="63ad4-123">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="63ad4-124">最多五個應用程式每週可封裝開始，但服務可以調整以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="63ad4-124">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![顯示應用程式檢閱、 封裝，並傳遞日期的行事曆](images/MCS-cal.png)

<span data-ttu-id="63ad4-126">一旦應用程式已送達，您就會收到通知。</span><span class="sxs-lookup"><span data-stu-id="63ad4-126">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="63ad4-127">此時，您必須 21 天關閉執行接受度測試並簽署 Microsoft 受管理電腦入口網站中的工作。</span><span class="sxs-lookup"><span data-stu-id="63ad4-127">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="63ad4-128">如果您接受度測試期間發現應用程式的一些問題拒絕 Microsoft 受管理電腦入口網站中的應用程式，您將了解及解決問題 MCS packager 與連線透過電子郵件。</span><span class="sxs-lookup"><span data-stu-id="63ad4-128">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="63ad4-129">測試帳戶和環境</span><span class="sxs-lookup"><span data-stu-id="63ad4-129">Testing accounts and environment</span></span>

<span data-ttu-id="63ad4-130">針對封裝小組，以完成移轉至 Microsoft Intune 我們建議您提供特定的權限：</span><span class="sxs-lookup"><span data-stu-id="63ad4-130">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="63ad4-131">Microsoft Intune 應用程式部署功能來新增及指派應用程式封裝程式存取</span><span class="sxs-lookup"><span data-stu-id="63ad4-131">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="63ad4-132">測試群組、 使用者帳戶和授權 packagers 能夠測試應用程式</span><span class="sxs-lookup"><span data-stu-id="63ad4-132">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="63ad4-133">MCS 會使用這些權限來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="63ad4-133">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="63ad4-134">確保虛擬機器設定為 Microsoft 受管理的電腦上都有適用於應用程式</span><span class="sxs-lookup"><span data-stu-id="63ad4-134">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="63ad4-135">將應用程式上傳至 Microsoft Intune 部署到您的使用者</span><span class="sxs-lookup"><span data-stu-id="63ad4-135">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="63ad4-136">沒有這些權限，很可能 MCS 往前移，但他們將無法上傳至您環境的應用程式。</span><span class="sxs-lookup"><span data-stu-id="63ad4-136">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


