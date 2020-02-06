---
title: 使用 Office 365 中的客戶金鑰服務加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 使用客戶金鑰，您可以控制您組織的加密金鑰，然後設定 [要用來加密存放在 Microsoft 資料中心中的 Office 365。
ms.openlocfilehash: ee62065542ea50091d73362dd8d05f2e4e7dc337
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804771"
---
# <a name="service-encryption-with-customer-key-in-office-365"></a><span data-ttu-id="a07c3-103">使用 Office 365 中的客戶金鑰服務加密</span><span class="sxs-lookup"><span data-stu-id="a07c3-103">Service encryption with Customer Key in Office 365</span></span>

<span data-ttu-id="a07c3-104">Office 365 提供基準，啟用透過 BitLocker 與分散式金鑰管理員 (DKM) 的磁碟區層級加密。</span><span class="sxs-lookup"><span data-stu-id="a07c3-104">Office 365 provides baseline, volume-level encryption enabled through BitLocker and Distributed Key Manager (DKM).</span></span> <span data-ttu-id="a07c3-105">Office 365 提供多一層的加密您的內容應用程式層級。</span><span class="sxs-lookup"><span data-stu-id="a07c3-105">Office 365 offers an added layer of encryption at the application level for your content.</span></span> <span data-ttu-id="a07c3-106">此內容包含資料從 Exchange Online、 Skype for Business，SharePoint Online、 商務用 OneDrive 和小組檔案。</span><span class="sxs-lookup"><span data-stu-id="a07c3-106">This content includes data from Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="a07c3-107">此額外的階層的加密稱為服務加密。</span><span class="sxs-lookup"><span data-stu-id="a07c3-107">This added layer of encryption is called service encryption.</span></span>

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a><span data-ttu-id="a07c3-108">服務加密、 BitLocker，與客戶金鑰共同運作方式</span><span class="sxs-lookup"><span data-stu-id="a07c3-108">How service encryption, BitLocker, and Customer Key work together</span></span>

<span data-ttu-id="a07c3-109">服務加密可確保該內容靜態加密應用程式層級。</span><span class="sxs-lookup"><span data-stu-id="a07c3-109">Service encryption ensures that content at rest is encrypted at the application layer.</span></span> <span data-ttu-id="a07c3-110">**BitLocker 與 DKM 的 Office 365 服務中的靜態永遠加密您的資料**。</span><span class="sxs-lookup"><span data-stu-id="a07c3-110">**Your data is always encrypted at rest in the Office 365 service with BitLocker and DKM**.</span></span> <span data-ttu-id="a07c3-111">如需詳細資訊，請參閱 「 安全性、 隱私權和 Office 365 的合規性資訊 」，以及[如何 Exchange Online 保護您電子郵件機密資料](exchange-online-secures-email-secrets.md)。</span><span class="sxs-lookup"><span data-stu-id="a07c3-111">For more information, see the "Security, Privacy, and Compliance Information for Office 365", and [How Exchange Online secures your email secrets](exchange-online-secures-email-secrets.md).</span></span> <span data-ttu-id="a07c3-112">客戶金鑰提供額外保護，防範檢視的資料未經授權的系統或人員，並輔助 Microsoft 資料中心中的 BitLocker 磁碟加密。</span><span class="sxs-lookup"><span data-stu-id="a07c3-112">Customer Key provides additional protection against viewing of data by unauthorized systems or personnel, and complements BitLocker disk encryption in Microsoft datacenters.</span></span> <span data-ttu-id="a07c3-113">若要防止 Microsoft 人員可以存取客戶資料，並不是服務加密。</span><span class="sxs-lookup"><span data-stu-id="a07c3-113">Service encryption is not meant to prevent Microsoft personnel from accessing customer data.</span></span> <span data-ttu-id="a07c3-114">主要目的是協助客戶會議法規或控制根機碼的合規性責任。</span><span class="sxs-lookup"><span data-stu-id="a07c3-114">The primary purpose is to assist customers in meeting regulatory or compliance obligations for controlling root keys.</span></span> <span data-ttu-id="a07c3-115">客戶明確授權提供新增的值使用他們的加密金鑰的 O365 服務雲端服務，例如電子文件探索、 反惡意程式碼、 反垃圾郵件，搜尋編製索引] 等。</span><span class="sxs-lookup"><span data-stu-id="a07c3-115">Customers explicitly authorize O365 services to use their encryption keys to provide value added cloud services, such as eDiscovery, anti-malware, anti-spam, search indexing, etc.</span></span>

<span data-ttu-id="a07c3-116">客戶金鑰服務加密做為基礎，並可讓您提供並控制加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="a07c3-116">Customer Key is built on service encryption and lets you provide and control encryption keys.</span></span> <span data-ttu-id="a07c3-117">Office 365 然後使用這些金鑰來加密存放在[線上服務條款 (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="a07c3-117">Office 365 then uses these keys to encrypt your data at rest as described in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx).</span></span> <span data-ttu-id="a07c3-118">客戶金鑰可協助您符合規範，因為您可以控制加密金鑰來加密及解密資料所使用的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a07c3-118">Customer Key helps you meet compliance obligations because you control the encryption keys that Office 365 uses to encrypt and decrypt data.</span></span>
  
<span data-ttu-id="a07c3-119">客戶金鑰可增強組織能夠滿足指定索引鍵的排列方式與雲端服務提供者的符合性需求。</span><span class="sxs-lookup"><span data-stu-id="a07c3-119">Customer Key enhances the ability of your organization to meet the demands of compliance requirements that specify key arrangements with the cloud service provider.</span></span> <span data-ttu-id="a07c3-120">使用客戶金鑰，您可以提供並控制您 Office 365 資料待用應用程式層級根加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="a07c3-120">With Customer Key, you provide and control the root encryption keys for your Office 365 data at-rest at the application level.</span></span> <span data-ttu-id="a07c3-121">因此，您會演練控制貴組織的機碼。</span><span class="sxs-lookup"><span data-stu-id="a07c3-121">As a result, you exercise control over your organization's keys.</span></span> <span data-ttu-id="a07c3-122">如果您決定要結束該服務，您會撤銷存取您的組織根機碼。</span><span class="sxs-lookup"><span data-stu-id="a07c3-122">If you decide to exit the service, you revoke access to your organization's root keys.</span></span> <span data-ttu-id="a07c3-123">所有 Office 365 服務，撤銷存取的金鑰都是向資料刪除路徑上的第一個步驟。</span><span class="sxs-lookup"><span data-stu-id="a07c3-123">For all Office 365 services, revoking access to the keys is the first step on the path towards data deletion.</span></span> <span data-ttu-id="a07c3-124">藉由撤銷存取權的機碼，此資料是服務無法讀取。</span><span class="sxs-lookup"><span data-stu-id="a07c3-124">By revoking access to the keys, the data is unreadable to the service.</span></span>

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a><span data-ttu-id="a07c3-125">客戶金鑰來加密在 Office 365 中的靜態資料</span><span class="sxs-lookup"><span data-stu-id="a07c3-125">Customer Key encrypts data at rest in Office 365</span></span>

<span data-ttu-id="a07c3-126">使用您提供的機碼，來加密的 Office 365 的客戶金鑰：</span><span class="sxs-lookup"><span data-stu-id="a07c3-126">Using keys you provide, Customer Key for Office 365 encrypts:</span></span>

- <span data-ttu-id="a07c3-127">SharePoint Online、 商務用 OneDrive 和小組檔案。</span><span class="sxs-lookup"><span data-stu-id="a07c3-127">SharePoint Online, OneDrive for Business, and Teams files.</span></span>
- <span data-ttu-id="a07c3-128">檔案上傳至商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="a07c3-128">Files uploaded to OneDrive for Business.</span></span>
- <span data-ttu-id="a07c3-129">Exchange Online 的信箱內容，包括電子郵件內文的內容、 行事曆項目和電子郵件附件內的內容。</span><span class="sxs-lookup"><span data-stu-id="a07c3-129">Exchange Online mailbox content including e-mail body content, calendar entries, and the content within email attachments.</span></span>
- <span data-ttu-id="a07c3-130">商務用 Skype 的文字交談。</span><span class="sxs-lookup"><span data-stu-id="a07c3-130">Text conversations from Skype for Business.</span></span>

<span data-ttu-id="a07c3-131">我們目前不提供客戶控制項的 Skype 會議廣播和 Skype 會議內容上傳的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="a07c3-131">We don't currently offer customer control of the encryption keys for Skype Meeting Broadcast and Skype Meeting content uploads.</span></span> <span data-ttu-id="a07c3-132">相反地，此內容會經過加密，以及在 Office 365 中的所有其他內容。</span><span class="sxs-lookup"><span data-stu-id="a07c3-132">Instead, this content is encrypted along with all other content in Office 365.</span></span>

### <a name="customer-key-with-hybrid-deployments"></a><span data-ttu-id="a07c3-133">客戶金鑰與混合式部署</span><span class="sxs-lookup"><span data-stu-id="a07c3-133">Customer Key with hybrid deployments</span></span>

<span data-ttu-id="a07c3-134">客戶金鑰只會加密定域機組中的靜態資料。</span><span class="sxs-lookup"><span data-stu-id="a07c3-134">Customer Key only encrypts data at rest in the cloud.</span></span> <span data-ttu-id="a07c3-135">客戶金鑰無法運作以保護您的內部部署信箱和檔案。</span><span class="sxs-lookup"><span data-stu-id="a07c3-135">Customer Key does not work to protect your on-premises mailboxes and files.</span></span> <span data-ttu-id="a07c3-136">您可以將使用另一個方法，例如 BitLocker 您內部部署資料的加密。</span><span class="sxs-lookup"><span data-stu-id="a07c3-136">You can encrypt your on-premises data using another method, such as BitLocker.</span></span>

## <a name="about-the-data-encryption-policy-dep"></a><span data-ttu-id="a07c3-137">關於資料加密原則 (DEP)</span><span class="sxs-lookup"><span data-stu-id="a07c3-137">About the data encryption policy (DEP)</span></span>

<span data-ttu-id="a07c3-138">資料加密原則定義來加密資料使用每個您提供 read 可用性的機碼的加密階層受到 Microsoft 的機碼。</span><span class="sxs-lookup"><span data-stu-id="a07c3-138">A data encryption policy defines the encryption hierarchy to encrypt data using each of the keys you provide as well as the availability key protected by Microsoft.</span></span> <span data-ttu-id="a07c3-139">您建立 DEPs 使用 PowerShell cmdlet，以不同的每個服務，以及指派這些應用程式資料加密。</span><span class="sxs-lookup"><span data-stu-id="a07c3-139">You create DEPs using PowerShell cmdlets, which are different for each service, and assign those to encrypt application data.</span></span> <span data-ttu-id="a07c3-140">例如：</span><span class="sxs-lookup"><span data-stu-id="a07c3-140">For example:</span></span>

<span data-ttu-id="a07c3-141">**Exchange Online 和商務用 Skype**您可以建立每個租用戶最多 50 個 DEPs。</span><span class="sxs-lookup"><span data-stu-id="a07c3-141">**Exchange Online and Skype for Business** You can create up to 50 DEPs per tenant.</span></span> <span data-ttu-id="a07c3-142">您建立 DEPs 關聯至您在 Azure 金鑰保存庫中的客戶金鑰，然後將 DEPs 指派給個別信箱。</span><span class="sxs-lookup"><span data-stu-id="a07c3-142">You associate DEPs to your Customer Keys in Azure Key Vault and then assign DEPs to individual mailboxes.</span></span> <span data-ttu-id="a07c3-143">當您將 DEP 指派給信箱：</span><span class="sxs-lookup"><span data-stu-id="a07c3-143">When you assign a DEP to a mailbox:</span></span>

- <span data-ttu-id="a07c3-144">信箱已標示的信箱移動。</span><span class="sxs-lookup"><span data-stu-id="a07c3-144">the mailbox is marked for a mailbox move.</span></span> <span data-ttu-id="a07c3-145">根據在 Office 365 中的優先順序，如下所述[的移動要求的 Office 365 服務中](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)。</span><span class="sxs-lookup"><span data-stu-id="a07c3-145">Based on priorities in Office 365 as described here [Move requests in the Office 365 service](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).</span></span>

- <span data-ttu-id="a07c3-146">加密會在移動信箱。</span><span class="sxs-lookup"><span data-stu-id="a07c3-146">The encryption takes place while the mailbox is moved.</span></span> <span data-ttu-id="a07c3-147">允許 72 小時，讓要成為加密與新部署的信箱</span><span class="sxs-lookup"><span data-stu-id="a07c3-147">Allow 72 hours for the mailbox to become encrypted with the new DEP.</span></span> <span data-ttu-id="a07c3-148">如果信箱未加密之後等待 72 小時指派 DEP 的時間，請連絡 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="a07c3-148">If the mailboxes aren't encrypted after waiting 72 hours from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="a07c3-149">更新版本中，您可以重新整理 DEP，或將不同的 DEP 指派給信箱[管理 Office 365 的客戶金鑰](customer-key-manage.md)所述。</span><span class="sxs-lookup"><span data-stu-id="a07c3-149">Later, you can either refresh the DEP or assign a different DEP to the mailbox as described in [Manage Customer Key for Office 365](customer-key-manage.md).</span></span> <span data-ttu-id="a07c3-150">每個信箱都必須有適當的授權才能指派相依性</span><span class="sxs-lookup"><span data-stu-id="a07c3-150">Each mailbox must have appropriate licenses in order to assign a DEP.</span></span> <span data-ttu-id="a07c3-151">如需授權的詳細資訊，請參閱[之前設定客戶金鑰](customer-key-set-up.md#before-you-set-up-customer-key)。</span><span class="sxs-lookup"><span data-stu-id="a07c3-151">For more information about licensing, see [Before you set up Customer Key](customer-key-set-up.md#before-you-set-up-customer-key).</span></span>

<span data-ttu-id="a07c3-152">**SharePoint Online、 商務用 OneDrive 和小組檔案**如果您使用多地理位置功能，您可以建立最多一個 DEP 每個地理位置為您的組織。</span><span class="sxs-lookup"><span data-stu-id="a07c3-152">**SharePoint Online, OneDrive for Business, and Teams files** If you're using the multi-geo feature, you can create up to one DEP per geo for your organization.</span></span> <span data-ttu-id="a07c3-153">您可以使用不同的客戶金鑰的每個地理位置。</span><span class="sxs-lookup"><span data-stu-id="a07c3-153">You can use different Customer Keys for each geo.</span></span> <span data-ttu-id="a07c3-154">如果您不使用多地理位置功能，您可以只建立一個 DEP 每個租用戶。</span><span class="sxs-lookup"><span data-stu-id="a07c3-154">If you're not using the multi-geo feature, you can only create one DEP per tenant.</span></span> <span data-ttu-id="a07c3-155">當您指派 DEP 時，加密便會自動開始，但可能需要一些時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="a07c3-155">When you assign the DEP, encryption begins automatically but can take some time to complete.</span></span> <span data-ttu-id="a07c3-156">在 [[設定 Office 365 的客戶金鑰](customer-key-set-up.md)的詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="a07c3-156">Refer to the details in [Set up Customer Key for Office 365](customer-key-set-up.md).</span></span>

## <a name="leaving-the-service"></a><span data-ttu-id="a07c3-157">離開服務</span><span class="sxs-lookup"><span data-stu-id="a07c3-157">Leaving the service</span></span>

<span data-ttu-id="a07c3-158">客戶金鑰可協助您符合規範，讓您離開 Office 365 服務時撤銷您的金鑰。</span><span class="sxs-lookup"><span data-stu-id="a07c3-158">Customer Key assists you in meeting compliance obligations by allowing you to revoke your keys when you leave the Office 365 service.</span></span> <span data-ttu-id="a07c3-159">當您撤銷一部分離開服務您機碼時，可用性機碼會刪除產生密碼編譯刪除您的資料。</span><span class="sxs-lookup"><span data-stu-id="a07c3-159">When you revoke your keys as part of leaving the service, the availability key is deleted resulting in cryptographic deletion of your data.</span></span> <span data-ttu-id="a07c3-160">密碼編譯刪除減少資料殘餘這是很重要的會議安全性與合規性責任的風險。</span><span class="sxs-lookup"><span data-stu-id="a07c3-160">Cryptographic deletion mitigates the risk of data remanence which is important for meeting both security and compliance obligations.</span></span> <span data-ttu-id="a07c3-161">如需資料清除程序與索引鍵被撤銷，請參閱[撤銷您金鑰並啟動資料清除路徑程序](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。</span><span class="sxs-lookup"><span data-stu-id="a07c3-161">For information about the data purge process and key revocation, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

### <a name="encryption-ciphers-used-by-customer-key"></a><span data-ttu-id="a07c3-162">使用客戶金鑰加密 cipher</span><span class="sxs-lookup"><span data-stu-id="a07c3-162">Encryption ciphers used by Customer Key</span></span>

<span data-ttu-id="a07c3-163">客戶金鑰可用於各種加密 cipher 加密金鑰，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="a07c3-163">Customer Key uses a variety of encryption ciphers to encrypt keys as shown in the following figures.</span></span>

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="a07c3-164">加密 cipher 用來加密金鑰，Exchange Online 和商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="a07c3-164">Encryption ciphers used to encrypt keys for Exchange Online and Skype for Business</span></span>

![Exchange Online 客戶金鑰加密 cipher](media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="a07c3-166">加密 cipher 用來加密金鑰，如 SharePoint Online、 商務用 OneDrive 和小組檔案</span><span class="sxs-lookup"><span data-stu-id="a07c3-166">Encryption ciphers used to encrypt keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

![SharePoint Online 客戶金鑰加密 cipher](media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a><span data-ttu-id="a07c3-168">相關文章</span><span class="sxs-lookup"><span data-stu-id="a07c3-168">Related articles</span></span>

- [<span data-ttu-id="a07c3-169">設定 Office 365 客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="a07c3-169">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="a07c3-170">管理 office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="a07c3-170">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="a07c3-171">展開或旋轉客戶金鑰或可用性機碼</span><span class="sxs-lookup"><span data-stu-id="a07c3-171">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="a07c3-172">了解可用性機碼</span><span class="sxs-lookup"><span data-stu-id="a07c3-172">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="a07c3-173">Office 365 中的客戶加密箱</span><span class="sxs-lookup"><span data-stu-id="a07c3-173">Customer Lockbox in Office 365</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="a07c3-174">Office 365 服務加密</span><span class="sxs-lookup"><span data-stu-id="a07c3-174">Office 365 Service Encryption</span></span>](office-365-service-encryption.md)
