---
title: 在 Microsoft Defender for Endpoint 中主控防火牆報告
description: 在 Microsoft 365 的安全性中心內主控及流覽防火牆報告。
keywords: windows defender，防火牆
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809252"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4f3c0-104">在 Microsoft Defender for Endpoint 中主控防火牆報告</span><span class="sxs-lookup"><span data-stu-id="4f3c0-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4f3c0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4f3c0-105">**Applies to:**</span></span>
- [<span data-ttu-id="4f3c0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4f3c0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4f3c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f3c0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="4f3c0-108">如果您是系統管理員，您現在可以主控防火牆報表來[Microsoft 365 的安全性中心](https://security.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="4f3c0-109">這項功能可讓您從集中位置查看 Windows 10 和 Windows 伺服器2019防火牆報告。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4f3c0-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="4f3c0-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="4f3c0-111">您必須執行 Windows 10 或 Windows 伺服器2019。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="4f3c0-112">若要將板載裝置加入至 Microsoft Defender for Endpoint service，請參閱 [此處](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="4f3c0-113">為了讓 Microsoft 365 的安全性中心開始接收資料，您必須針對具有高級安全性的 Windows Defender 防火牆啟用 **審核事件**。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="4f3c0-114">審核篩選平臺封包丟棄</span><span class="sxs-lookup"><span data-stu-id="4f3c0-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="4f3c0-115">審核篩選平臺連接</span><span class="sxs-lookup"><span data-stu-id="4f3c0-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="4f3c0-116">使用群組原則物件編輯器、本機安全性原則或 auditpol.exe 命令來啟用這些事件。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="4f3c0-117">如需詳細資訊，請參閱 [這裡](/windows/win32/fwp/auditing-and-logging)。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="4f3c0-118">這兩個 PowerShell 命令為：</span><span class="sxs-lookup"><span data-stu-id="4f3c0-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="4f3c0-119">**auditpol/set/subcategory： "篩選平臺封包 Drop"/failure： enable**</span><span class="sxs-lookup"><span data-stu-id="4f3c0-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="4f3c0-120">**auditpol/set/subcategory： "a 篩選平臺 Connection"/failure： enable**</span><span class="sxs-lookup"><span data-stu-id="4f3c0-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="4f3c0-121">處理常式</span><span class="sxs-lookup"><span data-stu-id="4f3c0-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="4f3c0-122">請務必遵循上述區段中的指示，並正確設定您的裝置，以進行早期預覽參與。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="4f3c0-123">啟用事件後，Microsoft 365 的安全性中心會開始監控資料。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="4f3c0-124">遠端 IP、遠端埠、本機埠、本機 IP、電腦名稱稱、跨輸入和輸出連線的處理常式。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="4f3c0-125">管理員現在可以[在這裡](https://security.microsoft.com/firewall)看到 Windows 主機防火牆活動。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="4f3c0-126">透過下載[自訂報表腳本](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)，以利用 Power BI 監視 Windows Defender 防火牆活動，可加速其他報告。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="4f3c0-127">在反映資料之前，可能需要長達12小時。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="4f3c0-128">支援的案例</span><span class="sxs-lookup"><span data-stu-id="4f3c0-128">Supported scenarios</span></span>
<span data-ttu-id="4f3c0-129">Ring0 預覽期間支援下列案例。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="4f3c0-130">安全中心的防火牆報告</span><span class="sxs-lookup"><span data-stu-id="4f3c0-130">Firewall reporting in security center</span></span>

<span data-ttu-id="4f3c0-131">以下是幾個防火牆報告頁面的範例。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="4f3c0-132">您可以在這裡找到輸入、輸出和應用程式活動的摘要。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="4f3c0-133">您可以前往直接存取此頁面 https://security.microsoft.com/firewall 。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f3c0-134">![主機防火牆報告頁面](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="4f3c0-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="4f3c0-135">您也可以移至 **報告**  >  **安全性報告**  >  **裝置** (區段) 位於 **防火牆封鎖的輸入** 連線卡的底部，即可存取這些報告。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="4f3c0-136">從「已封鎖連線的電腦」到裝置</span><span class="sxs-lookup"><span data-stu-id="4f3c0-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="4f3c0-137">卡片支援互動式物件。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-137">Cards support interactive objects.</span></span> <span data-ttu-id="4f3c0-138">您可以按一下裝置名稱（會在新索引標籤 https://securitycenter.microsoft.com 中啟動）並直接前往 [ **裝置時程表** ] 索引標籤，以深入查看裝置的活動。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f3c0-139">![具有封鎖連線的電腦](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="4f3c0-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="4f3c0-140">您現在可以選取 [ **時程表** ] 索引標籤，它會提供與該裝置相關聯的事件清單。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="4f3c0-141">在查看窗格右上角的 [ **篩選** ] 按鈕上按一下滑鼠右鍵，選取您要的事件種類。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="4f3c0-142">在此情況下，請選取 **防火牆事件** ，並將窗格篩選為防火牆事件。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f3c0-143">![篩選按鈕](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="4f3c0-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="4f3c0-144">深入搜尋高級搜尋 (預覽重新整理) </span><span class="sxs-lookup"><span data-stu-id="4f3c0-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="4f3c0-145">防火牆報告會透過按一下 [**開啟高級搜尋**] 按鈕，直接從卡片鑽孔到 **高級搜尋**。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="4f3c0-146">將預先填入查詢。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f3c0-147">![開啟 [高級搜尋] 按鈕](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="4f3c0-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="4f3c0-148">現在可以執行查詢，並可探索過去30天內所有相關的防火牆事件。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="4f3c0-149">如需其他報告或自訂變更，可將查詢匯出至 Power BI 以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="4f3c0-150">您可以透過下載[自訂報表腳本](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)，使用 Power BI 監視 Windows Defender 防火牆活動，以加速自訂報告。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 