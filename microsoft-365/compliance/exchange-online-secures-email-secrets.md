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
description: 除了 Office 365 信任中心提供安全性、 隱私權和規範資訊的 Office 365，您可能想要知道 Office 365 如何協助保護您在其資料中心中提供的機密資料。 我們會使用稱為分散式金鑰管理員 (DKM) 的技術。
ms.openlocfilehash: 6ba60616ee72a4457d81f3f9c2049007afdcbb1d
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800073"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="d0e04-104">Exchange Online 如何保護您的電子郵件機密資料</span><span class="sxs-lookup"><span data-stu-id="d0e04-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="d0e04-105">本文說明 Microsoft 如何保護您的電子郵件機密資料，在其資料中心。</span><span class="sxs-lookup"><span data-stu-id="d0e04-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="d0e04-106">我們要如何保護您所提供的機密資料資訊？</span><span class="sxs-lookup"><span data-stu-id="d0e04-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="d0e04-107">除了 Office 365 信任中心提供[安全性、 隱私權和規範資訊的 Office 365](https://go.microsoft.com/fwlink/?linkid=874644)，您可能想要知道 Office 365 如何協助保護您在其資料中心中提供的機密資料。</span><span class="sxs-lookup"><span data-stu-id="d0e04-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="d0e04-108">我們會使用稱為分散式金鑰管理員 (DKM) 的技術。</span><span class="sxs-lookup"><span data-stu-id="d0e04-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="d0e04-109">[分散式金鑰管理員](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)(DKM) 是使用一組秘密金鑰來加密及解密資訊用戶端功能。</span><span class="sxs-lookup"><span data-stu-id="d0e04-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="d0e04-110">只有在 Active Directory 網域服務中的特定安全性群組的成員可以存取這些機碼，以便解密由 DKM 加密的資料。</span><span class="sxs-lookup"><span data-stu-id="d0e04-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="d0e04-111">在 Exchange Online 中，只有在其下的 Exchange 處理程序執行特定服務帳戶屬於該 [安全性] 群組。</span><span class="sxs-lookup"><span data-stu-id="d0e04-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="d0e04-112">資料中心裡的標準作業程序的一部分，沒有人所指定屬於此安全性群組的認證，因此沒有 human 具有存取權才能解密這些機密的機碼。</span><span class="sxs-lookup"><span data-stu-id="d0e04-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="d0e04-113">偵錯、 疑難排解或稽核的用途，資料中心系統管理員必須要求提升權限的存取權的入侵屬於 [安全性] 群組的暫存認證。</span><span class="sxs-lookup"><span data-stu-id="d0e04-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="d0e04-114">此程序需要多個法律核准層級。</span><span class="sxs-lookup"><span data-stu-id="d0e04-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="d0e04-115">如果授與存取權，所有活動是記錄和稽核。</span><span class="sxs-lookup"><span data-stu-id="d0e04-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="d0e04-116">除了存取會只授與固定間隔的時間之後，它會自動到期。</span><span class="sxs-lookup"><span data-stu-id="d0e04-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="d0e04-117">額外的保護，DKM 技術包含自動化金鑰變換和封存。</span><span class="sxs-lookup"><span data-stu-id="d0e04-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="d0e04-118">這也可確保您可以繼續存取舊內容，而不需無限期依賴相同的金鑰。</span><span class="sxs-lookup"><span data-stu-id="d0e04-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="d0e04-119">在其中沒有 Exchange Online 進行地方使用 DKM？</span><span class="sxs-lookup"><span data-stu-id="d0e04-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="d0e04-120">Microsoft 使用[分散式金鑰管理員](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)加密您的機密資料在 Exchange Online 資料中心。</span><span class="sxs-lookup"><span data-stu-id="d0e04-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="d0e04-121">例如：</span><span class="sxs-lookup"><span data-stu-id="d0e04-121">For example:</span></span>
  
- <span data-ttu-id="d0e04-122">已連線的帳戶的電子郵件帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="d0e04-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="d0e04-123">已連線的帳戶是協力廠商的帳戶，例如 Hotmail、 Gmail 和 yahoo ！</span><span class="sxs-lookup"><span data-stu-id="d0e04-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="d0e04-124">郵件帳號。</span><span class="sxs-lookup"><span data-stu-id="d0e04-124">mail accounts.</span></span>

- <span data-ttu-id="d0e04-125">客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="d0e04-125">Customer key.</span></span> <span data-ttu-id="d0e04-126">如果您使用[使用 Office 365 中的客戶金鑰服務加密](customer-key-overview.md)，您將使用[Azure 金鑰保存庫](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)來保護您的機密資料。</span><span class="sxs-lookup"><span data-stu-id="d0e04-126">If you are using [Service encryption with Customer Key in Office 365](customer-key-overview.md), you'll use [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0e04-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="d0e04-127">Related topics</span></span>

[<span data-ttu-id="d0e04-128">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="d0e04-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="d0e04-129">關於 Office 365 中加密的技術參考細節</span><span class="sxs-lookup"><span data-stu-id="d0e04-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="d0e04-130">服務保證在 Office 365 安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="d0e04-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

