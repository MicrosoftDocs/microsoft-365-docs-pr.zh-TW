---
title: 設定適用於 Windows 10 電腦的裝置保護設定
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
description: 了解預設和其他 Microsoft 365 商務版來保護 Windows 10 裝置中可用的設定。
ms.openlocfilehash: ab306e3d5a6011a0e7d537c98ecca6ef49ff82d9
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575751"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="a1abe-103">設定適用於 Windows 10 電腦的裝置保護設定</span><span class="sxs-lookup"><span data-stu-id="a1abe-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="a1abe-104">保護 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="a1abe-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="a1abe-105">觀看如何使用 Microsoft 365 商務版 來保護 Windows 10 裝置的影片：</span><span class="sxs-lookup"><span data-stu-id="a1abe-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="a1abe-106">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="a1abe-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="a1abe-107">在左側導覽中，選擇 [**裝置** \> **原則** \> **新增**。</span><span class="sxs-lookup"><span data-stu-id="a1abe-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="a1abe-108">在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="a1abe-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="a1abe-109">[**原則類型**] 下選擇 [ **Windows 10 裝置設定**]。</span><span class="sxs-lookup"><span data-stu-id="a1abe-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="a1abe-110">依序展開 [**保護 Windows 10 裝置**\>設定您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="a1abe-110">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="a1abe-111">See [Available settings](#available-settings) for more information.</span><span class="sxs-lookup"><span data-stu-id="a1abe-111">See [Available settings](#available-settings) for more information.</span></span> 
    
    <span data-ttu-id="a1abe-112">您隨時可以使用 [**重設預設設定**] 連結回復到預設設定。</span><span class="sxs-lookup"><span data-stu-id="a1abe-112">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="a1abe-114">下一步] 決定**人員會收到這些設定？**</span><span class="sxs-lookup"><span data-stu-id="a1abe-114">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="a1abe-115">如果您不想要使用預設**的所有使用者**安全性群組，選擇**變更**] 中，搜尋人員會收到這些設定的 [安全性] 群組\>**選取**。</span><span class="sxs-lookup"><span data-stu-id="a1abe-115">If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="a1abe-116">最後，選擇 [**完成**] 以儲存原則，並將它指派到裝置。</span><span class="sxs-lookup"><span data-stu-id="a1abe-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="a1abe-117">可用的設定</span><span class="sxs-lookup"><span data-stu-id="a1abe-117">Available settings</span></span>

<span data-ttu-id="a1abe-118">預設所有設定都是**上**。</span><span class="sxs-lookup"><span data-stu-id="a1abe-118">By default all settings are **On**.</span></span> <span data-ttu-id="a1abe-119">下列為可用的設定。</span><span class="sxs-lookup"><span data-stu-id="a1abe-119">The following settings are available.</span></span>
  
<span data-ttu-id="a1abe-120">如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a1abe-120">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a1abe-121">設定</span><span class="sxs-lookup"><span data-stu-id="a1abe-121">Setting</span></span>  <br/> |<span data-ttu-id="a1abe-122">描述</span><span class="sxs-lookup"><span data-stu-id="a1abe-122">Description</span></span>  <br/> |
|<span data-ttu-id="a1abe-123">使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害</span><span class="sxs-lookup"><span data-stu-id="a1abe-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="a1abe-124">需要開啟 Windows Defender 防毒軟體，以保護電腦免於遭受連接至網際網路時的安全威脅。</span><span class="sxs-lookup"><span data-stu-id="a1abe-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="a1abe-125">協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅</span><span class="sxs-lookup"><span data-stu-id="a1abe-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="a1abe-126">開啟 Microsoft Edge 中的設定，以協助保護使用者免受惡意網站與下載檔案的威脅。</span><span class="sxs-lookup"><span data-stu-id="a1abe-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="a1abe-127">使用能減少裝置受攻擊面的規則</span><span class="sxs-lookup"><span data-stu-id="a1abe-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="a1abe-p104">設定為 [開啟] 時，受攻擊面縮減能協助系統封鎖惡意程式碼通常會用來感染裝置的動作和 App。只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。請參閱[縮減受攻擊面](https://go.microsoft.com/fwlink/?linkid=870417)以深入了解。  </span><span class="sxs-lookup"><span data-stu-id="a1abe-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="a1abe-131">保護資料夾來抵擋勒索軟體等威脅</span><span class="sxs-lookup"><span data-stu-id="a1abe-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="a1abe-p105">這項設定使用受控資料夾存取權來保護公司資料，不讓可疑或惡意的 App 修改。系統會封鎖這類型的 App，不讓它們變更受保護資料夾中的資料。只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。請參閱[使用受控資料夾存取權來保護資料夾](https://go.microsoft.com/fwlink/?linkid=870418)以深入了解。  </span><span class="sxs-lookup"><span data-stu-id="a1abe-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="a1abe-136">避免連線到網際網路上可能有惡意之內容的網路存取行為</span><span class="sxs-lookup"><span data-stu-id="a1abe-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="a1abe-p106">請使用這項設定來封鎖前往聲譽不佳之網際網路位置 (可能裝載了網路釣魚詐騙郵件、惡意探索或其他惡意內容) 的連外使用者連線。只有在 Windows Defender 防毒軟體設為 [開啟] 時，這項設定才能夠使用。請參閱[保護您的網路](https://go.microsoft.com/fwlink/?linkid=870419)以深入了解。  </span><span class="sxs-lookup"><span data-stu-id="a1abe-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="a1abe-140">利用 BitLocker 來協助您保護電腦上的檔案和資料夾，抵擋未經授權的存取行為</span><span class="sxs-lookup"><span data-stu-id="a1abe-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="a1abe-p107">Bitlocker 能為電腦硬碟加密來保護資料，以及在電腦遺失或遭竊時保護資料來避免資料外洩。如需詳細資訊，請參閱 [Bitlocker 常見問題集](https://go.microsoft.com/fwlink/?linkid=871000)。  </span><span class="sxs-lookup"><span data-stu-id="a1abe-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="a1abe-143">允許使用者從 Microsoft Store 下載 App</span><span class="sxs-lookup"><span data-stu-id="a1abe-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="a1abe-144">讓使用者從 Microsoft Store 下載並安裝 App。</span><span class="sxs-lookup"><span data-stu-id="a1abe-144">Lets users download and install apps from the Microsoft Store.</span></span> <span data-ttu-id="a1abe-145">應用程式包括所有項目從遊戲生產力工具]，讓我們保留**上**，此設定，但您可以將它關閉額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="a1abe-145">Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.</span></span>  <br/> |
|<span data-ttu-id="a1abe-146">允許使用者存取 Cortana</span><span class="sxs-lookup"><span data-stu-id="a1abe-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="a1abe-147">Cortana 非常實用！</span><span class="sxs-lookup"><span data-stu-id="a1abe-147">Cortana can be very helpful!</span></span> <span data-ttu-id="a1abe-148">她可以開啟設定或關閉您，提供指示，並請確定您已在約會現場，因此我們將此**上**預設。</span><span class="sxs-lookup"><span data-stu-id="a1abe-148">She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.</span></span>  <br/> |
|<span data-ttu-id="a1abe-149">允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告</span><span class="sxs-lookup"><span data-stu-id="a1abe-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="a1abe-150">Windows 祕訣相當實用，並且能在新功能推出時引導使用者。</span><span class="sxs-lookup"><span data-stu-id="a1abe-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="a1abe-151">自動讓 Windows 10 裝置保持在最新狀態</span><span class="sxs-lookup"><span data-stu-id="a1abe-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="a1abe-152">確保 Windows 10 裝置能自動收到最新的更新。</span><span class="sxs-lookup"><span data-stu-id="a1abe-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="a1abe-153">閒置這段時間之後關閉裝置螢幕</span><span class="sxs-lookup"><span data-stu-id="a1abe-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="a1abe-p110">確保使用者閒置時，公司資料已受到保護。使用者可能會在咖啡館等公共場所工作，當使用者暫時離開或是分心時，他們的裝置就容易受到他人任意窺伺。此設定能讓您控制螢幕將於使用者閒置多久之後關閉。</span><span class="sxs-lookup"><span data-stu-id="a1abe-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

