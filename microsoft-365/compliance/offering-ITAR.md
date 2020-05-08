---
title: Arm 規章中的國際流量（ITAR）
description: Azure 政府支援客戶在具有 Arm Regs 功能的系統中建立國際流量。
keywords: Microsoft 365, 合規性, 方案
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: c19b10b436d40364d15ce6bf8569d18b0a0e7b7b
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065728"
---
# <a name="international-traffic-in-arms-regulations-itar"></a><span data-ttu-id="f6e0d-104">Arm 規章中的國際流量（ITAR）</span><span class="sxs-lookup"><span data-stu-id="f6e0d-104">International Traffic in Arms Regulations (ITAR)</span></span>

## <a name="itar-overview"></a><span data-ttu-id="f6e0d-105">ITAR 概述</span><span class="sxs-lookup"><span data-stu-id="f6e0d-105">ITAR overview</span></span>

<span data-ttu-id="f6e0d-106">美國州的部門負責管理防護文章的匯出和暫時匯入（表示在 [US Munitions] 清單中指定的任何專案或技術資料，如 Title 22 CFR 121.1 中所述），該清單是由 Arm 匯出控制法案（Title 22 USC 2778）和 Arm 規章（ITAR）中的國際流量（Title 22 CFR 120-130）控制。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-106">The US Department of State is responsible for managing the export and temporary import of defense articles (meaning any item or technical data designated under the US Munitions List, as described in Title 22 CFR 121.1) that are governed by the Arms Export Control Act (Title 22 USC 2778) and the International Traffic in Arms Regulations (ITAR) (Title 22 CFR 120–130).</span></span> <span data-ttu-id="f6e0d-107">國防商貿控制（DDTC）的 Directorate 負責管理這些程式所管轄的實體。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-107">The Directorate for Defense Trade Controls (DDTC) is responsible for managing entities governed under these programs.</span></span>

## <a name="microsoft-and-itar"></a><span data-ttu-id="f6e0d-108">Microsoft 和 ITAR</span><span class="sxs-lookup"><span data-stu-id="f6e0d-108">Microsoft and ITAR</span></span>

<span data-ttu-id="f6e0d-109">Microsoft 提供某些可以支援 ITAR 義務之客戶的雲端服務或服務功能。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-109">Microsoft provides certain cloud services or service features that can support customers with ITAR obligations.</span></span> <span data-ttu-id="f6e0d-110">雖然 ITAR 未提供相容性認證，但 Microsoft 會運作並設計出範圍內的服務，以支援客戶的 ITAR 義務和合規性計畫。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-110">While there is no compliance certification for the ITAR, Microsoft operates and has designed in-scope services to be capable of supporting a customer’s ITAR obligations and compliance program.</span></span>  
  
<span data-ttu-id="f6e0d-111">Microsoft Azure 政府和 Microsoft Office 365 美國政府 for 國防可透過其他合約承諾向客戶提供有關所儲存資料位置的 ITAR，以及將這些資料存取至 US 人員的能力限制。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-111">Microsoft Azure Government and Microsoft Office 365 U.S. Government for Defense provide support for customers with data subject to the ITAR through additional contractual commitments to customers regarding the location of stored data, and limitations on the ability to access such data to US persons.</span></span> <span data-ttu-id="f6e0d-112">Microsoft 為這些政府雲端服務的基礎結構和操作元件提供這些保證，但客戶最終負責其環境中其應用程式的保護和架構。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-112">Microsoft provides these assurances for the infrastructure and operational components of these government cloud services, but customers are ultimately responsible for the protection and architecture of their applications within their environments.</span></span>  
  
<span data-ttu-id="f6e0d-113">客戶必須為其他合約簽署其他合約，以將 Microsoft 的意圖儲存 ITAR 控制的資料，讓 Microsoft 能夠遵守我們對客戶及美國政府的責任。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-113">Customers must sign additional agreements formally notifying Microsoft of their intention to store ITAR-controlled data, so that Microsoft may comply with responsibilities both to our customers and to the US government.</span></span>  
  
<span data-ttu-id="f6e0d-114">ITAR 對舉報違規有特定責任，可提供某些風險降低的效益。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-114">The ITAR has specific obligations to report violations, which can provide certain risk mitigation benefits.</span></span> <span data-ttu-id="f6e0d-115">Microsoft Enterprise 合約修正可讓 Microsoft 與客戶一起運作，以舉報這類違規行為。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-115">The Microsoft Enterprise Agreement Amendment enables Microsoft and the customer to work together in reporting such violations.</span></span>  
  
<span data-ttu-id="f6e0d-116">尋找主控 ITAR 管制資料的客戶應使用其 Microsoft 帳戶和授權小組來深入瞭解、取得正確的協定，以及存取相關的系統架構資訊。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-116">Customers seeking to host ITAR-regulated data should work with their Microsoft account and licensing teams to learn more, obtain proper agreements, and access relevant system architecture information.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="f6e0d-117">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="f6e0d-117">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="f6e0d-118">Azure 政府</span><span class="sxs-lookup"><span data-stu-id="f6e0d-118">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="f6e0d-119">Office 365 美國政府國防版</span><span class="sxs-lookup"><span data-stu-id="f6e0d-119">Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)

## <a name="frequently-asked-questions"></a><span data-ttu-id="f6e0d-120">常見問題集</span><span class="sxs-lookup"><span data-stu-id="f6e0d-120">Frequently asked questions</span></span>

<span data-ttu-id="f6e0d-121">**我可以在哪裡要求規範資訊？**</span><span class="sxs-lookup"><span data-stu-id="f6e0d-121">**Where can I request compliance information?**</span></span>

<span data-ttu-id="f6e0d-122">請與您的 Microsoft 客戶代表聯繫。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-122">Contact your Microsoft account representative.</span></span>

## <a name="resources"></a><span data-ttu-id="f6e0d-123">資源</span><span class="sxs-lookup"><span data-stu-id="f6e0d-123">Resources</span></span>

- [<span data-ttu-id="f6e0d-124">DDTC ITAR</span><span class="sxs-lookup"><span data-stu-id="f6e0d-124">DDTC ITAR</span></span>](https://www.pmddtc.state.gov/?id=ddtc_kb_article_page&sys_id=24d528fddbfc930044f9ff621f961987)
- [<span data-ttu-id="f6e0d-125">ITAR Title 22 CFR 120-130</span><span class="sxs-lookup"><span data-stu-id="f6e0d-125">ITAR Title 22 CFR 120–130</span></span>](https://aka.ms/itar)
- [<span data-ttu-id="f6e0d-126">搭配使用 Azure 政府與 ITAR 控制的資料</span><span class="sxs-lookup"><span data-stu-id="f6e0d-126">Using Azure Government with ITAR controlled data</span></span>](https://aka.ms/azure-itar-guide)
- [<span data-ttu-id="f6e0d-127">Azure 政府</span><span class="sxs-lookup"><span data-stu-id="f6e0d-127">Azure Government</span></span>](https://azure.microsoft.com/features/gov/)
- [<span data-ttu-id="f6e0d-128">Office 365 美國政府版</span><span class="sxs-lookup"><span data-stu-id="f6e0d-128">Office 365 U.S. Government</span></span>](https://products.office.com/government/office-365-web-services-for-government)
- [<span data-ttu-id="f6e0d-129">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="f6e0d-129">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
