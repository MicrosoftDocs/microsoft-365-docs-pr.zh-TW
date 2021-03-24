---
title: 建立檔案的指示器
ms.reviewer: ''
description: 為定義實體的偵測、預防和排除的檔案雜湊，建立指示器。
keywords: file，hash，manage，允許，封鎖，封鎖，clean，惡意，檔案雜湊，ip 位址，url，網域
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
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060119"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="b559f-104">建立檔案的指示器</span><span class="sxs-lookup"><span data-stu-id="b559f-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b559f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b559f-105">**Applies to:**</span></span>
- [<span data-ttu-id="b559f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b559f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b559f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b559f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="b559f-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b559f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b559f-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b559f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="b559f-110">您可以 banning 潛在的惡意檔案或可疑惡意程式碼，以避免進一步傳播您組織中的攻擊。</span><span class="sxs-lookup"><span data-stu-id="b559f-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="b559f-111">如果您知道可能是惡意遷移的可執行檔 (PE) file，您可以將它封鎖。</span><span class="sxs-lookup"><span data-stu-id="b559f-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="b559f-112">此作業可防止在組織中的機器上讀取、寫入或執行此作業。</span><span class="sxs-lookup"><span data-stu-id="b559f-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="b559f-113">您可以透過兩種方式來建立檔案的指示器：</span><span class="sxs-lookup"><span data-stu-id="b559f-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="b559f-114">透過 [設定] 頁面建立指示器</span><span class="sxs-lookup"><span data-stu-id="b559f-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="b559f-115">使用 [檔案詳細資料] 頁面中的 [新增指示器] 按鈕建立上下文指示器</span><span class="sxs-lookup"><span data-stu-id="b559f-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="b559f-116">開始之前</span><span class="sxs-lookup"><span data-stu-id="b559f-116">Before you begin</span></span>
<span data-ttu-id="b559f-117">在建立檔案的指示器之前，請務必先瞭解下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="b559f-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="b559f-118">如果您的組織使用 Windows Defender 防病毒和雲端式保護，則可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b559f-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="b559f-119">如需詳細資訊，請參閱 [在 Microsoft Defender 防毒軟體中使用下一代技術（透過雲端提供的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)）。</span><span class="sxs-lookup"><span data-stu-id="b559f-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="b559f-120">反惡意軟體用戶端版本必須是4.18.1901 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b559f-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="b559f-121">在 Windows 10 版本1703或更新版本、Windows server 2016 及2019上的電腦上支援。</span><span class="sxs-lookup"><span data-stu-id="b559f-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="b559f-122">若要開始封鎖檔案，您必須先在 [設定] 中 [關閉 [ **封鎖] 或 [允許** ] 功能](advanced-features.md) 。</span><span class="sxs-lookup"><span data-stu-id="b559f-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="b559f-123">這項功能的設計是為了防止可疑的惡意程式碼 (或可能的惡意檔案) 從網頁下載。</span><span class="sxs-lookup"><span data-stu-id="b559f-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="b559f-124">它目前支援可遷移的可執行檔 (PE) 檔案（包括 _.exe_ 和 _.dll_ 檔案）。</span><span class="sxs-lookup"><span data-stu-id="b559f-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="b559f-125">覆蓋範圍會隨著時間擴充。</span><span class="sxs-lookup"><span data-stu-id="b559f-125">The coverage will be extended over time.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="b559f-126">如果檔案的分類存在於 allow 或封鎖動作之前的設備快取上，則無法在檔案上執行 allow 或 block 功能</span><span class="sxs-lookup"><span data-stu-id="b559f-126">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
>- <span data-ttu-id="b559f-127">受信任的簽署檔會以不同方式處理。</span><span class="sxs-lookup"><span data-stu-id="b559f-127">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="b559f-128">已優化用於處理惡意檔的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="b559f-128">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="b559f-129">嘗試封鎖信任的簽署檔案，在某些情況下，可能會有效能的含義。</span><span class="sxs-lookup"><span data-stu-id="b559f-129">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>

 
>[!NOTE]
><span data-ttu-id="b559f-130">通常會在幾分鐘內強制執行檔封鎖，但可長達30分鐘。</span><span class="sxs-lookup"><span data-stu-id="b559f-130">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="b559f-131">從 [設定] 頁面建立檔案的指標</span><span class="sxs-lookup"><span data-stu-id="b559f-131">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="b559f-132">在功能窗格中，選取 [**設定**  >  **指示器**]。</span><span class="sxs-lookup"><span data-stu-id="b559f-132">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="b559f-133">選取 [檔案 **雜湊** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b559f-133">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="b559f-134">選取 [ **新增指示器**]。</span><span class="sxs-lookup"><span data-stu-id="b559f-134">Select **Add indicator**.</span></span>

4. <span data-ttu-id="b559f-135">指定下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="b559f-135">Specify the following details:</span></span>
   - <span data-ttu-id="b559f-136">標記-指定實體詳細資料並定義指示器的到期期限。</span><span class="sxs-lookup"><span data-stu-id="b559f-136">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="b559f-137">Action-指定要採取的動作並提供描述。</span><span class="sxs-lookup"><span data-stu-id="b559f-137">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="b559f-138">Scope-定義機器群組的範圍。</span><span class="sxs-lookup"><span data-stu-id="b559f-138">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="b559f-139">在 [摘要] 索引標籤中查看詳細資料，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b559f-139">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="b559f-140">從 [檔案詳細資料] 頁面建立上下文指示器</span><span class="sxs-lookup"><span data-stu-id="b559f-140">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="b559f-141">對檔案採取 [回應動作](respond-file-alerts.md) 的其中一個選項是為檔案新增標記。</span><span class="sxs-lookup"><span data-stu-id="b559f-141">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="b559f-142">當您為檔案新增指示器雜湊時，您可以選擇每當組織中的機器嘗試執行時，才引發警示並封鎖檔。</span><span class="sxs-lookup"><span data-stu-id="b559f-142">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="b559f-143">標記自動封鎖的檔案不會出現在檔案的動作中心，但提醒仍會顯示在 [警示] 佇列中。</span><span class="sxs-lookup"><span data-stu-id="b559f-143">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b559f-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="b559f-144">Related topics</span></span>
- [<span data-ttu-id="b559f-145">建立指示器</span><span class="sxs-lookup"><span data-stu-id="b559f-145">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="b559f-146">為 IPs 和 URLs/網域建立指示器</span><span class="sxs-lookup"><span data-stu-id="b559f-146">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="b559f-147">根據憑證建立指示器</span><span class="sxs-lookup"><span data-stu-id="b559f-147">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="b559f-148">管理指示器</span><span class="sxs-lookup"><span data-stu-id="b559f-148">Manage indicators</span></span>](indicator-manage.md)
