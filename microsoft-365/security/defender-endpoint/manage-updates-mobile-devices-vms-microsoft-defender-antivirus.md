---
title: 定義 Microsoft Defender 防毒軟體如何更新行動裝置
description: 管理行動裝置（例如膝上機）應如何使用 Microsoft Defender 防病毒防護更新進行更新。
keywords: 更新，保護，排程更新，電池，行動裝置，膝上型電腦，筆記本，自願加入，microsoft update，wsus，覆寫
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 143b0cb4bac1d3307e440f98fa4278f38e07c7f2
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269537"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="68458-104">管理行動裝置和虛擬機器 (VM) 的更新</span><span class="sxs-lookup"><span data-stu-id="68458-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="68458-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="68458-105">**Applies to:**</span></span>

- [<span data-ttu-id="68458-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="68458-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="68458-107">行動裝置和 Vm 可能需要更多設定，以確保更新不會影響效能。</span><span class="sxs-lookup"><span data-stu-id="68458-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="68458-108">這些裝置有兩個可用的設定：</span><span class="sxs-lookup"><span data-stu-id="68458-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="68458-109">在未使用 WSUS 連線的情況下，在行動電腦上加入宣告 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="68458-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="68458-110">在使用電池電源時防止安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="68458-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="68458-111">下列文章在下列情況中也會很有用：</span><span class="sxs-lookup"><span data-stu-id="68458-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="68458-112">設定排程和追趕掃描</span><span class="sxs-lookup"><span data-stu-id="68458-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="68458-113">管理已過期端點的更新</span><span class="sxs-lookup"><span data-stu-id="68458-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="68458-114">虛擬桌面基礎結構 (VDI) 環境中 Microsoft Defender 防毒軟體的部署指南</span><span class="sxs-lookup"><span data-stu-id="68458-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="68458-115">在未使用 WSUS 連線的情況下，在行動電腦上加入宣告 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="68458-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="68458-116">當行動裝置未連接到公司網路或沒有 WSUS 連線時，您可以使用 Microsoft 更新，將在執行 Microsoft Defender 防病毒的行動裝置上的安全性智慧保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="68458-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="68458-117">這表示即使您已將 WSUS 設定為覆寫 Microsoft Update，也可以透過 Microsoft Update) 將保護更新傳送至裝置 (。</span><span class="sxs-lookup"><span data-stu-id="68458-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="68458-118">您可以採用下列其中一種方式，選擇參加行動裝置上的 Microsoft 更新：</span><span class="sxs-lookup"><span data-stu-id="68458-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="68458-119">使用群組原則變更設定。</span><span class="sxs-lookup"><span data-stu-id="68458-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="68458-120">使用 VBScript 建立腳本，然後在網路中的每一部電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="68458-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="68458-121">透過 [ **設定** ] 功能表，手動選擇在您的網路上的每一部電腦。</span><span class="sxs-lookup"><span data-stu-id="68458-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="68458-122">使用群組原則加入宣告 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="68458-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="68458-123">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="68458-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="68458-124">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="68458-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="68458-125">選取 [ **原則** ]，然後選取 [ **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="68458-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="68458-126">將樹狀目錄展開為 **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **簽名更新**。</span><span class="sxs-lookup"><span data-stu-id="68458-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="68458-127">將 [ **允許 Microsoft 更新的安全性智慧更新** ] 設定為 [ **啟用**]，然後選取  **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="68458-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="68458-128">使用 VBScript 加入宣告 Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="68458-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="68458-129">使用 MSDN 文章 [加入宣告 Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) 中的指示來建立 VBScript。</span><span class="sxs-lookup"><span data-stu-id="68458-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="68458-130">在您的網路中的每一部電腦上執行您所建立的 VBScript。</span><span class="sxs-lookup"><span data-stu-id="68458-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="68458-131">手動加入宣告 Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="68458-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="68458-132">在您想要加入的電腦上，在 [**更新 & 的安全性** 設定中開啟 **Windows update** 。</span><span class="sxs-lookup"><span data-stu-id="68458-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="68458-133">選取 [ **高級** 選項]。</span><span class="sxs-lookup"><span data-stu-id="68458-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="68458-134">選取 [ **在我更新 Windows 時，提供其他 Microsoft 產品的更新**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="68458-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="68458-135">在使用電池電源時防止安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="68458-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="68458-136">您可以將 Microsoft Defender 防病毒設定為僅在電腦連線至有線電源時下載保護更新。</span><span class="sxs-lookup"><span data-stu-id="68458-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="68458-137">使用群組原則防止在電池電源上進行安全性情報更新</span><span class="sxs-lookup"><span data-stu-id="68458-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="68458-138">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，選擇您要設定的群組原則物件，然後開啟以供編輯。</span><span class="sxs-lookup"><span data-stu-id="68458-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="68458-139">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="68458-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="68458-140">選取 [ **原則** ]，然後選取 [ **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="68458-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="68458-141">將樹狀目錄展開為 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **簽名更新**，然後設定 **允許使用電池供電時，啟用安全智慧更新**。 </span><span class="sxs-lookup"><span data-stu-id="68458-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="68458-142">然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="68458-142">Then select **OK**.</span></span> 

<span data-ttu-id="68458-143">當電腦使用電池電源時，此動作可防止下載保護更新。</span><span class="sxs-lookup"><span data-stu-id="68458-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="68458-144">相關文章</span><span class="sxs-lookup"><span data-stu-id="68458-144">Related articles</span></span>

- [<span data-ttu-id="68458-145">管理 Microsoft Defender 防病毒更新並套用基準</span><span class="sxs-lookup"><span data-stu-id="68458-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="68458-146">在 Windows 10 中更新及管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="68458-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)