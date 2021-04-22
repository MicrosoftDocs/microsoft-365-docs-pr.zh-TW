---
title: Microsoft Defender 與 Defender for Endpoint 的相容性
description: 瞭解 Windows Defender 如何與 Microsoft Defender for Endpoint 搭配使用，以及如何在使用協力廠商反惡意軟體用戶端時運作。
keywords: windows defender 相容性，defender，Microsoft Defender for Endpoint，defender for endpoint，殺毒軟體，mde
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
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a8dca4a80385fabcdc64a5584474214d05be4a6c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935374"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="167e7-104">Microsoft Defender 防病毒與 Microsoft Defender for Endpoint 的相容性</span><span class="sxs-lookup"><span data-stu-id="167e7-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="167e7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="167e7-105">**Applies to:**</span></span>
- [<span data-ttu-id="167e7-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="167e7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="167e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="167e7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="167e7-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="167e7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="167e7-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="167e7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="167e7-110">Microsoft Defender for Endpoint agent 取決於 Microsoft Defender 防毒軟體的某些功能，例如檔案掃描。</span><span class="sxs-lookup"><span data-stu-id="167e7-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="167e7-111">Endpoint 的 defender 不遵循 Microsoft Defender 防病毒排除設定。</span><span class="sxs-lookup"><span data-stu-id="167e7-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="167e7-112">您必須在 Defender for Endpoint 裝置上設定安全性智慧更新，以判斷 Microsoft Defender 防病毒是否使用中的反惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="167e7-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="167e7-113">如需詳細資訊，請參閱 [管理 Microsoft Defender 防病毒更新及套用基準](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="167e7-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="167e7-114">如果架裝置是由協力廠商反惡意軟體用戶端保護，該端點上的 Microsoft Defender 防毒軟體會進入被動模式。</span><span class="sxs-lookup"><span data-stu-id="167e7-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="167e7-115">Microsoft Defender 防病毒將繼續接收更新，而且會將 *mspeng.exe* 程式列為執行服務，但不會執行掃描，也不會取代執行中的協力廠商反惡意程式碼用戶端。</span><span class="sxs-lookup"><span data-stu-id="167e7-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="167e7-116">將會停用 Microsoft Defender 防病毒介面，而且裝置上的使用者將無法使用 Microsoft Defender 防病毒來執行隨選掃描或設定大部分的選項。</span><span class="sxs-lookup"><span data-stu-id="167e7-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="167e7-117">如需詳細資訊，請參閱 [Microsoft Defender 防病毒和 Defender For Endpoint 相容性主題](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="167e7-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
