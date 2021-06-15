---
title: 部署和啟用 Microsoft Defender 防毒軟體
description: 使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、群組原則、PowerShell Cmdlet 或 WMI，部署 Microsoft Defender 防毒軟體以保護端點。
keywords: 部署、啟用、Microsoft Defender 防毒軟體
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a847e65adb0402d4c5f98e19424677ccdc1011da
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925740"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="a7f04-104">部署和啟用 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="a7f04-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a7f04-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a7f04-105">**Applies to:**</span></span>

- [<span data-ttu-id="a7f04-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a7f04-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a7f04-107">視您所使用的管理工具而定，您可能需要特別啟用或設定 Microsoft Defender 防毒軟體保護。</span><span class="sxs-lookup"><span data-stu-id="a7f04-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="a7f04-108">請參閱[部署、管理及報告 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md#ref2)的表格，以取得如何使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、群組原則、Active Directory、Microsoft Azure、PowerShell Cmdlet 及 Windows 管理指令 (WMI) 來啟用保護的指示。</span><span class="sxs-lookup"><span data-stu-id="a7f04-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="a7f04-109">某些案例需要更多有關如何成功部署或設定 Microsoft Defender 防毒軟體保護（如虛擬桌面基礎結構 (VDI) 環境）的指導方針。</span><span class="sxs-lookup"><span data-stu-id="a7f04-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="a7f04-110">本節中的其餘文章提供在[VDI 或遠端桌面服務 (RDS) 環境中，設定 Microsoft Defender 防毒軟體虛擬機器 (vm) ](deployment-vdi-microsoft-defender-antivirus.md)的端對端建議和最佳作法。</span><span class="sxs-lookup"><span data-stu-id="a7f04-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="a7f04-111">相關文章</span><span class="sxs-lookup"><span data-stu-id="a7f04-111">Related articles</span></span>

- [<span data-ttu-id="a7f04-112">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="a7f04-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a7f04-113">部署、管理更新及報告 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="a7f04-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a7f04-114">虛擬桌面基礎結構 (VDI) 環境中 Microsoft Defender 防毒軟體的部署指南</span><span class="sxs-lookup"><span data-stu-id="a7f04-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)