---
title: 設定事件中樞
description: 瞭解如何設定事件中樞
keywords: 事件 hub、configure、insights
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985545"
---
# <a name="configure-your-event-hub"></a><span data-ttu-id="9bb4b-104">設定事件中樞</span><span class="sxs-lookup"><span data-stu-id="9bb4b-104">Configure your Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9bb4b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-105">**Applies to:**</span></span>
- [<span data-ttu-id="9bb4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bb4b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="9bb4b-107">瞭解如何設定事件中樞，使其能從 Microsoft 365 Defender 中攝取事件。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-107">Learn how to configure your Event Hub so that it can ingest events from Microsoft 365 Defender.</span></span>


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a><span data-ttu-id="9bb4b-108">在事件 Hub 訂閱中設定必要的資源提供者</span><span class="sxs-lookup"><span data-stu-id="9bb4b-108">Setup the required Resource Provider in the Event Hub subscription</span></span>


1. <span data-ttu-id="9bb4b-109">登入 [Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-109">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
1. <span data-ttu-id="9bb4b-110">選取 [ **訂閱] \> {***選取事件中心將部署到的訂閱***} \> 資源提供者**。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-110">Select **Subscriptions \> {***Select the subscription the event hub will be deployed to***} \> Resource providers**.</span></span>
1. <span data-ttu-id="9bb4b-111">確認已註冊 **Microsoft Insights** 提供者。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-111">Verify that the **Microsoft.Insights** Provider is registered.</span></span> <span data-ttu-id="9bb4b-112">否則，請進行註冊。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-112">Otherwise, register it.</span></span>

![Microsoft Azure 中資源提供者的影像](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a><span data-ttu-id="9bb4b-114">安裝 Azure Active Directory 應用程式註冊</span><span class="sxs-lookup"><span data-stu-id="9bb4b-114">Setup Azure Active Directory App Registration</span></span>


><span data-ttu-id="9bb4b-115">!記必須將系統管理員角色或 Azure Active Directory (AAD) 設定為允許非管理員註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-115">![NOTE] You must have Administrator role or Azure Active Directory (AAD) must be set to allow non-Administrators to register apps.</span></span> <span data-ttu-id="9bb4b-116">您也必須具有擁有者或使用者存取系統管理員角色，才能指派服務主體角色。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-116">You must also have an Owner or User Access Administrator role to assign the service principal a role.</span></span>  
><span data-ttu-id="9bb4b-117">如需詳細資訊，請參閱[在入口網站中建立 Azure AD app & 服務主體-Microsoft 身分識別平臺 \| Microsoft](/azure/active-directory/develop/howto-create-service-principal-portal)檔。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-117">For more information, see [Create an Azure AD app & service principal in the portal - Microsoft identity platform \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span></span>

1. <span data-ttu-id="9bb4b-118">建立新的註冊 (，它原本會在 **Azure Active Directory \> 應用程式註冊 \> 新註冊** 中建立服務主體) 。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-118">Create a new registration (which inherently creates a service principal) in **Azure Active Directory \> App registrations \> New registration.**</span></span>

1. <span data-ttu-id="9bb4b-119">填寫表單只顯示名稱 (不需要重新導向 URI) 。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-119">Fill out the form with just the Name (no Redirect URI is required).</span></span>

    ![註冊應用程式的影像](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![概覽資訊的影像](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. <span data-ttu-id="9bb4b-122">按一下 [憑證]，以建立機密。 **& 機密的 \> 新用戶端密碼**：</span><span class="sxs-lookup"><span data-stu-id="9bb4b-122">Create a secret by clicking on **Certificates & secrets \> New client secret**:</span></span>

    ![憑證和機密的影像](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
><span data-ttu-id="9bb4b-124">**您將無法再次存取用戶端密碼，因此請務必加以儲存**。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-124">**You won't be able to access the client secret again so make sure to save it**.</span></span>

## <a name="setup-event-hub-namespace"></a><span data-ttu-id="9bb4b-125">安裝程式事件中心命名空間</span><span class="sxs-lookup"><span data-stu-id="9bb4b-125">Setup Event Hub namespace</span></span>


1. <span data-ttu-id="9bb4b-126">建立事件中心命名空間：</span><span class="sxs-lookup"><span data-stu-id="9bb4b-126">Create an Event Hub Namespace:</span></span>

    <span data-ttu-id="9bb4b-127">移 **至 [事件 \> 中心** ] [新增]，然後選取 [定價層]、[輸送量單位] 和 [自動增加] (需要符合您期望的負載的標準定價和功能) 。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-127">Go **to Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span></span>  
    <span data-ttu-id="9bb4b-128">如需詳細資訊，請參閱[定價-事件中樞 \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="9bb4b-128">For more information, see [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span></span>

    >[!NOTE]
    > <span data-ttu-id="9bb4b-129">您可以使用現有的事件中樞，但輸送量和縮放比例是在命名空間層級設定，因此建議您在 itsown 命名空間中放置事件中樞。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-129">You can use an existing event hub, but the throughput and scaling are set at the namespace level so it is recommended to place an event hub in itsown namespace.</span></span>

   ![事件中樞名稱空間的影像](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. <span data-ttu-id="9bb4b-131">您也需要此事件 Hub 命名空間的資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-131">You will also need the Resource ID of this Event Hub Namespace.</span></span> <span data-ttu-id="9bb4b-132">移至您的 Azure 事件中心命名空間頁面 \> 屬性。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-132">Go to your Azure Event Hubs namespace page \> Properties.</span></span> <span data-ttu-id="9bb4b-133">複製 [資源識別碼] 底下的文字，並將其記錄為在下方的 [M365 設定] 區段中使用。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-133">Copy the text under Resource ID and record it for use during the M365 Configuration section below.</span></span> 

    ![屬性圖像](../../media/759498162a4e93cbf17c4130d704d164.png)

1. <span data-ttu-id="9bb4b-135">在建立事件 Hub 命名空間之後，您將需要將應用程式註冊服務主體新增為 Reader、Azure 事件中樞資料接收器，以及將以投稿者登入 Microsoft 365 Defender 的使用者 (這也可以在資源群組或訂閱層級) 進行。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-135">Once the Event Hub Namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span>

    <span data-ttu-id="9bb4b-136">這是在 **事件中樞命名空間 \> 存取控制中執行的 \> (IAM)** 在 **角色指派** 下新增及驗證：</span><span class="sxs-lookup"><span data-stu-id="9bb4b-136">This is done in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span></span>

    ![存取控制的影像](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a><span data-ttu-id="9bb4b-138">安裝程式事件 Hub</span><span class="sxs-lookup"><span data-stu-id="9bb4b-138">Setup Event Hub</span></span>


<span data-ttu-id="9bb4b-139">**選項1：**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-139">**Option 1:**</span></span>

<span data-ttu-id="9bb4b-140">您可以在命名空間內建立事件中樞，而且 **所有** 事件種類 (您選取要匯出的表格) 會 **寫入至此事件** hub。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-140">You can create an Event Hub within your Namespace and **all** the Event Types (Tables) you select to export will be written into this **one** Event Hub.</span></span>

<span data-ttu-id="9bb4b-141">**選項2：**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-141">**Option 2:**</span></span>

<span data-ttu-id="9bb4b-142">您可以將每個資料表匯出至事件 Hub 命名空間中的不同事件集，而不是將所有的事件)  (類型匯出至事件 hub 命名空間內， (一個事件 hub 每個事件種類) 。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-142">Instead of exporting all the Event Types (Tables) into one Event Hub, you can export each table into a different Event Hub inside your Event Hub Namespace (one Event Hub per Event Type).</span></span>  

<span data-ttu-id="9bb4b-143">在此選項中，Microsoft 365 Defender 將為您建立事件中心。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-143">In this option, Microsoft 365 Defender will create Event Hubs for you.</span></span>  
>[!NOTE]
> <span data-ttu-id="9bb4b-144">如果您使用的是 **不** 屬於事件中心叢集的事件中心命名空間，則只有在您定義的每個匯出設定中，只要 Azure 限制每個事件 Hub 命名空間有10個事件中樞，您就可以選擇最多10個事件種類 (表格中) 匯出。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-144">If you are using an Event Hub Namespace that is **not** part of an Event Hub Cluster, you will only be able to choose up to 10 Event Types (Tables) to export in each Export Settings you define, due to an Azure limitation of 10 Event Hubs per Event Hub Namespace.</span></span>

<span data-ttu-id="9bb4b-145">例如：</span><span class="sxs-lookup"><span data-stu-id="9bb4b-145">For example:</span></span>

![範例事件中樞的影像](../../media/005c1f6c10c34420d387f594987f9ffe.png)

<span data-ttu-id="9bb4b-147">如果您選擇此選項，您可以略過 [[設定 Microsoft 365 Defender 以傳送電子郵件表格]](#configure-microsoft-365-defender-to-send-email-tables)區段。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-147">If you choose this option, you can skip to the [Configure Microsoft 365 Defender to send email tables](#configure-microsoft-365-defender-to-send-email-tables) section.</span></span>

<span data-ttu-id="9bb4b-148">選取 **事件中心 \> + 事件中樞**，以在命名空間中建立事件中樞。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-148">Create an Event Hub within your Namespace by selecting **Event Hubs \> + Event Hub**.</span></span>

<span data-ttu-id="9bb4b-149">分割區計數可透過平行性增加額外輸送量，因此建議您根據預期的負載增加此數目。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-149">The Partition Count allows for additional throughput via parallelism, so it is recommended to increase this number based on the load you are expecting.</span></span>  
<span data-ttu-id="9bb4b-150">建議使用預設的郵件保留及捕獲值為1和 Off。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-150">Default Message Retention and Capture values of 1 and Off are recommended.</span></span>

![建立事件中樞的影像](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

<span data-ttu-id="9bb4b-152">若為此事件中樞 (不命名空間) 您將需要使用 Send、聽取宣告來設定共用存取原則。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-152">For this Event Hub (not namespace) you will need to configure a Shared Access Policy with Send, Listen Claims.</span></span> <span data-ttu-id="9bb4b-153">按一下您的 **事件中心 \> 共用訪問原則 \>** ，然後新增並授與其原則名稱 (未用於其他地方) 並檢查 **傳送** 和 **聆聽**。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-153">Click on your **Event Hub \> Shared access policies \> + Add** and then give it a Policy name (not used elsewhere) and check **Send** and **Listen**.</span></span>

![共用存取原則的影像](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a><span data-ttu-id="9bb4b-155">設定傳送電子郵件表格的 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bb4b-155">Configure Microsoft 365 Defender to send email tables</span></span>


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a><span data-ttu-id="9bb4b-156">安裝程式 Microsoft 365 Defender 透過事件中樞將電子郵件表格傳送至 Splunk</span><span class="sxs-lookup"><span data-stu-id="9bb4b-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span></span>


1. <span data-ttu-id="9bb4b-157"><https://security.microsoft.com>使用符合下列所有角色需求的帳戶，登入 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="9bb4b-157">Login to Microsoft 365 Defender at <https://security.microsoft.com> with an account that meets all the following role requirements:</span></span>

    - <span data-ttu-id="9bb4b-158">參與者 role，位於事件中心 *命名空間* 資源層級或更高層，以供您要匯出的事件中樞。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-158">Contributor role at the Event Hub *Namespace* Resource level or higher for the Event Hub that you will be exporting to.</span></span> <span data-ttu-id="9bb4b-159">若未這麼做，當您嘗試儲存設定時，您會收到匯出錯誤。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-159">Without this you will get an export error when you try to save the settings.</span></span>

    - <span data-ttu-id="9bb4b-160">受限於 Microsoft 365 Defender 和 Azure 之租使用者的全域系統管理員或安全性系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span></span>

    ![安全性入口網站影像](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. <span data-ttu-id="9bb4b-162">按一下 [ **原始資料匯出 \> + 新增**]。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-162">Click on **Raw Data Export \> +Add**.</span></span>

    <span data-ttu-id="9bb4b-163">現在您會使用以上所記錄的資料。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-163">You will now use the data that your recorded above.</span></span>

    <span data-ttu-id="9bb4b-164">**名稱**：這是本機的，應為您環境中的任何作用。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-164">**Name**: This is local and should be whatever works in your environment.</span></span>

    <span data-ttu-id="9bb4b-165">**將事件轉寄給事件中樞**：選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-165">**Forward events to event hub**: Select this checkbox.</span></span>

    <span data-ttu-id="9bb4b-166">**事件-Hub 資源識別碼**：這是您在設定事件中樞時所記錄的事件 Hub 命名空間資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-166">**Event-Hub Resource ID**: This is the Event Hub Namespace Resource ID you  recorded above when you setup the Event Hub.</span></span>

    <span data-ttu-id="9bb4b-167">**事件-Hub name**：如果您在事件 Hub 命名空間內建立事件中樞，請貼上您所記錄的事件中心名稱。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-167">**Event-Hub name**:  If you created an Event Hub inside your Event Hub Namespace, paste the Event Hub  name you recorded above.</span></span>

    <span data-ttu-id="9bb4b-168">如果您選擇讓 Microsoft 365 Defender 針對每個事件種類建立事件中樞 (表格) 為您，請將此欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-168">If you choose to let Microsoft 365 Defender to create Event Hubs per Event Types  (Tables) for you, leave this field empty.</span></span>

    <span data-ttu-id="9bb4b-169">**事件種類**：選取您要轉寄給事件中樞的高級搜尋表格，然後再移至您的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-169">**Event Types**: Select the Advanced Hunting tables that you want to forward to the Event Hub and then on to your custom app.</span></span> <span data-ttu-id="9bb4b-170">警示表來自 Microsoft 365 Defender，裝置資料表來自 microsoft defender for Endpoint (EDR) ，而電子郵件表格來自 microsoft defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-170">Alert tables are from Microsoft 365 Defender, Devices tables are from Microsoft Defender for Endpoint (EDR), and Email tables are from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9bb4b-171">電子郵件事件會記錄所有的電子郵件交易。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-171">Email Events records all Email Transactions.</span></span> <span data-ttu-id="9bb4b-172">同時也會記錄 SafeLinks) 、附件 (Safe 附件的 URL (及傳遞事件) ，而且可以加入 NetworkMessageId 欄位上的電子郵件事件。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-172">The URL (SafeLinks), Attachment (Safe Attachments) and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.</span></span>

    ![流式處理 API 設定的影像](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. <span data-ttu-id="9bb4b-174">請務必按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-174">Make sure to click **Submit**.</span></span>

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a><span data-ttu-id="9bb4b-175">驗證事件是否要匯出至事件 Hub</span><span class="sxs-lookup"><span data-stu-id="9bb4b-175">Verify that the events are being exported to the Event Hub</span></span>


<span data-ttu-id="9bb4b-176">您可以執行基本的高級搜尋查詢，以驗證事件是否已傳送至事件 Hub。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-176">You can verify that events are being sent to the Event Hub by running a basic Advanced Hunting query.</span></span> <span data-ttu-id="9bb4b-177">選取 [ **搜尋 \> 高級搜尋 \> 查詢** ]，然後輸入下列查詢：</span><span class="sxs-lookup"><span data-stu-id="9bb4b-177">Select **Hunting \> Advanced Hunting \> Query** and enter the following query:</span></span>

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

<span data-ttu-id="9bb4b-178">這會顯示最近一小時內加入所有其他表格的電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-178">This will show you how many emails were received in the last hour joined across all the other tables.</span></span> <span data-ttu-id="9bb4b-179">如果您看到可匯出至事件中樞的事件，它也會顯示您。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-179">It will also show you if you are seeing events that could be exported to the event hub.</span></span> <span data-ttu-id="9bb4b-180">如果此計數顯示0，您將看不到事件 Hub 中的任何資料。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-180">If this count shows 0 then you won't see any data going out to the Event Hub.</span></span>

![高級搜尋的影像](../../media/c305e57dc6f72fa9eb035943f244738e.png)

<span data-ttu-id="9bb4b-182">一旦您驗證有要匯出的資料，您就可以查看事件 Hub，以確認郵件已傳入。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-182">Once you have verified there is data to export, you can view the Event Hub to verify that messages are incoming.</span></span> <span data-ttu-id="9bb4b-183">這最多可能需要一小時。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-183">This can take up to one hour.</span></span> 
 
1. <span data-ttu-id="9bb4b-184">在 Azure 中，移至 **事件中樞 \> 按一下 \> \> 事件中樞上的 [命名空間] 事件** 中心。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-184">In Azure, go to **Event Hubs \> Click on the Namespace \> Event Hubs \> Click on the Event Hub**.</span></span>  
1. <span data-ttu-id="9bb4b-185">在 **[一覽**] 底下，向下並在 [訊息] 圖表中，您應該會看到傳入的郵件。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-185">Under **Overview**, scroll down and in the Messages graph you should see Incoming Messages.</span></span> <span data-ttu-id="9bb4b-186">如果您沒有看到任何結果，則您的自訂應用程式無法接收任何郵件。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-186">If you don't see any results, then there will be no messages for your custom app to ingest.</span></span>

    ![包含郵件之 [概覽] 索引標籤的影像](../../media/e88060e315d76e74269a3fc866df047f.png)
