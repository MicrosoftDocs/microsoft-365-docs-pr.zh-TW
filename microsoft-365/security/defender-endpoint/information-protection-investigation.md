---
title: 使用敏感度標籤來設定事件回應的優先順序
description: 瞭解如何使用敏感度標籤優先順序和調查事件
keywords: 資訊、保護、資料、遺失、防護、標籤、dlp、事件、調查、調查
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d0c27ab2c6af8706e5e06a3c87b44e49c9185766
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059168"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="17db3-104">使用敏感度標籤來設定事件回應的優先順序</span><span class="sxs-lookup"><span data-stu-id="17db3-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="17db3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="17db3-105">**Applies to:**</span></span>
- [<span data-ttu-id="17db3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="17db3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="17db3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17db3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="17db3-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="17db3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="17db3-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="17db3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="17db3-110">典型的高級持續威脅週期包含資料 exfiltration。</span><span class="sxs-lookup"><span data-stu-id="17db3-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="17db3-111">在安全性事件中，一定要能夠優先考慮敏感檔案可能會有危險的情況，以保護公司資料和資訊。</span><span class="sxs-lookup"><span data-stu-id="17db3-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="17db3-112">Defender for Endpoint 可使用敏感度標籤，讓安全性事件的優先順序變得更簡單。</span><span class="sxs-lookup"><span data-stu-id="17db3-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="17db3-113">敏感度標籤會快速識別可能包含機密資訊（例如機密資訊）的裝置的事件。</span><span class="sxs-lookup"><span data-stu-id="17db3-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="17db3-114">調查涉及敏感性資料的事件</span><span class="sxs-lookup"><span data-stu-id="17db3-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="17db3-115">瞭解如何使用資料敏感度標籤來設定事件調查的優先順序。</span><span class="sxs-lookup"><span data-stu-id="17db3-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="17db3-116">已偵測到 Windows 10 版本1809或更新版本的標籤。</span><span class="sxs-lookup"><span data-stu-id="17db3-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="17db3-117">在 Microsoft Defender Security Center 中，選取 [ **事件**]。</span><span class="sxs-lookup"><span data-stu-id="17db3-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="17db3-118">向右流覽以查看 [ **資料敏感度** ] 欄。</span><span class="sxs-lookup"><span data-stu-id="17db3-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="17db3-119">此資料行會反映在與事件相關的裝置上看到的靈敏度標籤，以提供敏感檔案可能會受到事件影響的指示。</span><span class="sxs-lookup"><span data-stu-id="17db3-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![資料敏感度欄的影像](images/data-sensitivity-column.png)

    <span data-ttu-id="17db3-121">您也可以根據 **資料敏感度** 進行篩選</span><span class="sxs-lookup"><span data-stu-id="17db3-121">You can also filter based on **Data sensitivity**</span></span> 

    ![資料敏感度篩選的影像](images/data-sensitivity-filter.png)

3. <span data-ttu-id="17db3-123">開啟 [事件] 頁面以進一步調查。</span><span class="sxs-lookup"><span data-stu-id="17db3-123">Open the incident page to further investigate.</span></span>

    ![事件映射頁面詳細資料](images/incident-page.png)

4. <span data-ttu-id="17db3-125">選取 [ **裝置** ] 索引標籤，識別儲存敏感度標籤的裝置。</span><span class="sxs-lookup"><span data-stu-id="17db3-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![裝置索引標籤的影像](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="17db3-127">選取儲存敏感性資料的裝置，並在時程表中進行搜尋，以找出可能會受到影響的檔案，然後採取適當的動作，以確保資料受到保護。</span><span class="sxs-lookup"><span data-stu-id="17db3-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="17db3-128">您可以搜尋資料敏感度標籤，以縮小裝置時程表上所顯示的事件。</span><span class="sxs-lookup"><span data-stu-id="17db3-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="17db3-129">這樣做只會顯示與已說標籤名稱之檔案相關聯的事件。</span><span class="sxs-lookup"><span data-stu-id="17db3-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![根據標籤縮小搜尋結果時，裝置時程表的影像](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="17db3-131">透過高級搜尋中的 ' DeviceFileEvents ' 也會公開這些資料點，允許高級查詢及排程偵測採用帳戶敏感度標籤及檔案保護狀態。</span><span class="sxs-lookup"><span data-stu-id="17db3-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
