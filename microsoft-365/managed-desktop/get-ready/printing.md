---
title: 為 Microsoft 受管理的電腦準備列印資源
description: 確保列印順利運作的重要步驟
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1588a2c91bcbe0bd381acb6be4f9bd5562810860
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530244"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="b4f9f-104">為 Microsoft 受管理的電腦準備列印資源</span><span class="sxs-lookup"><span data-stu-id="b4f9f-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="b4f9f-105">當您準備好在 Microsoft 受管理的電腦上註冊時，您應該評估列印需求，並決定適合您環境的方式。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="b4f9f-106">您有三個選項：</span><span class="sxs-lookup"><span data-stu-id="b4f9f-106">You have three options:</span></span>
 
- <span data-ttu-id="b4f9f-107">部署 Microsoft 混合式雲端列印解決方案，讓 Microsoft 受管理的桌面裝置可輕鬆探索印表機。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-107">Deploy the Microsoft hybrid cloud print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="b4f9f-108">如需詳細資訊，請參閱[部署 Windows Server 混合式雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-108">For more information, see [Deploy Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
- <span data-ttu-id="b4f9f-109">使用自訂的 PowerShell 腳本直接部署印表機。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="b4f9f-110">請遵循 [[設定本機印表機](#set-up-local-printers)] 區段中的步驟來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section to do this.</span></span>
- <span data-ttu-id="b4f9f-111">使用與加入 Azure Active Directory 網域的 Windows 10 裝置相容的非 Microsoft 雲端列印解決方案。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="b4f9f-112">解決方案必須符合 Microsoft Managed Desktop 的軟體需求。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="b4f9f-113">如需詳細資訊，請參閱[Microsoft Managed Desktop app 需求](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="b4f9f-114">在所有情況下，如果無法從 Microsoft Update 或 Microsoft Store 取得印表機驅動程式，您必須自行取得，並使用 Microsoft Intune 將其打包以部署至 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="b4f9f-115">如需詳細資訊，請參閱[Intune 獨立-Win32 應用程式管理](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="b4f9f-115">For more, see [Intune Standalone - Win32 app management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="b4f9f-116">設定本機印表機</span><span class="sxs-lookup"><span data-stu-id="b4f9f-116">Set up local printers</span></span>

<span data-ttu-id="b4f9f-117">如果您已決定使用自訂的 PowerShell 腳本部署印表機，並準備好列印資源，請遵循下列步驟來部署共用印表機：</span><span class="sxs-lookup"><span data-stu-id="b4f9f-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="b4f9f-118">流覽至 Microsoft 受管理的桌面入口網站。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="b4f9f-119">在管理入口網站的**支援 > 支援要求**區段中，送出標示為「*印表機部署*」的要求，提供這些詳細資料：</span><span class="sxs-lookup"><span data-stu-id="b4f9f-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="b4f9f-120">將需要為 Microsoft 受管理的桌面裝置部署的共用印表機位置的所有 UNC 路徑</span><span class="sxs-lookup"><span data-stu-id="b4f9f-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="b4f9f-121">需要存取這些共用印表機的使用者群組</span><span class="sxs-lookup"><span data-stu-id="b4f9f-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="b4f9f-122">您可以使用系統管理入口網站，告知您要求完成的時間。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="b4f9f-123">起初，我們只會將設定部署至測試部署群組中的裝置。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="b4f9f-124">您必須測試及確認設定是否如預期那樣運作。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="b4f9f-125">使用支援要求中的 [**討論**] 索引標籤回復我們，以告知您完成測試的時間。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="b4f9f-126">然後，我們會將設定部署至其他部署群組。</span><span class="sxs-lookup"><span data-stu-id="b4f9f-126">We'll then deploy the configuration to the other deployment groups.</span></span>
