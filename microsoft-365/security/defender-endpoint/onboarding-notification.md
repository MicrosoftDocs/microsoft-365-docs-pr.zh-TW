---
title: 建立上架或脫離通知規則
description: 使用本機上架或脫離腳本時取得通知。
keywords: 上架，脫離，local，script，notification，rule
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
ms.openlocfilehash: 5dfdfc6d14add33154ed4c2370bca458e752125d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187119"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a><span data-ttu-id="81584-104">使用本機上架或脫離腳本時建立通知規則</span><span class="sxs-lookup"><span data-stu-id="81584-104">Create a notification rule when a local onboarding or offboarding script is used</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="81584-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="81584-105">**Applies to:**</span></span>
- [<span data-ttu-id="81584-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="81584-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="81584-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81584-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="81584-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="81584-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="81584-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="81584-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="81584-110">建立通知規則，以便在使用本機上架或脫離腳本時，系統會通知您。</span><span class="sxs-lookup"><span data-stu-id="81584-110">Create a notification rule so that when a local onboarding or offboarding script is used, you'll be notified.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="81584-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="81584-111">Before you begin</span></span>
<span data-ttu-id="81584-112">您必須具有下列許可權：</span><span class="sxs-lookup"><span data-stu-id="81584-112">You'll need to have access to:</span></span>
 - <span data-ttu-id="81584-113">最小) 的 Microsoft 流程 (流程方案1。</span><span class="sxs-lookup"><span data-stu-id="81584-113">Microsoft Flow (Flow Plan 1 at a minimum).</span></span> <span data-ttu-id="81584-114">如需詳細資訊，請參閱 [流程定價頁面](https://flow.microsoft.com/pricing/)。</span><span class="sxs-lookup"><span data-stu-id="81584-114">For more information, see [Flow pricing page](https://flow.microsoft.com/pricing/).</span></span>
 - <span data-ttu-id="81584-115">Azure 資料表或 SharePoint 清單或文件庫/SQL DB</span><span class="sxs-lookup"><span data-stu-id="81584-115">Azure Table or SharePoint List or Library / SQL DB</span></span>

## <a name="create-the-notification-flow"></a><span data-ttu-id="81584-116">建立通知流程</span><span class="sxs-lookup"><span data-stu-id="81584-116">Create the notification flow</span></span>

1. <span data-ttu-id="81584-117">在 [flow.microsoft.com](https://flow.microsoft.com/)中。</span><span class="sxs-lookup"><span data-stu-id="81584-117">In [flow.microsoft.com](https://flow.microsoft.com/).</span></span>

2. <span data-ttu-id="81584-118">流覽至 [ **我的流程 > 新的 > 排程-從空白**。</span><span class="sxs-lookup"><span data-stu-id="81584-118">Navigate to **My flows > New > Scheduled - from blank**.</span></span> 

    ![流量影像](images/new-flow.png)


3. <span data-ttu-id="81584-120">建立排程流程。</span><span class="sxs-lookup"><span data-stu-id="81584-120">Build a scheduled flow.</span></span>
   1. <span data-ttu-id="81584-121">輸入流程名稱。</span><span class="sxs-lookup"><span data-stu-id="81584-121">Enter a flow name.</span></span>
   2. <span data-ttu-id="81584-122">指定開始和時間。</span><span class="sxs-lookup"><span data-stu-id="81584-122">Specify the start and time.</span></span>
   3. <span data-ttu-id="81584-123">指定頻率。</span><span class="sxs-lookup"><span data-stu-id="81584-123">Specify the frequency.</span></span> <span data-ttu-id="81584-124">例如，每5分鐘。</span><span class="sxs-lookup"><span data-stu-id="81584-124">For example, every 5 minutes.</span></span>

    ![通知流程的影像](images/build-flow.png)

4. <span data-ttu-id="81584-126">選取 [+] 按鈕，以新增動作。</span><span class="sxs-lookup"><span data-stu-id="81584-126">Select the + button to add a new action.</span></span> <span data-ttu-id="81584-127">新的動作將是對 Defender security center 裝置 (s) API 的 HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="81584-127">The new action will be an HTTP request to the Defender for Endpoint security center device(s) API.</span></span> <span data-ttu-id="81584-128">您也可以將其取代為現成的「WDATP Connector」， (動作：「機器-取得機器的清單」 ) 。</span><span class="sxs-lookup"><span data-stu-id="81584-128">You can also replace it with the out-of-the-box "WDATP Connector" (action: "Machines - Get list of machines").</span></span> 

    ![迴圈映射及新增動作](images/recurrence-add.png)


5. <span data-ttu-id="81584-130">輸入下列 HTTP 欄位：</span><span class="sxs-lookup"><span data-stu-id="81584-130">Enter the following HTTP fields:</span></span>

   - <span data-ttu-id="81584-131">方法： "GET" 為取得裝置清單的值。</span><span class="sxs-lookup"><span data-stu-id="81584-131">Method: "GET" as a value to get the list of devices.</span></span>
   - <span data-ttu-id="81584-132">URI： Enter `https://api.securitycenter.microsoft.com/api/machines` 。</span><span class="sxs-lookup"><span data-stu-id="81584-132">URI: Enter `https://api.securitycenter.microsoft.com/api/machines`.</span></span>
   - <span data-ttu-id="81584-133">驗證：選取 [Active Directory OAuth]。</span><span class="sxs-lookup"><span data-stu-id="81584-133">Authentication: Select "Active Directory OAuth".</span></span>
   - <span data-ttu-id="81584-134">租使用者：登入 https://portal.azure.com 並流覽至 **Azure Active Directory > 應用程式註冊** ，並取得租使用者識別碼值。</span><span class="sxs-lookup"><span data-stu-id="81584-134">Tenant: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>
   - <span data-ttu-id="81584-135">觀眾： `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span><span class="sxs-lookup"><span data-stu-id="81584-135">Audience: `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span></span>
   - <span data-ttu-id="81584-136">用戶端 ID: 登入 https://portal.azure.com 及流覽 **Azure Active Directory > 應用程式註冊** 並取得用戶端識別碼值。</span><span class="sxs-lookup"><span data-stu-id="81584-136">Client ID: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and  get the Client ID value.</span></span>
   - <span data-ttu-id="81584-137">憑證類型：選取「機密」。</span><span class="sxs-lookup"><span data-stu-id="81584-137">Credential Type: Select "Secret".</span></span>
   - <span data-ttu-id="81584-138">機密：登入 https://portal.azure.com 並流覽至 **Azure Active Directory > 應用程式註冊** ，並取得租使用者識別碼值。</span><span class="sxs-lookup"><span data-stu-id="81584-138">Secret: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>

    ![HTTP 條件的影像](images/http-conditions.png)


6. <span data-ttu-id="81584-140">選取 [新增 **動作** **]，然後** 選取 [ **分析 JSON**]，以新增步驟。</span><span class="sxs-lookup"><span data-stu-id="81584-140">Add a new step by selecting **Add new action** then search for **Data Operations** and select **Parse JSON**.</span></span>

    ![資料作業的影像](images/data-operations.png)

7. <span data-ttu-id="81584-142">在 **內容** 欄位中新增正文。</span><span class="sxs-lookup"><span data-stu-id="81584-142">Add Body in the **Content** field.</span></span>

    ![分析 JSON 的影像](images/parse-json.png)

8. <span data-ttu-id="81584-144">選取 [ **使用範例負載以產生架構** 連結]。</span><span class="sxs-lookup"><span data-stu-id="81584-144">Select the **Use sample payload to generate schema** link.</span></span>

    ![具有有效負載的分析 json 影像](images/parse-json-schema.png)

9. <span data-ttu-id="81584-146">複製並貼上下列的 JSON 程式碼片段：</span><span class="sxs-lookup"><span data-stu-id="81584-146">Copy and paste the following JSON snippet:</span></span>

    ```
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10.  <span data-ttu-id="81584-147">從 JSON 呼叫中解壓縮值，並檢查架裝置 (s) 是否已于 SharePoint 清單註冊（如範例）：</span><span class="sxs-lookup"><span data-stu-id="81584-147">Extract the values from the JSON call and check if the onboarded device(s) is / are already registered at the SharePoint list as an example:</span></span>
- <span data-ttu-id="81584-148">如果是，將不會觸發任何通知</span><span class="sxs-lookup"><span data-stu-id="81584-148">If yes, no notification will be triggered</span></span>
- <span data-ttu-id="81584-149">若否，將會在 [SharePoint] 清單中註冊新的架裝置 (s) ，並將通知傳送至端點系統管理員的 Defender。</span><span class="sxs-lookup"><span data-stu-id="81584-149">If no, will register the new onboarded device(s) in the SharePoint list and a notification will be sent to the Defender for Endpoint admin</span></span>

    ![適用于每個的影像](images/flow-apply.png)

    ![適用于每個專案的映射](images/apply-to-each.png)

11. <span data-ttu-id="81584-152">在 [ **條件**] 底下，新增下列運算式： "length (body ( ' Get_items ' ) ？[' value '] ) "，並將 condition 設定為等於0。</span><span class="sxs-lookup"><span data-stu-id="81584-152">Under **Condition**, add the following expression: "length(body('Get_items')?['value'])" and set the condition to equal to 0.</span></span>

    <span data-ttu-id="81584-153">![適用于每個條件的映射](images/apply-to-each-value.png)</span><span class="sxs-lookup"><span data-stu-id="81584-153">![Image of apply to each condition](images/apply-to-each-value.png)</span></span>  
    <span data-ttu-id="81584-154">![Condition2 之 condition1 影像的影像 ](images/conditions-2.png) 
     ![](images/condition3.png)</span><span class="sxs-lookup"><span data-stu-id="81584-154">![Image of condition1](images/conditions-2.png) 
    ![Image of condition2](images/condition3.png)</span></span>  
<span data-ttu-id="81584-155">![傳送電子郵件的影像](images/send-email.png)</span><span class="sxs-lookup"><span data-stu-id="81584-155">![Image of send email](images/send-email.png)</span></span>

## <a name="alert-notification"></a><span data-ttu-id="81584-156">警示通知</span><span class="sxs-lookup"><span data-stu-id="81584-156">Alert notification</span></span>
<span data-ttu-id="81584-157">下圖是電子郵件通知的範例。</span><span class="sxs-lookup"><span data-stu-id="81584-157">The following image is an example of an email notification.</span></span>

![電子郵件通知的影像](images/alert-notification.png)


## <a name="tips"></a><span data-ttu-id="81584-159">秘訣</span><span class="sxs-lookup"><span data-stu-id="81584-159">Tips</span></span>

- <span data-ttu-id="81584-160">您可以使用 lastSeen 篩選：</span><span class="sxs-lookup"><span data-stu-id="81584-160">You can filter here using lastSeen only:</span></span>
    - <span data-ttu-id="81584-161">每60分鐘：</span><span class="sxs-lookup"><span data-stu-id="81584-161">Every 60 min:</span></span>
      - <span data-ttu-id="81584-162">過去7天內，所有的裝置都會看到過去的時間。</span><span class="sxs-lookup"><span data-stu-id="81584-162">Take all devices last seen in the past 7 days.</span></span> 

- <span data-ttu-id="81584-163">針對每個裝置：</span><span class="sxs-lookup"><span data-stu-id="81584-163">For each device:</span></span> 
    - <span data-ttu-id="81584-164">如果最後一次看到的屬性是在 [-7 days，-7days + 60 分鐘] 的一小時間隔內，則會產生脫離可能的 > 警示。</span><span class="sxs-lookup"><span data-stu-id="81584-164">If last seen property is on the one hour interval of [-7 days, -7days + 60 minutes ] -> Alert for offboarding possibility.</span></span>
    - <span data-ttu-id="81584-165">如果第一次看到的是上一個小時-> 上架警示。</span><span class="sxs-lookup"><span data-stu-id="81584-165">If first seen is on the past hour -> Alert for onboarding.</span></span>

<span data-ttu-id="81584-166">在此方案中，您將沒有重複的警示：有許多租使用者裝置。</span><span class="sxs-lookup"><span data-stu-id="81584-166">In this solution you will not have duplicate alerts: There are tenants that have numerous devices.</span></span> <span data-ttu-id="81584-167">取得所有這些裝置可能會非常昂貴，而且可能需要分頁。</span><span class="sxs-lookup"><span data-stu-id="81584-167">Getting all those devices might be very expensive and might require paging.</span></span>

<span data-ttu-id="81584-168">您可以將其分割為兩個查詢：</span><span class="sxs-lookup"><span data-stu-id="81584-168">You can split it to two queries:</span></span> 
1.  <span data-ttu-id="81584-169">若為脫離，只會使用 OData $filter 來取得此間隔，而且只會在符合條件時發出通知。</span><span class="sxs-lookup"><span data-stu-id="81584-169">For offboarding take only this interval using the OData $filter and only notify if the conditions are met.</span></span>
2.  <span data-ttu-id="81584-170">在過去一個小時內，所有的裝置都會看到最後一次看到的屬性 (如果第一個看到的屬性在過去一小時內，則最後一個看到的屬性必須在) 中。</span><span class="sxs-lookup"><span data-stu-id="81584-170">Take all devices last seen in the past hour and check first seen property for them (if the first seen property is on the past hour, the last seen must be there too).</span></span> 

