---
title: 郵件加密（OME）版本比較
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 協助說明郵件加密版本之間的差異。
ms.openlocfilehash: 89d145f19591ba59df6983bb8863a8e0cc28fcf3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626789"
---
# <a name="compare-versions-of-ome"></a><span data-ttu-id="e8e7c-103">比較 OME 版本</span><span class="sxs-lookup"><span data-stu-id="e8e7c-103">Compare versions of OME</span></span>

<span data-ttu-id="e8e7c-104">本文將舊版 Office 365 郵件加密（OME）與新的 OME 功能和 Office 365 的高級訊息加密進行比較。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-104">This article compares legacy Office 365 Message Encryption (OME) to the new OME capabilities and Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="e8e7c-105">新功能是 OME 和資訊版權管理（IRM）的合併和更新版本。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-105">The new capabilities are a merger and newer version of both OME and Information Rights Management (IRM).</span></span> <span data-ttu-id="e8e7c-106">此外，還會概括說明部署為 GCC 高的獨特特性。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-106">Unique characteristics of deploying into GCC High are also outlined.</span></span> <span data-ttu-id="e8e7c-107">這兩個可以在您的組織中共存。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-107">The two can coexist in your organization.</span></span> <span data-ttu-id="e8e7c-108">如需新功能運作方式的詳細資訊，請參閱[Office 365 Message Encryption （OME）](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-108">For information on how the new capabilities work, see [Office 365 Message Encryption (OME)](ome.md).</span></span>

||
|:-----|
|<span data-ttu-id="e8e7c-109">本文是有關 Office 365 郵件加密的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-109">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="e8e7c-110">本文適用于系統管理員和 ITPros。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-110">This article is intended for administrators and ITPros.</span></span> <span data-ttu-id="e8e7c-111">如果您只是尋找傳送或接收加密郵件的相關資訊，請參閱[Office 365 郵件加密（OME）](ome.md)中的文章清單，並找出最符合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-111">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a><span data-ttu-id="e8e7c-112">功能和功能的並列比較</span><span class="sxs-lookup"><span data-stu-id="e8e7c-112">Side-by-side comparison of features and capabilities</span></span>

|                                   |<span data-ttu-id="e8e7c-113">舊功能</span><span class="sxs-lookup"><span data-stu-id="e8e7c-113">Old features</span></span>       |                   |<span data-ttu-id="e8e7c-114">新功能</span><span class="sxs-lookup"><span data-stu-id="e8e7c-114">New features</span></span>              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|<span data-ttu-id="e8e7c-115">**功能**</span><span class="sxs-lookup"><span data-stu-id="e8e7c-115">**Capability**</span></span>                     | <span data-ttu-id="e8e7c-116">**舊版 OME**</span><span class="sxs-lookup"><span data-stu-id="e8e7c-116">**Legacy OME**</span></span>    | <span data-ttu-id="e8e7c-117">**IRM**</span><span class="sxs-lookup"><span data-stu-id="e8e7c-117">**IRM**</span></span>           | <span data-ttu-id="e8e7c-118">**新的 OME 功能**</span><span class="sxs-lookup"><span data-stu-id="e8e7c-118">**New OME capabilities**</span></span> |
|<span data-ttu-id="e8e7c-119">*傳送加密郵件*</span><span class="sxs-lookup"><span data-stu-id="e8e7c-119">*Sending an encrypted mail*</span></span>        |<span data-ttu-id="e8e7c-120">透過 Exchange 郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="e8e7c-120">Through Exchange mail flow rules</span></span>|<span data-ttu-id="e8e7c-121">使用者從 Outlook desktop 或網頁型 Outlook 啟動;或透過 Exchange 郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="e8e7c-121">End-user initiated from Outlook desktop or Outlook on the Web; or through Exchange mail flow rules</span></span>|<span data-ttu-id="e8e7c-122">使用者從 Outlook desktop、Mac 版 Outlook 或網頁型 Outlook 啟動;透過 Exchange 郵件流程規則（也稱為傳輸規則）和資料遺失防護（DLP）</span><span class="sxs-lookup"><span data-stu-id="e8e7c-122">End-user initiated from Outlook desktop, Outlook for Mac, or Outlook on the Web; through Exchange mail flow rules (also known as transport rules) and Data Loss Prevention (DLP)</span></span>|
|<span data-ttu-id="e8e7c-123">*Rights management 範本*</span><span class="sxs-lookup"><span data-stu-id="e8e7c-123">*Rights management template*</span></span>       |   <span data-ttu-id="e8e7c-124">不適用</span><span class="sxs-lookup"><span data-stu-id="e8e7c-124">N/A</span></span>      |<span data-ttu-id="e8e7c-125">[不要轉寄] 選項及自訂範本</span><span class="sxs-lookup"><span data-stu-id="e8e7c-125">Do Not Forward option and custom templates</span></span>|<span data-ttu-id="e8e7c-126">[不要轉寄] 選項、[只供加密] 選項及自訂範本</span><span class="sxs-lookup"><span data-stu-id="e8e7c-126">Do Not Forward option, Encrypt-Only option, and custom templates</span></span>|
|<span data-ttu-id="e8e7c-127">*收件者類型*</span><span class="sxs-lookup"><span data-stu-id="e8e7c-127">*Recipient type*</span></span>                   |<span data-ttu-id="e8e7c-128">內部和外部收件者</span><span class="sxs-lookup"><span data-stu-id="e8e7c-128">Internal and external recipients</span></span>|<span data-ttu-id="e8e7c-129">僅限內部收件者</span><span class="sxs-lookup"><span data-stu-id="e8e7c-129">Internal recipients only</span></span>         |<span data-ttu-id="e8e7c-130">內部和外部收件者</span><span class="sxs-lookup"><span data-stu-id="e8e7c-130">Internal and external recipients</span></span>|
|<span data-ttu-id="e8e7c-131">*內部收件者的經驗*</span><span class="sxs-lookup"><span data-stu-id="e8e7c-131">*Experience for internal recipient*</span></span>|<span data-ttu-id="e8e7c-132">收件者會收到 HTML 郵件，其可在網頁瀏覽器或行動裝置應用程式中下載及開啟</span><span class="sxs-lookup"><span data-stu-id="e8e7c-132">Recipients receive an HTML message, which they download and open in a web browser or mobile app</span></span>|<span data-ttu-id="e8e7c-133">Outlook 用戶端中的原生內嵌體驗</span><span class="sxs-lookup"><span data-stu-id="e8e7c-133">Native inline experience in Outlook clients</span></span>|<span data-ttu-id="e8e7c-134">使用 Outlook 用戶端的相同組織中收件者的原生內嵌經驗。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-134">Native inline experience for recipients in the same organization using Outlook clients.</span></span>  <span data-ttu-id="e8e7c-135">收件者可以使用 Outlook 以外的用戶端（不需要下載或應用程式）讀取來自 OME 入口網站的郵件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-135">Recipients can read message from OME portal using clients other than Outlook (no download or app required).</span></span>|
|<span data-ttu-id="e8e7c-136">*外部收件者的經驗*</span><span class="sxs-lookup"><span data-stu-id="e8e7c-136">*Experience for external recipient*</span></span>|<span data-ttu-id="e8e7c-137">收件者會收到 HTML 郵件，其可在網頁瀏覽器或行動裝置應用程式中下載及開啟</span><span class="sxs-lookup"><span data-stu-id="e8e7c-137">Recipients receive an HTML message, which they download and open in a web browser or mobile app</span></span>|<span data-ttu-id="e8e7c-138">不適用</span><span class="sxs-lookup"><span data-stu-id="e8e7c-138">N/A</span></span>|<span data-ttu-id="e8e7c-139">Microsoft 365 收件者的原生內聯體驗。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-139">Native inline experience for Microsoft 365 recipients.</span></span> <span data-ttu-id="e8e7c-140">所有其他收件者都可以從 OME 入口網站讀取訊息（不需要下載或應用程式）。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-140">All other recipients can read message from OME portal (no download or app required).</span></span>|
|<span data-ttu-id="e8e7c-141">*附件許可權*</span><span class="sxs-lookup"><span data-stu-id="e8e7c-141">*Attachment permissions*</span></span>           |<span data-ttu-id="e8e7c-142">不限制附件</span><span class="sxs-lookup"><span data-stu-id="e8e7c-142">No restrictions on attachments</span></span>|<span data-ttu-id="e8e7c-143">附件受到保護</span><span class="sxs-lookup"><span data-stu-id="e8e7c-143">Attachments are protected</span></span>|<span data-ttu-id="e8e7c-144">[不要轉寄] 選項及自訂範本會保護附件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-144">Attachments are protected for the Do Not Forward option and custom templates.</span></span> <span data-ttu-id="e8e7c-145">系統管理員可以選擇是否要保護只供加密之選項的附件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-145">Admins can choose whether attachments for the Encrypt-Only option are protected or not.</span></span>|
|<span data-ttu-id="e8e7c-146">*帶您自己的金鑰（BYOK）支援*</span><span class="sxs-lookup"><span data-stu-id="e8e7c-146">*Bring your own key (BYOK) support*</span></span>|<span data-ttu-id="e8e7c-147">無</span><span class="sxs-lookup"><span data-stu-id="e8e7c-147">None</span></span>                |<span data-ttu-id="e8e7c-148">無</span><span class="sxs-lookup"><span data-stu-id="e8e7c-148">None</span></span>               |<span data-ttu-id="e8e7c-149">支援 BYOK</span><span class="sxs-lookup"><span data-stu-id="e8e7c-149">BYOK supported</span></span>          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a><span data-ttu-id="e8e7c-150">透過舊版 OME 的新 OME 功能的優點</span><span class="sxs-lookup"><span data-stu-id="e8e7c-150">Advantages of the new OME capabilities over legacy OME</span></span>

<span data-ttu-id="e8e7c-151">新功能具有下列優點：</span><span class="sxs-lookup"><span data-stu-id="e8e7c-151">The new capabilities provide the following advantages:</span></span>

- <span data-ttu-id="e8e7c-152">可以使用僅限加密（啟用安全共同作業）、不轉寄及自訂限制。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-152">Ability to use Encrypt-Only (which enables secure collaboration), Do Not Forward, and custom restrictions.</span></span>
- <span data-ttu-id="e8e7c-153">寄件者可以從 Outlook Desktop、Mac 版 Outlook 和 Outlook 網頁版用戶端上的新功能，以手動方式傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-153">Senders can send mail encrypted with the new capabilities manually from Outlook Desktop, Outlook for Mac and Outlook on the web clients.</span></span>
- <span data-ttu-id="e8e7c-154">Microsoft 365 收件者可在支援的 Outlook 用戶端中使用內嵌經驗。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-154">Microsoft 365 recipients get to use an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="e8e7c-155">或者，系統管理員可以選擇顯示 Microsoft 365 收件者的署名體驗。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-155">Alternatively, admins can choose to show Microsoft 365 recipients a branded experience.</span></span>
- <span data-ttu-id="e8e7c-156">Microsoft 365 以外的帳戶（例如 Gmail、Yahoo 和 Microsoft 帳戶）與 OME 入口網站同盟，可提供更佳的使用者經驗給這些收件者。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-156">Accounts outside of Microsoft 365, such as Gmail, Yahoo, and Microsoft accounts, are federated with the OME portal, which provides a better user experience for these recipients.</span></span> <span data-ttu-id="e8e7c-157">所有其他身分識別使用一次性程式碼來存取加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-157">All other identities use a one-time pass code to access encrypted messages.</span></span>
- <span data-ttu-id="e8e7c-158">系統管理員可以自訂署名，以及建立多個品牌範本。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-158">Admins can customize branding, and create multiple branding templates.</span></span>
- <span data-ttu-id="e8e7c-159">系統管理員可以使用新功能撤銷加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-159">Admins can revoke emails encrypted with the new capabilities.</span></span>
- <span data-ttu-id="e8e7c-160">新功能透過安全性&amp;與合規性中心提供詳細的使用方式報告。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-160">The new capabilities provide detailed usage reports through the Security &amp; Compliance Center.</span></span>

## <a name="office-365-advanced-message-encryption-capabilities"></a><span data-ttu-id="e8e7c-161">Office 365 Advanced Message Encryption 功能</span><span class="sxs-lookup"><span data-stu-id="e8e7c-161">Office 365 Advanced Message Encryption capabilities</span></span>

<span data-ttu-id="e8e7c-162">Office 365 Advanced Message Encryption 在新的 OME 功能上提供其他功能。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-162">Office 365 Advanced Message Encryption offers additional capabilities on top of the new OME capabilities.</span></span> <span data-ttu-id="e8e7c-163">您的組織中必須設定新的 Office 365 郵件加密功能，才能使用高級郵件加密功能。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-163">You must have the new Office 365 Message Encryption capabilities set up in your organization in order to use the Advanced Message Encryption capabilities.</span></span> <span data-ttu-id="e8e7c-164">此外，為了使用這些功能，收件者必須透過 OME 入口網站來查看及回復安全郵件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-164">Also, in order to use these capabilities, recipients must view and reply to secure mail through the OME Portal.</span></span> <span data-ttu-id="e8e7c-165">高級功能包括：</span><span class="sxs-lookup"><span data-stu-id="e8e7c-165">The advanced capabilities  include:</span></span>

- <span data-ttu-id="e8e7c-166">郵件撤銷</span><span class="sxs-lookup"><span data-stu-id="e8e7c-166">Message revocation</span></span>

- <span data-ttu-id="e8e7c-167">郵件到期</span><span class="sxs-lookup"><span data-stu-id="e8e7c-167">Message expiration</span></span>

- <span data-ttu-id="e8e7c-168">多個品牌範本</span><span class="sxs-lookup"><span data-stu-id="e8e7c-168">Multiple branding templates</span></span>

<span data-ttu-id="e8e7c-169">在 GCC High 中不支援 Office 365 高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-169">Office 365 Advanced Message Encryption is not supported in GCC High.</span></span>

<span data-ttu-id="e8e7c-170">如需使用高級郵件加密的詳細資訊，請參閱[Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-170">For information on using Advanced Message Encryption, see [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).</span></span>

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a><span data-ttu-id="e8e7c-171">在 GCC 高部署中，Office 365 郵件加密的獨特特性</span><span class="sxs-lookup"><span data-stu-id="e8e7c-171">Unique characteristics of Office 365 Message Encryption in a GCC High deployment</span></span>

<span data-ttu-id="e8e7c-172">在 GCC 高環境中，Office 365 Advanced Message Encryption 無法使用。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-172">Office 365 Advanced Message Encryption is not available in a GCC High environment.</span></span> <span data-ttu-id="e8e7c-173">您也可以在 GCC 高環境中使用和自訂單一品牌範本。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-173">You can still use and customize a single brand template in a GCC High environment.</span></span>

<span data-ttu-id="e8e7c-174">此外，如果您計畫在 GCC 高環境中使用 Office 365 郵件加密，有一些有關收件者經驗的獨特特性。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-174">In addition, if you plan to use Office 365 Message Encryption in a GCC High environment, there are some unique characteristics about the recipient experience.</span></span>

### <a name="encrypted-email-from-gcc-high-to-gcc-high-recipients"></a><span data-ttu-id="e8e7c-175">來自 GCC 高達 GCC 高收件者的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="e8e7c-175">Encrypted email from GCC High to GCC High recipients</span></span>

<span data-ttu-id="e8e7c-176">寄件者可以手動加密 Outlook 中的電子郵件和 outlook 的 outlook 和 Mac 和 Outlook 網頁版，或組織可以設定使用 Exchange 郵件流程規則來加密電子郵件的原則。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-176">Senders can manually encrypt emails in Outlook for PC and Mac and Outlook on the web, or organizations can set up a policy to encrypt emails using Exchange mail flow rules.</span></span>

<span data-ttu-id="e8e7c-177">在相同的 Outlook 中，在 Outlook 中的收件者會收到與其他所有使用者相同的內嵌讀取體驗。電腦和 Mac 和 Outlook 網頁版。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-177">Recipients inside GCC High receive the same inline reading experience in Outlook for PC and Mac and Outlook on the web as all other users.</span></span>

### <a name="encrypted-email-from-gcc-high-to-non-gcc-high-recipients"></a><span data-ttu-id="e8e7c-178">來自 GCC 高達非 GCC 高收件者的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="e8e7c-178">Encrypted email from GCC High to Non-GCC High recipients</span></span>

<span data-ttu-id="e8e7c-179">在 GCC 高界限內的寄件者可以傳送加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-179">Senders inside GCC High can send encrypted email outside of the GCC High boundary.</span></span>

<span data-ttu-id="e8e7c-180">所有在 GCC （包括365商業性或 Yahoo 等電子郵件提供者的使用者）之外的收件者，都能接收包裝郵件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-180">All recipients outside GCC High, including commercial Microsoft 365 users, Outlook.com users, and other users of other email providers such as Gmail and Yahoo, receive a wrapper mail.</span></span> <span data-ttu-id="e8e7c-181">此包裝郵件會將收件者重新導向至 OME 入口網站，以便收件者可以閱讀和回復郵件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-181">This wrapper mail redirects the recipient to the OME Portal where the recipient can read and reply to message.</span></span>

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a><span data-ttu-id="e8e7c-182">舊版 OME 與相同承租人中的新功能的共存</span><span class="sxs-lookup"><span data-stu-id="e8e7c-182">Coexistence of legacy OME and the new capabilities in the same tenant</span></span>

<span data-ttu-id="e8e7c-183">您可以在同一個承租人中使用這兩種舊版 OME 和新功能。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-183">You can use both legacy OME and the new capabilities in the same tenant.</span></span> <span data-ttu-id="e8e7c-184">身為系統管理員，您可以在建立郵件流程規則時，選擇您要使用的 OME 版本來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-184">As an administrator, you do this by choosing which version of OME you want to use when you create your mail flow rules.</span></span>

- <span data-ttu-id="e8e7c-185">若要指定舊版的 OME，請使用 Exchange 郵件流程規則動作**Apply 舊版的 OME**。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-185">To specify the legacy version of OME, use the Exchange mail flow rule action **Apply the previous version of OME**.</span></span>

- <span data-ttu-id="e8e7c-186">若要指定新功能，請使用 Exchange 郵件流程規則動作**Apply Office 365 郵件加密和許可權保護**。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-186">To specify the new capabilities, use the Exchange mail flow rule action **Apply Office 365 Message Encryption and rights protection**.</span></span>

<span data-ttu-id="e8e7c-187">使用者可以使用 Outlook Desktop 中的新功能、Mac 版 Outlook 和網頁版的 Outlook，手動傳送已加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-187">Users can manually send mail that is encrypted with the new capabilities from Outlook Desktop, Outlook for Mac, and Outlook on the web.</span></span>

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a><span data-ttu-id="e8e7c-188">從舊版 OME 遷移至新功能</span><span class="sxs-lookup"><span data-stu-id="e8e7c-188">Migrate from legacy OME to the new capabilities</span></span>

<span data-ttu-id="e8e7c-189">雖然這兩個版本的 OME 可以共存，我們強烈建議您編輯舊的郵件流程規則，使用規則動作套用**舊版的 OME** ，以使用新功能。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-189">Even though both versions of OME can coexist, we highly recommend that you edit your old mail flow rules that use the rule action **Apply the previous version of OME** to use the new capabilities.</span></span> <span data-ttu-id="e8e7c-190">更新這些規則若要使用郵件流程規則動作 **，請套用 Office 365 郵件加密和許可權保護**。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-190">Update these rules to use the mail flow rule action **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="e8e7c-191">如需相關指示，請參閱[定義郵件流程規則，以加密 Office 365 中的電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-191">For instructions, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

## <a name="get-started-with-ome"></a><span data-ttu-id="e8e7c-192">開始使用 OME</span><span class="sxs-lookup"><span data-stu-id="e8e7c-192">Get started with OME</span></span>

<span data-ttu-id="e8e7c-193">一般來說，您的組織會自動啟用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-193">Typically, the new OME capabilities are automatically enabled for your organization.</span></span> <span data-ttu-id="e8e7c-194">如需組織內新 OME 功能的詳細資訊，請參閱[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-194">For more information about the new OME capabilities within your organization, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="e8e7c-195">如果您已啟用 Azure 資訊保護，系統就會自動為您的組織啟用舊版的 OME。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-195">The legacy version of OME is automatically enabled for your organization if you have enabled Azure Information Protection.</span></span> <span data-ttu-id="e8e7c-196">過去，即使未啟用 Azure 資訊保護，舊版 OME 也會正常運作。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-196">In the past, legacy OME worked even if Azure Information Protection wasn't enabled.</span></span> <span data-ttu-id="e8e7c-197">這已不再是案例。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-197">This is no longer the case.</span></span>

<span data-ttu-id="e8e7c-198">若要開始使用舊版 OME，若您已啟用 Azure 資訊保護，請設定使用規則動作的郵件流程規則：套用**舊版的 OME**。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-198">To start using legacy OME, if you have enabled Azure Information Protection, configure mail flow rules that use the rule action **Apply the previous version of OME**.</span></span> <span data-ttu-id="e8e7c-199">如需相關指示，請參閱[定義郵件流程規則以加密電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e7c-199">For instructions, see [Define mail flow rules to encrypt email messages](define-mail-flow-rules-to-encrypt-email.md).</span></span>
