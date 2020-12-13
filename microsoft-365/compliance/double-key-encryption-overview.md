---
title: 雙機碼加密概述及常見問題
description: 有關 Microsoft 365 雙金鑰加密的常見問題。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 32686e76018d8b6a361ea99e6b00271b9547ed95
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663058"
---
# <a name="double-key-encryption-frequently-asked-questions"></a><span data-ttu-id="f6a6d-103">雙機碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="f6a6d-103">Double Key Encryption frequently asked questions</span></span>

<span data-ttu-id="f6a6d-104">關於雙重金鑰加密的運作方式有疑問嗎？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-104">Have a question about how Double Key Encryption works?</span></span> <span data-ttu-id="f6a6d-105">在這裡檢查答案。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-105">Check for an answer here.</span></span>

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a><span data-ttu-id="f6a6d-106">什麼是 Microsoft 365 (DKE) 的雙金鑰加密？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-106">What is Double Key Encryption for Microsoft 365 (DKE)?</span></span>

<span data-ttu-id="f6a6d-107">Microsoft 365 的雙金鑰加密可讓客戶保護其高度機密的資料，以符合特殊的需求。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-107">Double Key Encryption for Microsoft 365 enables customers to protect their highly sensitive data to meet specialized requirements.</span></span> <span data-ttu-id="f6a6d-108">它可協助客戶維護其加密金鑰的「完全控制」。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-108">It helps customers maintain full control of their encryption keys.</span></span> <span data-ttu-id="f6a6d-109">它會使用兩個鍵來保護資料;您的控制項中有一個索引鍵，另一個會安全地儲存在 Microsoft Azure 中的金鑰。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-109">It uses two keys to protect data; one key in your control and a second key stored securely in Microsoft Azure.</span></span> <span data-ttu-id="f6a6d-110">查看以雙金鑰加密保護的資料時，需要同時存取這兩個金鑰。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-110">Viewing data protected with Double Key Encryption requires access to both keys.</span></span> <span data-ttu-id="f6a6d-111">因為 Microsoft 只能存取其中一項，所以 Microsoft 無法存取受保護的資料，因此可確保您能夠完全控制您的資料隱私權和安全性。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-111">Since Microsoft can access only one of these keys, protected data remains inaccessible to Microsoft, ensuring that you have full control over your data privacy and security.</span></span>  

<span data-ttu-id="f6a6d-112">您可以在您的選擇 (內部部署金鑰管理伺服器或雲端) 中，主控用來要求金鑰的雙金鑰加密服務。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-112">You can host the Double Key Encryption service used to request your key, in a location of your choice (on-premises key management server or in the cloud).</span></span> <span data-ttu-id="f6a6d-113">您可以像維護任何其他應用程式一樣維護服務。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-113">You maintain the service as you would any other application.</span></span> <span data-ttu-id="f6a6d-114">雙金鑰加密可讓您控制對 Double 金鑰加密服務的存取。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-114">Double Key Encryption enables you to control access to the Double Key Encryption service.</span></span> <span data-ttu-id="f6a6d-115">您可以將高度機密資料儲存在內部部署中，也可以將它移至雲端。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-115">You can store your highly sensitive data on-premises or move it to the cloud.</span></span> <span data-ttu-id="f6a6d-116">您可以自信預防協力廠商存取，因為您維護機碼的完全控制權。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-116">You can be confident about preventing third-party access because you maintain full control of your key.</span></span> <span data-ttu-id="f6a6d-117">雙金鑰加密可讓您將資料和機碼儲存在相同的位置。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-117">Double Key Encryption allows you to store your data and key in the same location.</span></span>

<span data-ttu-id="f6a6d-118">DKE 可協助您滿足各項管理法規的需求，例如一般資料保護法規 (GDPR) 、健康保險業便攜性和責任法案 (HIPAA) 、Gramm-Leach-Bliley 法案 (GLBA) ，俄羅斯的資料當地語系化法–聯邦法律否。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-118">DKE helps you meet regulatory requirements across several regulations and standards such as the General Data Protection Regulation (GDPR), the Health Insurance Portability and Accountability Act (HIPAA), the Gramm-Leach-Bliley Act (GLBA), Russia’s data localization law – Federal Law No.</span></span> <span data-ttu-id="f6a6d-119">242-FZ、澳大利亞的聯邦隱私權法案1988和紐西蘭的隱私權法案1993。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-119">242-FZ, Australia’s Federal Privacy Act 1988, and New Zealand’s Privacy Act 1993.</span></span>

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a><span data-ttu-id="f6a6d-120">我可以搭配 Microsoft Office 內建敏感度標籤使用雙金鑰加密嗎？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-120">Can I use Double Key Encryption with Microsoft Office built-in sensitivity labeling?</span></span>

<span data-ttu-id="f6a6d-121">您需要使用 Azure 資訊保護統一的標籤用戶端，以雙金鑰加密來保護檔。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-121">You'll need to use the Azure Information Protection unified labeling client to protect documents with Double Key Encryption.</span></span> <span data-ttu-id="f6a6d-122">目前，您無法使用 Microsoft Office 內建的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-122">Currently, you can't use Microsoft Office built-in sensitivity labeling.</span></span>

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a><span data-ttu-id="f6a6d-123">我可以搭配 DKE 使用的 Microsoft 365 應用程式？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-123">What Microsoft 365 Apps can I use with DKE?</span></span>

<span data-ttu-id="f6a6d-124">您可以使用 DKE 標籤，在 Windows 上使用 Word、Excel 和 PowerPoint 的桌上出版本來保護檔。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-124">You can use DKE labels to protect documents using the desktop versions of Word, Excel, and PowerPoint on Windows.</span></span> <span data-ttu-id="f6a6d-125">確定您使用的是12711或更新版本 (Windows 上的 Word、PowerPoint 和 Excel) 的桌上出版本。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-125">Ensure that you're using \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a><span data-ttu-id="f6a6d-126">雙機碼與現有的金鑰加密有何不同與現有的 (HYOK) 解決方案？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-126">How is Double Key Encryption different from the existing hold your own key (HYOK) solution?</span></span>

<span data-ttu-id="f6a6d-127">雙按鍵加密會以兩個金鑰來加密您的資料。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-127">Double Key Encryption encrypts your data with two keys.</span></span> <span data-ttu-id="f6a6d-128">您的加密金鑰在您的控制中，而第二個金鑰是儲存在 Microsoft Azure 中，可讓您將加密的資料移至雲端。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-128">Your encryption key is in your control and the second key is stored in Microsoft Azure, allowing you to move your encrypted data to the cloud.</span></span> <span data-ttu-id="f6a6d-129">HYOK 只會使用一個金鑰來保護您的內容，而且金鑰永遠都是在內部部署。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-129">HYOK protects your content with only one key and the key is always on premises.</span></span>  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a><span data-ttu-id="f6a6d-130">是否可以在外部共用雙金鑰加密檔？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-130">Can Double Key Encrypted documents be shared externally?</span></span>

<span data-ttu-id="f6a6d-131">您可以在不同的承租人上，與使用者共用雙機碼檔，只要使用者可以：</span><span class="sxs-lookup"><span data-stu-id="f6a6d-131">You can share Double Key Encrypted documents with users on a separate tenant as long as those users:</span></span>

- <span data-ttu-id="f6a6d-132">具備必要的許可權才能存取您的雙重金鑰加密服務中的金鑰。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-132">Have the required permission to access your key in your Double Key Encryption service.</span></span>

- <span data-ttu-id="f6a6d-133">具有存取您的金鑰在 Microsoft Azure 中所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-133">Have the required permission to access your key in Microsoft Azure.</span></span>

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a><span data-ttu-id="f6a6d-134">以 HYOK 保護的檔會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-134">What happens to documents that are protected with HYOK?</span></span>

<span data-ttu-id="f6a6d-135">部署雙重金鑰加密不會影響現有的 HYOK 設定。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-135">Deploying Double Key Encryption won't affect your existing HYOK setup.</span></span> <span data-ttu-id="f6a6d-136">不過，我們建議您開始與 HYOK 同時使用雙金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-136">However, we recommend that you start using Double Key Encryption in parallel with HYOK.</span></span>

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a><span data-ttu-id="f6a6d-137">我是否可以在非 Microsoft 不確定環境中執行雙重金鑰加密？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-137">Can I run Double Key Encryption in my non-Microsoft air-gapped environment?</span></span>

<span data-ttu-id="f6a6d-138">DKE 不支援這些環境，因為服務需要存取 Microsoft Azure。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-138">DKE doesn't support these environments because the service requires access to Microsoft Azure.</span></span>

## <a name="where-can-i-store-double-key-encrypted-documents"></a><span data-ttu-id="f6a6d-139">我可以在哪裡儲存雙金鑰加密檔？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-139">Where can I store Double Key Encrypted documents?</span></span>

<span data-ttu-id="f6a6d-140">您可以在內部部署或雲端中儲存雙金鑰加密檔。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-140">You can store Double Key Encrypted documents on-premises or in the cloud.</span></span> <span data-ttu-id="f6a6d-141">在雲端中，您可以將加密內容移至 SharePoint 線上和商務 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-141">In the cloud, you can move encrypted content to SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="f6a6d-142">因為 Microsoft 沒有私密金鑰的存取權，所以加密的資料會對 Microsoft 保持不透明。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-142">Since Microsoft doesn't have access to your private key, the encrypted data remains opaque to Microsoft.</span></span> <span data-ttu-id="f6a6d-143">這也表示您無法在 Office Web Apps 中線上查看加密的檔。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-143">This also means that you can't view the encrypted documents online in Office Web Apps.</span></span>

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a><span data-ttu-id="f6a6d-144">哪些地區和語言是可用的雙金鑰加密？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-144">What regions and languages is Double Key Encryption available in?</span></span> <span data-ttu-id="f6a6d-145">全球是否可使用雙金鑰加密？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-145">Is Double Key Encryption available worldwide?</span></span>

<span data-ttu-id="f6a6d-146">DKE 標籤會當地語系化為與 Microsoft 資訊保護中其他敏感度標籤相同的語言。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-146">DKE labels are localized to the same languages as other sensitivity labels in Microsoft Information Protection.</span></span> <span data-ttu-id="f6a6d-147">您可以在全球範圍內使用雙金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-147">Double Key Encryption is available worldwide.</span></span>

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a><span data-ttu-id="f6a6d-148">是否可以將非 DKE 標籤轉換為 DKE 標籤？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-148">Can I convert a non-DKE label to a DKE label?</span></span>

<span data-ttu-id="f6a6d-149">否。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-149">No.</span></span> <span data-ttu-id="f6a6d-150">您無法在建立標籤之後將 DKE 新增至標籤。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-150">You can’t add DKE to a label after you create it.</span></span> <span data-ttu-id="f6a6d-151">相反地，您必須在建立標籤時，選擇 [ **使用雙重金鑰加密** ]，並提供您的雙金鑰加密服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-151">Instead, you must choose **Use Double Key Encryption** and provide the URL of your Double Key Encryption service when you create the label.</span></span>

## <a name="how-do-i-roll-my-dke-keys"></a><span data-ttu-id="f6a6d-152">我要如何滾我的 DKE 機碼？</span><span class="sxs-lookup"><span data-stu-id="f6a6d-152">How do I roll my DKE keys?</span></span>

<span data-ttu-id="f6a6d-153">如需滾動 (（也稱為「旋轉」或「重新加密」）) 您儲存在 Azure 中的機碼的指示，請參閱 [Azure 資訊保護租使用者金鑰的作業](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-153">For instructions on rolling (also called rotating or rekeying) the key you store in Azure, see [Operations for your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key).</span></span>

<span data-ttu-id="f6a6d-154">如需為 DKE 服務建立新機碼的資訊，請參閱 [租使用者和重要設定](double-key-encryption.md#tenant-and-key-settings) 。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-154">See [Tenant and key settings](double-key-encryption.md#tenant-and-key-settings) for information on creating a new key for the DKE service.</span></span>

<span data-ttu-id="f6a6d-155">當您建立機碼時，您會設定名稱及 GUID。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-155">When you create a key, you set up a name and a GUID.</span></span> <span data-ttu-id="f6a6d-156">然後，如果您旋轉按鍵，就會保留具有 name 及 GUID 的舊記錄，但新增具有相同名稱但 GUID 的新記錄。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-156">Then, if you rotate a key, you keep the old record with the name and GUID but add a new record with the same name but different GUID.</span></span> <span data-ttu-id="f6a6d-157">新的機碼會設為作用中，讓公開金鑰 API 開始傳回新的加密。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-157">The new key gets set as active so that the public key API starts returning it for new encryption.</span></span> <span data-ttu-id="f6a6d-158">這兩個金鑰都可用於解密，因此可以解密新的內容和舊的內容。</span><span class="sxs-lookup"><span data-stu-id="f6a6d-158">Both keys are available for decryption so that new content and old content can be decrypted.</span></span>
