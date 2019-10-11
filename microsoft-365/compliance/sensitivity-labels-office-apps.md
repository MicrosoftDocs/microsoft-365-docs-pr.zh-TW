---
title: 敏感度標籤在 Office App 中的運作方式
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用敏感度標籤，您可以分類並協助保護敏感內容，同時確保人員的生產力與共同作業能力不會受到阻礙。您可以使用敏感度標籤在標記的內容上強制執行保護設定，例如加密或浮水印。
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417562"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="89fba-104">敏感度標籤在 Office App 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="89fba-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="89fba-105">使用 Office 應用程式中的敏感度標籤有何必要條件？</span><span class="sxs-lookup"><span data-stu-id="89fba-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="89fba-106">常見需求</span><span class="sxs-lookup"><span data-stu-id="89fba-106">Common requirements</span></span> 

- <span data-ttu-id="89fba-107">整合敏感度標籤必須在[安全性與合規性中心中設定和發佈](https://aka.ms/managemip)</span><span class="sxs-lookup"><span data-stu-id="89fba-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="89fba-108">使用者必須使用其公司帳戶登入 Office。</span><span class="sxs-lookup"><span data-stu-id="89fba-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="89fba-109">使用者必須獲派 Office 365 E3 或以上版本的授權。</span><span class="sxs-lookup"><span data-stu-id="89fba-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="89fba-110">Windows 版 Office 的其他需求</span><span class="sxs-lookup"><span data-stu-id="89fba-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="89fba-111">絕對不能在 Office 中執行 Azure 資訊保護用戶端。</span><span class="sxs-lookup"><span data-stu-id="89fba-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="89fba-112">另請參閱：[敏感度標籤可以和Windows 版 Office 中的 Azure 資訊保護用戶端一起執行嗎？](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)。</span><span class="sxs-lookup"><span data-stu-id="89fba-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="89fba-113">所有平台上 Outlook 的其他需求</span><span class="sxs-lookup"><span data-stu-id="89fba-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="89fba-114">如果您在標籤設定中開啟了內容標記，則必須使用 Exchange Online，才能在傳輸中插入內容標記。</span><span class="sxs-lookup"><span data-stu-id="89fba-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="89fba-115">目前 Office 支援哪些敏感度標籤功能？</span><span class="sxs-lookup"><span data-stu-id="89fba-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="89fba-116"><font size="-1">功能</span><span class="sxs-lookup"><span data-stu-id="89fba-116"><font size="-1">Capability</span></span><th><span data-ttu-id="89fba-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="89fba-117"><font size="-1">Windows</span></span><th><span data-ttu-id="89fba-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">網頁</span><span class="sxs-lookup"><span data-stu-id="89fba-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="89fba-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="89fba-119"><font size="-1"> Word</span></span><br>
<span data-ttu-id="89fba-120">Excel</span><span class="sxs-lookup"><span data-stu-id="89fba-120">Excel</span></span><br>
<span data-ttu-id="89fba-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="89fba-121">PowerPoint</span></span><br>
<span data-ttu-id="89fba-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="89fba-122">Outlook</span></span>


<td><span data-ttu-id="89fba-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="89fba-123"><font size="-1"> Word</span></span><br>
<span data-ttu-id="89fba-124">Excel</span><span class="sxs-lookup"><span data-stu-id="89fba-124">Excel</span></span><br>
<span data-ttu-id="89fba-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="89fba-125">PowerPoint</span></span><br>
<span data-ttu-id="89fba-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="89fba-126">Outlook</span></span>

<td><span data-ttu-id="89fba-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="89fba-127"><font size="-1"> Word</span></span><br>
<span data-ttu-id="89fba-128">Excel</span><span class="sxs-lookup"><span data-stu-id="89fba-128">Excel</span></span><br>
<span data-ttu-id="89fba-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="89fba-129">PowerPoint</span></span>
<td><span data-ttu-id="89fba-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="89fba-130"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="89fba-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="89fba-131"><font size="-1"> Word</span></span><br>
<span data-ttu-id="89fba-132">Excel</span><span class="sxs-lookup"><span data-stu-id="89fba-132">Excel</span></span><br>
<span data-ttu-id="89fba-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="89fba-133">PowerPoint</span></span>
<td><span data-ttu-id="89fba-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="89fba-134"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="89fba-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="89fba-135"><font size="-1"> Word</span></span><br>
<span data-ttu-id="89fba-136">Excel</span><span class="sxs-lookup"><span data-stu-id="89fba-136">Excel</span></span><br>
<span data-ttu-id="89fba-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="89fba-137">PowerPoint</span></span>
<td><span data-ttu-id="89fba-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="89fba-138"><font size="-1"> Outlook </b>
</span></span></tr>

<tr>
<td><span data-ttu-id="89fba-139"><font size="-1">手動套用、變更或移除標籤</span><span class="sxs-lookup"><span data-stu-id="89fba-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="89fba-140"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-140"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="89fba-142"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-142"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="89fba-144"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-144"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="89fba-146"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-147"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-147"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="89fba-149"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-150"><font size="-1">即將推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="89fba-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="89fba-151"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="89fba-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="89fba-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">套用預設標籤</a>
</span><span class="sxs-lookup"><span data-stu-id="89fba-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="89fba-153"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-153"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="89fba-155"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-155"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="89fba-157"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-157"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="89fba-159"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-160"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-160"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="89fba-162"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-163"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-164"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="89fba-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="89fba-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">需要變更標籤的理由</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="89fba-166"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-166"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="89fba-168"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-168"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="89fba-170"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-170"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="89fba-172"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-173"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-173"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="89fba-175"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-176"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-177"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="89fba-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="89fba-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">提供自訂說明頁面的說明連結</a>
</span><span class="sxs-lookup"><span data-stu-id="89fba-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="89fba-179"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-179"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="89fba-181"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-181"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="89fba-183"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-183"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="89fba-185"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-186"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-186"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="89fba-188"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-189"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-190"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="89fba-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="89fba-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">標記內容</a>
</span><span class="sxs-lookup"><span data-stu-id="89fba-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="89fba-192"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-192"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="89fba-194"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-194"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="89fba-196"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-196"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="89fba-198"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-199"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-199"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="89fba-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="89fba-201"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-202"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-203"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="89fba-203"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="89fba-204"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">指派預先定義的權限</a>
</span><span class="sxs-lookup"><span data-stu-id="89fba-204"><font size="-1">Assign pre-defined permissions</span></span><td><span data-ttu-id="89fba-205"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-205"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="89fba-207"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-207"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="89fba-209"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-209"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="89fba-211"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-212"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="89fba-212"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="89fba-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="89fba-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="89fba-214"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-215"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-216"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="89fba-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="89fba-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">讓使用者指派權限</a>
</span><span class="sxs-lookup"><span data-stu-id="89fba-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Let users assign permissions</a>
</span></span><td><span data-ttu-id="89fba-218"><font size="-1"><b>是</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="89fba-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="89fba-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="89fba-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="89fba-220"><font size="-1"><b>是</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="89fba-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="89fba-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="89fba-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="89fba-222"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-223"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-224"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="89fba-225"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="89fba-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="89fba-226"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-227"><font size="-1">即將推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="89fba-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="89fba-228"><font size="-1">傳送<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">標籤分析</a>資料給系統管理員</span><span class="sxs-lookup"><span data-stu-id="89fba-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="89fba-229"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="89fba-230"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="89fba-231"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-232"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-233"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-234"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-235"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-236"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="89fba-237"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">要求使用者在電子郵件和文件中套用標籤</a>
</span><span class="sxs-lookup"><span data-stu-id="89fba-237"><font size="-1">Require users to apply a label to their email and documents</span></span><td><span data-ttu-id="89fba-238"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="89fba-239"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="89fba-240"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-241"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-242"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-243"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-244"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-245"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="89fba-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">自動將敏感度標籤套用到內容</a>
</span><span class="sxs-lookup"><span data-stu-id="89fba-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Apply a sensitivity label to content automatically</a>
</span></span><td><span data-ttu-id="89fba-247"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="89fba-248"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="89fba-249"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-250"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-251"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-252"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-253"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="89fba-254"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="89fba-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="89fba-255"><sup>1</sup>如設定，系統會提示使用者說明標籤降級的理由。</span><span class="sxs-lookup"><span data-stu-id="89fba-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="89fba-256">但是，理由資料尚未提供給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="89fba-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="89fba-257">當支援 [傳送標籤分析資料給系統管理員] 功能時，系統就會提供此功能。</span><span class="sxs-lookup"><span data-stu-id="89fba-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="89fba-258"><sup>2</sup>目前只有 Windows 版和 Mac 版 Outlook 才能讓使用者指派權限。</span><span class="sxs-lookup"><span data-stu-id="89fba-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="89fba-259">Word、Excel 和 PowerPoint 的適用性未定。</span><span class="sxs-lookup"><span data-stu-id="89fba-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="89fba-260"><sup>3</sup>預計是 2019 年的第四季。</span><span class="sxs-lookup"><span data-stu-id="89fba-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="89fba-261">在內容加上敏感度標籤之後，何時會套用內容標記或加密功能？</span><span class="sxs-lookup"><span data-stu-id="89fba-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="89fba-262">應用程式</span><span class="sxs-lookup"><span data-stu-id="89fba-262">Application</span></span> | <span data-ttu-id="89fba-263">內容標記</span><span class="sxs-lookup"><span data-stu-id="89fba-263">Content marking</span></span> | <span data-ttu-id="89fba-264">加密</span><span class="sxs-lookup"><span data-stu-id="89fba-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="89fba-265">所有平台上的 Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="89fba-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="89fba-266">立即</span><span class="sxs-lookup"><span data-stu-id="89fba-266">Immediately</span></span> | <span data-ttu-id="89fba-267">立即</span><span class="sxs-lookup"><span data-stu-id="89fba-267">Immediately</span></span> |
| <span data-ttu-id="89fba-268">電腦版和 Mac 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="89fba-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="89fba-269">在 Exchange Online 傳送電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="89fba-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="89fba-270">立即</span><span class="sxs-lookup"><span data-stu-id="89fba-270">Immediately</span></span> |
| <span data-ttu-id="89fba-271">網頁版、iOS 版和 Android 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="89fba-271">Outlook on the web, iOS, and Android</span></span> | <span data-ttu-id="89fba-272">在 Exchange Online 傳送電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="89fba-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="89fba-273">在 Exchange Online 傳送電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="89fba-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="89fba-274">敏感度標籤可以和 Windows 版 Office 中的 Azure 資訊保護用戶端一起執行嗎？</span><span class="sxs-lookup"><span data-stu-id="89fba-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="89fba-275">不行。</span><span class="sxs-lookup"><span data-stu-id="89fba-275">No.</span></span> <span data-ttu-id="89fba-276">如果在 Windows 版 Office 中載入 Azure 資訊保護用戶端，敏感度標籤即會關閉。</span><span class="sxs-lookup"><span data-stu-id="89fba-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="89fba-277">如果您已安裝 Azure 資訊保護用戶端，但想要改用敏感度標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="89fba-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="89fba-278">設定 [在 Office 中使用 [敏感度] 功能以套用並檢視敏感度標籤] \*\*\*\* 的群組原則設定，這個設定可在 **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings** 下找到。</span><span class="sxs-lookup"><span data-stu-id="89fba-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="89fba-279">注意：這個設定可透過傳統的群組原則部署機制來部署，或是透過 [Office 雲端原則服務][](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)。</span><span class="sxs-lookup"><span data-stu-id="89fba-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="89fba-280">或者，您可以解除安裝或 [停用] [](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) Azure 資訊保護用戶端。</span><span class="sxs-lookup"><span data-stu-id="89fba-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="89fba-281">重新啟動所有 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="89fba-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="89fba-282">Office 的非訂閱版本是否支援敏感度標籤，例如 Office 2016 或 Office 2019？</span><span class="sxs-lookup"><span data-stu-id="89fba-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="89fba-283">不行。</span><span class="sxs-lookup"><span data-stu-id="89fba-283">No.</span></span> <span data-ttu-id="89fba-284">只有 Office 365 訂閱才支援敏感度標籤，所有非訂閱版本均不支援。</span><span class="sxs-lookup"><span data-stu-id="89fba-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="89fba-285">不過，可以在 Office 的非訂閱版本中使用 Azure 資訊保護的整合式標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="89fba-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="89fba-286">我在設定敏感度標籤之前已經部署好保護範本。</span><span class="sxs-lookup"><span data-stu-id="89fba-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="89fba-287">它們去哪裡了？</span><span class="sxs-lookup"><span data-stu-id="89fba-287">Where did they go?</span></span>

<span data-ttu-id="89fba-288">啟用敏感度標籤後，系統管理員定義的[保護範本](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)即會隱藏，Office 使用者無法使用，因為靈敏度標籤已啟用加密功能，因此這些範本是多餘的。</span><span class="sxs-lookup"><span data-stu-id="89fba-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="89fba-289">檔案或電子郵件是否可以有多個分類？</span><span class="sxs-lookup"><span data-stu-id="89fba-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="89fba-290">不行。</span><span class="sxs-lookup"><span data-stu-id="89fba-290">No.</span></span> <span data-ttu-id="89fba-291">使用者一次只能針對每個文件或電子郵件選取一個標籤。</span><span class="sxs-lookup"><span data-stu-id="89fba-291">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="89fba-292">標記電子郵件後，附件也會自動獲得相同的標記嗎？</span><span class="sxs-lookup"><span data-stu-id="89fba-292">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="89fba-293">不會。</span><span class="sxs-lookup"><span data-stu-id="89fba-293">No.</span></span> <span data-ttu-id="89fba-294">當您標記具有附件的電子郵件時，這些附件不會繼承相同的標籤。</span><span class="sxs-lookup"><span data-stu-id="89fba-294">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="89fba-295">附件會保持為沒有標籤，或者保留個別套用的標籤。</span><span class="sxs-lookup"><span data-stu-id="89fba-295">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="89fba-296">但是，如果電子郵件的標籤套用保護，則該保護將套用至 Office 附件。</span><span class="sxs-lookup"><span data-stu-id="89fba-296">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89fba-297">其他資源</span><span class="sxs-lookup"><span data-stu-id="89fba-297">Additional resources</span></span>

[<span data-ttu-id="89fba-298">Azure 資訊保護中分類與標籤的常見問題集</span><span class="sxs-lookup"><span data-stu-id="89fba-298">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="89fba-299">在 Office 中將敏感度標籤套用至您的文件和電子郵件</span><span class="sxs-lookup"><span data-stu-id="89fba-299">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
