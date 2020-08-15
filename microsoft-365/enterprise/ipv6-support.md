---
title: Office 365 服務中的 IPv6 支援
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 摘要：說明 Microsoft Office 365 元件和 Office 365 政府產品方案中的 IPv6 支援。
ms.openlocfilehash: c4ecd2ef26ecf660eb1d172b1951907724d2238a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688414"
---
# <a name="ipv6-support-in-office-365-services"></a><span data-ttu-id="3f4dd-103">Office 365 服務中的 IPv6 支援</span><span class="sxs-lookup"><span data-stu-id="3f4dd-103">IPv6 support in Office 365 services</span></span>

<span data-ttu-id="3f4dd-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="3f4dd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3f4dd-105">Office 365 同時支援 IPv6 和 IPv4;不過，並非所有的 Office 365 功能都會充分啟用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-105">Office 365 supports both IPv6 and IPv4; however, not all Office 365 features are fully enabled with IPv6.</span></span> <span data-ttu-id="3f4dd-106">這表示您必須同時使用 IPv4 和 IPv6 以連接至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-106">This means that you must use both IPv4 and IPv6 to connect to Office 365.</span></span> <span data-ttu-id="3f4dd-107">如果您要將輸出流量篩選到 Office 365，則可以在 [office 365 URLs 和 IP 位址範圍](urls-and-ip-address-ranges.md)一文中找到 office 365 支援的 IPv6 位址完整清單。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-107">If you are filtering your outbound traffic to Office 365, the full list of IPv6 addresses that are supported by Office 365 can be found in the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span> <span data-ttu-id="3f4dd-108">在設定網路並允許適當的 IPv6 位址之後，您可以從 Microsoft 下載中心下載 [Office 365 IPv6 測試方案](https://go.microsoft.com/fwlink/?LinkId=293447) 。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-108">After your network is configured and the appropriate IPv6 addresses are allowed, you can download the [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) from the Microsoft Download Center.</span></span>
  
## <a name="ipv6-support-in-office-365-subscription-service"></a><span data-ttu-id="3f4dd-109">Office 365 訂閱服務中的 IPv6 支援</span><span class="sxs-lookup"><span data-stu-id="3f4dd-109">IPv6 support in Office 365 subscription service</span></span>

### <a name="exchange-online-and-ipv6"></a><span data-ttu-id="3f4dd-110">Exchange Online 和 IPv6</span><span class="sxs-lookup"><span data-stu-id="3f4dd-110">Exchange Online and IPv6</span></span>

<span data-ttu-id="3f4dd-111">如果您用來連線至 Exchange Online 的程式支援 IPv6，則在有線網路和無線網路上預設會使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-111">If the program that you use to connect to Exchange Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="3f4dd-112">如果您想要控制與 Exchange Online 之間的通訊，請使用 [Office 365 URLs 和 ip 位址範圍](urls-and-ip-address-ranges.md)中的 ip 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-112">If you want to control communications to Exchange Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="sharepoint-online-and-ipv6"></a><span data-ttu-id="3f4dd-113">線上 SharePoint 和 IPv6</span><span class="sxs-lookup"><span data-stu-id="3f4dd-113">SharePoint Online and IPv6</span></span>

 <span data-ttu-id="3f4dd-114">**Office 365 政府 G1/G3/G4/K1** 如果您用來連線至 SharePoint Online 的程式支援 IPv6，則預設會嘗試使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-114">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
 <span data-ttu-id="3f4dd-115">**公用多租使用者雲端** Microsoft 可在您的要求 IPv6 線上 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-115">**Public multi-tenant cloud** Microsoft enables SharePoint Online IPv6 at your request.</span></span> <span data-ttu-id="3f4dd-116">您需要為組織的 DNS 基礎結構提供 CIDR 表示的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-116">You need to provide the CIDR notated IP addresses for your organization's DNS infrastructure.</span></span> <span data-ttu-id="3f4dd-117">請記住，其他組織無法共用此 DNS 基礎結構，因此無法為您的租使用者啟用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-117">Keep in mind that this DNS infrastructure can't be shared by other organizations for IPv6 to be enabled for your tenant.</span></span> <span data-ttu-id="3f4dd-118">啟用 IPv6 之後，如果您用來連線到 SharePoint Online 的程式支援 IPv6，則預設會使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-118">After IPv6 is enabled, if the program that you use to connect to SharePoint Online supports IPv6, it uses IPv6 by default.</span></span>
  
<span data-ttu-id="3f4dd-119">如果您用來連線至 SharePoint Online 的程式支援 IPv6，則在有線網路和無線網路上的預設 IPv6 都會使用。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-119">If the program that you use to connect to SharePoint Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="3f4dd-120">如果您想要控制 SharePoint 線上的通訊，請使用 [Office 365 URLs 和 IP 位址範圍](urls-and-ip-address-ranges.md)中的 ip 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-120">If you want to control communications to SharePoint Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
 <span data-ttu-id="3f4dd-121">**Office 365 政府 G1/G3/G4/K1** 如果您用來連線至 SharePoint Online 的程式支援 IPv6，則預設會嘗試使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-121">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
### <a name="skype-for-business-and-ipv6"></a><span data-ttu-id="3f4dd-122">商務用 Skype 和 IPv6</span><span class="sxs-lookup"><span data-stu-id="3f4dd-122">Skype for Business and IPv6</span></span>

<span data-ttu-id="3f4dd-123">請注意，商務用 Skype 不支援 IPv6，也無法再啟用。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-123">Please be aware IPv6 is not supported in Skype for Business and can no longer be enabled.</span></span>
  
### <a name="exchange-online-protection-and-ipv6"></a><span data-ttu-id="3f4dd-124">Exchange Online Protection 和 IPv6</span><span class="sxs-lookup"><span data-stu-id="3f4dd-124">Exchange Online Protection and IPv6</span></span>

<span data-ttu-id="3f4dd-125">Exchange Online Protection (EOP) 會在傳輸層安全性通訊協定進行傳輸時，支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-125">Exchange Online Protection (EOP) supports IPv6 if the transmission occurs over Transport Layer Security Protocol.</span></span> <span data-ttu-id="3f4dd-126">針對 EOP 範圍，使用 [Office 365 URLs 和 IP 位址範圍](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-126">For the EOP range, use [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="ipv6-support-for-office-365-government-offerings"></a><span data-ttu-id="3f4dd-127">Office 365 政府產品服務的 IPv6 支援</span><span class="sxs-lookup"><span data-stu-id="3f4dd-127">IPv6 support for Office 365 government offerings</span></span>

<span data-ttu-id="3f4dd-128">Office 365 IPv6 對政府產品的支援符合管理人員和預算 (OMB) 備忘錄，以供高層和代理商的首席資訊官和聯邦政府採用網際網路通訊協定第6版 (IPv6) 備忘錄。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-128">Office 365 IPv6 support for government offerings conforms to the Office of Management and Budget (OMB) Memorandum for Chief Information Officers of Executive Departments and Agencies, as well as the Federal Government Adoption of Internet Protocol Version 6 (IPv6) memorandum.</span></span> <span data-ttu-id="3f4dd-129">[適用于政府的 Microsoft Office 365](https://go.microsoft.com/fwlink/p/?LinkId=325414) 是一項多承租人服務，可將政府資料儲存在隔離的社區雲端中。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-129">[Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) is a multi-tenant service that stores US government data in a segregated community cloud.</span></span> <span data-ttu-id="3f4dd-130">與其他 Office 365 產品類似，它提供生產力和共同作業服務，包括 Exchange Online、商務用 Skype、SharePoint Online 和 Microsoft 365 應用程式的企業版。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-130">Like other Office 365 offerings, it provides productivity and collaboration services, including Exchange Online, Skype for Business, SharePoint Online, and Microsoft 365 Apps for enterprise.</span></span> 

<span data-ttu-id="3f4dd-131">Microsoft Office 365 政府版產品只適用于2013和更新版本。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-131">The Microsoft Office 365 government offerings apply only for 2013 and later.</span></span> <span data-ttu-id="3f4dd-132">如需有關 Office 365 政府方案的詳細資訊，請參閱 [宣佈 office 365 For 政府： A US 政府社區雲端](https://go.microsoft.com/fwlink/p/?LinkId=325414)。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-132">For more information about the Office 365 government offerings, see [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414).</span></span> <span data-ttu-id="3f4dd-133">Arm 規章中的國際流量 (ITAR) 是一組美國政府規定，可控制如何匯出及匯入 [美國 Munitions 清單 (USML) ](https://go.microsoft.com/fwlink/p/?LinkId=325415)上的國防相關文章和服務。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-133">International Traffic in Arms Regulations (ITAR) is a set of US government regulations that control the export and import of defense-related articles and services on the [United States Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415).</span></span> 

<span data-ttu-id="3f4dd-134">適用于企業的 microsoft Office 365 為 Microsoft 生產力解決方案提供專屬主控服務，以支援美國聯邦機關的安全性、隱私權和法規遵從性需求。 (FISMA) 認證和商業實體受制于 ITAR。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-134">Microsoft Office 365 for Enterprises provides dedicated hosting services for Microsoft productivity solutions that support the security, privacy, and regulatory compliance requirements for US federal agencies requiring Federal Information Security Management (FISMA) certification and commercial entities subject to ITAR.</span></span>
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a><span data-ttu-id="3f4dd-135">使用 IPv6 和 Office 365 時的考慮事項</span><span class="sxs-lookup"><span data-stu-id="3f4dd-135">Things to consider when using IPv6 and Office 365</span></span>

<span data-ttu-id="3f4dd-136">建議您不要停用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-136">We recommend that you do not disable IPv6.</span></span> <span data-ttu-id="3f4dd-137">如需詳細資訊，請參閱本 [指南文章](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-137">For more information, see this [guidance article](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span></span> <span data-ttu-id="3f4dd-138">若要決定網路上使用的 IP 版本，請考慮下列各項：</span><span class="sxs-lookup"><span data-stu-id="3f4dd-138">To determine what IP versions are being used on your network, consider the following:</span></span>
  
- <span data-ttu-id="3f4dd-139">如果在命令提示字元處顯示的 **IPConfig** 命令包含名為「IPv6 Address "或" 暫時性 IPv6 address "的列，表示您在環境中已 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-139">If the display of the **IPConfig** command at the command prompt contains rows named "IPv6 Address" or "Temporary IPv6 Address," you have IPv6 in your environment.</span></span>

- <span data-ttu-id="3f4dd-140">如果所有的 IPv6 位址開頭都是 "fe80"，且對應至名稱為「Link-Local IPv6 Address "的列，則您的環境中不會有 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-140">If all the IPv6 addresses begin with "fe80" and correspond to rows named "Link-Local IPv6 Address," you don't have IPv6 in your environment.</span></span>

<span data-ttu-id="3f4dd-141">這些考慮可能適用于您的網路：</span><span class="sxs-lookup"><span data-stu-id="3f4dd-141">These considerations might apply to your network:</span></span>
  
- <span data-ttu-id="3f4dd-142">公用訂閱服務不支援透過信用卡以信用卡進行購買 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-142">The public subscription service does not support purchase by credit card over IPv6.</span></span> <span data-ttu-id="3f4dd-143">這不會套用至政府社區 Cloud (GCC) ，因為政府具有 Enterprise 合約 (EA) 授權。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-143">This does not apply to the Government Community Cloud (GCC) because governments have Enterprise Agreement (EA) licensing.</span></span>

- <span data-ttu-id="3f4dd-144">IPv6 不支援某些 Rights Management Services (RMS) 案例。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-144">IPv6 does not support some Rights Management Services (RMS) scenarios.</span></span>

- <span data-ttu-id="3f4dd-145">IPv6 不支援 BlackBerry® Enterprise Server (BE) ，因為 BlackBerry 不支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-145">IPv6 does not support BlackBerry® Enterprise Server (BES) because BlackBerry doesn't support IPv6.</span></span>

- <span data-ttu-id="3f4dd-146">如果您使用 Active Directory Federation Services (AD FS) 與 Office 365，則不支援使用 IPv6 來公佈您的 AD FS 網路端點至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-146">If you use Active Directory Federation Services (AD FS) with Office 365, advertising your AD FS network endpoint to Office 365 using IPv6 is not supported.</span></span> <span data-ttu-id="3f4dd-147">使用 Exchange Online 時，請勿在 AD FS DNS 專案中包含 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="3f4dd-147">You should not include AAAA records in the AD FS DNS entry when using Exchange Online.</span></span> 

<span data-ttu-id="3f4dd-148">您可以使用下列短連結返回這裡：[https://aka.ms/o365ip6](https://aka.ms/o365ip6)</span><span class="sxs-lookup"><span data-stu-id="3f4dd-148">Here's a short link you can use to come back: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3f4dd-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3f4dd-149">See also</span></span>

<span data-ttu-id="3f4dd-150">[IPv6 學習藍圖](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span><span class="sxs-lookup"><span data-stu-id="3f4dd-150">[IPv6 Learning Roadmap](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span></span>
  
[<span data-ttu-id="3f4dd-151">IPv6 生存指南</span><span class="sxs-lookup"><span data-stu-id="3f4dd-151">IPv6 Survival Guide</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
