---
title: 設定適用於 Windows 10 電腦的裝置保護設定
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 深入瞭解 Microsoft 365 for business 中可用的預設和其他設定，以保護 Windows 10 裝置。
ms.openlocfilehash: 9096fb6a8fc790d9a9432578cfd8623f9cb69c7a
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011560"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="b27ef-103">設定適用於 Windows 10 電腦的裝置保護設定</span><span class="sxs-lookup"><span data-stu-id="b27ef-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="b27ef-104">保護 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="b27ef-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="b27ef-105">觀看有關如何使用 Microsoft 365 for business 保護 Windows 10 裝置的影片：</span><span class="sxs-lookup"><span data-stu-id="b27ef-105">View a video on how to secure Windows 10 devices with Microsoft 365 for business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="b27ef-106">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b27ef-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="b27ef-107">在左側導覽中，選擇 [**裝置** \> **原則** \> ] [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="b27ef-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="b27ef-108">在 [**新增原則**] 窗格中，輸入這個原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="b27ef-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="b27ef-109">在 [**原則類型**] 底下，選擇 [ **Windows 10 Device Configuration**]。</span><span class="sxs-lookup"><span data-stu-id="b27ef-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="b27ef-110">展開 [**安全的 Windows 10 裝置** \> ] 設定您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="b27ef-110">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="b27ef-111">如需詳細資訊，請參閱[可用設定](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="b27ef-111">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="b27ef-112">您可以隨時使用 [**重設預設值設定**] 連結，以回到預設設定。</span><span class="sxs-lookup"><span data-stu-id="b27ef-112">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="b27ef-114">下一步決定**誰將取得這些設定？**</span><span class="sxs-lookup"><span data-stu-id="b27ef-114">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="b27ef-115">如果您不想要使用預設的 [**所有使用者**] 安全性群組，請選擇 [**變更**]，然後搜尋將取得這些\> **設定的**安全性群組。</span><span class="sxs-lookup"><span data-stu-id="b27ef-115">If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="b27ef-116">最後，選擇 [**完成**] 以儲存原則，並將其指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="b27ef-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="b27ef-117">可用的設定</span><span class="sxs-lookup"><span data-stu-id="b27ef-117">Available settings</span></span>

<span data-ttu-id="b27ef-118">所有設定預設為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="b27ef-118">By default all settings are **On**.</span></span> <span data-ttu-id="b27ef-119">下列為可用的設定。</span><span class="sxs-lookup"><span data-stu-id="b27ef-119">The following settings are available.</span></span>
  
<span data-ttu-id="b27ef-120">如需詳細資訊，請參閱 how [To Intune for a protection features In Microsoft 365 Premium map To Intune settings](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ef-120">For more information, see [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b27ef-121">設定</span><span class="sxs-lookup"><span data-stu-id="b27ef-121">Setting</span></span>  <br/> |<span data-ttu-id="b27ef-122">描述</span><span class="sxs-lookup"><span data-stu-id="b27ef-122">Description</span></span>  <br/> |
|<span data-ttu-id="b27ef-123">使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害</span><span class="sxs-lookup"><span data-stu-id="b27ef-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="b27ef-124">需要開啟 Windows Defender 防毒軟體，以保護電腦免於遭受連接至網際網路時的安全威脅。</span><span class="sxs-lookup"><span data-stu-id="b27ef-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="b27ef-125">協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅</span><span class="sxs-lookup"><span data-stu-id="b27ef-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="b27ef-126">開啟 Microsoft Edge 中的設定，以協助保護使用者免受惡意網站與下載檔案的威脅。</span><span class="sxs-lookup"><span data-stu-id="b27ef-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="b27ef-127">使用能減少裝置受攻擊面的規則</span><span class="sxs-lookup"><span data-stu-id="b27ef-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="b27ef-p104">設定為 [開啟] 時，受攻擊面縮減能協助系統封鎖惡意程式碼通常會用來感染裝置的動作和 App。只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。請參閱[縮減受攻擊面](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)以深入了解。  </span><span class="sxs-lookup"><span data-stu-id="b27ef-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) to learn more.  </span></span><br/> |
|<span data-ttu-id="b27ef-131">保護資料夾來抵擋勒索軟體等威脅</span><span class="sxs-lookup"><span data-stu-id="b27ef-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="b27ef-132">這項設定使用受控資料夾存取權來保護公司資料，不讓可疑或惡意的 App 修改。</span><span class="sxs-lookup"><span data-stu-id="b27ef-132">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware.</span></span> <span data-ttu-id="b27ef-133">系統會封鎖這類型的 App，不讓它們變更受保護資料夾中的資料。</span><span class="sxs-lookup"><span data-stu-id="b27ef-133">These types of apps are blocked from making changes in protected folders.</span></span> <span data-ttu-id="b27ef-134">只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。</span><span class="sxs-lookup"><span data-stu-id="b27ef-134">This setting is only available if Windows Defender Antivirus is set to On.</span></span> <span data-ttu-id="b27ef-135">請參閱[使用可控資料夾存取保護資料夾](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA)以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="b27ef-135">See [Protect folders with Controlled folder access](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) to learn more.</span></span>  <br/> |
|<span data-ttu-id="b27ef-136">避免連線到網際網路上可能有惡意之內容的網路存取行為</span><span class="sxs-lookup"><span data-stu-id="b27ef-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="b27ef-137">使用此設定來封鎖向低信譽 Internet 位置（可能會主控網路釣魚詐騙、入侵或其他惡意內容）的外寄使用者連線。</span><span class="sxs-lookup"><span data-stu-id="b27ef-137">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits, or other malicious content.</span></span> <span data-ttu-id="b27ef-138">只有在 Windows Defender 防病毒設定為**On**時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="b27ef-138">This setting is only available if Windows Defender Antivirus is set to **On**.</span></span> <span data-ttu-id="b27ef-139">如需詳細資訊，請參閱[保護您的網路](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="b27ef-139">For more information, see [Protect your network](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).</span></span>  <br/> |
|<span data-ttu-id="b27ef-140">利用 BitLocker 來協助您保護電腦上的檔案和資料夾，抵擋未經授權的存取行為</span><span class="sxs-lookup"><span data-stu-id="b27ef-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="b27ef-141">Bitlocker 能為電腦硬碟加密來保護資料，以及在電腦遺失或遭竊時保護資料來避免資料外洩。</span><span class="sxs-lookup"><span data-stu-id="b27ef-141">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="b27ef-142">如需詳細資訊，請參閱[BITLOCKER FAQ](https://go.microsoft.com/fwlink/?linkid=871000)。</span><span class="sxs-lookup"><span data-stu-id="b27ef-142">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="b27ef-143">允許使用者從 Microsoft Store 下載 App</span><span class="sxs-lookup"><span data-stu-id="b27ef-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="b27ef-144">讓使用者從 Microsoft Store 下載並安裝 App。</span><span class="sxs-lookup"><span data-stu-id="b27ef-144">Lets users download and install apps from the Microsoft Store.</span></span> <span data-ttu-id="b27ef-145">應用程式包括從遊戲到生產力工具的所有專案，因此我們將此設定保留為**開啟**，但您可以關閉此設定，以進行額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="b27ef-145">Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.</span></span>  <br/> |
|<span data-ttu-id="b27ef-146">允許使用者存取 Cortana</span><span class="sxs-lookup"><span data-stu-id="b27ef-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="b27ef-147">Cortana 非常實用！</span><span class="sxs-lookup"><span data-stu-id="b27ef-147">Cortana can be very helpful!</span></span> <span data-ttu-id="b27ef-148">Cortana 可以為您開啟或關閉您的設定、提供行車方案，並確定您已開啟約會時間，因此我們預設會將此設定保留為**開啟**。</span><span class="sxs-lookup"><span data-stu-id="b27ef-148">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="b27ef-149">允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告</span><span class="sxs-lookup"><span data-stu-id="b27ef-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="b27ef-150">Windows 祕訣相當實用，並且能在新功能推出時引導使用者。</span><span class="sxs-lookup"><span data-stu-id="b27ef-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="b27ef-151">自動讓 Windows 10 裝置保持在最新狀態</span><span class="sxs-lookup"><span data-stu-id="b27ef-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="b27ef-152">確保 Windows 10 裝置能自動收到最新的更新。</span><span class="sxs-lookup"><span data-stu-id="b27ef-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="b27ef-153">閒置這段時間之後關閉裝置螢幕</span><span class="sxs-lookup"><span data-stu-id="b27ef-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="b27ef-p110">確保使用者閒置時，公司資料已受到保護。使用者可能會在咖啡館等公共場所工作，當使用者暫時離開或是分心時，他們的裝置就容易受到他人任意窺伺。此設定能讓您控制螢幕將於使用者閒置多久之後關閉。</span><span class="sxs-lookup"><span data-stu-id="b27ef-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
