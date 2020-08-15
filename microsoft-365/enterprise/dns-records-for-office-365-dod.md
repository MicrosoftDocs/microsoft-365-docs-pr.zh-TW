---
title: Office 365 DoD 的 DNS 記錄
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
description: 摘要： Office 365 DoD 的 DNS 記錄
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688469"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="fd643-103">Office 365 DoD 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="fd643-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="fd643-104">*本文適用于 Office 365 DoD 和 Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="fd643-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="fd643-105">加入 Office 365 DoD 的一部分，您必須將您的 SMTP 和 SIP 網域新增至您的線上服務租使用者。</span><span class="sxs-lookup"><span data-stu-id="fd643-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="fd643-106">您將使用 Azure AD PowerShell 中的 MsolDomain Cmdlet 來執行這項作業，或使用 [Azure 政府入口網站](https://portal.azure.us) 來開始新增網域及證明擁有權的程式。</span><span class="sxs-lookup"><span data-stu-id="fd643-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="fd643-107">當您將網域新增至租使用者並加以驗證之後，請使用下列指引為下列服務新增適當的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="fd643-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="fd643-108">您可能需要修改下表，以符合組織對輸入 MX 記錄 () s 的需求，以及您已具備的任何現有 Exchange 自動探索記錄 () 。</span><span class="sxs-lookup"><span data-stu-id="fd643-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="fd643-109">強烈建議您將這些 DNS 記錄與您的郵件小組協調，以避免任何中斷或錯誤傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="fd643-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="fd643-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fd643-110">Exchange Online</span></span>

| <span data-ttu-id="fd643-111">Type (類型)</span><span class="sxs-lookup"><span data-stu-id="fd643-111">Type</span></span> | <span data-ttu-id="fd643-112">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="fd643-112">Priority</span></span> | <span data-ttu-id="fd643-113">主機名稱</span><span class="sxs-lookup"><span data-stu-id="fd643-113">Host name</span></span> | <span data-ttu-id="fd643-114">指向 [位址] 或 [值]</span><span class="sxs-lookup"><span data-stu-id="fd643-114">Points to address or value</span></span> | <span data-ttu-id="fd643-115">TTL</span><span class="sxs-lookup"><span data-stu-id="fd643-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="fd643-116">MX</span><span class="sxs-lookup"><span data-stu-id="fd643-116">MX</span></span> | <span data-ttu-id="fd643-117">0</span><span class="sxs-lookup"><span data-stu-id="fd643-117">0</span></span> | @ | <span data-ttu-id="fd643-118">\* \*mail.protection.office365.us (請參閱下方的其他詳細資料) </span><span class="sxs-lookup"><span data-stu-id="fd643-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="fd643-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="fd643-119">1 Hour</span></span> |
| <span data-ttu-id="fd643-120">TXT</span><span class="sxs-lookup"><span data-stu-id="fd643-120">TXT</span></span> | - | @ | <span data-ttu-id="fd643-121">v = spf1 包含: spf.protection.outlook.com office365。美國所有</span><span class="sxs-lookup"><span data-stu-id="fd643-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="fd643-122">1 小時</span><span class="sxs-lookup"><span data-stu-id="fd643-122">1 Hour</span></span> |
| <span data-ttu-id="fd643-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd643-123">CNAME</span></span> | - | <span data-ttu-id="fd643-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fd643-124">autodiscover</span></span> | <span data-ttu-id="fd643-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="fd643-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="fd643-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="fd643-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="fd643-127">Exchange 自動探索記錄</span><span class="sxs-lookup"><span data-stu-id="fd643-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="fd643-128">如果您有 Exchange Server 內部部署，建議您在遷移至 Exchange Online 時保留現有的記錄，並在完成遷移時更新該記錄。</span><span class="sxs-lookup"><span data-stu-id="fd643-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="fd643-129">Exchange Online MX 記錄</span><span class="sxs-lookup"><span data-stu-id="fd643-129">Exchange Online MX Record</span></span>

<span data-ttu-id="fd643-130">公認的網域的 MX 記錄值遵循如上所述的標準 *格式： mail.protection.office365.us*，以您的預設租使用者名稱的第一個部分取代 *承租人* 。</span><span class="sxs-lookup"><span data-stu-id="fd643-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="fd643-131">例如，如果您的租使用者名稱是 contoso.onmicrosoft.us，您可以使用 **contoso.mail.protection.office365.us** 做為 MX 記錄的值。</span><span class="sxs-lookup"><span data-stu-id="fd643-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="fd643-132">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="fd643-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="fd643-133">CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="fd643-133">CNAME records</span></span>

| <span data-ttu-id="fd643-134">類型</span><span class="sxs-lookup"><span data-stu-id="fd643-134">Type</span></span> | <span data-ttu-id="fd643-135">主機名稱</span><span class="sxs-lookup"><span data-stu-id="fd643-135">Host name</span></span> | <span data-ttu-id="fd643-136">指向 [位址] 或 [值]</span><span class="sxs-lookup"><span data-stu-id="fd643-136">Points to address or value</span></span> | <span data-ttu-id="fd643-137">TTL</span><span class="sxs-lookup"><span data-stu-id="fd643-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="fd643-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd643-138">CNAME</span></span> | <span data-ttu-id="fd643-139">sip</span><span class="sxs-lookup"><span data-stu-id="fd643-139">sip</span></span> | <span data-ttu-id="fd643-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="fd643-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="fd643-141">1 小時</span><span class="sxs-lookup"><span data-stu-id="fd643-141">1 Hour</span></span> |
| <span data-ttu-id="fd643-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd643-142">CNAME</span></span> | <span data-ttu-id="fd643-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fd643-143">lyncdiscover</span></span> | <span data-ttu-id="fd643-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="fd643-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="fd643-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="fd643-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="fd643-146">SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="fd643-146">SRV records</span></span>

| <span data-ttu-id="fd643-147">Type (類型)</span><span class="sxs-lookup"><span data-stu-id="fd643-147">Type</span></span> | <span data-ttu-id="fd643-148">Service (服務)</span><span class="sxs-lookup"><span data-stu-id="fd643-148">Service</span></span> | <span data-ttu-id="fd643-149">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="fd643-149">Protocol</span></span> | <span data-ttu-id="fd643-150">Port (連接埠)</span><span class="sxs-lookup"><span data-stu-id="fd643-150">Port</span></span> | <span data-ttu-id="fd643-151">字體粗細</span><span class="sxs-lookup"><span data-stu-id="fd643-151">Weight</span></span> | <span data-ttu-id="fd643-152">優先順序</span><span class="sxs-lookup"><span data-stu-id="fd643-152">Priority</span></span> | <span data-ttu-id="fd643-153">名稱</span><span class="sxs-lookup"><span data-stu-id="fd643-153">Name</span></span> | <span data-ttu-id="fd643-154">Target (目標)</span><span class="sxs-lookup"><span data-stu-id="fd643-154">Target</span></span> | <span data-ttu-id="fd643-155">TTL</span><span class="sxs-lookup"><span data-stu-id="fd643-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="fd643-156">SRV</span><span class="sxs-lookup"><span data-stu-id="fd643-156">SRV</span></span> | <span data-ttu-id="fd643-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="fd643-157">\_sip</span></span> | <span data-ttu-id="fd643-158">\_Tls</span><span class="sxs-lookup"><span data-stu-id="fd643-158">\_tls</span></span> | <span data-ttu-id="fd643-159">443</span><span class="sxs-lookup"><span data-stu-id="fd643-159">443</span></span> | <span data-ttu-id="fd643-160">1</span><span class="sxs-lookup"><span data-stu-id="fd643-160">1</span></span> | <span data-ttu-id="fd643-161">100</span><span class="sxs-lookup"><span data-stu-id="fd643-161">100</span></span> | @ | <span data-ttu-id="fd643-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="fd643-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="fd643-163">1 Hour (1 小時)</span><span class="sxs-lookup"><span data-stu-id="fd643-163">1 Hour</span></span> |
| <span data-ttu-id="fd643-164">SRV</span><span class="sxs-lookup"><span data-stu-id="fd643-164">SRV</span></span> | <span data-ttu-id="fd643-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="fd643-165">\_sipfederationtls</span></span> | <span data-ttu-id="fd643-166">\_Tcp</span><span class="sxs-lookup"><span data-stu-id="fd643-166">\_tcp</span></span> | <span data-ttu-id="fd643-167">5061</span><span class="sxs-lookup"><span data-stu-id="fd643-167">5061</span></span> | <span data-ttu-id="fd643-168">1</span><span class="sxs-lookup"><span data-stu-id="fd643-168">1</span></span> | <span data-ttu-id="fd643-169">100</span><span class="sxs-lookup"><span data-stu-id="fd643-169">100</span></span> | @ | <span data-ttu-id="fd643-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="fd643-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="fd643-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="fd643-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="fd643-172">其他 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="fd643-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd643-173">如果您的 DNS 區域中有現有的 *msoid* CNAME 記錄，您必須在這段時間內從 DNS **移除** 記錄。</span><span class="sxs-lookup"><span data-stu-id="fd643-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="fd643-174">Msoid 記錄與 Microsoft 365 企業版應用程式不相容 \* (以前的 Office 365 ProPlus) \* 而且會使啟用不再成功。</span><span class="sxs-lookup"><span data-stu-id="fd643-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
