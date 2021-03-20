---
title: 獨立版 EOP 中的 Exchange 系統管理中心
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: 深入瞭解獨立 Exchange Online Protection (EOP) 中的 web 管理介面。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab834d14673370a39e148aefa568591ff4c50b8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916991"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="488bb-103">獨立版 EOP 中的 Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="488bb-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="488bb-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="488bb-104">**Applies to**</span></span>
-  [<span data-ttu-id="488bb-105">Exchange Online Protection 獨立</span><span class="sxs-lookup"><span data-stu-id="488bb-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="488bb-106">Exchange 系統管理中心 (EAC) 是以 web 為基礎的管理主控台，供獨立 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="488bb-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="488bb-107">在尋找本主題的 Exchange Online 版本嗎？</span><span class="sxs-lookup"><span data-stu-id="488bb-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="488bb-108">請參閱[Exchange admin center in Exchange Online](/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="488bb-108">See [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="488bb-109">開啟 EOP 中的 EAC</span><span class="sxs-lookup"><span data-stu-id="488bb-109">Open the EAC in EOP</span></span>

<span data-ttu-id="488bb-110">獨立 EOP 客戶可以使用下列方法存取 EAC：</span><span class="sxs-lookup"><span data-stu-id="488bb-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="488bb-111">**從 Microsoft 365 系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="488bb-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="488bb-112">移至 <https://admin.microsoft.com> 並按一下 [ **全部顯示**]。</span><span class="sxs-lookup"><span data-stu-id="488bb-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![按一下 Microsoft 365 系統管理中心內的 [全部顯示]](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="488bb-114">在出現的 [系統 **管理中心** ] 區段中，按一下 [ **所有系統管理中心**]。</span><span class="sxs-lookup"><span data-stu-id="488bb-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![按一下 [Microsoft 365 系統管理中心] 中的 [所有系統管理中心]。](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="488bb-116">在出現的 [ **所有系統管理中心** ] 頁面上，按一下 [ **Exchange Online Protection**]。</span><span class="sxs-lookup"><span data-stu-id="488bb-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="488bb-117">直接移至 `https://admin.protection.outlook.com/ecp/` 。</span><span class="sxs-lookup"><span data-stu-id="488bb-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="488bb-118">EOP 中 EAC 中的一般使用者介面元素</span><span class="sxs-lookup"><span data-stu-id="488bb-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="488bb-119">本節說明 EMC 中的使用者介面元素。</span><span class="sxs-lookup"><span data-stu-id="488bb-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Exchange Online Protection 中的 Exchange 系統管理中心](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="488bb-121">功能窗格</span><span class="sxs-lookup"><span data-stu-id="488bb-121">Feature Pane</span></span>

<span data-ttu-id="488bb-p102">這是您在 EAC 中執行大部分工作時的第一個導覽層級。功能窗格依功能區域組織。</span><span class="sxs-lookup"><span data-stu-id="488bb-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="488bb-124">收件 **者：這** 是您用來查看群組和外部連絡人的所在位置。</span><span class="sxs-lookup"><span data-stu-id="488bb-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="488bb-125">**許可權**：這是您管理系統管理員角色的位置。</span><span class="sxs-lookup"><span data-stu-id="488bb-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="488bb-126">**規範管理**：這是您可以找到系統管理員角色群組報告和系統管理員審核記錄報告的所在位置。</span><span class="sxs-lookup"><span data-stu-id="488bb-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="488bb-127">**保護**：這是您可以管理反惡意程式碼原則、預設連線篩選原則及 DKIM 的所在位置。</span><span class="sxs-lookup"><span data-stu-id="488bb-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="488bb-128">您應在安全性 & 規範中心管理反惡意程式碼原則和預設連線篩選原則。</span><span class="sxs-lookup"><span data-stu-id="488bb-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="488bb-129">如需詳細資訊，請參閱在 [EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md) 及 [設定 EOP 中的連線篩選](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="488bb-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="488bb-130">**郵件流程**：這是您管理郵件流程規則 (的所在位置，也稱為傳輸規則) 、公認的網域和連接器，以及您可以前往執行郵件追蹤的位置。</span><span class="sxs-lookup"><span data-stu-id="488bb-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="488bb-131">**混合** 式：這是您可以執行 [混合](/Exchange/hybrid-configuration-wizard)式設定向導的所在位置，以及您可以在其中安裝 [Exchange Online PowerShell 模組](/powershell/exchange/mfa-connect-to-exchange-online-powershell)的位置。</span><span class="sxs-lookup"><span data-stu-id="488bb-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="488bb-132">索引標籤</span><span class="sxs-lookup"><span data-stu-id="488bb-132">Tabs</span></span>

<span data-ttu-id="488bb-133">索引標籤是您的第二個導覽層級。</span><span class="sxs-lookup"><span data-stu-id="488bb-133">The tabs are your second level of navigation.</span></span> <span data-ttu-id="488bb-134">每一個功能區都包含不同的索引標籤，各自代表一項功能。</span><span class="sxs-lookup"><span data-stu-id="488bb-134">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="488bb-135">工具列</span><span class="sxs-lookup"><span data-stu-id="488bb-135">Toolbar</span></span>

<span data-ttu-id="488bb-p105">按一下大部分的索引標籤時，會看到一個工具列。工具列上的圖示會執行特定動作。下表描述圖示及其動作。</span><span class="sxs-lookup"><span data-stu-id="488bb-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="488bb-139">圖示</span><span class="sxs-lookup"><span data-stu-id="488bb-139">Icon</span></span>|<span data-ttu-id="488bb-140">名稱</span><span class="sxs-lookup"><span data-stu-id="488bb-140">Name</span></span>|<span data-ttu-id="488bb-141">動作</span><span class="sxs-lookup"><span data-stu-id="488bb-141">Action</span></span>|
|---|---|---|
|![新增圖示](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="488bb-143">新增</span><span class="sxs-lookup"><span data-stu-id="488bb-143">Add, New</span></span>|<span data-ttu-id="488bb-p106">使用此圖示來建立新的物件。這些圖示中有些擁有一個關聯的向下箭號，您可以按一下以顯示所能建立的其他物件。</span><span class="sxs-lookup"><span data-stu-id="488bb-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![編輯圖示](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="488bb-147">編輯</span><span class="sxs-lookup"><span data-stu-id="488bb-147">Edit</span></span>|<span data-ttu-id="488bb-148">使用此圖示來編輯物件。</span><span class="sxs-lookup"><span data-stu-id="488bb-148">Use this icon to edit an object.</span></span>|
|![刪除圖示](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="488bb-150">刪除</span><span class="sxs-lookup"><span data-stu-id="488bb-150">Delete</span></span>|<span data-ttu-id="488bb-p107">使用此圖示來刪除物件。部分刪除圖示擁有一個向下箭號，您可以按一下以顯示額外選項。</span><span class="sxs-lookup"><span data-stu-id="488bb-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![搜尋圖示](../../media/ITPro-EAC-.gif)|<span data-ttu-id="488bb-154">搜尋</span><span class="sxs-lookup"><span data-stu-id="488bb-154">Search</span></span>|<span data-ttu-id="488bb-155">使用此圖示來開啟搜尋方塊，您可在此處輸入想要尋找之物件的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="488bb-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![重新整理圖示](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="488bb-157">重新整理</span><span class="sxs-lookup"><span data-stu-id="488bb-157">Refresh</span></span>|<span data-ttu-id="488bb-158">使用此圖示來重新整理清單檢視。</span><span class="sxs-lookup"><span data-stu-id="488bb-158">Use this icon to refresh the list view.</span></span>|
|![[更多選項] 圖示](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="488bb-160">更多選項</span><span class="sxs-lookup"><span data-stu-id="488bb-160">More options</span></span>|<span data-ttu-id="488bb-p108">使用此圖示來檢視更多可對該索引標籤之物件執行的動作。例如，在 **[收件者 \> 使用者]** 中按一下此圖示會顯示可執行 **[進階搜尋]** 的選項。  </span><span class="sxs-lookup"><span data-stu-id="488bb-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.gif)![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="488bb-165">向上鍵和向下鍵</span><span class="sxs-lookup"><span data-stu-id="488bb-165">Up arrow and down arrow</span></span>|<span data-ttu-id="488bb-166">使用這些圖示向上或向下移動物件的優先順序。</span><span class="sxs-lookup"><span data-stu-id="488bb-166">Use these icons to move an object's priority up or down.</span></span>|
|![[移除] 圖示](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="488bb-168">移除</span><span class="sxs-lookup"><span data-stu-id="488bb-168">Remove</span></span>|<span data-ttu-id="488bb-169">使用此圖示來移除清單中的物件。</span><span class="sxs-lookup"><span data-stu-id="488bb-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="488bb-170">清單檢視</span><span class="sxs-lookup"><span data-stu-id="488bb-170">List View</span></span>

<span data-ttu-id="488bb-p109">當您選取索引標籤時，大部分情況下會看見清單檢視。EAC 清單檢視內可檢視的限制約為 10,000 個物件。此外，也包括分頁功能，所以你可以將結果分頁顯示。</span><span class="sxs-lookup"><span data-stu-id="488bb-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="488bb-174">詳細資料窗格</span><span class="sxs-lookup"><span data-stu-id="488bb-174">Details Pane</span></span>

<span data-ttu-id="488bb-p110">當您從清單檢視中選取物件時，該物件的相關資訊就會顯示在詳細資料窗格中。在部分情況下，詳細資料窗格包括管理工作。</span><span class="sxs-lookup"><span data-stu-id="488bb-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="488bb-177">個人資訊動態磚與說明</span><span class="sxs-lookup"><span data-stu-id="488bb-177">Me tile and Help</span></span>

<span data-ttu-id="488bb-178">**[自有磚]** 可讓您登出 EAC，然後以不同使用者的身分登入。</span><span class="sxs-lookup"><span data-stu-id="488bb-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="488bb-179">您可以從 [**説明**] 的 [說明] ![ 圖示 ](../../media/ITPro-EAC-HelpIcon.gif) 下拉式功能表中執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="488bb-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="488bb-180">**說明：** 按一下 [說明圖示]![](../../media/ITPro-EAC-HelpIcon.gif) 即可檢視線上說明內容。</span><span class="sxs-lookup"><span data-stu-id="488bb-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="488bb-181">**意見** 反應：留下意見反應。</span><span class="sxs-lookup"><span data-stu-id="488bb-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="488bb-182">**社區**：在社區論壇中張貼尋找答案的問題。</span><span class="sxs-lookup"><span data-stu-id="488bb-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="488bb-183">**停用說明泡泡圖**：[說明泡泡圖] 會在您建立或編輯物件時，顯示欄位的內容說明。</span><span class="sxs-lookup"><span data-stu-id="488bb-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="488bb-184">您可以關閉 [說明泡泡圖]，或是在停用的狀態下將它開啟。</span><span class="sxs-lookup"><span data-stu-id="488bb-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="488bb-185">**顯示命令記錄**：會開啟新的視窗，顯示根據 EAC 中設定之專案的對等 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="488bb-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="488bb-186">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="488bb-186">Supported Browsers</span></span>

<span data-ttu-id="488bb-187">為享有 EAC 最佳使用體驗，建議您一律使用最新的瀏覽器、Office 用戶端和應用程式。</span><span class="sxs-lookup"><span data-stu-id="488bb-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="488bb-188">我們也建議您隨時安裝最新的軟體更新。</span><span class="sxs-lookup"><span data-stu-id="488bb-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="488bb-189">如需此服務支援的瀏覽器和系統需求的詳細資訊，請參閱 [Office 的系統需求](https://products.office.com/office-system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="488bb-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="488bb-190">支援的語言</span><span class="sxs-lookup"><span data-stu-id="488bb-190">Supported languages</span></span>

<span data-ttu-id="488bb-191">在獨立 EOP 中，EAC 支援和使用下列語言。</span><span class="sxs-lookup"><span data-stu-id="488bb-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="488bb-192">阿姆哈拉文</span><span class="sxs-lookup"><span data-stu-id="488bb-192">Amharic</span></span>
- <span data-ttu-id="488bb-193">阿拉伯文</span><span class="sxs-lookup"><span data-stu-id="488bb-193">Arabic</span></span>
- <span data-ttu-id="488bb-194">巴斯克文 (巴斯克文)</span><span class="sxs-lookup"><span data-stu-id="488bb-194">Basque (Basque)</span></span>
- <span data-ttu-id="488bb-195">孟加拉文 (印度)</span><span class="sxs-lookup"><span data-stu-id="488bb-195">Bengali (India)</span></span>
- <span data-ttu-id="488bb-196">保加利亞文</span><span class="sxs-lookup"><span data-stu-id="488bb-196">Bulgarian</span></span>
- <span data-ttu-id="488bb-197">卡達隆尼亞文</span><span class="sxs-lookup"><span data-stu-id="488bb-197">Catalan</span></span>
- <span data-ttu-id="488bb-198">簡體中文</span><span class="sxs-lookup"><span data-stu-id="488bb-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="488bb-199">繁體中文</span><span class="sxs-lookup"><span data-stu-id="488bb-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="488bb-200">克羅埃西亞文</span><span class="sxs-lookup"><span data-stu-id="488bb-200">Croatian</span></span>
- <span data-ttu-id="488bb-201">捷克文</span><span class="sxs-lookup"><span data-stu-id="488bb-201">Czech</span></span>
- <span data-ttu-id="488bb-202">丹麥文</span><span class="sxs-lookup"><span data-stu-id="488bb-202">Danish</span></span>
- <span data-ttu-id="488bb-203">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="488bb-203">Dutch</span></span>
- <span data-ttu-id="488bb-204">英文</span><span class="sxs-lookup"><span data-stu-id="488bb-204">English</span></span>
- <span data-ttu-id="488bb-205">愛沙尼亞文</span><span class="sxs-lookup"><span data-stu-id="488bb-205">Estonian</span></span>
- <span data-ttu-id="488bb-206">菲律賓文 (菲律賓)</span><span class="sxs-lookup"><span data-stu-id="488bb-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="488bb-207">芬蘭文</span><span class="sxs-lookup"><span data-stu-id="488bb-207">Finnish</span></span>
- <span data-ttu-id="488bb-208">法文</span><span class="sxs-lookup"><span data-stu-id="488bb-208">French</span></span>
- <span data-ttu-id="488bb-209">加里斯亞文</span><span class="sxs-lookup"><span data-stu-id="488bb-209">Galician</span></span>
- <span data-ttu-id="488bb-210">德文</span><span class="sxs-lookup"><span data-stu-id="488bb-210">German</span></span>
- <span data-ttu-id="488bb-211">希臘文</span><span class="sxs-lookup"><span data-stu-id="488bb-211">Greek</span></span>
- <span data-ttu-id="488bb-212">古吉拉特文</span><span class="sxs-lookup"><span data-stu-id="488bb-212">Gujarati</span></span>
- <span data-ttu-id="488bb-213">希伯來文</span><span class="sxs-lookup"><span data-stu-id="488bb-213">Hebrew</span></span>
- <span data-ttu-id="488bb-214">印度文</span><span class="sxs-lookup"><span data-stu-id="488bb-214">Hindi</span></span>
- <span data-ttu-id="488bb-215">匈牙利文</span><span class="sxs-lookup"><span data-stu-id="488bb-215">Hungarian</span></span>
- <span data-ttu-id="488bb-216">冰島文</span><span class="sxs-lookup"><span data-stu-id="488bb-216">Icelandic</span></span>
- <span data-ttu-id="488bb-217">印尼文</span><span class="sxs-lookup"><span data-stu-id="488bb-217">Indonesian</span></span>
- <span data-ttu-id="488bb-218">義大利文</span><span class="sxs-lookup"><span data-stu-id="488bb-218">Italian</span></span>
- <span data-ttu-id="488bb-219">日文</span><span class="sxs-lookup"><span data-stu-id="488bb-219">Japanese</span></span>
- <span data-ttu-id="488bb-220">坎那達文</span><span class="sxs-lookup"><span data-stu-id="488bb-220">Kannada</span></span>
- <span data-ttu-id="488bb-221">哈薩克文</span><span class="sxs-lookup"><span data-stu-id="488bb-221">Kazakh</span></span>
- <span data-ttu-id="488bb-222">史瓦希里文</span><span class="sxs-lookup"><span data-stu-id="488bb-222">Kiswahili</span></span>
- <span data-ttu-id="488bb-223">韓文</span><span class="sxs-lookup"><span data-stu-id="488bb-223">Korean</span></span>
- <span data-ttu-id="488bb-224">拉脫維亞文</span><span class="sxs-lookup"><span data-stu-id="488bb-224">Latvian</span></span>
- <span data-ttu-id="488bb-225">立陶宛文</span><span class="sxs-lookup"><span data-stu-id="488bb-225">Lithuanian</span></span>
- <span data-ttu-id="488bb-226">馬來文 (汶萊)</span><span class="sxs-lookup"><span data-stu-id="488bb-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="488bb-227">馬來文 (馬來西亞)</span><span class="sxs-lookup"><span data-stu-id="488bb-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="488bb-228">馬來亞拉姆文</span><span class="sxs-lookup"><span data-stu-id="488bb-228">Malayalam</span></span>
- <span data-ttu-id="488bb-229">馬拉提文</span><span class="sxs-lookup"><span data-stu-id="488bb-229">Marathi</span></span>
- <span data-ttu-id="488bb-230">挪威文 (巴克摩)</span><span class="sxs-lookup"><span data-stu-id="488bb-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="488bb-231">挪威文 (尼洛斯克)</span><span class="sxs-lookup"><span data-stu-id="488bb-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="488bb-232">歐利亞文</span><span class="sxs-lookup"><span data-stu-id="488bb-232">Oriya</span></span>
- <span data-ttu-id="488bb-233">波斯文</span><span class="sxs-lookup"><span data-stu-id="488bb-233">Persian</span></span>
- <span data-ttu-id="488bb-234">波蘭文</span><span class="sxs-lookup"><span data-stu-id="488bb-234">Polish</span></span>
- <span data-ttu-id="488bb-235">葡萄牙文 (巴西)</span><span class="sxs-lookup"><span data-stu-id="488bb-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="488bb-236">葡萄牙文 (葡萄牙)</span><span class="sxs-lookup"><span data-stu-id="488bb-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="488bb-237">羅馬尼亞文</span><span class="sxs-lookup"><span data-stu-id="488bb-237">Romanian</span></span>
- <span data-ttu-id="488bb-238">俄文</span><span class="sxs-lookup"><span data-stu-id="488bb-238">Russian</span></span>
- <span data-ttu-id="488bb-239">塞爾維亞文 (斯拉夫、塞爾維亞)</span><span class="sxs-lookup"><span data-stu-id="488bb-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="488bb-240">塞爾維亞文 (拉丁)</span><span class="sxs-lookup"><span data-stu-id="488bb-240">Serbian (Latin)</span></span>
- <span data-ttu-id="488bb-241">斯洛伐克文</span><span class="sxs-lookup"><span data-stu-id="488bb-241">Slovak</span></span>
- <span data-ttu-id="488bb-242">斯洛維尼亞文</span><span class="sxs-lookup"><span data-stu-id="488bb-242">Slovenian</span></span>
- <span data-ttu-id="488bb-243">西班牙文</span><span class="sxs-lookup"><span data-stu-id="488bb-243">Spanish</span></span>
- <span data-ttu-id="488bb-244">瑞典文</span><span class="sxs-lookup"><span data-stu-id="488bb-244">Swedish</span></span>
- <span data-ttu-id="488bb-245">坦米爾文</span><span class="sxs-lookup"><span data-stu-id="488bb-245">Tamil</span></span>
- <span data-ttu-id="488bb-246">特拉古文</span><span class="sxs-lookup"><span data-stu-id="488bb-246">Telugu</span></span>
- <span data-ttu-id="488bb-247">泰文</span><span class="sxs-lookup"><span data-stu-id="488bb-247">Thai</span></span>
- <span data-ttu-id="488bb-248">土耳其文</span><span class="sxs-lookup"><span data-stu-id="488bb-248">Turkish</span></span>
- <span data-ttu-id="488bb-249">烏克蘭文</span><span class="sxs-lookup"><span data-stu-id="488bb-249">Ukrainian</span></span>
- <span data-ttu-id="488bb-250">烏都文</span><span class="sxs-lookup"><span data-stu-id="488bb-250">Urdu</span></span>
- <span data-ttu-id="488bb-251">越南文</span><span class="sxs-lookup"><span data-stu-id="488bb-251">Vietnamese</span></span>
- <span data-ttu-id="488bb-252">威爾斯文</span><span class="sxs-lookup"><span data-stu-id="488bb-252">Welsh</span></span>