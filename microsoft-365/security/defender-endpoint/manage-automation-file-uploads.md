---
title: 管理自動化檔上傳
description: 啟用內容分析並設定將送出以進行分析的副檔名和電子郵件附件擴充功能
keywords: 自動化，檔案，上傳，內容，分析，檔案，擴充，電子郵件，附件
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
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060699"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="2b6d1-104">管理自動化檔上傳</span><span class="sxs-lookup"><span data-stu-id="2b6d1-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2b6d1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2b6d1-105">**Applies to:**</span></span>
- [<span data-ttu-id="2b6d1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2b6d1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2b6d1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b6d1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2b6d1-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2b6d1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2b6d1-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2b6d1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="2b6d1-110">啟用內容分析功能，讓某些檔案和電子郵件附件可自動上傳至雲端，以進行其他檢查，以進行自動調查。</span><span class="sxs-lookup"><span data-stu-id="2b6d1-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="2b6d1-111">指定副檔名名稱和電子郵件附件分機名稱，以識別檔案和電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="2b6d1-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="2b6d1-112">例如，如果您將 *exe* 和 *bat* 新增為檔案或附件分機名稱，則會自動將這些分機號碼的所有檔案或附件傳送至雲端，以在自動調查期間進行其他檢查。</span><span class="sxs-lookup"><span data-stu-id="2b6d1-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="2b6d1-113">新增副檔名名稱和附件分機名稱。</span><span class="sxs-lookup"><span data-stu-id="2b6d1-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="2b6d1-114">在功能窗格中，選取 [**設定**  >  **自動化** 檔案上傳]。</span><span class="sxs-lookup"><span data-stu-id="2b6d1-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="2b6d1-115">切換 [內容分析] 設定為 [ **開啟** ] 和 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="2b6d1-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="2b6d1-116">請以逗號設定下列副檔名及分隔副檔名：</span><span class="sxs-lookup"><span data-stu-id="2b6d1-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="2b6d1-117">檔案 **副檔名**-電子郵件附件以外的可疑檔案會提交其他檢查</span><span class="sxs-lookup"><span data-stu-id="2b6d1-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="2b6d1-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="2b6d1-118">Related topics</span></span>
- [<span data-ttu-id="2b6d1-119">管理自動化資料夾排除</span><span class="sxs-lookup"><span data-stu-id="2b6d1-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
