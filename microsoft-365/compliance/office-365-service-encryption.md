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
ms.openlocfilehash: 4759cfda13ab5044ddf5980d7e61004e9e7626fa
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024773"
---
# <a name="service-encryption"></a><span data-ttu-id="5fe6c-103">服務加密</span><span class="sxs-lookup"><span data-stu-id="5fe6c-103">Service Encryption</span></span>

<span data-ttu-id="5fe6c-104">除了使用大量的加密、Exchange Online、商務用 Skype、SharePoint 線上和 OneDrive 商務用，也會使用服務加密來加密客戶資料。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="5fe6c-105">服務加密允許兩個主要的管理選項：</span><span class="sxs-lookup"><span data-stu-id="5fe6c-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="5fe6c-106">Microsoft managed 金鑰</span><span class="sxs-lookup"><span data-stu-id="5fe6c-106">Microsoft managed keys</span></span>
<span data-ttu-id="5fe6c-107">Microsoft 管理所有的加密金鑰，包括服務加密的根機碼。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="5fe6c-108">此選項目前可用於 SharePoint 線上和商務 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-108">This option is currently available in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="5fe6c-109">此選項目前正為 Exchange Online 進行推出。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-109">This option is currently being rolled out for Exchange Online.</span></span> <span data-ttu-id="5fe6c-110">除非您決定使用客戶金鑰進行板載，否則 Microsoft 受管理的金鑰會提供預設的服務加密。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-110">Microsoft managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="5fe6c-111">如果您在稍後的日期決定停止使用客戶金鑰而不遵循資料清除路徑，則您的資料會以 Microsoft 受管理的金鑰保持加密。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-111">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft managed keys.</span></span> <span data-ttu-id="5fe6c-112">您的資料通常會在此預設層級加密，至少一次。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-112">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="5fe6c-113">客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="5fe6c-113">Customer Key</span></span>
<span data-ttu-id="5fe6c-114">您可以提供與服務加密搭配使用的根機碼，並使用 Azure Key Vault 管理這些金鑰。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-114">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="5fe6c-115">Microsoft 管理所有其他機碼。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-115">Microsoft manages all other keys.</span></span> <span data-ttu-id="5fe6c-116">此選項叫用客戶機碼，目前可用於 Exchange Online、SharePoint 線上和商務 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-116">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="5fe6c-117">（先前稱為 BYOK 的高級加密。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-117">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="5fe6c-118">請參閱增強針對原始宣告的[Office 365 客戶的透明性和控制權](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-118">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="5fe6c-119">服務加密可提供多項優點。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-119">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="5fe6c-120">例如，客戶金鑰：</span><span class="sxs-lookup"><span data-stu-id="5fe6c-120">For example, Customer Key:</span></span>

- <span data-ttu-id="5fe6c-121">在增強式加密保護之上提供版權保護和管理功能。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-121">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="5fe6c-122">包含客戶金鑰選項，可讓多租使用者服務提供每個租使用者金鑰管理的服務。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-122">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="5fe6c-123">讓 Windows 作業系統管理員分開存取作業系統所儲存或處理的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-123">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="5fe6c-124">增強 Microsoft 365 的功能，以滿足具有加密之相容性需求的客戶的需求。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-124">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="5fe6c-125">使用客戶金鑰，您可以使用內部部署硬體服務模組（HSM）或 Azure Key Vault （AKV）來產生您自己的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-125">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="5fe6c-126">不論您產生金鑰的方式為何，您可以使用 AKV 來控制和管理 Office 365 所使用的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-126">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="5fe6c-127">當您的金鑰儲存在 AKV 中之後，即可將其當作用來加密您的信箱資料或檔案之其中一個 keychains 的根。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-127">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="5fe6c-128">客戶金鑰的另一個好處是，您可以透過 Microsoft 處理資料的能力來控制。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-128">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="5fe6c-129">如果您想要從 Office 365 中移除資料，例如，如果您想要使用 Microsoft 來終止服務，或移除儲存在雲端中的部分資料，您可以這麼做，並使用客戶金鑰做為技術控制。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-129">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="5fe6c-130">這可確保任何人（包括 Microsoft）都無法存取或處理資料。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-130">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="5fe6c-131">客戶金鑰補充及補充客戶密碼箱，您可以用來控制 Microsoft 人員對資料的存取。</span><span class="sxs-lookup"><span data-stu-id="5fe6c-131">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="5fe6c-132">若要瞭解如何設定適用于 Exchange Online、商務用 Skype、SharePoint Online （包括小組網站）和商務 OneDrive 的 Microsoft 365 的客戶金鑰，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="5fe6c-132">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="5fe6c-133">使用客戶金鑰的服務加密</span><span class="sxs-lookup"><span data-stu-id="5fe6c-133">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="5fe6c-134">設定客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="5fe6c-134">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="5fe6c-135">管理客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="5fe6c-135">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="5fe6c-136">滾動或輪替客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="5fe6c-136">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="5fe6c-137">瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="5fe6c-137">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

