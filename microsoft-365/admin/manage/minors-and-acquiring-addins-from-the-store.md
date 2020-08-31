---
title: 對存放區中的增益集進行未成年人和取得
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 深入瞭解一般資料保護法規 (GDPR) 管理未成年人之個人資料的規章。
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306548"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="b2bb7-103">對存放區中的增益集進行未成年人和取得</span><span class="sxs-lookup"><span data-stu-id="b2bb7-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="b2bb7-104">一般資料保護法規 (GDPR) 是一種已生效的歐盟法規（可能會是25，2018）。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="b2bb7-105">它可讓使用者具備及保護其資料的權力。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="b2bb7-106">其中一個 GDPR 的其中一個方面是，所有未成年人都無法將其個人資料傳送給他們的父系或監護人未獲核准的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="b2bb7-107">定義為次要的特定年齡取決於個人所在的地區。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="b2bb7-108">法律規定具有「父母同意」規定的地區包括美國、韓國、英國和歐盟。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="b2bb7-109">針對這些地區，將會封鎖 (透過 Azure Active Directory) 取得任何新的 Office 增益集，並執行先前取得之增益集的次要功能。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="b2bb7-110">對於沒有法令規定的國家，將不會有下載限制。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="b2bb7-111">根據 Azure Active Directory 中所指定的資料，將使用者判斷為次要。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="b2bb7-112">組織管理員負責宣告法律年齡群組和該使用者的「父母同意」。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="b2bb7-113">如果上層/監護人 consents 使用特定增益集，則組織系統管理員可以使用集中式部署，將該增益集部署至所有已同意的未成年人。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="b2bb7-114">若要 GDPR 相容性，您必須確定在學校/組織中部署下列 Office 組建中的其中一項。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="b2bb7-115">**Word、Excel、PowerPoint 及專案**：</span><span class="sxs-lookup"><span data-stu-id="b2bb7-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="b2bb7-116">**平台**</span><span class="sxs-lookup"><span data-stu-id="b2bb7-116">**Platform**</span></span> <br/> |<span data-ttu-id="b2bb7-117">**組建號碼**</span><span class="sxs-lookup"><span data-stu-id="b2bb7-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="b2bb7-118">Microsoft 365 應用程式 enterprise (目前通道) </span><span class="sxs-lookup"><span data-stu-id="b2bb7-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="b2bb7-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="b2bb7-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="b2bb7-120">適用于企業的 Microsoft 365 應用程式 (半年 Enterprise 通道) </span><span class="sxs-lookup"><span data-stu-id="b2bb7-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="b2bb7-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="b2bb7-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="b2bb7-122">Office 2016 for Windows</span><span class="sxs-lookup"><span data-stu-id="b2bb7-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="b2bb7-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="b2bb7-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="b2bb7-124">Office 2013 for Windows</span><span class="sxs-lookup"><span data-stu-id="b2bb7-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="b2bb7-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="b2bb7-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="b2bb7-126">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="b2bb7-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="b2bb7-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="b2bb7-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="b2bb7-128">網頁版 Office</span><span class="sxs-lookup"><span data-stu-id="b2bb7-128">Office for the web</span></span>  <br/> |<span data-ttu-id="b2bb7-129">不適用</span><span class="sxs-lookup"><span data-stu-id="b2bb7-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="b2bb7-130">**Outlook**：</span><span class="sxs-lookup"><span data-stu-id="b2bb7-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="b2bb7-131">**平台**</span><span class="sxs-lookup"><span data-stu-id="b2bb7-131">**Platform**</span></span> <br/> |<span data-ttu-id="b2bb7-132">**組建號碼**</span><span class="sxs-lookup"><span data-stu-id="b2bb7-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="b2bb7-133">Outlook 2016 for Windows (MSI) </span><span class="sxs-lookup"><span data-stu-id="b2bb7-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="b2bb7-134">建立無待定</span><span class="sxs-lookup"><span data-stu-id="b2bb7-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="b2bb7-135">適用于 Windows (C2R 的 Outlook 2016) </span><span class="sxs-lookup"><span data-stu-id="b2bb7-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="b2bb7-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="b2bb7-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="b2bb7-137">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="b2bb7-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="b2bb7-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="b2bb7-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="b2bb7-139">iOS 的 Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="b2bb7-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="b2bb7-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="b2bb7-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="b2bb7-141">適用于 Android 的 Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="b2bb7-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="b2bb7-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="b2bb7-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="b2bb7-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="b2bb7-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="b2bb7-144">不適用</span><span class="sxs-lookup"><span data-stu-id="b2bb7-144">N/A</span></span>  <br/> |

 <span data-ttu-id="b2bb7-145">**Office 2013 需求**</span><span class="sxs-lookup"><span data-stu-id="b2bb7-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="b2bb7-146">如果啟用 Active Directory 驗證程式庫 (ADAL) ，則 Windows 的 Word、Excel 及 PowerPoint 2013 會支援相同的各處檢查。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="b2bb7-147">規範有兩個選項，如接下來所述。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="b2bb7-148">**啟用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-148">**Enable ADAL**.</span></span> <span data-ttu-id="b2bb7-149">本文說明如何啟用 ADAL for Office 2013：搭配 [使用 Microsoft 365 新式驗證與 office 用戶端](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="b2bb7-150">您也需要將登錄機碼設定為啟用 ADAL，如在 [Windows 裝置上啟用 Office 2013 新式驗證](../security-and-compliance/enable-modern-authentication.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="b2bb7-151">此外，您必須安裝下列 Office 2013 的四月更新：</span><span class="sxs-lookup"><span data-stu-id="b2bb7-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="b2bb7-152">Office 2013 的安全性更新說明：4月10日（2018）</span><span class="sxs-lookup"><span data-stu-id="b2bb7-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="b2bb7-153">2018年4月3日，Office 2013 的更新 (KB4018333) </span><span class="sxs-lookup"><span data-stu-id="b2bb7-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="b2bb7-154">**不要啟用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="b2bb7-155">如果您無法在 Office 2013 中啟用 ADAL，我們建議使用「群組原則」來關閉 Office 用戶端的存放區。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="b2bb7-156">有關如何關閉 Office 相關應用程式設定的資訊位於 [這裡](https://technet.microsoft.com/library/cc178992.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b2bb7-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="b2bb7-157">相關文章</span><span class="sxs-lookup"><span data-stu-id="b2bb7-157">Related articles</span></span>

[<span data-ttu-id="b2bb7-158">在系統管理中心部署增益集</span><span class="sxs-lookup"><span data-stu-id="b2bb7-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="b2bb7-159">在系統管理中心管理增益集</span><span class="sxs-lookup"><span data-stu-id="b2bb7-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
