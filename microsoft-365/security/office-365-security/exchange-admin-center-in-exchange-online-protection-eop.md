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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: 深入瞭解獨立 Exchange Online Protection (EOP) 中的 web 管理介面。
ms.openlocfilehash: d5753f687461a5495c2431db687263d7211bcbf5
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652906"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="3c937-103">獨立版 EOP 中的 Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="3c937-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="3c937-104">Exchange 系統管理中心 (EAC) 是以 web 為基礎的管理主控台，供獨立 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="3c937-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="3c937-105">在尋找本主題的 Exchange Online 版本嗎？</span><span class="sxs-lookup"><span data-stu-id="3c937-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="3c937-106">請參閱[Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="3c937-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="3c937-107">開啟 EOP 中的 EAC</span><span class="sxs-lookup"><span data-stu-id="3c937-107">Open the EAC in EOP</span></span>

<span data-ttu-id="3c937-108">獨立 EOP 客戶可以使用下列方法存取 EAC：</span><span class="sxs-lookup"><span data-stu-id="3c937-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="3c937-109">**從 Microsoft 365 系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="3c937-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="3c937-110">移至 <https://admin.microsoft.com> 並按一下 [**全部顯示**]。</span><span class="sxs-lookup"><span data-stu-id="3c937-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![按一下 Microsoft 365 系統管理中心內的 [全部顯示]](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="3c937-112">在出現的 [系統**管理中心**] 區段中，按一下 [**所有系統管理中心**]。</span><span class="sxs-lookup"><span data-stu-id="3c937-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![按一下 [Microsoft 365 系統管理中心] 中的 [所有系統管理中心]。](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="3c937-114">在出現的 [**所有系統管理中心**] 頁面上，按一下 [ **Exchange Online Protection**]。</span><span class="sxs-lookup"><span data-stu-id="3c937-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="3c937-115">直接移至 `https://admin.protection.outlook.com/ecp/` 。</span><span class="sxs-lookup"><span data-stu-id="3c937-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="3c937-116">EOP 中 EAC 中的一般使用者介面元素</span><span class="sxs-lookup"><span data-stu-id="3c937-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="3c937-117">本節說明 EMC 中的使用者介面元素。</span><span class="sxs-lookup"><span data-stu-id="3c937-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="3c937-119">功能窗格</span><span class="sxs-lookup"><span data-stu-id="3c937-119">Feature Pane</span></span>

<span data-ttu-id="3c937-p102">這是您在 EAC 中執行大部分工作時的第一個導覽層級。功能窗格依功能區域組織。</span><span class="sxs-lookup"><span data-stu-id="3c937-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="3c937-122">收件**者：這**是您用來查看群組和外部連絡人的所在位置。</span><span class="sxs-lookup"><span data-stu-id="3c937-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="3c937-123">**許可權**：這是您管理系統管理員角色的位置。</span><span class="sxs-lookup"><span data-stu-id="3c937-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="3c937-124">**規範管理**：這是您可以找到系統管理員角色群組報告和系統管理員審核記錄報告的所在位置。</span><span class="sxs-lookup"><span data-stu-id="3c937-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="3c937-125">**保護**：這是您可以管理反惡意程式碼原則、預設連線篩選原則及 DKIM 的所在位置。</span><span class="sxs-lookup"><span data-stu-id="3c937-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3c937-126">您應在安全性 & 規範中心管理反惡意程式碼原則和預設連線篩選原則。</span><span class="sxs-lookup"><span data-stu-id="3c937-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="3c937-127">如需詳細資訊，請參閱在[EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)及[設定 EOP 中的連線篩選](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="3c937-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="3c937-128">**郵件流程**：這是您管理郵件流程規則 (的所在位置，也稱為傳輸規則) 、公認的網域和連接器，以及您可以前往執行郵件追蹤的位置。</span><span class="sxs-lookup"><span data-stu-id="3c937-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="3c937-129">**混合**式：這是您可以執行[混合](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)式設定向導的所在位置，以及您可以在其中安裝[Exchange Online PowerShell 模組](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)的位置。</span><span class="sxs-lookup"><span data-stu-id="3c937-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="3c937-130">索引標籤</span><span class="sxs-lookup"><span data-stu-id="3c937-130">Tabs</span></span>

<span data-ttu-id="3c937-131">索引標籤是您的第二個導覽層級。</span><span class="sxs-lookup"><span data-stu-id="3c937-131">The tabs are your second level of navigation.</span></span> <span data-ttu-id="3c937-132">每一個功能區都包含不同的索引標籤，各自代表一項功能。</span><span class="sxs-lookup"><span data-stu-id="3c937-132">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="3c937-133">工具列</span><span class="sxs-lookup"><span data-stu-id="3c937-133">Toolbar</span></span>

<span data-ttu-id="3c937-p105">按一下大部分的索引標籤時，會看到一個工具列。工具列上的圖示會執行特定動作。下表描述圖示及其動作。</span><span class="sxs-lookup"><span data-stu-id="3c937-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="3c937-137">圖示</span><span class="sxs-lookup"><span data-stu-id="3c937-137">Icon</span></span>|<span data-ttu-id="3c937-138">名稱</span><span class="sxs-lookup"><span data-stu-id="3c937-138">Name</span></span>|<span data-ttu-id="3c937-139">動作</span><span class="sxs-lookup"><span data-stu-id="3c937-139">Action</span></span>|
|---|---|---|
|![新增圖示](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="3c937-141">新增</span><span class="sxs-lookup"><span data-stu-id="3c937-141">Add, New</span></span>|<span data-ttu-id="3c937-p106">使用此圖示來建立新的物件。這些圖示中有些擁有一個關聯的向下箭號，您可以按一下以顯示所能建立的其他物件。</span><span class="sxs-lookup"><span data-stu-id="3c937-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![編輯圖示](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="3c937-145">編輯</span><span class="sxs-lookup"><span data-stu-id="3c937-145">Edit</span></span>|<span data-ttu-id="3c937-146">使用此圖示來編輯物件。</span><span class="sxs-lookup"><span data-stu-id="3c937-146">Use this icon to edit an object.</span></span>|
|![刪除圖示](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="3c937-148">刪除</span><span class="sxs-lookup"><span data-stu-id="3c937-148">Delete</span></span>|<span data-ttu-id="3c937-p107">使用此圖示來刪除物件。部分刪除圖示擁有一個向下箭號，您可以按一下以顯示額外選項。</span><span class="sxs-lookup"><span data-stu-id="3c937-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![搜尋圖示](../../media/ITPro-EAC-.gif)|<span data-ttu-id="3c937-152">搜尋</span><span class="sxs-lookup"><span data-stu-id="3c937-152">Search</span></span>|<span data-ttu-id="3c937-153">使用此圖示來開啟搜尋方塊，您可在此處輸入想要尋找之物件的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="3c937-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![重新整理圖示](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="3c937-155">重新整理</span><span class="sxs-lookup"><span data-stu-id="3c937-155">Refresh</span></span>|<span data-ttu-id="3c937-156">使用此圖示來重新整理清單檢視。</span><span class="sxs-lookup"><span data-stu-id="3c937-156">Use this icon to refresh the list view.</span></span>|
|![[更多選項] 圖示](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="3c937-158">更多選項</span><span class="sxs-lookup"><span data-stu-id="3c937-158">More options</span></span>|<span data-ttu-id="3c937-p108">使用此圖示來檢視更多可對該索引標籤之物件執行的動作。例如，在 **[收件者 \> 使用者]** 中按一下此圖示會顯示可執行 **[進階搜尋]** 的選項。  </span><span class="sxs-lookup"><span data-stu-id="3c937-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.gif)![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="3c937-163">向上鍵和向下鍵</span><span class="sxs-lookup"><span data-stu-id="3c937-163">Up arrow and down arrow</span></span>|<span data-ttu-id="3c937-164">使用這些圖示向上或向下移動物件的優先順序。</span><span class="sxs-lookup"><span data-stu-id="3c937-164">Use these icons to move an object's priority up or down.</span></span>|
|![[移除] 圖示](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="3c937-166">移除</span><span class="sxs-lookup"><span data-stu-id="3c937-166">Remove</span></span>|<span data-ttu-id="3c937-167">使用此圖示來移除清單中的物件。</span><span class="sxs-lookup"><span data-stu-id="3c937-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="3c937-168">清單檢視</span><span class="sxs-lookup"><span data-stu-id="3c937-168">List View</span></span>

<span data-ttu-id="3c937-p109">當您選取索引標籤時，大部分情況下會看見清單檢視。EAC 清單檢視內可檢視的限制約為 10,000 個物件。此外，也包括分頁功能，所以你可以將結果分頁顯示。</span><span class="sxs-lookup"><span data-stu-id="3c937-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="3c937-172">詳細資料窗格</span><span class="sxs-lookup"><span data-stu-id="3c937-172">Details Pane</span></span>

<span data-ttu-id="3c937-p110">當您從清單檢視中選取物件時，該物件的相關資訊就會顯示在詳細資料窗格中。在部分情況下，詳細資料窗格包括管理工作。</span><span class="sxs-lookup"><span data-stu-id="3c937-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="3c937-175">個人資訊動態磚與說明</span><span class="sxs-lookup"><span data-stu-id="3c937-175">Me tile and Help</span></span>

<span data-ttu-id="3c937-p111">**[自有磚]** 可讓您登出 EAC，然後以不同使用者的身分登入。您可以從 **[說明]**![說明圖示](../../media/ITPro-EAC-HelpIcon.gif) 下拉式功能表執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3c937-p111">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="3c937-178">**說明：** 按一下 [說明圖示]![](../../media/ITPro-EAC-HelpIcon.gif) 即可檢視線上說明內容。</span><span class="sxs-lookup"><span data-stu-id="3c937-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="3c937-179">**意見**反應：留下意見反應。</span><span class="sxs-lookup"><span data-stu-id="3c937-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="3c937-180">**社區**：在社區論壇中張貼尋找答案的問題。</span><span class="sxs-lookup"><span data-stu-id="3c937-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="3c937-181">**停用說明泡泡圖**：[說明泡泡圖] 會在您建立或編輯物件時，顯示欄位的內容說明。</span><span class="sxs-lookup"><span data-stu-id="3c937-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="3c937-182">您可以關閉 [說明泡泡圖]，或是在停用的狀態下將它開啟。</span><span class="sxs-lookup"><span data-stu-id="3c937-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="3c937-183">**顯示命令記錄**：會開啟新的視窗，顯示根據 EAC 中設定之專案的對等 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="3c937-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="3c937-184">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="3c937-184">Supported Browsers</span></span>

<span data-ttu-id="3c937-185">為享有 EAC 最佳使用體驗，建議您一律使用最新的瀏覽器、Office 用戶端和應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c937-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="3c937-186">我們也建議您隨時安裝最新的軟體更新。</span><span class="sxs-lookup"><span data-stu-id="3c937-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="3c937-187">如需此服務支援的瀏覽器和系統需求的詳細資訊，請參閱 [Office 的系統需求](https://products.office.com/office-system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="3c937-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="3c937-188">支援的語言</span><span class="sxs-lookup"><span data-stu-id="3c937-188">Supported languages</span></span>

<span data-ttu-id="3c937-189">在獨立 EOP 中，EAC 支援和使用下列語言。</span><span class="sxs-lookup"><span data-stu-id="3c937-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="3c937-190">阿姆哈拉文</span><span class="sxs-lookup"><span data-stu-id="3c937-190">Amharic</span></span>
- <span data-ttu-id="3c937-191">阿拉伯文</span><span class="sxs-lookup"><span data-stu-id="3c937-191">Arabic</span></span>
- <span data-ttu-id="3c937-192">巴斯克文 (巴斯克文)</span><span class="sxs-lookup"><span data-stu-id="3c937-192">Basque (Basque)</span></span>
- <span data-ttu-id="3c937-193">孟加拉文 (印度)</span><span class="sxs-lookup"><span data-stu-id="3c937-193">Bengali (India)</span></span>
- <span data-ttu-id="3c937-194">保加利亞文</span><span class="sxs-lookup"><span data-stu-id="3c937-194">Bulgarian</span></span>
- <span data-ttu-id="3c937-195">卡達隆尼亞文</span><span class="sxs-lookup"><span data-stu-id="3c937-195">Catalan</span></span>
- <span data-ttu-id="3c937-196">簡體中文</span><span class="sxs-lookup"><span data-stu-id="3c937-196">Chinese (Simplified)</span></span>
- <span data-ttu-id="3c937-197">繁體中文</span><span class="sxs-lookup"><span data-stu-id="3c937-197">Chinese (Traditional)</span></span>
- <span data-ttu-id="3c937-198">克羅埃西亞文</span><span class="sxs-lookup"><span data-stu-id="3c937-198">Croatian</span></span>
- <span data-ttu-id="3c937-199">捷克文</span><span class="sxs-lookup"><span data-stu-id="3c937-199">Czech</span></span>
- <span data-ttu-id="3c937-200">丹麥文</span><span class="sxs-lookup"><span data-stu-id="3c937-200">Danish</span></span>
- <span data-ttu-id="3c937-201">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="3c937-201">Dutch</span></span>
- <span data-ttu-id="3c937-202">英文</span><span class="sxs-lookup"><span data-stu-id="3c937-202">English</span></span>
- <span data-ttu-id="3c937-203">愛沙尼亞文</span><span class="sxs-lookup"><span data-stu-id="3c937-203">Estonian</span></span>
- <span data-ttu-id="3c937-204">菲律賓文 (菲律賓)</span><span class="sxs-lookup"><span data-stu-id="3c937-204">Filipino (Philippines)</span></span>
- <span data-ttu-id="3c937-205">芬蘭文</span><span class="sxs-lookup"><span data-stu-id="3c937-205">Finnish</span></span>
- <span data-ttu-id="3c937-206">法文</span><span class="sxs-lookup"><span data-stu-id="3c937-206">French</span></span>
- <span data-ttu-id="3c937-207">加里斯亞文</span><span class="sxs-lookup"><span data-stu-id="3c937-207">Galician</span></span>
- <span data-ttu-id="3c937-208">德文</span><span class="sxs-lookup"><span data-stu-id="3c937-208">German</span></span>
- <span data-ttu-id="3c937-209">希臘文</span><span class="sxs-lookup"><span data-stu-id="3c937-209">Greek</span></span>
- <span data-ttu-id="3c937-210">古吉拉特文</span><span class="sxs-lookup"><span data-stu-id="3c937-210">Gujarati</span></span>
- <span data-ttu-id="3c937-211">希伯來文</span><span class="sxs-lookup"><span data-stu-id="3c937-211">Hebrew</span></span>
- <span data-ttu-id="3c937-212">印度文</span><span class="sxs-lookup"><span data-stu-id="3c937-212">Hindi</span></span>
- <span data-ttu-id="3c937-213">匈牙利文</span><span class="sxs-lookup"><span data-stu-id="3c937-213">Hungarian</span></span>
- <span data-ttu-id="3c937-214">冰島文</span><span class="sxs-lookup"><span data-stu-id="3c937-214">Icelandic</span></span>
- <span data-ttu-id="3c937-215">印尼文</span><span class="sxs-lookup"><span data-stu-id="3c937-215">Indonesian</span></span>
- <span data-ttu-id="3c937-216">義大利文</span><span class="sxs-lookup"><span data-stu-id="3c937-216">Italian</span></span>
- <span data-ttu-id="3c937-217">日文</span><span class="sxs-lookup"><span data-stu-id="3c937-217">Japanese</span></span>
- <span data-ttu-id="3c937-218">坎那達文</span><span class="sxs-lookup"><span data-stu-id="3c937-218">Kannada</span></span>
- <span data-ttu-id="3c937-219">哈薩克文</span><span class="sxs-lookup"><span data-stu-id="3c937-219">Kazakh</span></span>
- <span data-ttu-id="3c937-220">史瓦希里文</span><span class="sxs-lookup"><span data-stu-id="3c937-220">Kiswahili</span></span>
- <span data-ttu-id="3c937-221">韓文</span><span class="sxs-lookup"><span data-stu-id="3c937-221">Korean</span></span>
- <span data-ttu-id="3c937-222">拉脫維亞文</span><span class="sxs-lookup"><span data-stu-id="3c937-222">Latvian</span></span>
- <span data-ttu-id="3c937-223">立陶宛文</span><span class="sxs-lookup"><span data-stu-id="3c937-223">Lithuanian</span></span>
- <span data-ttu-id="3c937-224">馬來文 (汶萊)</span><span class="sxs-lookup"><span data-stu-id="3c937-224">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="3c937-225">馬來文 (馬來西亞)</span><span class="sxs-lookup"><span data-stu-id="3c937-225">Malay (Malaysia)</span></span>
- <span data-ttu-id="3c937-226">馬來亞拉姆文</span><span class="sxs-lookup"><span data-stu-id="3c937-226">Malayalam</span></span>
- <span data-ttu-id="3c937-227">馬拉提文</span><span class="sxs-lookup"><span data-stu-id="3c937-227">Marathi</span></span>
- <span data-ttu-id="3c937-228">挪威文 (巴克摩)</span><span class="sxs-lookup"><span data-stu-id="3c937-228">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="3c937-229">挪威文 (尼洛斯克)</span><span class="sxs-lookup"><span data-stu-id="3c937-229">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="3c937-230">歐利亞文</span><span class="sxs-lookup"><span data-stu-id="3c937-230">Oriya</span></span>
- <span data-ttu-id="3c937-231">波斯文</span><span class="sxs-lookup"><span data-stu-id="3c937-231">Persian</span></span>
- <span data-ttu-id="3c937-232">波蘭文</span><span class="sxs-lookup"><span data-stu-id="3c937-232">Polish</span></span>
- <span data-ttu-id="3c937-233">葡萄牙文 (巴西)</span><span class="sxs-lookup"><span data-stu-id="3c937-233">Portuguese (Brazil)</span></span>
- <span data-ttu-id="3c937-234">葡萄牙文 (葡萄牙)</span><span class="sxs-lookup"><span data-stu-id="3c937-234">Portuguese (Portugal)</span></span>
- <span data-ttu-id="3c937-235">羅馬尼亞文</span><span class="sxs-lookup"><span data-stu-id="3c937-235">Romanian</span></span>
- <span data-ttu-id="3c937-236">俄文</span><span class="sxs-lookup"><span data-stu-id="3c937-236">Russian</span></span>
- <span data-ttu-id="3c937-237">塞爾維亞文 (斯拉夫、塞爾維亞)</span><span class="sxs-lookup"><span data-stu-id="3c937-237">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="3c937-238">塞爾維亞文 (拉丁)</span><span class="sxs-lookup"><span data-stu-id="3c937-238">Serbian (Latin)</span></span>
- <span data-ttu-id="3c937-239">斯洛伐克文</span><span class="sxs-lookup"><span data-stu-id="3c937-239">Slovak</span></span>
- <span data-ttu-id="3c937-240">斯洛維尼亞文</span><span class="sxs-lookup"><span data-stu-id="3c937-240">Slovenian</span></span>
- <span data-ttu-id="3c937-241">西班牙文</span><span class="sxs-lookup"><span data-stu-id="3c937-241">Spanish</span></span>
- <span data-ttu-id="3c937-242">瑞典文</span><span class="sxs-lookup"><span data-stu-id="3c937-242">Swedish</span></span>
- <span data-ttu-id="3c937-243">坦米爾文</span><span class="sxs-lookup"><span data-stu-id="3c937-243">Tamil</span></span>
- <span data-ttu-id="3c937-244">特拉古文</span><span class="sxs-lookup"><span data-stu-id="3c937-244">Telugu</span></span>
- <span data-ttu-id="3c937-245">泰文</span><span class="sxs-lookup"><span data-stu-id="3c937-245">Thai</span></span>
- <span data-ttu-id="3c937-246">土耳其文</span><span class="sxs-lookup"><span data-stu-id="3c937-246">Turkish</span></span>
- <span data-ttu-id="3c937-247">烏克蘭文</span><span class="sxs-lookup"><span data-stu-id="3c937-247">Ukrainian</span></span>
- <span data-ttu-id="3c937-248">烏都文</span><span class="sxs-lookup"><span data-stu-id="3c937-248">Urdu</span></span>
- <span data-ttu-id="3c937-249">越南文</span><span class="sxs-lookup"><span data-stu-id="3c937-249">Vietnamese</span></span>
- <span data-ttu-id="3c937-250">威爾斯文</span><span class="sxs-lookup"><span data-stu-id="3c937-250">Welsh</span></span>
