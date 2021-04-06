---
title: 設定自動化調查和修正功能
description: 在 Microsoft Defender for Endpoint 中設定您的自動化調查和修正功能。
keywords: 設定、設定、自動化、調查、偵測、提醒、修復、回應
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 31a1c79440a8c1edc2bc8e2f2a163ded2a92fd64
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165762"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a901d-104">在 Microsoft Defender for Endpoint 中設定自動調查和修正功能</span><span class="sxs-lookup"><span data-stu-id="a901d-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a901d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a901d-105">**Applies to:**</span></span>
- [<span data-ttu-id="a901d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a901d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a901d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a901d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a901d-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a901d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a901d-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a901d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="a901d-110">如果您的組織使用 [Microsoft defender for](https://docs.microsoft.com/windows/security/threat-protection/) Endpoint (Defender for endpoint) ， [自動化調查和修復功能](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) 可儲存您的安全性作業小組時間和精力。</span><span class="sxs-lookup"><span data-stu-id="a901d-110">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="a901d-111">如 [這篇博客文章](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)所述，這些功能會模仿安全性分析員調查和修正威脅的理想步驟。</span><span class="sxs-lookup"><span data-stu-id="a901d-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="a901d-112">[深入瞭解自動化調查和修復](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="a901d-112">[Learn more about automated investigation and remediation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="a901d-113">若要設定自動調查和修正，請</span><span class="sxs-lookup"><span data-stu-id="a901d-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="a901d-114">[開啟功能](#turn-on-automated-investigation-and-remediation);和</span><span class="sxs-lookup"><span data-stu-id="a901d-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="a901d-115">[設定裝置群組](#set-up-device-groups)。</span><span class="sxs-lookup"><span data-stu-id="a901d-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="a901d-116">開啟自動調查和修正</span><span class="sxs-lookup"><span data-stu-id="a901d-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="a901d-117">以全域管理員或安全性管理員的身分，移至 Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="a901d-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="a901d-118">在功能窗格中，選擇 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="a901d-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="a901d-119">在 [ **一般** ] 區段中，選取 [ **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="a901d-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="a901d-120">開啟 **自動調查** 並 **自動解決提醒**。</span><span class="sxs-lookup"><span data-stu-id="a901d-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="a901d-121">設定裝置群組</span><span class="sxs-lookup"><span data-stu-id="a901d-121">Set up device groups</span></span>

1. <span data-ttu-id="a901d-122">在 [Microsoft Defender Security Center (] [https://securitycenter.windows.com](https://securitycenter.windows.com)) 的 [ **設定** ] 頁面上，選取 [ **許可權**] 底下的 [ **裝置群組**]。</span><span class="sxs-lookup"><span data-stu-id="a901d-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="a901d-123">選取 [ **+ 新增裝置群組**]。</span><span class="sxs-lookup"><span data-stu-id="a901d-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="a901d-124">建立至少一個裝置群組，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a901d-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="a901d-125">指定裝置群組的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="a901d-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="a901d-126">在 [ **自動化層級] 清單** 中，自動選取一個層級（如 **完整–修正威脅**）。</span><span class="sxs-lookup"><span data-stu-id="a901d-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="a901d-127">「自動化」層級決定是否會自動採取或只在核准時採取修復動作。</span><span class="sxs-lookup"><span data-stu-id="a901d-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="a901d-128">若要深入瞭解，請參閱自動化 [調查和修正中的自動化層級](automation-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="a901d-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="a901d-129">在 [ **成員** ] 區段中，使用一或多個條件來識別及納入裝置。</span><span class="sxs-lookup"><span data-stu-id="a901d-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="a901d-130">在 [ **使用者存取** ] 索引標籤上，選取應該存取您所建立之裝置群組的 [Azure Active Directory 群組](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) 。</span><span class="sxs-lookup"><span data-stu-id="a901d-130">On the **User access** tab, select the [Azure Active Directory groups](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="a901d-131">當您完成設定裝置群組時，請選取 [ **完成** ]。</span><span class="sxs-lookup"><span data-stu-id="a901d-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a901d-132">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a901d-132">Next steps</span></span>

- [<span data-ttu-id="a901d-133">流覽行動中心以查看擱置和完成的修復動作</span><span class="sxs-lookup"><span data-stu-id="a901d-133">Visit the Action Center to view pending and completed remediation actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="a901d-134">審閱及核准擱置的動作</span><span class="sxs-lookup"><span data-stu-id="a901d-134">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="a901d-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a901d-135">See also</span></span>

- [<span data-ttu-id="a901d-136">在 Microsoft Defender for Endpoint 中處理誤報/負片</span><span class="sxs-lookup"><span data-stu-id="a901d-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)