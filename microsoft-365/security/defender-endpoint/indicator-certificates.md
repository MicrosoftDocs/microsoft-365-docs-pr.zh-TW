---
title: 根據憑證建立指示器
ms.reviewer: ''
description: 根據定義實體的偵測、預防和排除憑證，建立指示器。
keywords: ioc，憑證，憑證，管理，允許，封鎖，封鎖，clean，惡意，檔案雜湊，ip 位址，url，網域
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
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164678"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="abea6-104">根據憑證建立指示器</span><span class="sxs-lookup"><span data-stu-id="abea6-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="abea6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="abea6-105">**Applies to:**</span></span>
- [<span data-ttu-id="abea6-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="abea6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="abea6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abea6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="abea6-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="abea6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="abea6-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="abea6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="abea6-110">您可以為憑證建立指示器。</span><span class="sxs-lookup"><span data-stu-id="abea6-110">You can create indicators for certificates.</span></span> <span data-ttu-id="abea6-111">常見的使用案例包括：</span><span class="sxs-lookup"><span data-stu-id="abea6-111">Some common use cases include:</span></span>

- <span data-ttu-id="abea6-112">案例當您需要部署封鎖技術時（例如 [攻擊面降減規則](attack-surface-reduction.md) 和 [可控資料夾存取](controlled-folders.md) ），但是需要在允許清單中新增憑證，以允許來自簽署應用程式的行為。</span><span class="sxs-lookup"><span data-stu-id="abea6-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="abea6-113">封鎖整個組織中特定簽署應用程式的使用。</span><span class="sxs-lookup"><span data-stu-id="abea6-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="abea6-114">透過建立指示器以封鎖應用程式的憑證，Windows Defender AV 會使檔案執行 (區塊和修正) ，而且自動化調查和修正行為相同。</span><span class="sxs-lookup"><span data-stu-id="abea6-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="abea6-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="abea6-115">Before you begin</span></span>

<span data-ttu-id="abea6-116">在為憑證建立指示器之前，請務必先瞭解下列需求：</span><span class="sxs-lookup"><span data-stu-id="abea6-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="abea6-117">如果您的組織使用 Windows Defender 防病毒和雲端式保護，則可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="abea6-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="abea6-118">如需詳細資訊，請參閱 [管理以雲端為基礎的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="abea6-118">For more information, see [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="abea6-119">反惡意軟體用戶端版本必須是4.18.1901 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="abea6-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="abea6-120">在 Windows 10 版本1703或更新版本、Windows server 2016 及2019上的電腦上支援。</span><span class="sxs-lookup"><span data-stu-id="abea6-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="abea6-121">病毒和威脅防護定義必須是最新的。</span><span class="sxs-lookup"><span data-stu-id="abea6-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="abea6-122">此功能目前支援輸入。CER 或。PEM 副檔名。</span><span class="sxs-lookup"><span data-stu-id="abea6-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="abea6-123">有效的葉憑證是具有有效憑證路徑的簽署憑證，且必須與 (CA) 的憑證授權單位系所信任的憑證授權單位單位。</span><span class="sxs-lookup"><span data-stu-id="abea6-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="abea6-124">或者，您可以使用自訂的 (自我簽署) 憑證，只要用戶端信任 (根 CA 憑證是安裝在本機電腦「受信任的根身分憑證授權」 ) 。</span><span class="sxs-lookup"><span data-stu-id="abea6-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="abea6-125">允許/封鎖憑證 IOCs 的子系或父項不會包含在 allow/封鎖的 IoC 功能中，只支援分葉憑證。</span><span class="sxs-lookup"><span data-stu-id="abea6-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="abea6-126">無法封鎖 Microsoft 簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="abea6-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="abea6-127">從 [設定] 頁面建立憑證的指示器：</span><span class="sxs-lookup"><span data-stu-id="abea6-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="abea6-128">建立及移除憑證 IoC 最多可能需要3小時。</span><span class="sxs-lookup"><span data-stu-id="abea6-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="abea6-129">在功能窗格中，選取 [**設定**  >  **指示器**]。</span><span class="sxs-lookup"><span data-stu-id="abea6-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="abea6-130">選取 [ **憑證** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="abea6-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="abea6-131">選取 [ **新增指示器**]。</span><span class="sxs-lookup"><span data-stu-id="abea6-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="abea6-132">指定下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="abea6-132">Specify the following details:</span></span>
   - <span data-ttu-id="abea6-133">標記-指定實體詳細資料並定義指示器的到期期限。</span><span class="sxs-lookup"><span data-stu-id="abea6-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="abea6-134">Action-指定要採取的動作並提供描述。</span><span class="sxs-lookup"><span data-stu-id="abea6-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="abea6-135">Scope-定義機器群組的範圍。</span><span class="sxs-lookup"><span data-stu-id="abea6-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="abea6-136">在 [摘要] 索引標籤中查看詳細資料，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="abea6-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="abea6-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="abea6-137">Related topics</span></span>
- [<span data-ttu-id="abea6-138">建立指示器</span><span class="sxs-lookup"><span data-stu-id="abea6-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="abea6-139">建立檔案的指示器</span><span class="sxs-lookup"><span data-stu-id="abea6-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="abea6-140">為 IPs 和 URLs/網域建立指示器</span><span class="sxs-lookup"><span data-stu-id="abea6-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="abea6-141">管理指示器</span><span class="sxs-lookup"><span data-stu-id="abea6-141">Manage indicators</span></span>](indicator-manage.md)
