---
title: 優化 ASR 規則的部署和偵測
description: 優化攻擊面減少 (ASR) 規則可識別及避免一般惡意程式碼利用漏洞。
keywords: 板載，Intune management，microsoft defender for Endpoint，microsoft defender，Windows Defender，攻擊面降低，ASR，安全性基準
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5590e62e7838bb9f611320b6d0e5c573b2be084
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841555"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="d37eb-104">優化 ASR 規則的部署和偵測</span><span class="sxs-lookup"><span data-stu-id="d37eb-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d37eb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d37eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="d37eb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d37eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d37eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d37eb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d37eb-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d37eb-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="d37eb-109">[註冊免費試用版](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="d37eb-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="d37eb-110">[攻擊面減少 (ASR) 規則](./attack-surface-reduction.md) 會識別及避免一般惡意程式碼利用漏洞。</span><span class="sxs-lookup"><span data-stu-id="d37eb-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="d37eb-111">它們會控制可能的惡意程式碼的執行時機和方式。</span><span class="sxs-lookup"><span data-stu-id="d37eb-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="d37eb-112">例如，他們可以阻止 JavaScript 或 VBScript 啟動已下載的可執行檔、從 Office 宏封鎖 WIN32 API 呼叫，以及從 USB 磁片磁碟機封鎖執行的程式。</span><span class="sxs-lookup"><span data-stu-id="d37eb-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="d37eb-113">![攻擊面管理卡](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="d37eb-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="d37eb-114">*攻擊面管理卡*</span><span class="sxs-lookup"><span data-stu-id="d37eb-114">*Attack surface management card*</span></span>

<span data-ttu-id="d37eb-115">「*攻擊面管理卡*」是 Microsoft 365 安全性中心工具的進入點，可供您用來進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="d37eb-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="d37eb-116">瞭解目前如何在組織中部署 ASR 規則。</span><span class="sxs-lookup"><span data-stu-id="d37eb-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="d37eb-117">檢查 ASR 偵測並找出可能不正確的偵測結果。</span><span class="sxs-lookup"><span data-stu-id="d37eb-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="d37eb-118">分析排除專案的影響，並產生要排除的檔案路徑清單。</span><span class="sxs-lookup"><span data-stu-id="d37eb-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="d37eb-119">選取 [**移至攻擊介面管理**  >  **監控] & 報告 > 攻擊面減少規則，> 新增排除** 專案。</span><span class="sxs-lookup"><span data-stu-id="d37eb-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="d37eb-120">您可以從那裡流覽至 Microsoft 365 安全性中心的其他區段。</span><span class="sxs-lookup"><span data-stu-id="d37eb-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="d37eb-121">![Microsoft 365 security center 中的攻擊面降低規則頁面上新增排除標籤](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="d37eb-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="d37eb-122">*Microsoft 365 安全性中心的攻擊面降低規則頁面中的 [**新增排除**] 索引標籤*</span><span class="sxs-lookup"><span data-stu-id="d37eb-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="d37eb-123">若要存取 Microsoft 365 的安全性中心，您需要 Microsoft 365 E3 或 E5 授權，以及 Azure Active Directory 上具有特定角色的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d37eb-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="d37eb-124">[讀取必要的授權和許可權](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。</span><span class="sxs-lookup"><span data-stu-id="d37eb-124">[Read about required licenses and permissions](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="d37eb-125">如需 Microsoft 365 安全性中心內 ASR 規則部署的詳細資訊，請參閱[監視和管理 ASR 規則部署和](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)偵測。</span><span class="sxs-lookup"><span data-stu-id="d37eb-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="d37eb-126">**相關主題**</span><span class="sxs-lookup"><span data-stu-id="d37eb-126">**Related topics**</span></span>

* [<span data-ttu-id="d37eb-127">確保您的裝置已正確設定</span><span class="sxs-lookup"><span data-stu-id="d37eb-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="d37eb-128">取得架至 Microsoft Defender for Endpoint 的裝置</span><span class="sxs-lookup"><span data-stu-id="d37eb-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="d37eb-129">監視 Microsoft Defender for Endpoint security 基準的合規性</span><span class="sxs-lookup"><span data-stu-id="d37eb-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
