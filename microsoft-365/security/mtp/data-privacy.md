---
title: Microsoft 威脅防護資料安全性與隱私權
description: 描述服務的隱私權和資料安全性。
keywords: 隱私權, 資料, 安全性, 信任中心, 資訊集合
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 708ae0965eadd453ad4a8fd1dd7c29231cb07916
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910919"
---
# <a name="microsoft-threat-protection-data-security-and-privacy"></a><span data-ttu-id="1d8c7-104">Microsoft 威脅防護資料安全性與隱私權</span><span class="sxs-lookup"><span data-stu-id="1d8c7-104">Microsoft Threat Protection data security and privacy</span></span>

<span data-ttu-id="1d8c7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1d8c7-105">**Applies to:**</span></span>
- <span data-ttu-id="1d8c7-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="1d8c7-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="1d8c7-107">若使用 Microsoft 威脅防護預覽，即表示您同意下列條款：</span><span class="sxs-lookup"><span data-stu-id="1d8c7-107">By using the Microsoft Threat Protection preview you consent to the following terms:</span></span>

<span data-ttu-id="1d8c7-108">您的適用客戶資料 (如線上服務條款 ("OST") 中所定義) 將會從其他 Microsoft 服務轉移到 Microsoft 威脅防護，以及從 Microsoft 威脅防護轉移回適用的 Microsoft 服務。</span><span class="sxs-lookup"><span data-stu-id="1d8c7-108">Your applicable Customer Data (as defined in the Online Service Terms ("OST")) will be transferred from other Microsoft services into Microsoft Threat Protection and from Microsoft Threat Protection back to applicable Microsoft services.</span></span> <span data-ttu-id="1d8c7-109">在此預覽期間，在 Microsoft 威脅防護中使用客戶資料，將會遵循 Microsoft Defender 進階威脅防護 (Microsoft Defender ATP) 的資料處理標準和承諾。</span><span class="sxs-lookup"><span data-stu-id="1d8c7-109">For the duration of this preview, use of your Customer Data in Microsoft Threat Protection will follow the data handling standards and commitments for Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP).</span></span> <span data-ttu-id="1d8c7-110">您認可此類承諾可能與轉移客戶資料的服務不同。</span><span class="sxs-lookup"><span data-stu-id="1d8c7-110">You acknowledge that such commitments may differ from the services from which that Customer Data is transferred.</span></span> <span data-ttu-id="1d8c7-111">此外，儲存在 Microsoft 威脅防護中的客戶資料，將會在您所選用於儲存您的 Microsoft Defender ATP 客戶資料的地理位置中儲存待用，這可能會與您對其他服務所選取的相關地區有所不同。</span><span class="sxs-lookup"><span data-stu-id="1d8c7-111">Further, Customer Data stored in Microsoft Threat Protection will be stored at rest in the Geo you selected for storage of your Microsoft Defender ATP Customer Data, which may differ from the Geo you selected in connection with other services.</span></span> <span data-ttu-id="1d8c7-112">Microsoft 不會將客戶資料傳送到這類地區以外的地方，[Microsoft 信任中心](https://www.microsoft.com/trust-center)的 Microsoft 信任中心之「資料位置」一節中所述除外。</span><span class="sxs-lookup"><span data-stu-id="1d8c7-112">Microsoft will not transfer the Customer Data outside of such Geo except as noted in the "Data Location" section of the Microsoft Trust Center located at [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span>

<span data-ttu-id="1d8c7-113">此外，當您判斷哪些使用者可以存取 Microsoft 威脅防護時，Microsoft 威脅防護目前不允許使用角色型存取控制 ("RBAC")。</span><span class="sxs-lookup"><span data-stu-id="1d8c7-113">Further, while you determine which of your users may access Microsoft Threat Protection, Microsoft Threat Protection does not currently allow for role-based access control ("RBAC").</span></span> <span data-ttu-id="1d8c7-114">您認可在 Microsoft 威脅防護從支援 RBAC 的 Microsoft 服務接收資料的情況下，該服務中的存取層級將不會套用至 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="1d8c7-114">You acknowledge that to the extent Microsoft Threat Protection receives data from a Microsoft service that does support RBAC, access levels in that service will not apply in Microsoft Threat Protection.</span></span>


<span data-ttu-id="1d8c7-115">如需有關特定產品的資料儲存與隱私權資訊的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="1d8c7-115">For more information on the data storage and privacy information of the specific products see:</span></span>
- [<span data-ttu-id="1d8c7-116">Microsoft Defender ATP 資料儲存與隱私權</span><span class="sxs-lookup"><span data-stu-id="1d8c7-116">Microsoft Defender ATP data storage and privacy</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [<span data-ttu-id="1d8c7-117">Microsoft Cloud App Security 資料安全性與隱私權</span><span class="sxs-lookup"><span data-stu-id="1d8c7-117">Microsoft Cloud App Security data security and privacy</span></span>](https://docs.microsoft.com/cloud-app-security/cas-compliance-trust)
- [<span data-ttu-id="1d8c7-118">Office 365 隱私權、安全性和透明化</span><span class="sxs-lookup"><span data-stu-id="1d8c7-118">Office 365 privacy, security, and transparency</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/privacy-security-and-transparency#advanced-threat-protection)