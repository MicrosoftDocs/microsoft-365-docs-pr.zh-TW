---
title: 在 Microsoft Defender for Endpoint 中啟用 SIEM 整合
description: Enable SIEM integration 以接收您安全性資訊和事件管理 (SIEM) 解決方案中的偵測。
keywords: 啟用 siem connector、siem、connector、security 資訊和事件
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060364"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b5038-104">在 Microsoft Defender for Endpoint 中啟用 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="b5038-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5038-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b5038-105">**Applies to:**</span></span>
- [<span data-ttu-id="b5038-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b5038-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="b5038-107">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b5038-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5038-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b5038-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="b5038-109">啟用安全性資訊和事件管理 (SIEM) 整合，讓您可以從 Microsoft Defender Security Center 提取偵測。</span><span class="sxs-lookup"><span data-stu-id="b5038-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="b5038-110">使用您的 SIEM 解決方案或直接連線至偵測到的 REST API 來提取偵測。</span><span class="sxs-lookup"><span data-stu-id="b5038-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="b5038-111">[Microsoft Defender For Endpoint Alert](alerts.md) 是由一或多個偵測所組成。</span><span class="sxs-lookup"><span data-stu-id="b5038-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="b5038-112">[Microsoft Defender For Endpoint 偵測](api-portal-mapping.md) 是由裝置上發生的可疑事件及其相關警示詳細資料所組成。</span><span class="sxs-lookup"><span data-stu-id="b5038-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="b5038-113">Microsoft Defender for Endpoint Alert API 是最新的警示消耗 API，且包含每個警示的相關證據的詳細清單。</span><span class="sxs-lookup"><span data-stu-id="b5038-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="b5038-114">如需詳細資訊，請參閱 [Alert 方法和屬性](alerts.md) 和 [清單警示](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b5038-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5038-115">必要條件</span><span class="sxs-lookup"><span data-stu-id="b5038-115">Prerequisites</span></span>

- <span data-ttu-id="b5038-116">啟用此設定的使用者必須具有在 Azure Active Directory (AAD) 中建立應用程式的許可權。</span><span class="sxs-lookup"><span data-stu-id="b5038-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="b5038-117">這是具有下列角色的人員：</span><span class="sxs-lookup"><span data-stu-id="b5038-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="b5038-118">安全性管理員和全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="b5038-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="b5038-119">雲端應用程式系統管理員</span><span class="sxs-lookup"><span data-stu-id="b5038-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="b5038-120">應用程式系統管理員</span><span class="sxs-lookup"><span data-stu-id="b5038-120">Application Administrator</span></span>
  - <span data-ttu-id="b5038-121">服務主體的擁有者</span><span class="sxs-lookup"><span data-stu-id="b5038-121">Owner of the service principal</span></span>

- <span data-ttu-id="b5038-122">在初始啟用期間，會顯示一個彈出畫面，以供輸入認證。</span><span class="sxs-lookup"><span data-stu-id="b5038-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="b5038-123">請確定您允許此網站的快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="b5038-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="b5038-124">啟用 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="b5038-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="b5038-125">在功能窗格中，選取 [**設定**  >  **SIEM**]。</span><span class="sxs-lookup"><span data-stu-id="b5038-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![SIEM 整合從設定 menu1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="b5038-127">如果您嘗試啟用 SIEM 連接器應用程式時遇到錯誤，請檢查瀏覽器的快顯封鎖器設定。</span><span class="sxs-lookup"><span data-stu-id="b5038-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="b5038-128">當您啟用功能時，它可能會封鎖所開啟的新視窗。</span><span class="sxs-lookup"><span data-stu-id="b5038-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="b5038-129">選取 [ **啟用 SIEM 整合**]。</span><span class="sxs-lookup"><span data-stu-id="b5038-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="b5038-130">這會以預先填入的值來啟動 **SIEM connector access 詳細資料** 區段，且會在您的 Azure Active Directory (azure AD) 租使用者下建立應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5038-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="b5038-131">用戶端密碼只會顯示一次。</span><span class="sxs-lookup"><span data-stu-id="b5038-131">The client secret is only displayed once.</span></span> <span data-ttu-id="b5038-132">請確定您將其複本存放在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="b5038-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![SIEM 整合從設定 menu2](images/siem_details.png)

3. <span data-ttu-id="b5038-134">選擇您在組織中使用的 SIEM 類型。</span><span class="sxs-lookup"><span data-stu-id="b5038-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b5038-135">如果您選取 [HP ArcSight]，則需要儲存下列兩個設定檔：</span><span class="sxs-lookup"><span data-stu-id="b5038-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="b5038-136">WDATP-connector.jsonparser 屬性</span><span class="sxs-lookup"><span data-stu-id="b5038-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="b5038-137">WDATP-連接器。屬性</span><span class="sxs-lookup"><span data-stu-id="b5038-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="b5038-138">若要透過程式設計存取直接連線至偵測到的 REST API，請選擇 [ **一般 API**]。</span><span class="sxs-lookup"><span data-stu-id="b5038-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="b5038-139">複製個別值，或選取 [ **將詳細資料儲存至** 檔案] 以下載包含所有值的檔案。</span><span class="sxs-lookup"><span data-stu-id="b5038-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="b5038-140">選取 [ **產生權杖** ]，以取得存取和重新整理權杖。</span><span class="sxs-lookup"><span data-stu-id="b5038-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="b5038-141">您需要每90天產生一個新的重新整理權杖。</span><span class="sxs-lookup"><span data-stu-id="b5038-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="b5038-142">依照指示，為 [Microsoft Defender For Endpoint 建立 AZURE AD 應用程式註冊](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) ，並指派正確的許可權給它，以閱讀提醒。</span><span class="sxs-lookup"><span data-stu-id="b5038-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="b5038-143">您現在可以繼續設定 SIEM 解決方案，或透過程式設計存取來連線到偵測的 REST API。</span><span class="sxs-lookup"><span data-stu-id="b5038-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="b5038-144">設定 SIEM 解決方案以允許其從 Microsoft Defender Security Center 接收偵測時，您需要使用權杖。</span><span class="sxs-lookup"><span data-stu-id="b5038-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="b5038-145">整合 Microsoft Defender for Endpoint with IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="b5038-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="b5038-146">您可以設定 IBM QRadar 從 Microsoft Defender for Endpoint 收集偵測。</span><span class="sxs-lookup"><span data-stu-id="b5038-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b5038-147">如需詳細資訊，請參閱 [IBM 知識中心](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。</span><span class="sxs-lookup"><span data-stu-id="b5038-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5038-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b5038-148">See also</span></span>
- [<span data-ttu-id="b5038-149">設定 HP ArcSight 以拉入 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="b5038-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="b5038-150">Microsoft Defender for Endpoint 偵測欄位</span><span class="sxs-lookup"><span data-stu-id="b5038-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="b5038-151">使用 REST API 提取 Microsoft Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="b5038-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="b5038-152">疑難排解 SIEM 工具整合問題</span><span class="sxs-lookup"><span data-stu-id="b5038-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
