---
title: 疑難排解 Microsoft Defender for Endpoint 中的 SIEM 工具整合問題
description: 疑難排解搭配 Microsoft Defender for Endpoint 使用 SIEM 工具時可能發生的問題。
keywords: 疑難排解、siem、用戶端密碼、機密
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 9c4f3da57796903fc22314574f389bcdd92ca4b3
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311985"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="625b1-104">為 SIEM 工具整合問題疑難排解</span><span class="sxs-lookup"><span data-stu-id="625b1-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="625b1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="625b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="625b1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="625b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="625b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="625b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="625b1-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="625b1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="625b1-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="625b1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="625b1-110">在您的 SIEM 工具中提取偵測時，您可能需要對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="625b1-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="625b1-111">此頁面提供疑難排解可能遇到之問題的詳細步驟。</span><span class="sxs-lookup"><span data-stu-id="625b1-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="625b1-112">瞭解如何取得新的用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="625b1-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="625b1-113">如果您的用戶端密碼到期，或您已在啟用 SIEM 工具應用程式時，誤放了您所提供的副本，您將需要取得新的機密。</span><span class="sxs-lookup"><span data-stu-id="625b1-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="625b1-114">登入 [Azure 管理入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="625b1-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="625b1-115">選取 **[Azure Active Directory]**。</span><span class="sxs-lookup"><span data-stu-id="625b1-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="625b1-116">選取您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="625b1-116">Select your tenant.</span></span>

4. <span data-ttu-id="625b1-117">按一下 [ **應用程式註冊**]。</span><span class="sxs-lookup"><span data-stu-id="625b1-117">Click **App registrations**.</span></span> <span data-ttu-id="625b1-118">然後在 [應用程式] 清單中，選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="625b1-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="625b1-119">選取 [ **憑證 & 機密** ] 區段，按一下 [新用戶端密碼]，然後提供描述並指定有效期限。</span><span class="sxs-lookup"><span data-stu-id="625b1-119">Select **Certificates & Secrets** section, Click on New Client Secret, then provide a description and specify the validity duration.</span></span>

6. <span data-ttu-id="625b1-120">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="625b1-120">Click **Save**.</span></span> <span data-ttu-id="625b1-121">會顯示機碼值。</span><span class="sxs-lookup"><span data-stu-id="625b1-121">The key value is displayed.</span></span>

7. <span data-ttu-id="625b1-122">複製此值，並將其儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="625b1-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="625b1-123">取得重新整理存取權杖時的錯誤</span><span class="sxs-lookup"><span data-stu-id="625b1-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="625b1-124">如果您嘗試在使用威脅智慧 API 或 SIEM 工具時取得重新整理權杖時遇到錯誤，您必須在 Azure Active Directory 中新增相關應用程式的回復 URL。</span><span class="sxs-lookup"><span data-stu-id="625b1-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="625b1-125">登入 [Azure 管理入口網站](https://ms.portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="625b1-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="625b1-126">選取 **[Azure Active Directory]**。</span><span class="sxs-lookup"><span data-stu-id="625b1-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="625b1-127">選取您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="625b1-127">Select your tenant.</span></span>

4. <span data-ttu-id="625b1-128">按一下 [ **應用程式註冊**]。</span><span class="sxs-lookup"><span data-stu-id="625b1-128">Click **App Registrations**.</span></span> <span data-ttu-id="625b1-129">然後在 [應用程式] 清單中，選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="625b1-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="625b1-130">新增下列 URL:</span><span class="sxs-lookup"><span data-stu-id="625b1-130">Add the following URL:</span></span>
   - <span data-ttu-id="625b1-131">歐盟的歐盟： `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="625b1-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="625b1-132">英國： `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="625b1-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="625b1-133">美國：  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` 。</span><span class="sxs-lookup"><span data-stu-id="625b1-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="625b1-134">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="625b1-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="625b1-135">啟用 SIEM 連接器應用程式時發生錯誤</span><span class="sxs-lookup"><span data-stu-id="625b1-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="625b1-136">如果您嘗試啟用 SIEM 連接器應用程式時遇到錯誤，請檢查瀏覽器的快顯封鎖器設定。</span><span class="sxs-lookup"><span data-stu-id="625b1-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="625b1-137">當您啟用功能時，它可能會封鎖所開啟的新視窗。</span><span class="sxs-lookup"><span data-stu-id="625b1-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="625b1-138">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="625b1-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="625b1-139">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="625b1-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="625b1-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="625b1-140">Related topics</span></span>
- [<span data-ttu-id="625b1-141">在 Microsoft Defender for Endpoint 中啟用 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="625b1-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="625b1-142">設定 ArcSight 以拉入 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="625b1-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="625b1-143">向 SIEM 工具提取偵測</span><span class="sxs-lookup"><span data-stu-id="625b1-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="625b1-144">Microsoft Defender for Endpoint 偵測欄位</span><span class="sxs-lookup"><span data-stu-id="625b1-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="625b1-145">使用 REST API 提取 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="625b1-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
