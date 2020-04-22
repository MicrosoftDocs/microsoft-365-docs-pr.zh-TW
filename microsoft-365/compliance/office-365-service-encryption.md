---
title: 服務加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：瞭解 Microsoft Office 365 中的資料恢復能力。
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632238"
---
# <a name="service-encryption"></a><span data-ttu-id="c304c-103">服務加密</span><span class="sxs-lookup"><span data-stu-id="c304c-103">Service Encryption</span></span>

<span data-ttu-id="c304c-104">除了使用大量的加密、Exchange Online、商務用 Skype、SharePoint 線上和 OneDrive 商務用，也會使用服務加密來加密客戶資料。</span><span class="sxs-lookup"><span data-stu-id="c304c-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="c304c-105">服務加密允許兩個主要的管理選項：</span><span class="sxs-lookup"><span data-stu-id="c304c-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="c304c-106">Microsoft 管理所有的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="c304c-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="c304c-107">（目前 SharePoint 線上 OneDrive、商務用 Skype 和商務用 Skype 等此選項。）</span><span class="sxs-lookup"><span data-stu-id="c304c-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="c304c-108">您的組織提供根機碼。</span><span class="sxs-lookup"><span data-stu-id="c304c-108">Your organization supplies the root keys.</span></span> <span data-ttu-id="c304c-109">您可以使用 Azure Key Vault 管理這些金鑰。</span><span class="sxs-lookup"><span data-stu-id="c304c-109">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="c304c-110">此選項稱為「客戶金鑰」。</span><span class="sxs-lookup"><span data-stu-id="c304c-110">This option is called Customer Key.</span></span> <span data-ttu-id="c304c-111">客戶金鑰目前適用于 Exchange Online、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype 及小組檔案。</span><span class="sxs-lookup"><span data-stu-id="c304c-111">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="c304c-112">如果您使用客戶金鑰，這些金鑰會取代 Microsoft 受管理的金鑰來加密您的資料。</span><span class="sxs-lookup"><span data-stu-id="c304c-112">If you use Customer Key, these keys replace Microsoft-managed keys to encrypt your data.</span></span>

<span data-ttu-id="c304c-113">服務加密可提供多項優點。</span><span class="sxs-lookup"><span data-stu-id="c304c-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="c304c-114">例如，客戶金鑰：</span><span class="sxs-lookup"><span data-stu-id="c304c-114">For example, Customer Key:</span></span>

- <span data-ttu-id="c304c-115">在增強式加密保護之上提供版權保護和管理功能。</span><span class="sxs-lookup"><span data-stu-id="c304c-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="c304c-116">包含客戶金鑰選項，可讓多租使用者服務提供每個租使用者金鑰管理的服務。</span><span class="sxs-lookup"><span data-stu-id="c304c-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="c304c-117">讓 Windows 作業系統管理員分開存取作業系統所儲存或處理的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="c304c-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="c304c-118">增強 Microsoft 365 的功能，以滿足具有加密之相容性需求的客戶的需求。</span><span class="sxs-lookup"><span data-stu-id="c304c-118">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="c304c-119">客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="c304c-119">Customer Key</span></span>

<span data-ttu-id="c304c-120">使用客戶金鑰，您可以使用內部部署硬體服務模組（HSM）或 Azure Key Vault （AKV）來產生您自己的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="c304c-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="c304c-121">不論您產生金鑰的方式為何，您可以使用 AKV 來控制和管理 Office 365 所使用的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="c304c-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="c304c-122">當您的金鑰儲存在 AKV 中之後，即可將其當作用來加密您的信箱資料或檔案之其中一個 keychains 的根。</span><span class="sxs-lookup"><span data-stu-id="c304c-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="c304c-123">客戶金鑰的另一個好處是，您可以透過 Microsoft 處理資料的能力來控制。</span><span class="sxs-lookup"><span data-stu-id="c304c-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="c304c-124">如果您想要從 Office 365 中移除資料，例如，如果您想要使用 Microsoft 來終止服務，或移除儲存在雲端中的部分資料，您可以這麼做，並使用客戶金鑰做為技術控制。</span><span class="sxs-lookup"><span data-stu-id="c304c-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="c304c-125">這可確保任何人（包括 Microsoft）都無法存取或處理資料。</span><span class="sxs-lookup"><span data-stu-id="c304c-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="c304c-126">客戶金鑰補充及補充客戶密碼箱，您可以用來控制 Microsoft 人員對資料的存取。</span><span class="sxs-lookup"><span data-stu-id="c304c-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="c304c-127">若要瞭解如何設定適用于 Exchange Online、商務用 Skype、SharePoint Online （包括小組網站）和商務 OneDrive 的 Microsoft 365 的客戶金鑰，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c304c-127">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="c304c-128">使用客戶金鑰的服務加密</span><span class="sxs-lookup"><span data-stu-id="c304c-128">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="c304c-129">設定客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="c304c-129">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="c304c-130">管理客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="c304c-130">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="c304c-131">滾動或輪替客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="c304c-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="c304c-132">瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="c304c-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
