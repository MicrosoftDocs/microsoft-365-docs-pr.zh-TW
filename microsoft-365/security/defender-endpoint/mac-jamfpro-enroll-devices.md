---
title: 在 macOS 裝置上，將 Microsoft Defender 用於端點註冊到 Jamf Pro
description: 在 macOS 裝置上，將 Microsoft Defender 用於端點註冊到 Jamf Pro
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，安裝，部署，卸載，intune，jamfpro，macos，catalina，mojave，高塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0fa0db3ba85ff003d91b43d06c709ab66c37ce02
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933094"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a><span data-ttu-id="34023-104">在 macOS 裝置上，將 Microsoft Defender 用於端點註冊到 Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="34023-104">Enroll Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="34023-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="34023-105">**Applies to:**</span></span>
- [<span data-ttu-id="34023-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="34023-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="34023-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34023-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="34023-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="34023-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="34023-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="34023-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="34023-110">註冊 macOS 裝置</span><span class="sxs-lookup"><span data-stu-id="34023-110">Enroll macOS devices</span></span>

<span data-ttu-id="34023-111">有多種方法可以取得 JamF 的登記。</span><span class="sxs-lookup"><span data-stu-id="34023-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="34023-112">本文將引導您進行兩種方法：</span><span class="sxs-lookup"><span data-stu-id="34023-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="34023-113">方法1：註冊邀請</span><span class="sxs-lookup"><span data-stu-id="34023-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="34023-114">方法2：預備登記</span><span class="sxs-lookup"><span data-stu-id="34023-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="34023-115">如需完整清單，請參閱 [關於電腦註冊](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)。</span><span class="sxs-lookup"><span data-stu-id="34023-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="34023-116">註冊方法1：註冊邀請</span><span class="sxs-lookup"><span data-stu-id="34023-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="34023-117">在 Jamf Pro 儀表板中，流覽至 [**註冊邀請**]。</span><span class="sxs-lookup"><span data-stu-id="34023-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![設定 settings1 的影像](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="34023-119">選取 [ **+ 新增**]。</span><span class="sxs-lookup"><span data-stu-id="34023-119">Select **+ New**.</span></span>

    ![自動產生的標誌說明的特寫](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="34023-121">在 **[指定邀請** 的收件者] 底下 > 在 [ **電子郵件地址** ] 中，輸入收件者 (es) 的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="34023-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![設定 settings2 的影像](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![設定 settings3 的影像](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="34023-124">例如： janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="34023-124">For example: janedoe@contoso.com</span></span>

    ![設定 settings4 的影像](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="34023-126">設定邀請的訊息。</span><span class="sxs-lookup"><span data-stu-id="34023-126">Configure the message for the invitation.</span></span>

    ![設定 settings5 的影像](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![設定 settings6 的影像](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![設定 settings7 的影像](images/3ced5383a6be788486d89d407d042f28.png)

    ![設定 settings8 的影像](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="34023-131">註冊方法2：預備登記</span><span class="sxs-lookup"><span data-stu-id="34023-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="34023-132">在 Jamf Pro 儀表板中，流覽至 [預先 **安排註冊**]。</span><span class="sxs-lookup"><span data-stu-id="34023-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![設定 settings9 的影像](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="34023-134">依照電腦預先加以 [登記](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="34023-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="34023-135">註冊 macOS 裝置</span><span class="sxs-lookup"><span data-stu-id="34023-135">Enroll macOS device</span></span>

1. <span data-ttu-id="34023-136">選取 [ **繼續** ]，然後從 [ **系統偏好** 設定] 視窗中安裝 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="34023-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Jamf Pro enrollment1 的影像](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="34023-138">安裝 CA 憑證之後，請回到瀏覽器視窗，然後選取 [ **繼續** ] 並安裝 MDM 設定檔。</span><span class="sxs-lookup"><span data-stu-id="34023-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Jamf Pro enrollment2 的影像](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="34023-140">選取 [ **允許** 從 JAMF 下載]。</span><span class="sxs-lookup"><span data-stu-id="34023-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Jamf Pro enrollment3 的影像](images/jamfpro-download.png)

4. <span data-ttu-id="34023-142">選取 [ **繼續** ]，繼續執行 MDM 設定檔安裝。</span><span class="sxs-lookup"><span data-stu-id="34023-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Jamf Pro enrollment4 的影像](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="34023-144">選取 [ **繼續** ] 安裝 MDM 設定檔。</span><span class="sxs-lookup"><span data-stu-id="34023-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Jamf Pro enrollment5 的影像](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="34023-146">選取 [ **繼續**  ] 以完成設定。</span><span class="sxs-lookup"><span data-stu-id="34023-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Jamf Pro enrollment6 的影像](images/jamfpro-mdm-profile.png)
