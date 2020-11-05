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
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解 Microsoft 365 電子檔探索工具如何處理附加至電子郵件的加密檔。
ms.openlocfilehash: 89e6457015289055c56278f5f8650ce022ecf081
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920706"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a><span data-ttu-id="c07c8-103">Microsoft 365 eDiscovery tools 中的解密</span><span class="sxs-lookup"><span data-stu-id="c07c8-103">Decryption in Microsoft 365 eDiscovery tools</span></span>

<span data-ttu-id="c07c8-104">組織使用加密技術來保護組織內的敏感內容，並確保只有適當的人員可以存取該內容。</span><span class="sxs-lookup"><span data-stu-id="c07c8-104">Organizations use encryption technology to protect sensitive content within their organization and ensure that only the right people have access to that content.</span></span> <span data-ttu-id="c07c8-105">組織會使用各種類型的加密，這兩種都是 Microsoft 加密技術和協力廠商的技術，以符合安全性需求及保護其機密資訊。</span><span class="sxs-lookup"><span data-stu-id="c07c8-105">Organizations use various types of encryption, both Microsoft encryption technologies and third-party technologies to meet their security requirements and protect their sensitive information.</span></span>

<span data-ttu-id="c07c8-106">迄今為止，在 Microsoft 365 中的 eDiscovery 工作流程中管理加密的內容，需要根據所使用的加密類型和工作流程中的特定階段，以特殊方式處理加密的專案。</span><span class="sxs-lookup"><span data-stu-id="c07c8-106">To date, managing encrypted content in the eDiscovery workflow in Microsoft 365 requires special handling of encrypted items depending on the type of encryption used and the specific stage in the workflow.</span></span> <span data-ttu-id="c07c8-107">這主要是在從內容搜尋、核心 eDiscovery 案例及高級 eDiscovery 案例中匯出電子郵件內容時進行解密。</span><span class="sxs-lookup"><span data-stu-id="c07c8-107">This was primarily achieved by decrypting email message content when it was exported from content searches, Core eDiscovery cases, and Advanced eDiscovery cases.</span></span> <span data-ttu-id="c07c8-108">在匯出內容之前，無法預覽以 Microsoft 加密技術加密的內容。</span><span class="sxs-lookup"><span data-stu-id="c07c8-108">Content encrypted with Microsoft encryption technologies couldn't be previewed until it was exported.</span></span> <span data-ttu-id="c07c8-109">在 [Advanced eDiscovery] 中，已使用處理錯誤來標記加密內容，這需要您下載加密的專案，解密它，然後將解密的檔案上傳至審閱集。</span><span class="sxs-lookup"><span data-stu-id="c07c8-109">In Advanced eDiscovery, encrypted content was flagged with a processing error, which required that you download the encrypted item, decrypt it, and then upload the decrypted file to a review set.</span></span>

<span data-ttu-id="c07c8-110">為了讓您更容易管理 eDiscovery 工作流程中的加密內容，Microsoft 365 eDiscovery 工具可以解密已附加到電子郵件的加密檔案，並在 Exchange Online 中傳送。</span><span class="sxs-lookup"><span data-stu-id="c07c8-110">To make it easier to manage encrypted content in the eDiscovery workflow, Microsoft 365 eDiscovery tools can decrypt encrypted files that are attached to email messages and sent in Exchange Online.</span></span> <span data-ttu-id="c07c8-111">在此新功能之前，只會解密由 rights management (及未附加) 所保護的電子郵件內容。</span><span class="sxs-lookup"><span data-stu-id="c07c8-111">Prior to this new capability, only the content of an email message protected by rights management (and not attached files) was decrypted.</span></span> <span data-ttu-id="c07c8-112">現在，如果以 Microsoft 加密技術加密的檔案附加至符合搜尋準則的電子郵件，當搜尋結果準備好進行預覽時，就會解密加密的檔案。</span><span class="sxs-lookup"><span data-stu-id="c07c8-112">Now, if a file that's encrypted with a Microsoft encryption technology is attached to an email message that matches the search criteria, the encrypted file will be decrypted when the search results are prepared for preview.</span></span> <span data-ttu-id="c07c8-113">這可讓 eDiscovery 管理員在預覽搜尋結果時，查看加密電子郵件附件的內容。</span><span class="sxs-lookup"><span data-stu-id="c07c8-113">This allows eDiscovery managers to view the content of encrypted email attachments when previewing search results.</span></span>

> [!NOTE]
> <span data-ttu-id="c07c8-114">從2021年1月開始，Microsoft 365 eDiscovery 工具將支援 SharePoint 線上和商務 OneDrive 中儲存的加密檔。</span><span class="sxs-lookup"><span data-stu-id="c07c8-114">Starting in January 2021, Microsoft 365 eDiscovery tools will support encrypted documents stored in SharePoint Online and OneDrive for Business.</span></span>

## <a name="supported-encryption-technologies"></a><span data-ttu-id="c07c8-115">支援的加密技術</span><span class="sxs-lookup"><span data-stu-id="c07c8-115">Supported encryption technologies</span></span>

<span data-ttu-id="c07c8-116">Microsoft eDiscovery 工具支援以 Microsoft 加密技術加密的專案。</span><span class="sxs-lookup"><span data-stu-id="c07c8-116">Microsoft eDiscovery tools support items encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="c07c8-117">這些技術包括 Office 郵件加密、Microsoft 資訊保護 (敏感度標籤) 和 Azure Rights Management。</span><span class="sxs-lookup"><span data-stu-id="c07c8-117">These technologies include Office Message Encryption, Microsoft Information Protection (sensitivity labels), and Azure Rights Management.</span></span> <span data-ttu-id="c07c8-118">如需 Microsoft 加密技術的相關資訊，請參閱 [encryption](encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="c07c8-118">For more information about Microsoft encryption technologies, see [Encryption](encryption.md).</span></span> <span data-ttu-id="c07c8-119">不支援以協力廠商加密技術加密的內容。</span><span class="sxs-lookup"><span data-stu-id="c07c8-119">Content encrypted by third-party encryption technologies is not supported.</span></span> <span data-ttu-id="c07c8-120">這包括預覽或匯出以非 Microsoft 技術加密的內容時不支援。</span><span class="sxs-lookup"><span data-stu-id="c07c8-120">This includes no support when previewing or exporting content encrypted with non-Microsoft technologies.</span></span>

## <a name="ediscovery-activities-that-support-encrypted-items"></a><span data-ttu-id="c07c8-121">支援加密專案的 eDiscovery 活動</span><span class="sxs-lookup"><span data-stu-id="c07c8-121">eDiscovery activities that support encrypted items</span></span>

<span data-ttu-id="c07c8-122">下表列出在 Microsoft 365 eDiscovery 工具中執行的工作，這些工具可支援電子郵件 massages 所附加的加密檔案解密。</span><span class="sxs-lookup"><span data-stu-id="c07c8-122">The following table identifies the tasks performed in Microsoft 365 eDiscovery tools that support decryption of encrypted files attached to email massages.</span></span> <span data-ttu-id="c07c8-123">支援工作可以在附加至符合搜尋準則之電子郵件的加密檔案上執行。</span><span class="sxs-lookup"><span data-stu-id="c07c8-123">The support tasks can be performed on an encrypted file that's attached to an email message that matches the criteria of a search.</span></span> <span data-ttu-id="c07c8-124">"N/A" 的值表示該功能在對應的 eDiscovery 工具中不可用。</span><span class="sxs-lookup"><span data-stu-id="c07c8-124">A value of "N/A" indicates that the function isn't available in the corresponding eDiscovery tool.</span></span>

|<span data-ttu-id="c07c8-125">eDiscovery 任務</span><span class="sxs-lookup"><span data-stu-id="c07c8-125">eDiscovery task</span></span>  |<span data-ttu-id="c07c8-126">內容搜尋</span><span class="sxs-lookup"><span data-stu-id="c07c8-126">Content Search</span></span>  |<span data-ttu-id="c07c8-127">核心電子文件探索</span><span class="sxs-lookup"><span data-stu-id="c07c8-127">Core eDiscovery</span></span>  |<span data-ttu-id="c07c8-128">進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="c07c8-128">Advanced eDiscovery</span></span>  |
|:---------|:---------|:---------|:---------|
|<span data-ttu-id="c07c8-129">搜尋加密檔中的內容</span><span class="sxs-lookup"><span data-stu-id="c07c8-129">Search for content in encrypted files</span></span>     |<span data-ttu-id="c07c8-130">否</span><span class="sxs-lookup"><span data-stu-id="c07c8-130">No</span></span>      |<span data-ttu-id="c07c8-131">否</span><span class="sxs-lookup"><span data-stu-id="c07c8-131">No</span></span>      |<span data-ttu-id="c07c8-132">否</span><span class="sxs-lookup"><span data-stu-id="c07c8-132">No</span></span>      |
|<span data-ttu-id="c07c8-133">預覽加密檔</span><span class="sxs-lookup"><span data-stu-id="c07c8-133">Preview encrypted files</span></span>     |<span data-ttu-id="c07c8-134">是</span><span class="sxs-lookup"><span data-stu-id="c07c8-134">Yes</span></span>      |<span data-ttu-id="c07c8-135">是</span><span class="sxs-lookup"><span data-stu-id="c07c8-135">Yes</span></span>     |<span data-ttu-id="c07c8-136">是</span><span class="sxs-lookup"><span data-stu-id="c07c8-136">Yes</span></span>       |
|<span data-ttu-id="c07c8-137">查看審閱集中的加密檔</span><span class="sxs-lookup"><span data-stu-id="c07c8-137">Review encrypted files in a review set</span></span>    |<span data-ttu-id="c07c8-138">不適用</span><span class="sxs-lookup"><span data-stu-id="c07c8-138">N/A</span></span>      |<span data-ttu-id="c07c8-139">不適用</span><span class="sxs-lookup"><span data-stu-id="c07c8-139">N/A</span></span>        | <span data-ttu-id="c07c8-140">是</span><span class="sxs-lookup"><span data-stu-id="c07c8-140">Yes</span></span>        |
|<span data-ttu-id="c07c8-141">匯出加密檔</span><span class="sxs-lookup"><span data-stu-id="c07c8-141">Export encrypted files</span></span>    |<span data-ttu-id="c07c8-142">是</span><span class="sxs-lookup"><span data-stu-id="c07c8-142">Yes</span></span>       |<span data-ttu-id="c07c8-143">是</span><span class="sxs-lookup"><span data-stu-id="c07c8-143">Yes</span></span>  |<span data-ttu-id="c07c8-144">是</span><span class="sxs-lookup"><span data-stu-id="c07c8-144">Yes</span></span>    |

## <a name="requirements-for-decryption-in-ediscovery"></a><span data-ttu-id="c07c8-145">電子檔探索中解密的需求</span><span class="sxs-lookup"><span data-stu-id="c07c8-145">Requirements for decryption in eDiscovery</span></span>

<span data-ttu-id="c07c8-146">您必須獲指派 RMS 解密角色，才能預覽、審閱及匯出以 Microsoft 加密技術加密的附加檔案。</span><span class="sxs-lookup"><span data-stu-id="c07c8-146">You have to be assigned the RMS Decrypt role to preview, review, and export attached files encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="c07c8-147">您也必須被指派此角色，以複查和查詢在高級 eDiscovery 中新增至審閱集的加密電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="c07c8-147">You also have to be assigned this role to review and query encrypted email attachments that are added to a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="c07c8-148">預設會將此角色指派給 Office 365 Security & 合規性中心內的 eDiscovery 管理員角色群組。</span><span class="sxs-lookup"><span data-stu-id="c07c8-148">This role is assigned by default to the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="c07c8-149">如需有關 RMS 解密角色的詳細資訊，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md#rms-decrypt)。</span><span class="sxs-lookup"><span data-stu-id="c07c8-149">For more information about the RMS Decrypt role, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).</span></span>
