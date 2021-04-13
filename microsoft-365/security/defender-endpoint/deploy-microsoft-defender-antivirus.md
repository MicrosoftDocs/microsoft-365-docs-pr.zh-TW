---
title: 部署及啟用 Microsoft Defender 防毒程式
description: 使用 Microsoft Intune、Microsoft Endpoint Configuration 管理員、群組原則、PowerShell Cmdlet 或 WMI，部署 Microsoft Defender 防病毒以保護您的端點。
keywords: 部署、啟用、Microsoft Defender 防毒程式
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: efc2aa0f48cb2bc55e729b65c892a07b74c1bc46
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690235"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="0b337-104">部署及啟用 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="0b337-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0b337-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0b337-105">**Applies to:**</span></span>

- [<span data-ttu-id="0b337-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0b337-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0b337-107">視您使用的管理工具而定，您可能需要特別啟用或設定 Microsoft Defender 防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="0b337-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="0b337-108">請參閱 [Microsoft Defender 防病毒的部署、管理及報告](deploy-manage-report-microsoft-defender-antivirus.md#ref2) 中的表格，以取得如何使用 microsoft Intune、microsoft 端點設定管理員、群組原則、Active Directory、microsoft Azure、PowerShell Cmdlet 及 Windows 管理指令 (WMI) 來啟用保護的指示。</span><span class="sxs-lookup"><span data-stu-id="0b337-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="0b337-109">某些案例針對如何成功部署或設定 Microsoft Defender 防防毒保護（如虛擬桌面基礎結構 (VDI) 環境），需要更多指導方針。</span><span class="sxs-lookup"><span data-stu-id="0b337-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="0b337-110">本節中的其餘文章會提供在 [VDI 或遠端桌面服務 (RDS) 環境中，設定 Microsoft Defender 防毒軟體機器 (vm) ](deployment-vdi-microsoft-defender-antivirus.md)的端對端建議和最佳作法。</span><span class="sxs-lookup"><span data-stu-id="0b337-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="0b337-111">相關文章</span><span class="sxs-lookup"><span data-stu-id="0b337-111">Related articles</span></span>

- [<span data-ttu-id="0b337-112">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="0b337-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="0b337-113">在 Microsoft Defender 防病毒上部署、管理更新及報告</span><span class="sxs-lookup"><span data-stu-id="0b337-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b337-114">虛擬桌面基礎結構中的 Microsoft Defender 防病毒部署指南 (VDI) 環境</span><span class="sxs-lookup"><span data-stu-id="0b337-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)