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
ms.openlocfilehash: 1de7eadfcf95a54917c1d5e2cc0d42cc1ad486a5
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378647"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="9ba2d-104">敏感度標籤在 Office App 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="9ba2d-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="9ba2d-105">使用 Office 應用程式中的敏感度標籤有何必要條件？</span><span class="sxs-lookup"><span data-stu-id="9ba2d-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="9ba2d-106">常見需求</span><span class="sxs-lookup"><span data-stu-id="9ba2d-106">Common requirements</span></span> 

- <span data-ttu-id="9ba2d-107">整合敏感度標籤必須在[安全性與合規性中心中設定和發佈](https://aka.ms/managemip)</span><span class="sxs-lookup"><span data-stu-id="9ba2d-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="9ba2d-108">使用者必須使用其公司帳戶登入 Office。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="9ba2d-109">使用者必須獲派 Office 365 E3 或以上版本的授權。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="9ba2d-110">Windows 版 Office 的其他需求</span><span class="sxs-lookup"><span data-stu-id="9ba2d-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="9ba2d-111">絕對不能在 Office 中執行 Azure 資訊保護用戶端。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="9ba2d-112">另請參閱：[敏感度標籤可以和Windows 版 Office 中的 Azure 資訊保護用戶端一起執行嗎？](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="9ba2d-113">所有平台上 Outlook 的其他需求</span><span class="sxs-lookup"><span data-stu-id="9ba2d-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="9ba2d-114">如果您在標籤設定中開啟了內容標記，則必須使用 Exchange Online，才能在傳輸中插入內容標記。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="9ba2d-115">目前 Office 支援哪些敏感度標籤功能？</span><span class="sxs-lookup"><span data-stu-id="9ba2d-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="9ba2d-116"><font size="-1">功能</span><span class="sxs-lookup"><span data-stu-id="9ba2d-116"><font size="-1"></span></span><th><span data-ttu-id="9ba2d-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="9ba2d-117"><font size="-1"></span></span><th><span data-ttu-id="9ba2d-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">網頁</span><span class="sxs-lookup"><span data-stu-id="9ba2d-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="9ba2d-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="9ba2d-119"><font size="-1">Word</span></span><br>
<span data-ttu-id="9ba2d-120">Excel</span><span class="sxs-lookup"><span data-stu-id="9ba2d-120">Excel</span></span><br>
<span data-ttu-id="9ba2d-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9ba2d-121">PowerPoint</span></span><br>
<span data-ttu-id="9ba2d-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="9ba2d-122">Outlook</span></span>


<td><span data-ttu-id="9ba2d-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="9ba2d-123"><font size="-1">Word</span></span><br>
<span data-ttu-id="9ba2d-124">Excel</span><span class="sxs-lookup"><span data-stu-id="9ba2d-124">Excel</span></span><br>
<span data-ttu-id="9ba2d-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9ba2d-125">PowerPoint</span></span><br>
<span data-ttu-id="9ba2d-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="9ba2d-126">Outlook</span></span>

<td><span data-ttu-id="9ba2d-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="9ba2d-127"><font size="-1">Word</span></span><br>
<span data-ttu-id="9ba2d-128">Excel</span><span class="sxs-lookup"><span data-stu-id="9ba2d-128">Excel</span></span><br>
<span data-ttu-id="9ba2d-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9ba2d-129">PowerPoint</span></span>
<td><span data-ttu-id="9ba2d-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="9ba2d-130"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="9ba2d-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="9ba2d-131"><font size="-1">Word</span></span><br>
<span data-ttu-id="9ba2d-132">Excel</span><span class="sxs-lookup"><span data-stu-id="9ba2d-132">Excel</span></span><br>
<span data-ttu-id="9ba2d-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9ba2d-133">PowerPoint</span></span>
<td><span data-ttu-id="9ba2d-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="9ba2d-134"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="9ba2d-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="9ba2d-135"><font size="-1">Word</span></span><br>
<span data-ttu-id="9ba2d-136">Excel</span><span class="sxs-lookup"><span data-stu-id="9ba2d-136">Excel</span></span><br>
<span data-ttu-id="9ba2d-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9ba2d-137">PowerPoint</span></span>
<td><span data-ttu-id="9ba2d-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-138">Outlook</span></span></tr>

<tr>
<td><span data-ttu-id="9ba2d-139"><font size="-1">手動套用、變更或移除標籤</span><span class="sxs-lookup"><span data-stu-id="9ba2d-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="9ba2d-140"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-140">Yes.</span></span><br><span data-ttu-id="9ba2d-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="9ba2d-142"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-142">Yes.</span></span><br><span data-ttu-id="9ba2d-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="9ba2d-144"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-144">Yes.</span></span><br><span data-ttu-id="9ba2d-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="9ba2d-146"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-147"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-147">Yes.</span></span><br><span data-ttu-id="9ba2d-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="9ba2d-149"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-150"><font size="-1">即將推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9ba2d-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="9ba2d-151"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="9ba2d-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">套用預設標籤</a>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="9ba2d-153"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-153">Yes.</span></span><br><span data-ttu-id="9ba2d-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="9ba2d-155"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-155">Yes.</span></span><br><span data-ttu-id="9ba2d-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="9ba2d-157"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-157">Yes.</span></span><br><span data-ttu-id="9ba2d-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="9ba2d-159"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-160"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-160">Yes.</span></span><br><span data-ttu-id="9ba2d-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="9ba2d-162"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-163"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-164"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="9ba2d-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">需要變更標籤的理由</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="9ba2d-166"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-166">Yes.</span></span><br><span data-ttu-id="9ba2d-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="9ba2d-168"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-168">Yes.</span></span><br><span data-ttu-id="9ba2d-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="9ba2d-170"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-170">Yes.</span></span><br><span data-ttu-id="9ba2d-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="9ba2d-172"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-173"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-173">Yes.</span></span><br><span data-ttu-id="9ba2d-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="9ba2d-175"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-176"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-177"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="9ba2d-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">提供自訂說明頁面的說明連結</a>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="9ba2d-179"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-179">Yes.</span></span><br><span data-ttu-id="9ba2d-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="9ba2d-181"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-181">Yes.</span></span><br><span data-ttu-id="9ba2d-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="9ba2d-183"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-183">Yes.</span></span><br><span data-ttu-id="9ba2d-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="9ba2d-185"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-186"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-186">Yes.</span></span><br><span data-ttu-id="9ba2d-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="9ba2d-188"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-189"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-190"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="9ba2d-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">標記內容</a>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="9ba2d-192"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-192">Yes.</span></span><br><span data-ttu-id="9ba2d-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="9ba2d-194"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-194">Yes.</span></span><br><span data-ttu-id="9ba2d-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="9ba2d-196"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-196">Yes.</span></span><br><span data-ttu-id="9ba2d-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="9ba2d-198"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-199"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-199">Yes.</span></span><br><span data-ttu-id="9ba2d-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="9ba2d-201"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-202"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-203"><font size="-1">即將推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9ba2d-203"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="9ba2d-204"><font size="-1">指派預先定義的權限</span><span class="sxs-lookup"><span data-stu-id="9ba2d-204"><font size="-1">Assign pre-defined permissions</span></span>
<td><span data-ttu-id="9ba2d-205"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-205">Yes.</span></span><br><span data-ttu-id="9ba2d-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="9ba2d-207"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-207">Yes.</span></span><br><span data-ttu-id="9ba2d-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="9ba2d-209"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-209">Yes.</span></span><br><span data-ttu-id="9ba2d-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="9ba2d-211"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-212"><font size="-1"><b>是</b></span><span class="sxs-lookup"><span data-stu-id="9ba2d-212">Yes.</span></span><br><span data-ttu-id="9ba2d-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="9ba2d-214"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-215"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-216"><font size="-1">即將推出<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="9ba2d-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">讓使用者指派權限</a>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-217">Let users assign permissions</span></span><td><span data-ttu-id="9ba2d-218"><font size="-1"><b>是</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9ba2d-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="9ba2d-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="9ba2d-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="9ba2d-220"><font size="-1"><b>是</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9ba2d-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="9ba2d-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="9ba2d-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="9ba2d-222"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-223"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-224"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="9ba2d-225"><font size="-1">即將推出<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="9ba2d-226"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-227"><font size="-1">即將推出<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9ba2d-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="9ba2d-228"><font size="-1">傳送<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">標籤分析</a>資料給系統管理員</span><span class="sxs-lookup"><span data-stu-id="9ba2d-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="9ba2d-229"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="9ba2d-230"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="9ba2d-231"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-232"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-233"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-234"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-235"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-236"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="9ba2d-237"><font size="-1">要求使用者在電子郵件和文件中套用標籤</span><span class="sxs-lookup"><span data-stu-id="9ba2d-237"><font size="-1">Require users to apply a label to their email and documents</span></span>
<td><span data-ttu-id="9ba2d-238"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="9ba2d-239"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="9ba2d-240"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-241"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-242"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-243"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-244"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-245"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="9ba2d-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">自動將敏感度標籤套用到內容</a>
</span><span class="sxs-lookup"><span data-stu-id="9ba2d-246">Apply a sensitivity label to content automatically</span></span><td><span data-ttu-id="9ba2d-247"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="9ba2d-248"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="9ba2d-249"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-250"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-251"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-252"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-253"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="9ba2d-254"><font size="-1">未定</span><span class="sxs-lookup"><span data-stu-id="9ba2d-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="9ba2d-255"><sup>1</sup>如設定，系統會提示使用者說明標籤降級的理由。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="9ba2d-256">但是，理由資料尚未提供給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="9ba2d-257">當支援 [傳送標籤分析資料給系統管理員] 功能時，系統就會提供此功能。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="9ba2d-258"><sup>2</sup>目前只有 Windows 版和 Mac 版 Outlook 才能讓使用者指派權限。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="9ba2d-259">Word、Excel 和 PowerPoint 的適用性未定。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="9ba2d-260"><sup>3</sup>預計是 2019 年的第四季。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="9ba2d-261">在內容加上敏感度標籤之後，何時會套用內容標記或加密功能？</span><span class="sxs-lookup"><span data-stu-id="9ba2d-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="9ba2d-262">應用程式</span><span class="sxs-lookup"><span data-stu-id="9ba2d-262">Application</span></span> | <span data-ttu-id="9ba2d-263">內容標記</span><span class="sxs-lookup"><span data-stu-id="9ba2d-263">Content marking</span></span> | <span data-ttu-id="9ba2d-264">加密</span><span class="sxs-lookup"><span data-stu-id="9ba2d-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="9ba2d-265">所有平台上的 Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9ba2d-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="9ba2d-266">立即</span><span class="sxs-lookup"><span data-stu-id="9ba2d-266">Immediately</span></span> | <span data-ttu-id="9ba2d-267">立即</span><span class="sxs-lookup"><span data-stu-id="9ba2d-267">Immediately</span></span> |
| <span data-ttu-id="9ba2d-268">電腦版和 Mac 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="9ba2d-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="9ba2d-269">在 Exchange Online 傳送電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="9ba2d-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="9ba2d-270">立即</span><span class="sxs-lookup"><span data-stu-id="9ba2d-270">Immediately</span></span> |
| <span data-ttu-id="9ba2d-271">所有平台上的 Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9ba2d-271">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="9ba2d-272">在 Exchange Online 傳送電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="9ba2d-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="9ba2d-273">在 Exchange Online 傳送電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="9ba2d-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="9ba2d-274">敏感度標籤可以和 Windows 版 Office 中的 Azure 資訊保護用戶端一起執行嗎？</span><span class="sxs-lookup"><span data-stu-id="9ba2d-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="9ba2d-275">不行。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-275">No.</span></span> <span data-ttu-id="9ba2d-276">如果在 Windows 版 Office 中載入 Azure 資訊保護用戶端，敏感度標籤即會關閉。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="9ba2d-277">如果您已安裝 Azure 資訊保護用戶端，但想要改用敏感度標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="9ba2d-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="9ba2d-278">設定 [在 Office 中使用 [敏感度] 功能以套用並檢視敏感度標籤] \*\*\*\* 的群組原則設定，這個設定可在 **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings** 下找到。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="9ba2d-279">注意：這個設定可透過傳統的群組原則部署機制來部署，或是透過 [Office 雲端原則服務][](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="9ba2d-280">或者，您可以解除安裝或 [停用] [](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) Azure 資訊保護用戶端。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="9ba2d-281">重新啟動所有 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="9ba2d-282">Office 的非訂閱版本是否支援敏感度標籤，例如 Office 2016 或 Office 2019？</span><span class="sxs-lookup"><span data-stu-id="9ba2d-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="9ba2d-283">不行。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-283">No.</span></span> <span data-ttu-id="9ba2d-284">只有 Office 365 訂閱才支援敏感度標籤，所有非訂閱版本均不支援。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="9ba2d-285">不過，可以在 Office 的非訂閱版本中使用 Azure 資訊保護的整合式標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="9ba2d-286">我在設定敏感度標籤之前已經部署好保護範本。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="9ba2d-287">它們去哪裡了？</span><span class="sxs-lookup"><span data-stu-id="9ba2d-287">Where did they go?</span></span>

<span data-ttu-id="9ba2d-288">啟用敏感度標籤後，系統管理員定義的[保護範本](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)即會隱藏，Office 使用者無法使用，因為靈敏度標籤已啟用加密功能，因此這些範本是多餘的。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="9ba2d-289">檔案或電子郵件是否可以有多個分類？</span><span class="sxs-lookup"><span data-stu-id="9ba2d-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="9ba2d-290">使用者一次只能為每個文件或電子郵件選取一個標籤，因此就只會有一個分類。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-290">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span> <span data-ttu-id="9ba2d-291">不過，如果使用者選取子標籤，即會同時套用兩個標籤；一個主要標籤和一個次要標籤。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-291">However, if users select a sublabel, this actually applies two labels at the same time; a primary label and a secondary label.</span></span> <span data-ttu-id="9ba2d-292">使用子標籤後，檔案可以有兩個分類，分別表示父/子關係，以提供另一層控制。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-292">By using sublabels, a file can have two classifications that denote a parent/child relationship for an additional level of control.</span></span> 

<span data-ttu-id="9ba2d-293">例如， **機密** 標籤可能包含 如 **法務** 和 **財務**等子標籤。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-293">For example, the label **Confidential** might contain sublabels such as **Legal** and **Finance**.</span></span> <span data-ttu-id="9ba2d-294">您可以將不同的分類視覺標記和不同的版權管理範本套用到這些子標籤。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-294">You can apply different classification visual markings and different Rights Management templates to these sublabels.</span></span> <span data-ttu-id="9ba2d-295">使用者無法自行選取 **機密** 標籤；只能選取其子標籤，如 **法務**。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-295">A user cannot select the **Confidential** label by itself; only one of its sublabels, such as **Legal**.</span></span> <span data-ttu-id="9ba2d-296">因此，他們所見的標籤為 **機密** / **法務**。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-296">As a result, the label that they see set is **Confidential** / **Legal**.</span></span> <span data-ttu-id="9ba2d-297">該檔案的中繼資料包含一個 **機密**的自訂文字屬性、一個 **法務**的自訂文字屬性，另一個包含這兩個值的自訂文字屬性 (**C機密法務**)。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-297">The metadata for that file includes one custom text property for **Confidential**, one custom text property for **Legal**, and another that contains both values (**Confidential Legal**).</span></span> 

<span data-ttu-id="9ba2d-298">當您使用子標籤時，請不要在主要標籤上設定視覺標記、保護和條件。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-298">When you use sublabels, don't configure visual markings, protection, and conditions at the primary label.</span></span> <span data-ttu-id="9ba2d-299">當您使用子層級時，請只在子標籤上設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-299">When you use sublevels, configure these setting on the sublabel only.</span></span> <span data-ttu-id="9ba2d-300">如果您在主要標籤和子標籤上設定這些設定，則會優先採用子標籤上的設定。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-300">If you configure these settings on the primary label and its sublabel, the settings at the sublabel take precedence.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="9ba2d-301">標記電子郵件後，附件也會自動獲得相同的標記嗎？</span><span class="sxs-lookup"><span data-stu-id="9ba2d-301">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="9ba2d-302">不會。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-302">No.</span></span> <span data-ttu-id="9ba2d-303">當您標記具有附件的電子郵件時，這些附件不會繼承相同的標籤。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-303">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="9ba2d-304">附件會保持為沒有標籤，或者保留個別套用的標籤。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-304">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="9ba2d-305">但是，如果電子郵件的標籤套用保護，則該保護將套用至 Office 附件。</span><span class="sxs-lookup"><span data-stu-id="9ba2d-305">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9ba2d-306">其他資源</span><span class="sxs-lookup"><span data-stu-id="9ba2d-306">Additional resources</span></span>

[<span data-ttu-id="9ba2d-307">Azure 資訊保護中分類與標籤的常見問題集</span><span class="sxs-lookup"><span data-stu-id="9ba2d-307">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="9ba2d-308">在 Office 中將敏感度標籤套用至您的文件和電子郵件</span><span class="sxs-lookup"><span data-stu-id="9ba2d-308">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)