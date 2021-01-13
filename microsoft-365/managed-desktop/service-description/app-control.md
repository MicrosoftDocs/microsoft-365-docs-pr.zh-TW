---
title: 應用程式控制
description: 如何在應用程式中使用應用程式控制及信任
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841300"
---
# <a name="app-control"></a><span data-ttu-id="c101d-104">應用程式控制</span><span class="sxs-lookup"><span data-stu-id="c101d-104">App control</span></span>

<span data-ttu-id="c101d-105">應用程式控制是 Microsoft Managed Desktop 中的選用安全性作法，可限制用戶端裝置上程式碼的執行。</span><span class="sxs-lookup"><span data-stu-id="c101d-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="c101d-106">此控制項要求只有由客戶核准的發行者清單所簽署的程式碼才能執行，以降低惡意軟體或惡意腳本的風險。</span><span class="sxs-lookup"><span data-stu-id="c101d-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="c101d-107">這個控制具有許多安全性好處，但主要目的是為了保護資料和身分識別從用戶端的漏洞。</span><span class="sxs-lookup"><span data-stu-id="c101d-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="c101d-108">Microsoft 受管理的桌面透過建立可啟用核心生產力案例的基準原則，簡化應用程式控制原則的管理。</span><span class="sxs-lookup"><span data-stu-id="c101d-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="c101d-109">您可以將信任擴充至您環境中的應用程式和腳本特有的其他簽署者。</span><span class="sxs-lookup"><span data-stu-id="c101d-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="c101d-110">任何安全性技術都需要與使用者經驗、安全性和成本之間的平衡。</span><span class="sxs-lookup"><span data-stu-id="c101d-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="c101d-111">應用程式控制可減少環境中惡意軟體的威脅，但對使用者和 IT 管理員的後續動作也會有影響。</span><span class="sxs-lookup"><span data-stu-id="c101d-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="c101d-112">**其他安全性：**</span><span class="sxs-lookup"><span data-stu-id="c101d-112">**Additional security:**</span></span>

<span data-ttu-id="c101d-113">禁止在裝置上執行應用程式控制原則所信任的應用程式或腳本。</span><span class="sxs-lookup"><span data-stu-id="c101d-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="c101d-114">**您的額外責任：**</span><span class="sxs-lookup"><span data-stu-id="c101d-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="c101d-115">您負責測試您的應用程式，以識別應用程式控制項原則是否會封鎖這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="c101d-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="c101d-116">若有 (或) 封鎖的應用程式，您就會負責識別所需的簽章詳細資料，並要求透過管理入口網站進行變更。</span><span class="sxs-lookup"><span data-stu-id="c101d-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="c101d-117">**Microsoft 受管理的桌面責任：**</span><span class="sxs-lookup"><span data-stu-id="c101d-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="c101d-118">Microsoft 受管理的桌面維護基本原則，可讓核心 Microsoft 產品（如 M365 應用程式、Windows、小組、OneDrive 等等）。</span><span class="sxs-lookup"><span data-stu-id="c101d-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="c101d-119">Microsoft Managed Desktop 插入您信任的簽署者，並將更新的原則部署至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="c101d-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="c101d-120">在應用程式中管理信任</span><span class="sxs-lookup"><span data-stu-id="c101d-120">Managing trust in applications</span></span>

<span data-ttu-id="c101d-121">Microsoft 受管理的桌面 curates 信任 Microsoft 技術核心元件的基準原則。</span><span class="sxs-lookup"><span data-stu-id="c101d-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="c101d-122">接下來，您可以 *將* 您自己的應用程式和腳本的信任，告知 Microsoft 受管理的桌面您已信任他們。</span><span class="sxs-lookup"><span data-stu-id="c101d-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="c101d-123">基準原則</span><span class="sxs-lookup"><span data-stu-id="c101d-123">Base policy</span></span>

<span data-ttu-id="c101d-124">Microsoft 受管理的桌面會與 Microsoft cybersecurity 專家共同作業原則，建立及維護標準原則，可讓大部分透過 Microsoft Intune 部署的應用程式封鎖代碼編譯或執行不受信任檔案的執行等危險活動。</span><span class="sxs-lookup"><span data-stu-id="c101d-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="c101d-125">基準原則採用下列方法來限制軟體執行：</span><span class="sxs-lookup"><span data-stu-id="c101d-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="c101d-126">系統管理員所執行的檔案將允許執行。</span><span class="sxs-lookup"><span data-stu-id="c101d-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="c101d-127">在 *不* 在使用者可寫入目錄中的檔案中，將允許執行檔案。</span><span class="sxs-lookup"><span data-stu-id="c101d-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="c101d-128">檔是由 [受信任的簽署者](#signer-requests)簽署。</span><span class="sxs-lookup"><span data-stu-id="c101d-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="c101d-129">Microsoft 所簽署的大部分檔案都會執行，但是有些會遭到封鎖，以防止高風險動作（如程式碼編譯）。</span><span class="sxs-lookup"><span data-stu-id="c101d-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="c101d-130">如果系統管理員以外的使用者可以將應用程式或腳本新增至裝置 (也就是說，它位於使用者可寫入的目錄) 中，除非系統管理員已特別允許，否則我們不會允許執行它。</span><span class="sxs-lookup"><span data-stu-id="c101d-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="c101d-131">如果使用者企圖安裝惡意程式碼，如果使用者執行的應用程式中有一個弱點會嘗試安裝惡意程式碼，或是使用者故意嘗試執行未授權的應用程式或腳本，我們的原則將會停止執行。</span><span class="sxs-lookup"><span data-stu-id="c101d-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="c101d-132">簽署者要求</span><span class="sxs-lookup"><span data-stu-id="c101d-132">Signer requests</span></span>

<span data-ttu-id="c101d-133">您會告訴我們您信任的軟體發行者所提供的應用程式，可供您用來歸檔 *簽署者要求*。</span><span class="sxs-lookup"><span data-stu-id="c101d-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="c101d-134">這樣一來，我們就會將信任資訊新增至基準應用程式控制原則，並允許任何簽入該發行者憑證的軟體都在您的裝置上執行。</span><span class="sxs-lookup"><span data-stu-id="c101d-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="c101d-135">審核及強制執行的原則</span><span class="sxs-lookup"><span data-stu-id="c101d-135">Audit and Enforced policies</span></span>

<span data-ttu-id="c101d-136">Microsoft 受管理的桌面會使用兩個 Microsoft Intune 原則提供應用程式控制：</span><span class="sxs-lookup"><span data-stu-id="c101d-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="c101d-137">審核原則</span><span class="sxs-lookup"><span data-stu-id="c101d-137">Audit policy</span></span>
<span data-ttu-id="c101d-138">這個原則會建立記錄檔，記錄強制執行的原則是否會封鎖應用程式或腳本。</span><span class="sxs-lookup"><span data-stu-id="c101d-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="c101d-139">審核原則不會強制執行應用程式控制規則，也可用於測試目的，以識別應用程式是否需要發行者例外。</span><span class="sxs-lookup"><span data-stu-id="c101d-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="c101d-140">它會記錄事件檢視器中) 的警告 (8003 或8006事件，而不是封鎖執行或安裝指定的應用程式或腳本。</span><span class="sxs-lookup"><span data-stu-id="c101d-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="c101d-141">強制原則</span><span class="sxs-lookup"><span data-stu-id="c101d-141">Enforced policy</span></span>
<span data-ttu-id="c101d-142">這個原則會封鎖不受信任的應用程式和腳本，並在應用程式或腳本封鎖時建立記錄。</span><span class="sxs-lookup"><span data-stu-id="c101d-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="c101d-143">強制執行的原則可防止標準使用者執行儲存在使用者可寫入目錄中的應用程式或腳本。</span><span class="sxs-lookup"><span data-stu-id="c101d-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="c101d-144">測試群組中的裝置已套用審核原則，可供您用來驗證任何應用程式是否會造成問題。</span><span class="sxs-lookup"><span data-stu-id="c101d-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="c101d-145">所有其他群組 (優先) 使用強制原則，因此這些群組中的使用者將無法執行不受信任的應用程式或腳本。</span><span class="sxs-lookup"><span data-stu-id="c101d-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







