---
title: Office 365 GCC High 的 DNS 記錄
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 摘要： Office 365 GCC 高的 DNS 記錄
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688458"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="8daa7-103">Office 365 GCC High 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="8daa7-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="8daa7-104">*本文適用于 Office 365 GCC 高及 Microsoft 365 GCC 高*</span><span class="sxs-lookup"><span data-stu-id="8daa7-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="8daa7-105">在 Office 365 GCC 高的情況下，您必須將您的 SMTP 和 SIP 網域新增至您的線上服務租使用者。</span><span class="sxs-lookup"><span data-stu-id="8daa7-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="8daa7-106">您將使用 Azure AD 中的 New-MsolDomain Cmdlet 來執行此動作 PowerShell 或使用 [Azure 政府入口網站](https://portal.azure.us) 來開始新增網域及證明擁有權的程式。</span><span class="sxs-lookup"><span data-stu-id="8daa7-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="8daa7-107">當您將網域新增至租使用者並加以驗證之後，請使用下列指引為下列服務新增適當的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="8daa7-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="8daa7-108">您可能需要修改下表，以符合組織對輸入 MX 記錄 () s 的需求，以及您已具備的任何現有 Exchange 自動探索記錄 () 。</span><span class="sxs-lookup"><span data-stu-id="8daa7-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="8daa7-109">強烈建議您將這些 DNS 記錄與您的郵件小組協調，以避免任何中斷或錯誤傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8daa7-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="8daa7-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8daa7-110">Exchange Online</span></span>

| <span data-ttu-id="8daa7-111">Type (類型)</span><span class="sxs-lookup"><span data-stu-id="8daa7-111">Type</span></span> | <span data-ttu-id="8daa7-112">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="8daa7-112">Priority</span></span> | <span data-ttu-id="8daa7-113">主機名稱</span><span class="sxs-lookup"><span data-stu-id="8daa7-113">Host name</span></span> | <span data-ttu-id="8daa7-114">指向位址或值</span><span class="sxs-lookup"><span data-stu-id="8daa7-114">Points to address or value</span></span> | <span data-ttu-id="8daa7-115">TTL</span><span class="sxs-lookup"><span data-stu-id="8daa7-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="8daa7-116">MX</span><span class="sxs-lookup"><span data-stu-id="8daa7-116">MX</span></span> | <span data-ttu-id="8daa7-117">0</span><span class="sxs-lookup"><span data-stu-id="8daa7-117">0</span></span> | @ | <span data-ttu-id="8daa7-118">\*\* mail.protection.office365.us (請參閱下方的其他詳細資料) </span><span class="sxs-lookup"><span data-stu-id="8daa7-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="8daa7-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8daa7-119">1 Hour</span></span> |
| <span data-ttu-id="8daa7-120">TXT</span><span class="sxs-lookup"><span data-stu-id="8daa7-120">TXT</span></span> | - | @ | <span data-ttu-id="8daa7-121">v = spf1 包含: spf.protection.outlook.com office365。美國所有</span><span class="sxs-lookup"><span data-stu-id="8daa7-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="8daa7-122">1 小時</span><span class="sxs-lookup"><span data-stu-id="8daa7-122">1 Hour</span></span> |
| <span data-ttu-id="8daa7-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="8daa7-123">CNAME</span></span> | - | <span data-ttu-id="8daa7-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8daa7-124">autodiscover</span></span> | <span data-ttu-id="8daa7-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="8daa7-125">autodiscover.office365.us</span></span> | <span data-ttu-id="8daa7-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8daa7-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="8daa7-127">Exchange自動探索記錄</span><span class="sxs-lookup"><span data-stu-id="8daa7-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="8daa7-128">如果您有 Exchange Server 內部部署，建議您在遷移至 Exchange Online 時保留現有的記錄，並在完成遷移之後更新該記錄。</span><span class="sxs-lookup"><span data-stu-id="8daa7-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="8daa7-129">Exchange OnlineMX 記錄</span><span class="sxs-lookup"><span data-stu-id="8daa7-129">Exchange Online MX Record</span></span>

<span data-ttu-id="8daa7-130">公認的網域的 MX 記錄值遵循如上所述的標準 *格式： mail.protection.office365.us*，以您的預設租使用者名稱的第一個部分取代 *承租人* 。</span><span class="sxs-lookup"><span data-stu-id="8daa7-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="8daa7-131">例如，如果您的租使用者名稱是 contoso.onmicrosoft.us，您可以使用 **contoso.mail.protection.office365.us** 做為 MX 記錄的值。</span><span class="sxs-lookup"><span data-stu-id="8daa7-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="8daa7-132">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="8daa7-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="8daa7-133">CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="8daa7-133">CNAME records</span></span>

| <span data-ttu-id="8daa7-134">類型</span><span class="sxs-lookup"><span data-stu-id="8daa7-134">Type</span></span> | <span data-ttu-id="8daa7-135">主機名稱</span><span class="sxs-lookup"><span data-stu-id="8daa7-135">Host name</span></span> | <span data-ttu-id="8daa7-136">指向位址或值</span><span class="sxs-lookup"><span data-stu-id="8daa7-136">Points to address or value</span></span> | <span data-ttu-id="8daa7-137">TTL</span><span class="sxs-lookup"><span data-stu-id="8daa7-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="8daa7-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="8daa7-138">CNAME</span></span> | <span data-ttu-id="8daa7-139">sip</span><span class="sxs-lookup"><span data-stu-id="8daa7-139">sip</span></span> | <span data-ttu-id="8daa7-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="8daa7-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="8daa7-141">1 小時</span><span class="sxs-lookup"><span data-stu-id="8daa7-141">1 Hour</span></span> |
| <span data-ttu-id="8daa7-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="8daa7-142">CNAME</span></span> | <span data-ttu-id="8daa7-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8daa7-143">lyncdiscover</span></span> | <span data-ttu-id="8daa7-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="8daa7-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="8daa7-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8daa7-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="8daa7-146">SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="8daa7-146">SRV records</span></span>

| <span data-ttu-id="8daa7-147">Type (類型)</span><span class="sxs-lookup"><span data-stu-id="8daa7-147">Type</span></span> | <span data-ttu-id="8daa7-148">Service (服務)</span><span class="sxs-lookup"><span data-stu-id="8daa7-148">Service</span></span> | <span data-ttu-id="8daa7-149">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="8daa7-149">Protocol</span></span> | <span data-ttu-id="8daa7-150">Port (連接埠)</span><span class="sxs-lookup"><span data-stu-id="8daa7-150">Port</span></span> | <span data-ttu-id="8daa7-151">字體粗細</span><span class="sxs-lookup"><span data-stu-id="8daa7-151">Weight</span></span> | <span data-ttu-id="8daa7-152">優先順序</span><span class="sxs-lookup"><span data-stu-id="8daa7-152">Priority</span></span> | <span data-ttu-id="8daa7-153">名稱</span><span class="sxs-lookup"><span data-stu-id="8daa7-153">Name</span></span> | <span data-ttu-id="8daa7-154">Target (目標)</span><span class="sxs-lookup"><span data-stu-id="8daa7-154">Target</span></span> | <span data-ttu-id="8daa7-155">TTL</span><span class="sxs-lookup"><span data-stu-id="8daa7-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="8daa7-156">SRV</span><span class="sxs-lookup"><span data-stu-id="8daa7-156">SRV</span></span> | <span data-ttu-id="8daa7-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="8daa7-157">\_sip</span></span> | <span data-ttu-id="8daa7-158">\_Tls</span><span class="sxs-lookup"><span data-stu-id="8daa7-158">\_tls</span></span> | <span data-ttu-id="8daa7-159">443</span><span class="sxs-lookup"><span data-stu-id="8daa7-159">443</span></span> | <span data-ttu-id="8daa7-160">1</span><span class="sxs-lookup"><span data-stu-id="8daa7-160">1</span></span> | <span data-ttu-id="8daa7-161">100</span><span class="sxs-lookup"><span data-stu-id="8daa7-161">100</span></span> | @ | <span data-ttu-id="8daa7-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="8daa7-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="8daa7-163">1 Hour (1 小時)</span><span class="sxs-lookup"><span data-stu-id="8daa7-163">1 Hour</span></span> |
| <span data-ttu-id="8daa7-164">SRV</span><span class="sxs-lookup"><span data-stu-id="8daa7-164">SRV</span></span> | <span data-ttu-id="8daa7-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8daa7-165">\_sipfederationtls</span></span> | <span data-ttu-id="8daa7-166">\_Tcp</span><span class="sxs-lookup"><span data-stu-id="8daa7-166">\_tcp</span></span> | <span data-ttu-id="8daa7-167">5061</span><span class="sxs-lookup"><span data-stu-id="8daa7-167">5061</span></span> | <span data-ttu-id="8daa7-168">1</span><span class="sxs-lookup"><span data-stu-id="8daa7-168">1</span></span> | <span data-ttu-id="8daa7-169">100</span><span class="sxs-lookup"><span data-stu-id="8daa7-169">100</span></span> | @ | <span data-ttu-id="8daa7-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="8daa7-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="8daa7-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8daa7-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="8daa7-172">其他 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="8daa7-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8daa7-173">如果您的 DNS 區域中有現有的 *msoid* CNAME 記錄，您必須在這段時間內從 DNS **移除** 記錄。</span><span class="sxs-lookup"><span data-stu-id="8daa7-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="8daa7-174">msoid 記錄與 *(以前 Office 365 專業增強版)* 的 Microsoft 365 企業版應用程式不相容，因此會使您無法成功啟用。</span><span class="sxs-lookup"><span data-stu-id="8daa7-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
