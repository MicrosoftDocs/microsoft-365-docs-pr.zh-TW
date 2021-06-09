---
title: Windows 資訊保護概觀
ms.reviewer: ''
description: 深入瞭解資訊保護如何在 Windows 中運作，以識別及保護機密資訊。
keywords: 資訊、保護、dlp、資料、遺失、防護、保護
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9d68f879fe8fd9379b286c106ed9229895f91b9a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841102"
---
# <a name="information-protection-in-windows-overview"></a><span data-ttu-id="c89df-104">Windows 資訊保護概觀</span><span class="sxs-lookup"><span data-stu-id="c89df-104">Information protection in Windows overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c89df-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c89df-105">**Applies to:**</span></span>

- [<span data-ttu-id="c89df-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c89df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c89df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c89df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c89df-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c89df-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c89df-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c89df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="c89df-110">資訊保護是 Microsoft 365 企業版套件不可或缺的一部分，提供智慧防護以保持機密資料的安全性，同時在工作場所中啟用生產力。</span><span class="sxs-lookup"><span data-stu-id="c89df-110">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span>


>[!TIP]
> <span data-ttu-id="c89df-111">請閱讀我們的博客文章，瞭解 microsoft Defender for Endpoint 如何與 microsoft 資訊保護整合，以[探索、保護及監視 Windows 裝置上的機密資料](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)。</span><span class="sxs-lookup"><span data-stu-id="c89df-111">Read our blog post about how Microsoft Defender for Endpoint integrates with Microsoft Information Protection to [discover, protect, and monitor sensitive data on Windows devices](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/).</span></span>

<span data-ttu-id="c89df-112">Defender for Endpoint 套用下列方法來探索、分類及保護資料：</span><span class="sxs-lookup"><span data-stu-id="c89df-112">Defender for Endpoint applies the following methods to discover, classify, and protect data:</span></span>

- <span data-ttu-id="c89df-113">**資料探索**-識別 Windows 裝置上的敏感性資料時面臨危險</span><span class="sxs-lookup"><span data-stu-id="c89df-113">**Data discovery** - Identify sensitive data on Windows devices at risk</span></span>
- <span data-ttu-id="c89df-114">**資料分類**-根據常見的 Microsoft 資訊保護 (MIP) 原則，以 Office 365 安全性 & 規範中心管理。</span><span class="sxs-lookup"><span data-stu-id="c89df-114">**Data classification** - Automatically classify data based on common Microsoft Information Protection (MIP) policies managed in Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="c89df-115">自動分類可讓您保護機密資料，即使使用者未手動分類也是如此。</span><span class="sxs-lookup"><span data-stu-id="c89df-115">Auto-classification allows you to protect sensitive data even if the end user hasn’t manually classified it.</span></span>


## <a name="data-discovery-and-data-classification"></a><span data-ttu-id="c89df-116">資料探索和資料分類</span><span class="sxs-lookup"><span data-stu-id="c89df-116">Data discovery and data classification</span></span>

<span data-ttu-id="c89df-117">Defender for Endpoint 會自動探索具有敏感度標籤的檔案，以及包含機密資訊類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="c89df-117">Defender for Endpoint automatically discovers files with sensitivity labels and files that contain sensitive information types.</span></span>

<span data-ttu-id="c89df-118">敏感度標籤會分類並協助保護機密內容。</span><span class="sxs-lookup"><span data-stu-id="c89df-118">Sensitivity labels classify and help protect sensitive content.</span></span>

<span data-ttu-id="c89df-119">Office 365 資料遺失防護中的機密資訊類型 (DLP) 實現分為兩類：</span><span class="sxs-lookup"><span data-stu-id="c89df-119">Sensitive information types in the Office 365 data loss prevention (DLP) implementation fall under two categories:</span></span>

- <span data-ttu-id="c89df-120">預設</span><span class="sxs-lookup"><span data-stu-id="c89df-120">Default</span></span>
- <span data-ttu-id="c89df-121">自訂</span><span class="sxs-lookup"><span data-stu-id="c89df-121">Custom</span></span>

<span data-ttu-id="c89df-122">預設的機密資訊類型包括銀行帳戶號碼、社會保險號碼或國內 IDs 等資訊。</span><span class="sxs-lookup"><span data-stu-id="c89df-122">Default sensitive information types include information such as bank account numbers, social security numbers, or national IDs.</span></span> <span data-ttu-id="c89df-123">如需詳細資訊，請參閱 [敏感資訊類型的外觀](/office365/securitycompliance/what-the-sensitive-information-types-look-for)。</span><span class="sxs-lookup"><span data-stu-id="c89df-123">For more information, see [What the sensitive information type look for](/office365/securitycompliance/what-the-sensitive-information-types-look-for).</span></span>

<span data-ttu-id="c89df-124">自訂類型是您定義的，其設計目的是為了保護不同類型的敏感資訊 (例如，員工 IDs 或專案編號) 。</span><span class="sxs-lookup"><span data-stu-id="c89df-124">Custom types are ones that you define and is designed to protect a different type of sensitive information (for example, employee IDs or project numbers).</span></span> <span data-ttu-id="c89df-125">如需詳細資訊，請參閱 [建立自訂機密資訊類型](/office365/securitycompliance/create-a-custom-sensitive-information-type)。</span><span class="sxs-lookup"><span data-stu-id="c89df-125">For more information see, [Create a custom sensitive information type](/office365/securitycompliance/create-a-custom-sensitive-information-type).</span></span>

<span data-ttu-id="c89df-126">當您在 Windows 裝置上建立或編輯檔案時，當其包含機密資訊時，資料端點的 Defender 會掃描要評估的內容。</span><span class="sxs-lookup"><span data-stu-id="c89df-126">When a file is created or edited on a  Windows device, Defender for Endpoint scans the content to evaluate if it contains sensitive information.</span></span>

<span data-ttu-id="c89df-127">開啟 Azure 資訊保護整合，這樣一來，當以標籤或資訊類型為端點發現包含機密資訊的檔案時，它會自動轉送到裝置的 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="c89df-127">Turn on the Azure Information Protection integration so that when a file that contains sensitive information is discovered by Defender for Endpoint though labels or information types, it is automatically forwarded to Azure Information Protection from the device.</span></span>

![使用 Azure 資訊保護的 [設定] 頁面的圖像](images/atp-settings-aip.png)

<span data-ttu-id="c89df-129">您可以在 Azure 資訊保護–資料探索儀表板上查看報告的信號。</span><span class="sxs-lookup"><span data-stu-id="c89df-129">The reported signals can be viewed on the Azure Information Protection – Data discovery dashboard.</span></span>

## <a name="azure-information-protection---data-discovery-dashboard"></a><span data-ttu-id="c89df-130">Azure 資訊保護-資料探索儀表板</span><span class="sxs-lookup"><span data-stu-id="c89df-130">Azure Information Protection - Data discovery dashboard</span></span>

<span data-ttu-id="c89df-131">此儀表板會顯示由 Defender for Endpoint 和 Azure 資訊保護所探索之資料的摘要探索資訊。</span><span class="sxs-lookup"><span data-stu-id="c89df-131">This dashboard presents a summarized discovery information of data discovered by both Defender for Endpoint and Azure Information Protection.</span></span> <span data-ttu-id="c89df-132">來自于端點的資料會以位置類型-端點標示。</span><span class="sxs-lookup"><span data-stu-id="c89df-132">Data from Defender for Endpoint is marked with Location Type - Endpoint.</span></span>

![Azure 資訊保護的影像-資料探索](images/azure-data-discovery.png)

<span data-ttu-id="c89df-134">請注意，右側的 [裝置風險] 欄是指直接從 Endpoint 取得此裝置風險，指出已探索該檔案的安全性裝置風險層級，其依據是由 Defender for Endpoint 所偵測到的作用中安全性威脅。</span><span class="sxs-lookup"><span data-stu-id="c89df-134">Notice the Device Risk column on the right, this device risk is derived directly from Defender for Endpoint, indicating the risk level of the security device where the file was discovered, based on the active security threats detected by Defender for Endpoint.</span></span>

<span data-ttu-id="c89df-135">按一下裝置以查看此裝置上所看到之檔案的清單，其靈敏度標籤和資訊類型。</span><span class="sxs-lookup"><span data-stu-id="c89df-135">Click on a device to view a list of files observed on this device, with their sensitivity labels and information types.</span></span>

>[!NOTE]
><span data-ttu-id="c89df-136">請等待大約15-20 分鐘，Azure 資訊保護儀表板探索才能反映已發現的檔案。</span><span class="sxs-lookup"><span data-stu-id="c89df-136">Please allow approximately 15-20 minutes for the Azure Information Protection Dashboard Discovery to reflect discovered files.</span></span>

## <a name="log-analytics"></a><span data-ttu-id="c89df-137">記錄分析</span><span class="sxs-lookup"><span data-stu-id="c89df-137">Log Analytics</span></span>

<span data-ttu-id="c89df-138">您也可以在 [Azure 記錄分析](/azure/log-analytics/log-analytics-overview)中使用以 Defender 做為基礎的資料探索，您可以在原始資料上執行複雜的查詢。</span><span class="sxs-lookup"><span data-stu-id="c89df-138">Data discovery based on Defender for Endpoint is also available in [Azure Log Analytics](/azure/log-analytics/log-analytics-overview), where you can perform complex queries over the raw data.</span></span>

<span data-ttu-id="c89df-139">如需 Azure 資訊保護分析的詳細資訊，請參閱 [適用于 Azure 資訊保護的中央報告](/azure/information-protection/reports-aip)。</span><span class="sxs-lookup"><span data-stu-id="c89df-139">For more information on Azure Information Protection analytics, see [Central reporting for Azure Information Protection](/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="c89df-140">在 Azure 入口網站中開啟 Azure 記錄分析，並在 standard 或古典) 中開啟查詢產生器 (。</span><span class="sxs-lookup"><span data-stu-id="c89df-140">Open Azure Log Analytics in Azure portal and open a query builder (standard or classic).</span></span>

<span data-ttu-id="c89df-141">若要查看 Defender 的端點資料，請執行包含下列專案的查詢：</span><span class="sxs-lookup"><span data-stu-id="c89df-141">To view Defender for Endpoint data, perform a query that contains:</span></span>

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

<span data-ttu-id="c89df-142">**先決條件：**</span><span class="sxs-lookup"><span data-stu-id="c89df-142">**Prerequisites:**</span></span>

- <span data-ttu-id="c89df-143">客戶必須具備 Azure 資訊保護的訂閱。</span><span class="sxs-lookup"><span data-stu-id="c89df-143">Customers must have a subscription for Azure Information Protection.</span></span>
- <span data-ttu-id="c89df-144">在 Microsoft Defender 資訊安全中心中啟用 Azure 資訊保護整合：</span><span class="sxs-lookup"><span data-stu-id="c89df-144">Enable Azure Information Protection integration in Microsoft Defender Security Center:</span></span>
    - <span data-ttu-id="c89df-145">移至 **設定** 在 Microsoft Defender 資訊安全中心中，按一下 **[一般**] 下的 [**高級] 設定**。</span><span class="sxs-lookup"><span data-stu-id="c89df-145">Go to **Settings** in Microsoft Defender Security Center, click on **Advanced Settings** under **General**.</span></span>



