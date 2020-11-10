---
title: EDiscovery 中的解密
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 瞭解 Microsoft 365 電子檔探索工具如何處理附加至電子郵件的加密檔。
ms.openlocfilehash: 3a4a094f1da28c9a017836c099507f5af739b0b9
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951116"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a><span data-ttu-id="9bec3-103">Microsoft 365 eDiscovery tools 中的解密</span><span class="sxs-lookup"><span data-stu-id="9bec3-103">Decryption in Microsoft 365 eDiscovery tools</span></span>

<span data-ttu-id="9bec3-104">加密是檔案保護和資訊保護原則的重要部分。</span><span class="sxs-lookup"><span data-stu-id="9bec3-104">Encryption is an important part of your file protection and information protection strategy.</span></span> <span data-ttu-id="9bec3-105">所有類型的組織都使用加密技術來保護組織內的敏感內容，並確保只有適當的人員可以存取該內容。</span><span class="sxs-lookup"><span data-stu-id="9bec3-105">Organizations of all types use encryption technology to protect sensitive content within their organization and ensure that only the right people have access to that content.</span></span>

<span data-ttu-id="9bec3-106">若要在加密內容上執行一般 eDiscovery 工作，請 eDiscovery 管理員在從內容搜尋、核心 eDiscovery 案例及高級 eDiscovery 案例中匯出電子郵件內容時，必須加以解密。</span><span class="sxs-lookup"><span data-stu-id="9bec3-106">To execute common eDiscovery tasks on encrypted content, eDiscovery managers were required to decrypt email message content as it was exported from content searches, Core eDiscovery cases, and Advanced eDiscovery cases.</span></span> <span data-ttu-id="9bec3-107">在匯出使用 Microsoft 加密技術的內容之前，無法進行審閱。</span><span class="sxs-lookup"><span data-stu-id="9bec3-107">Content encrypted with Microsoft encryption technologies was not available for review until after it was exported.</span></span>

<span data-ttu-id="9bec3-108">為了讓您更容易管理 eDiscovery 工作流程中的加密內容，Microsoft 365 eDiscovery 工具現在整合了附加至電子郵件訊息並在 Exchange Online 中傳送的加密檔解密。</span><span class="sxs-lookup"><span data-stu-id="9bec3-108">To make it easier to manage encrypted content in the eDiscovery workflow, Microsoft 365 eDiscovery tools now incorporate decryption of encrypted files that are attached to email messages and sent in Exchange Online.</span></span> <span data-ttu-id="9bec3-109">在此新功能之前，只會解密由 rights management (及未附加) 所保護的電子郵件內容。</span><span class="sxs-lookup"><span data-stu-id="9bec3-109">Prior to this new capability, only the content of an email message protected by rights management (and not attached files) were decrypted.</span></span> <span data-ttu-id="9bec3-110">現在，如果以 Microsoft 加密技術加密的檔案附加至符合搜尋準則的電子郵件，當搜尋結果準備好進行審閱時，就會解密加密的檔案。</span><span class="sxs-lookup"><span data-stu-id="9bec3-110">Now, if a file that's encrypted with a Microsoft encryption technology is attached to an email message that matches the search criteria, the encrypted file will be decrypted when the search results are prepared for review.</span></span> <span data-ttu-id="9bec3-111">這可讓 eDiscovery 管理員在預覽搜尋結果時查看加密電子郵件附件的內容，並在將其新增至「高級 eDiscovery」中的審閱集之後加以複查。</span><span class="sxs-lookup"><span data-stu-id="9bec3-111">This allows eDiscovery managers to view the content of encrypted email attachments when previewing search results, and review them once they have been added to a review set in Advanced eDiscovery.</span></span>

> [!NOTE]
> <span data-ttu-id="9bec3-112">Microsoft 365 eDiscovery tools 將支援 SharePoint Online 和商務 OneDrive 中儲存的加密檔。</span><span class="sxs-lookup"><span data-stu-id="9bec3-112">Starting soon Microsoft 365 eDiscovery tools will support encrypted documents stored in SharePoint Online and OneDrive for Business.</span></span>

## <a name="supported-encryption-technologies"></a><span data-ttu-id="9bec3-113">支援的加密技術</span><span class="sxs-lookup"><span data-stu-id="9bec3-113">Supported encryption technologies</span></span>

<span data-ttu-id="9bec3-114">Microsoft eDiscovery 工具支援以 Microsoft 加密技術加密的專案。</span><span class="sxs-lookup"><span data-stu-id="9bec3-114">Microsoft eDiscovery tools support items encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="9bec3-115">這些技術包括 Office 郵件加密、Microsoft 資訊保護 (即將推出) 和 Azure Rights Management。</span><span class="sxs-lookup"><span data-stu-id="9bec3-115">These technologies include Office Message Encryption, Microsoft Information Protection (coming soon), and Azure Rights Management.</span></span> <span data-ttu-id="9bec3-116">如需 Microsoft 加密技術的相關資訊，請參閱 [encryption](encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="9bec3-116">For more information about Microsoft encryption technologies, see [Encryption](encryption.md).</span></span> <span data-ttu-id="9bec3-117">不支援以協力廠商加密技術加密的內容。</span><span class="sxs-lookup"><span data-stu-id="9bec3-117">Content encrypted by third-party encryption technologies isn't supported.</span></span> <span data-ttu-id="9bec3-118">這包括預覽或匯出以非 Microsoft 技術加密的內容時不支援。</span><span class="sxs-lookup"><span data-stu-id="9bec3-118">This includes no support when previewing or exporting content encrypted with non-Microsoft technologies.</span></span>

## <a name="ediscovery-activities-that-support-encrypted-items"></a><span data-ttu-id="9bec3-119">支援加密專案的 eDiscovery 活動</span><span class="sxs-lookup"><span data-stu-id="9bec3-119">eDiscovery activities that support encrypted items</span></span>

<span data-ttu-id="9bec3-120">下表列出在 Microsoft 365 eDiscovery 工具中執行的工作，這些工具可支援電子郵件 massages 所附加的加密檔案解密。</span><span class="sxs-lookup"><span data-stu-id="9bec3-120">The following table identifies the tasks performed in Microsoft 365 eDiscovery tools that support decryption of encrypted files attached to email massages.</span></span> <span data-ttu-id="9bec3-121">支援工作可以在附加至符合搜尋準則之電子郵件的加密檔案上執行。</span><span class="sxs-lookup"><span data-stu-id="9bec3-121">The support tasks can be performed on an encrypted file that's attached to an email message that matches the criteria of a search.</span></span> <span data-ttu-id="9bec3-122">"N/A" 的值表示該功能在對應的 eDiscovery 工具中不可用。</span><span class="sxs-lookup"><span data-stu-id="9bec3-122">A value of "N/A" indicates that the function isn't available in the corresponding eDiscovery tool.</span></span>

|<span data-ttu-id="9bec3-123">eDiscovery 任務</span><span class="sxs-lookup"><span data-stu-id="9bec3-123">eDiscovery task</span></span>  |<span data-ttu-id="9bec3-124">內容搜尋</span><span class="sxs-lookup"><span data-stu-id="9bec3-124">Content search</span></span>  |<span data-ttu-id="9bec3-125">核心電子文件探索</span><span class="sxs-lookup"><span data-stu-id="9bec3-125">Core eDiscovery</span></span>  |<span data-ttu-id="9bec3-126">進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="9bec3-126">Advanced eDiscovery</span></span>  |
|:---------|:---------|:---------|:---------|
|<span data-ttu-id="9bec3-127">搜尋加密檔中的內容</span><span class="sxs-lookup"><span data-stu-id="9bec3-127">Search for content in encrypted files</span></span>     |<span data-ttu-id="9bec3-128">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-128">Yes</span></span>      |<span data-ttu-id="9bec3-129">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-129">Yes</span></span>      |<span data-ttu-id="9bec3-130">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-130">Yes</span></span>      |
|<span data-ttu-id="9bec3-131">預覽加密檔</span><span class="sxs-lookup"><span data-stu-id="9bec3-131">Preview encrypted files</span></span>     |<span data-ttu-id="9bec3-132">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-132">Yes</span></span>      |<span data-ttu-id="9bec3-133">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-133">Yes</span></span>     |<span data-ttu-id="9bec3-134">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-134">Yes</span></span>       |
|<span data-ttu-id="9bec3-135">查看審閱集中的加密檔</span><span class="sxs-lookup"><span data-stu-id="9bec3-135">Review encrypted files in a review set</span></span>    |<span data-ttu-id="9bec3-136">不適用</span><span class="sxs-lookup"><span data-stu-id="9bec3-136">N/A</span></span>      |<span data-ttu-id="9bec3-137">不適用</span><span class="sxs-lookup"><span data-stu-id="9bec3-137">N/A</span></span>        | <span data-ttu-id="9bec3-138">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-138">Yes</span></span>        |
|<span data-ttu-id="9bec3-139">匯出加密檔</span><span class="sxs-lookup"><span data-stu-id="9bec3-139">Export encrypted files</span></span>    |<span data-ttu-id="9bec3-140">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-140">Yes</span></span>       |<span data-ttu-id="9bec3-141">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-141">Yes</span></span>  |<span data-ttu-id="9bec3-142">是</span><span class="sxs-lookup"><span data-stu-id="9bec3-142">Yes</span></span>    |

## <a name="requirements-for-decryption-in-ediscovery"></a><span data-ttu-id="9bec3-143">電子檔探索中解密的需求</span><span class="sxs-lookup"><span data-stu-id="9bec3-143">Requirements for decryption in eDiscovery</span></span>

<span data-ttu-id="9bec3-144">您必須獲指派 RMS 解密角色，才能預覽、審閱及匯出以 Microsoft 加密技術加密的附加檔案。</span><span class="sxs-lookup"><span data-stu-id="9bec3-144">You have to be assigned the RMS Decrypt role to preview, review, and export attached files encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="9bec3-145">您也必須被指派此角色，以複查和查詢在高級 eDiscovery 中新增至審閱集的加密電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="9bec3-145">You also have to be assigned this role to review and query encrypted email attachments that are added to a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="9bec3-146">預設會將此角色指派給 Office 365 Security & 合規性中心內的 eDiscovery 管理員角色群組。</span><span class="sxs-lookup"><span data-stu-id="9bec3-146">This role is assigned by default to the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="9bec3-147">如需有關 RMS 解密角色的詳細資訊，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md#rms-decrypt)。</span><span class="sxs-lookup"><span data-stu-id="9bec3-147">For more information about the RMS Decrypt role, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).</span></span>
