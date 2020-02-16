---
title: Office 365 服務加密
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
description: 摘要： 了解 Microsoft Office 365 中的資料復原。
ms.openlocfilehash: ec7f794a62a910fadaece890cf73451644d44109
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071110"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="4418d-103">Office 365 服務加密</span><span class="sxs-lookup"><span data-stu-id="4418d-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="4418d-104">除了使用磁碟區層級加密，Exchange Online、 Skype for Business、 SharePoint Online 和商務用 OneDrive 也使用服務加密來加密客戶資料。</span><span class="sxs-lookup"><span data-stu-id="4418d-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="4418d-105">服務加密可讓兩個金鑰管理選項：</span><span class="sxs-lookup"><span data-stu-id="4418d-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="4418d-106">Microsoft 可管理所有的密碼編譯金鑰。</span><span class="sxs-lookup"><span data-stu-id="4418d-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="4418d-107">（此選項是 SharePoint Online、 商務用 OneDrive 與 Skype for Business 中目前無法使用）。</span><span class="sxs-lookup"><span data-stu-id="4418d-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="4418d-108">客戶提供根機碼搭配服務加密和客戶管理使用 Azure Key Vault 這些機碼。</span><span class="sxs-lookup"><span data-stu-id="4418d-108">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault.</span></span> <span data-ttu-id="4418d-109">Microsoft 可管理所有其他機碼。</span><span class="sxs-lookup"><span data-stu-id="4418d-109">Microsoft manages all other keys.</span></span> <span data-ttu-id="4418d-110">此選項稱為客戶金鑰，而且目前適用於 Exchange Online、 SharePoint Online 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="4418d-110">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="4418d-111">（先前稱為使用 BYOK 進階加密。</span><span class="sxs-lookup"><span data-stu-id="4418d-111">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="4418d-112">請參閱[增強透明度及控制 Office 365 客戶](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)的原始的宣告。）</span><span class="sxs-lookup"><span data-stu-id="4418d-112">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="4418d-113">服務加密提供多個好處。</span><span class="sxs-lookup"><span data-stu-id="4418d-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="4418d-114">例如，客戶金鑰：</span><span class="sxs-lookup"><span data-stu-id="4418d-114">For example, Customer Key:</span></span>

- <span data-ttu-id="4418d-115">提供的權限以強式的加密保護的保護和管理功能。</span><span class="sxs-lookup"><span data-stu-id="4418d-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="4418d-116">包含客戶金鑰] 選項，可讓多承租人服務來提供每個租用戶金鑰管理。</span><span class="sxs-lookup"><span data-stu-id="4418d-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="4418d-117">提供 Windows 作業系統系統管理員與分開存取客戶資料儲存或處理的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4418d-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="4418d-118">增強了 Office 365 能夠滿足客戶的有關加密的符合性需求。</span><span class="sxs-lookup"><span data-stu-id="4418d-118">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="4418d-119">客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="4418d-119">Customer Key</span></span>

<span data-ttu-id="4418d-120">您可以使用客戶金鑰，來產生您自己的密碼編譯金鑰，使用內部部署硬體服務模組 (HSM) 或 Azure Key Vault (AKV)。</span><span class="sxs-lookup"><span data-stu-id="4418d-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="4418d-121">不論您如何產生金鑰，您可以使用 AKV 來控制及管理 Office 365 所使用的密碼編譯金鑰。</span><span class="sxs-lookup"><span data-stu-id="4418d-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="4418d-122">一旦您金鑰會儲存在 AKV，他們可以做的其中一個加密您的信箱資料或檔案 keychains 根目錄。</span><span class="sxs-lookup"><span data-stu-id="4418d-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="4418d-123">客戶金鑰的另一個好處是控制項必須透過 Microsoft 能夠處理您的資料。</span><span class="sxs-lookup"><span data-stu-id="4418d-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="4418d-124">如果您想要移除 Office 365 中的資料，例如好像您想要終止與 Microsoft 服務或移除資料儲存在雲端的一部份，您可以這麼做為技術的控制項使用客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="4418d-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="4418d-125">這可確保沒有人，包括 Microsoft，則可以存取或處理的資料。</span><span class="sxs-lookup"><span data-stu-id="4418d-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="4418d-126">客戶金鑰是此外，您用來控制由 Microsoft 人員自您資料的存取權的客戶加密箱的補充。</span><span class="sxs-lookup"><span data-stu-id="4418d-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="4418d-127">若要了解如何設定客戶金鑰的 Office 365 的 Exchange Online、 商務用 Skype、 SharePoint Online，包括小組網站和商務用 OneDrive，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4418d-127">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="4418d-128">使用 Office 365 中的客戶金鑰服務加密</span><span class="sxs-lookup"><span data-stu-id="4418d-128">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="4418d-129">設定 Office 365 客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="4418d-129">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="4418d-130">管理 office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="4418d-130">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="4418d-131">展開或旋轉客戶金鑰或可用性機碼</span><span class="sxs-lookup"><span data-stu-id="4418d-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="4418d-132">了解可用性機碼</span><span class="sxs-lookup"><span data-stu-id="4418d-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
