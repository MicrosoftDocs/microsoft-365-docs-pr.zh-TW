---
title: 使用客戶金鑰的服務加密
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
description: 使用客戶金鑰，您可以控制組織的加密金鑰，然後設定 Microsoft 365，以使用這些金鑰在 Microsoft 資料中心內加密您的資料。
ms.openlocfilehash: 701dc306a81e12db7dd1062d2a840621b710abd3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635589"
---
# <a name="service-encryption-with-customer-key"></a><span data-ttu-id="4c5d8-103">使用客戶金鑰的服務加密</span><span class="sxs-lookup"><span data-stu-id="4c5d8-103">Service encryption with Customer Key</span></span>

<span data-ttu-id="4c5d8-104">Microsoft 365 提供使用 BitLocker 和分散式金鑰管理員（DKM）來啟用基準、磁片區層級加密。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-104">Microsoft 365 provides baseline, volume-level encryption enabled through BitLocker and Distributed Key Manager (DKM).</span></span> <span data-ttu-id="4c5d8-105">Microsoft 365 在應用層級為您的內容提供額外的加密層級。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-105">Microsoft 365 offers an added layer of encryption at the application level for your content.</span></span> <span data-ttu-id="4c5d8-106">此內容包含 Exchange Online 中的資料、商務用 Skype、SharePoint 線上、商務 OneDrive，以及小組檔案。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-106">This content includes data from Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="4c5d8-107">這個新增的加密層稱為「服務加密」。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-107">This added layer of encryption is called service encryption.</span></span>

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a><span data-ttu-id="4c5d8-108">服務加密、BitLocker 及客戶金鑰共同運作的方式</span><span class="sxs-lookup"><span data-stu-id="4c5d8-108">How service encryption, BitLocker, and Customer Key work together</span></span>

<span data-ttu-id="4c5d8-109">服務加密可確保靜態內容會在應用層加密。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-109">Service encryption ensures that content at rest is encrypted at the application layer.</span></span> <span data-ttu-id="4c5d8-110">在**Microsoft 365 服務中，您的資料會永遠以靜態方式加密，並 BitLocker 和 DKM**。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-110">**Your data is always encrypted at rest in the Microsoft 365 service with BitLocker and DKM**.</span></span> <span data-ttu-id="4c5d8-111">如需詳細資訊，請參閱《安全性、隱私權和規範資訊》，以及[Exchange Online 如何保護您的電子郵件機密](exchange-online-secures-email-secrets.md)。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-111">For more information, see the "Security, Privacy, and Compliance Information", and [How Exchange Online secures your email secrets](exchange-online-secures-email-secrets.md).</span></span> <span data-ttu-id="4c5d8-112">客戶金鑰提供額外的保護，以防止未經授權的系統或人員查看資料，以及在 Microsoft 資料中心中補充 BitLocker 磁片加密。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-112">Customer Key provides additional protection against viewing of data by unauthorized systems or personnel, and complements BitLocker disk encryption in Microsoft datacenters.</span></span> <span data-ttu-id="4c5d8-113">服務加密不是為了防止 Microsoft 人員存取客戶資料。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-113">Service encryption is not meant to prevent Microsoft personnel from accessing customer data.</span></span> <span data-ttu-id="4c5d8-114">主要用途是協助客戶滿足控制根機碼的管制或合規性義務。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-114">The primary purpose is to assist customers in meeting regulatory or compliance obligations for controlling root keys.</span></span> <span data-ttu-id="4c5d8-115">客戶會明確授權 O365 服務使用加密金鑰，以提供增值的雲端服務，例如 eDiscovery、反惡意程式碼、反垃圾郵件、搜尋索引等等。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-115">Customers explicitly authorize O365 services to use their encryption keys to provide value added cloud services, such as eDiscovery, anti-malware, anti-spam, search indexing, etc.</span></span>

<span data-ttu-id="4c5d8-116">客戶金鑰是以服務加密為基礎，可讓您提供和控制加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-116">Customer Key is built on service encryption and lets you provide and control encryption keys.</span></span> <span data-ttu-id="4c5d8-117">然後，Microsoft 365 會使用這些金鑰來加密您的資料，如[線上服務條款（OST）](https://www.microsoft.com/licensing/product-licensing/products.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-117">Microsoft 365 then uses these keys to encrypt your data at rest as described in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx).</span></span> <span data-ttu-id="4c5d8-118">客戶金鑰可協助您符合法規遵從性義務，因為您可以控制 Microsoft 365 用來加密及解密資料的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-118">Customer Key helps you meet compliance obligations because you control the encryption keys that Microsoft 365 uses to encrypt and decrypt data.</span></span>
  
<span data-ttu-id="4c5d8-119">客戶金鑰可提升您的組織符合規範需求的能力，以指定與雲端服務提供者的重要安排。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-119">Customer Key enhances the ability of your organization to meet the demands of compliance requirements that specify key arrangements with the cloud service provider.</span></span> <span data-ttu-id="4c5d8-120">使用客戶金鑰，您可以在應用層級為您的 Microsoft 365 資料同時提供及控制根加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-120">With Customer Key, you provide and control the root encryption keys for your Microsoft 365 data at-rest at the application level.</span></span> <span data-ttu-id="4c5d8-121">因此，您會練習控制組織的按鍵。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-121">As a result, you exercise control over your organization's keys.</span></span> <span data-ttu-id="4c5d8-122">如果您決定要退出服務，請撤銷您組織的根機碼的存取權。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-122">If you decide to exit the service, you revoke access to your organization's root keys.</span></span> <span data-ttu-id="4c5d8-123">針對所有 Microsoft 365 服務，撤銷機碼存取權的第一步是資料刪除的路徑。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-123">For all Microsoft 365 services, revoking access to the keys is the first step on the path towards data deletion.</span></span> <span data-ttu-id="4c5d8-124">透過撤銷對機碼的存取權，無法將資料從服務中讀取。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-124">By revoking access to the keys, the data is unreadable to the service.</span></span>

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a><span data-ttu-id="4c5d8-125">客戶金鑰會在 Office 365 中加密靜態資料</span><span class="sxs-lookup"><span data-stu-id="4c5d8-125">Customer Key encrypts data at rest in Office 365</span></span>

<span data-ttu-id="4c5d8-126">使用您提供的金鑰，客戶金鑰加密：</span><span class="sxs-lookup"><span data-stu-id="4c5d8-126">Using keys you provide, Customer Key encrypts:</span></span>

- <span data-ttu-id="4c5d8-127">SharePoint 線上、商務及小組檔案的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-127">SharePoint Online, OneDrive for Business, and Teams files.</span></span>
- <span data-ttu-id="4c5d8-128">上傳至商務 OneDrive 的檔案。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-128">Files uploaded to OneDrive for Business.</span></span>
- <span data-ttu-id="4c5d8-129">Exchange Online 信箱內容，包括電子郵件內文內容、行事曆專案，以及電子郵件附件中的內容。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-129">Exchange Online mailbox content including e-mail body content, calendar entries, and the content within email attachments.</span></span>
- <span data-ttu-id="4c5d8-130">商務用 Skype 中的文字交談。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-130">Text conversations from Skype for Business.</span></span>

<span data-ttu-id="4c5d8-131">目前我們並不會為 Skype 會議廣播和 Skype 會議內容上傳的加密金鑰提供客戶控制權。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-131">We don't currently offer customer control of the encryption keys for Skype Meeting Broadcast and Skype Meeting content uploads.</span></span> <span data-ttu-id="4c5d8-132">相反地，此內容會與 Office 365 中的所有其他內容一起加密。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-132">Instead, this content is encrypted along with all other content in Office 365.</span></span>

### <a name="customer-key-with-hybrid-deployments"></a><span data-ttu-id="4c5d8-133">具有混合式部署的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="4c5d8-133">Customer Key with hybrid deployments</span></span>

<span data-ttu-id="4c5d8-134">客戶金鑰只會加密雲端中靜態的資料。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-134">Customer Key only encrypts data at rest in the cloud.</span></span> <span data-ttu-id="4c5d8-135">客戶金鑰不會用來保護您的內部部署信箱和檔案。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-135">Customer Key does not work to protect your on-premises mailboxes and files.</span></span> <span data-ttu-id="4c5d8-136">您可以使用另一種方法（例如 BitLocker）來加密您的內部部署資料。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-136">You can encrypt your on-premises data using another method, such as BitLocker.</span></span>

## <a name="about-the-data-encryption-policy-dep"></a><span data-ttu-id="4c5d8-137">關於資料加密原則（DEP）</span><span class="sxs-lookup"><span data-stu-id="4c5d8-137">About the data encryption policy (DEP)</span></span>

<span data-ttu-id="4c5d8-138">資料加密原則定義加密階層，使用您提供的每個金鑰以及 Microsoft 所保護的可用性金鑰來加密資料。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-138">A data encryption policy defines the encryption hierarchy to encrypt data using each of the keys you provide as well as the availability key protected by Microsoft.</span></span> <span data-ttu-id="4c5d8-139">您可以使用 PowerShell Cmdlet 來建立 DEPs，這些 Cmdlet 會不同于每個服務，並指派這些 DEPs 以加密應用程式資料。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-139">You create DEPs using PowerShell cmdlets, which are different for each service, and assign those DEPs to encrypt application data.</span></span> <span data-ttu-id="4c5d8-140">例如：</span><span class="sxs-lookup"><span data-stu-id="4c5d8-140">For example:</span></span>

<span data-ttu-id="4c5d8-141">**Exchange Online 和商務用 Skype**每個租使用者最多可以建立 50 DEPs。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-141">**Exchange Online and Skype for Business** You can create up to 50 DEPs per tenant.</span></span> <span data-ttu-id="4c5d8-142">您可以將 DEPs 關聯到 Azure Key Vault 中的客戶機碼，然後將 DEPs 指派給個別信箱。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-142">You associate DEPs to your Customer Keys in Azure Key Vault and then assign DEPs to individual mailboxes.</span></span> <span data-ttu-id="4c5d8-143">當您為信箱指派 DEP 時：</span><span class="sxs-lookup"><span data-stu-id="4c5d8-143">When you assign a DEP to a mailbox:</span></span>

- <span data-ttu-id="4c5d8-144">信箱已標記為要移動信箱。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-144">the mailbox is marked for a mailbox move.</span></span> <span data-ttu-id="4c5d8-145">根據此處所述的 Microsoft 365 中的優先順序，在[microsoft 365 服務中移動要求](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-145">Based on priorities in Microsoft 365 as described here [Move requests in the Microsoft 365 service](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).</span></span>

- <span data-ttu-id="4c5d8-146">移動信箱時，會進行加密。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-146">The encryption takes place while the mailbox is moved.</span></span> <span data-ttu-id="4c5d8-147">允許信箱的72小時使用新的 DEP 進行加密。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-147">Allow 72 hours for the mailbox to become encrypted with the new DEP.</span></span> <span data-ttu-id="4c5d8-148">如果信箱在您指派 DEP 的時間之後，等待72小時之後未加密，請與 Microsoft 聯繫。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-148">If the mailboxes aren't encrypted after waiting 72 hours from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="4c5d8-149">稍後，您可以依照[管理 Office 365 的客戶金鑰](customer-key-manage.md)中所述的方式，重新整理 DEP 或指派不同的 dep 至信箱。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-149">Later, you can either refresh the DEP or assign a different DEP to the mailbox as described in [Manage Customer Key for Office 365](customer-key-manage.md).</span></span> <span data-ttu-id="4c5d8-150">每個信箱都必須有適當的授權，才可指派 DEP。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-150">Each mailbox must have appropriate licenses in order to assign a DEP.</span></span> <span data-ttu-id="4c5d8-151">如需授權的詳細資訊，請參閱[設定客戶金鑰之前](customer-key-set-up.md#before-you-set-up-customer-key)。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-151">For more information about licensing, see [Before you set up Customer Key](customer-key-set-up.md#before-you-set-up-customer-key).</span></span>

<span data-ttu-id="4c5d8-152">**SharePoint 線上、商務及小組檔案的 OneDrive**如果您使用的是多地理位置功能，您的組織可以為每個地理位置建立多個 DEP。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-152">**SharePoint Online, OneDrive for Business, and Teams files** If you're using the multi-geo feature, you can create up to one DEP per geo for your organization.</span></span> <span data-ttu-id="4c5d8-153">您可以針對每個地理位置使用不同的客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-153">You can use different Customer Keys for each geo.</span></span> <span data-ttu-id="4c5d8-154">如果您不是使用多地理位置功能，則每個承租人只能建立一個 DEP。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-154">If you're not using the multi-geo feature, you can only create one DEP per tenant.</span></span> <span data-ttu-id="4c5d8-155">當您指派 DEP 時，加密會自動開始，但可能需要一些時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-155">When you assign the DEP, encryption begins automatically but can take some time to complete.</span></span> <span data-ttu-id="4c5d8-156">請參閱[設定客戶金鑰](customer-key-set-up.md)中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-156">Refer to the details in [Set up Customer Key](customer-key-set-up.md).</span></span>

## <a name="leaving-the-service"></a><span data-ttu-id="4c5d8-157">離開服務</span><span class="sxs-lookup"><span data-stu-id="4c5d8-157">Leaving the service</span></span>

<span data-ttu-id="4c5d8-158">客戶金鑰可協助您在離開 Microsoft 365 服務時撤銷您的金鑰，以協助您履行法規遵從性義務。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-158">Customer Key assists you in meeting compliance obligations by allowing you to revoke your keys when you leave the Microsoft 365 service.</span></span> <span data-ttu-id="4c5d8-159">當您在離開服務時撤銷您的金鑰時，會刪除可用性機碼，以加密刪除您的資料。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-159">When you revoke your keys as part of leaving the service, the availability key is deleted resulting in cryptographic deletion of your data.</span></span> <span data-ttu-id="4c5d8-160">加密刪除可降低資料 remanence 的風險，這對於迎接安全性和合規性義務很重要。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-160">Cryptographic deletion mitigates the risk of data remanence which is important for meeting both security and compliance obligations.</span></span> <span data-ttu-id="4c5d8-161">如需有關資料清除程式和金鑰吊銷的詳細資訊，請參閱[撤銷您的金鑰，然後啟動資料清除路徑處理](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)程式。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-161">For information about the data purge process and key revocation, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

### <a name="encryption-ciphers-used-by-customer-key"></a><span data-ttu-id="4c5d8-162">客戶金鑰使用的加密密碼</span><span class="sxs-lookup"><span data-stu-id="4c5d8-162">Encryption ciphers used by Customer Key</span></span>

<span data-ttu-id="4c5d8-163">客戶金鑰使用各種加密密碼來加密金鑰，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="4c5d8-163">Customer Key uses a variety of encryption ciphers to encrypt keys as shown in the following figures.</span></span>

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="4c5d8-164">加密密碼，用來加密 Exchange Online 和商務用 Skype 的金鑰</span><span class="sxs-lookup"><span data-stu-id="4c5d8-164">Encryption ciphers used to encrypt keys for Exchange Online and Skype for Business</span></span>

![Exchange Online 客戶機碼的加密密碼](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="4c5d8-166">用來加密 SharePoint 線上、商務 OneDrive 與小組檔案的金鑰的加密密碼</span><span class="sxs-lookup"><span data-stu-id="4c5d8-166">Encryption ciphers used to encrypt keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

![SharePoint Online 客戶機碼的加密密碼](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a><span data-ttu-id="4c5d8-168">相關文章</span><span class="sxs-lookup"><span data-stu-id="4c5d8-168">Related articles</span></span>

- [<span data-ttu-id="4c5d8-169">設定客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="4c5d8-169">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="4c5d8-170">管理客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="4c5d8-170">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="4c5d8-171">滾動或旋轉客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="4c5d8-171">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="4c5d8-172">深入瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="4c5d8-172">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="4c5d8-173">客戶加密箱</span><span class="sxs-lookup"><span data-stu-id="4c5d8-173">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="4c5d8-174">服務加密</span><span class="sxs-lookup"><span data-stu-id="4c5d8-174">Service Encryption</span></span>](office-365-service-encryption.md)
