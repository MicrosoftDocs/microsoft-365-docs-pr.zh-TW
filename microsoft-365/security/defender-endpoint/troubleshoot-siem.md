---
title: 疑難排解 Microsoft Defender ATP 中的 SIEM 工具整合問題
description: 疑難排解搭配 Microsoft Defender ATP 使用 SIEM 工具時可能發生的問題。
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
ms.openlocfilehash: 7a6bb0c455ed0406c941e9269b8b04b5cfe738be
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058680"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="3b1d9-104">疑難排解 SIEM 工具整合問題</span><span class="sxs-lookup"><span data-stu-id="3b1d9-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3b1d9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3b1d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b1d9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3b1d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3b1d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b1d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="3b1d9-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3b1d9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3b1d9-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="3b1d9-110">在您的 SIEM 工具中提取偵測時，您可能需要對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="3b1d9-111">此頁面提供疑難排解可能遇到之問題的詳細步驟。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="3b1d9-112">瞭解如何取得新的用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="3b1d9-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="3b1d9-113">如果您的用戶端密碼到期，或您已在啟用 SIEM 工具應用程式時，誤放了您所提供的副本，您將需要取得新的機密。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="3b1d9-114">登入 [Azure 管理入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="3b1d9-115">選取 **[Azure Active Directory]**。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="3b1d9-116">選取您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-116">Select your tenant.</span></span>

4. <span data-ttu-id="3b1d9-117">按一下 [ **應用程式註冊**]。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-117">Click **App registrations**.</span></span> <span data-ttu-id="3b1d9-118">然後在 [應用程式] 清單中，選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="3b1d9-119">選取機 **碼** 區段，然後提供重要描述並指定金鑰有效期限。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="3b1d9-120">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-120">Click **Save**.</span></span> <span data-ttu-id="3b1d9-121">會顯示機碼值。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-121">The key value is displayed.</span></span>

7. <span data-ttu-id="3b1d9-122">複製此值，並將其儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="3b1d9-123">取得重新整理存取權杖時的錯誤</span><span class="sxs-lookup"><span data-stu-id="3b1d9-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="3b1d9-124">如果您嘗試在使用威脅智慧 API 或 SIEM 工具時取得重新整理權杖時遇到錯誤，您必須在 Azure Active Directory 中新增相關應用程式的回復 URL。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="3b1d9-125">登入 [Azure 管理入口網站](https://ms.portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="3b1d9-126">選取 **[Azure Active Directory]**。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="3b1d9-127">選取您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-127">Select your tenant.</span></span>

4. <span data-ttu-id="3b1d9-128">按一下 [ **應用程式註冊**]。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-128">Click **App Registrations**.</span></span> <span data-ttu-id="3b1d9-129">然後在 [應用程式] 清單中，選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="3b1d9-130">新增下列 URL:</span><span class="sxs-lookup"><span data-stu-id="3b1d9-130">Add the following URL:</span></span>
   - <span data-ttu-id="3b1d9-131">歐盟的歐盟： `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="3b1d9-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="3b1d9-132">英國： `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="3b1d9-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="3b1d9-133">美國：  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` 。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="3b1d9-134">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="3b1d9-135">啟用 SIEM 連接器應用程式時發生錯誤</span><span class="sxs-lookup"><span data-stu-id="3b1d9-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="3b1d9-136">如果您嘗試啟用 SIEM 連接器應用程式時遇到錯誤，請檢查瀏覽器的快顯封鎖器設定。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="3b1d9-137">當您啟用功能時，它可能會封鎖所開啟的新視窗。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="3b1d9-138">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3b1d9-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3b1d9-139">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3b1d9-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="3b1d9-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="3b1d9-140">Related topics</span></span>
- [<span data-ttu-id="3b1d9-141">在 Microsoft Defender for Endpoint 中啟用 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="3b1d9-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="3b1d9-142">設定 ArcSight 以拉入 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="3b1d9-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="3b1d9-143">向 SIEM 工具提取偵測</span><span class="sxs-lookup"><span data-stu-id="3b1d9-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="3b1d9-144">Microsoft Defender for Endpoint 偵測欄位</span><span class="sxs-lookup"><span data-stu-id="3b1d9-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="3b1d9-145">使用 REST API 提取 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="3b1d9-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
