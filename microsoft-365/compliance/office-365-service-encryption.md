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
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：瞭解 Microsoft Office 365 的服務層級資料加密。
ms.openlocfilehash: fb6bf87fbd51bcb4383e9eb595ef11f081989d86
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211940"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="0c250-103">Office 365 服務加密</span><span class="sxs-lookup"><span data-stu-id="0c250-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="0c250-104">除了使用 BitLocker 用於大量加密、Exchange Online、商務用 Skype、SharePoint Online、OneDrive 商務用，以及小組也會使用服務加密來加密客戶資料。</span><span class="sxs-lookup"><span data-stu-id="0c250-104">In addition to using BitLocker for volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="0c250-105">服務加密允許兩個主要的管理選項：</span><span class="sxs-lookup"><span data-stu-id="0c250-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="0c250-106">Microsoft 管理所有的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="0c250-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="0c250-107">此選項目前可用於 SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype 和團隊聊天。</span><span class="sxs-lookup"><span data-stu-id="0c250-107">This option is currently available in SharePoint Online, OneDrive for Business, Skype for Business, and Teams chats.</span></span> <span data-ttu-id="0c250-108">根據預設，您的資料會以 Microsoft 管理的金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="0c250-108">Your data is encrypted by default with Microsoft-managed keys.</span></span>

- <span data-ttu-id="0c250-109">您的組織提供根機碼。</span><span class="sxs-lookup"><span data-stu-id="0c250-109">Your organization supplies the root keys.</span></span> <span data-ttu-id="0c250-110">您可以使用 Azure Key Vault 管理這些金鑰。</span><span class="sxs-lookup"><span data-stu-id="0c250-110">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="0c250-111">此選項稱為「客戶金鑰」。</span><span class="sxs-lookup"><span data-stu-id="0c250-111">This option is called Customer Key.</span></span> <span data-ttu-id="0c250-112">客戶金鑰目前適用于 Exchange Online、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype 及小組檔案。</span><span class="sxs-lookup"><span data-stu-id="0c250-112">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="0c250-113">如果您使用客戶金鑰，這些金鑰會取代 Microsoft 受管理的金鑰來加密您的資料。</span><span class="sxs-lookup"><span data-stu-id="0c250-113">If you use Customer Key, these keys replace Microsoft-managed keys to encrypt your data.</span></span>

<span data-ttu-id="0c250-114">不論選擇哪個選項，服務加密都會提供多項優點：</span><span class="sxs-lookup"><span data-stu-id="0c250-114">Whatever option you choose, service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="0c250-115">強制進行使用者驗證，以取得及解密已授權使用者要求的資料。</span><span class="sxs-lookup"><span data-stu-id="0c250-115">Enforces user authentication to retrieve and decrypt data requested by an authorized user.</span></span>

- <span data-ttu-id="0c250-116">讓 Windows 作業系統管理員分開存取作業系統所儲存或處理的客戶資料。</span><span class="sxs-lookup"><span data-stu-id="0c250-116">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="0c250-117">增強 Office 365 的功能，以符合具有加密之相容性需求之客戶的需求。</span><span class="sxs-lookup"><span data-stu-id="0c250-117">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="0c250-118">若要瞭解如何設定適用于 Exchange Online、商務用 Skype、SharePoint 線上、商務 OneDrive 或小組檔案的 Office 365 客戶金鑰，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="0c250-118">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files, see these articles:</span></span>

- [<span data-ttu-id="0c250-119">Office 365 中的客戶機碼服務加密</span><span class="sxs-lookup"><span data-stu-id="0c250-119">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="0c250-120">設定 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="0c250-120">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="0c250-121">管理 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="0c250-121">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="0c250-122">滾動或輪替客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="0c250-122">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="0c250-123">瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="0c250-123">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
