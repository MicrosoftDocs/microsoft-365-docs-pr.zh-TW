---
title: Exchange Online 如何保護您的電子郵件機密資料
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: 除了提供 Microsoft 365 的安全性、隱私權和合規性資訊的 Office 365 信任中心之外，您可能還想知道 Microsoft 如何協助保護您在其資料中心中儲存的機密。 我們使用稱為「分散式金鑰管理員」的技術 (DKM) 。
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906959"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="5fbcb-104">Exchange Online 如何保護您的電子郵件機密資料</span><span class="sxs-lookup"><span data-stu-id="5fbcb-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="5fbcb-105">本文說明 Microsoft 如何在其資料中心內保護您的電子郵件機密。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="5fbcb-106">如何保護您所提供的機密資訊的安全性？</span><span class="sxs-lookup"><span data-stu-id="5fbcb-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="5fbcb-107">除了提供 [office 365 的安全性、隱私權及合規性資訊](./get-started-with-service-trust-portal.md)的 Office 365 信任中心之外，您可能還想知道 Microsoft 如何協助保護您在其資料中心內提供的機密。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](./get-started-with-service-trust-portal.md), you might want to know how Microsoft helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="5fbcb-108">我們使用稱為「分散式金鑰管理員」的技術 (DKM) 。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="5fbcb-109">[分散式金鑰管理員](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) 是一種用戶端功能，使用一組機密金鑰來加密及解密資訊。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="5fbcb-110">只有 Active Directory 網域服務中特定安全性群組的成員才能存取這些機碼，以便解密由 DKM 所加密的資料。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="5fbcb-111">在 Exchange Online 中，只有在執行 Exchange 程式的特定服務帳戶才屬於該安全性群組。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="5fbcb-112">在資料中心的標準作業程式中，未被任何人提供此安全性群組的一部分認證，因此沒有人員可以存取可將這些機密解密的金鑰。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="5fbcb-113">針對調試、疑難排解或審計目的，資料中心管理員必須要求提升存取權，才可取得屬於安全性群組一部分的臨時認證。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="5fbcb-114">此程式需要多個合法的法律核准層級。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="5fbcb-115">若授予存取權，就會記錄並審核所有活動。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="5fbcb-116">此外，access 只會被授與已設定的時間間隔之後自動到期。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="5fbcb-117">針對額外的保護，DKM 技術包含自動化金鑰翻轉和封存。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="5fbcb-118">這也可確保您可以繼續存取較舊的內容，而不需要無限期地依賴相同的金鑰。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="5fbcb-119">Exchange Online 利用 DKM 的位置如何？</span><span class="sxs-lookup"><span data-stu-id="5fbcb-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="5fbcb-120">Microsoft 使用 [ [分散式金鑰管理員](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) ]，在 Exchange Online 資料中心內加密您的機密。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="5fbcb-121">例如：</span><span class="sxs-lookup"><span data-stu-id="5fbcb-121">For example:</span></span>
  
- <span data-ttu-id="5fbcb-122">已線上帳戶的電子郵件帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="5fbcb-123">連線的帳戶是協力廠商帳戶，例如 Hotmail、Gmail 和 Yahoo！</span><span class="sxs-lookup"><span data-stu-id="5fbcb-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="5fbcb-124">郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-124">mail accounts.</span></span>

- <span data-ttu-id="5fbcb-125">客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-125">Customer key.</span></span> <span data-ttu-id="5fbcb-126">如果您使用 [服務加密搭配客戶金鑰](customer-key-overview.md)，您將使用 [Azure 金鑰 Vault](/azure/key-vault/key-vault-whatis) 來保護您的機密。</span><span class="sxs-lookup"><span data-stu-id="5fbcb-126">If you are using [Service encryption with Customer Key](customer-key-overview.md), you'll use [Azure Key Vault](/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5fbcb-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="5fbcb-127">Related topics</span></span>

[<span data-ttu-id="5fbcb-128">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="5fbcb-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="5fbcb-129">關於加密的技術參考詳細資料</span><span class="sxs-lookup"><span data-stu-id="5fbcb-129">Technical reference details about encryption</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="5fbcb-130">安全性與 &amp; 合規性中心的服務保證</span><span class="sxs-lookup"><span data-stu-id="5fbcb-130">Service assurance in the Security &amp; Compliance Center</span></span>](./service-assurance.md)
