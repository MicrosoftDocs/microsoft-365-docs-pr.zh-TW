---
title: 現有裝置的 Windows 10 企業部署為就地升級
description: 設定及部署使用 System Center Configuration Manager 就地升級為 Windows 10 Enterprise 映像提供指導。
keywords: Microsoft 365、 Microsoft 365 企業版、 Microsoft 365 文件、 Windows 10 Enterprise、 部署、 使用就地升級、 Configuration Manager System Center Configuration Manager
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 3df76c0de7b5a8b12c063113c79f9efa4e33b4c1
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866641"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a><span data-ttu-id="bbee1-104">步驟 2： 部署現有裝置的就地升級為 Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbee1-104">Step 2: Deploy Windows 10 Enterprise for existing devices as an in-place upgrade</span></span>

<span data-ttu-id="bbee1-105">*本文適用於 Microsoft 365 企業版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="bbee1-105">*This article applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="bbee1-p101">升級 Pc 目前為 Windows 10 執行 Windows 7 或 Windows 8.1 最簡單的路徑是透過就地升級。您可以使用 System Center Configuration Manager (Configuration Manager) 工作順序完全自動化程序。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p101">The simplest path to upgrade PCs currently running Windows 7 or Windows 8.1 to Windows 10 is through an in-place upgrade. You can use a System Center Configuration Manager (Configuration Manager) task sequence to completely automate the process.</span></span> 

<span data-ttu-id="bbee1-p102">如果您有現有的電腦執行 Windows 7 或 Windows 8.1，建議此路徑如果您的組織已部署 Windows 10。這如何運用 Windows 安裝程式 (Setup.exe) 以執行就地升級，以自動會保留所有的資料、 設定、 應用程式，並從現有的作業系統版本的驅動程式。這需要最少的 IT 努力，因為不需要任何複雜部署基礎結構。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p102">If you have existing computers running Windows 7 or Windows 8.1, we recommend this path if your organization is deploying Windows 10. This leverages the Windows installation program (Setup.exe) to perform an in-place upgrade, which automatically preserves all data, settings, applications, and drivers from the existing operating system version. This requires the least IT effort, because there is no need for any complex deployment infrastructure.</span></span>

<span data-ttu-id="bbee1-111">請遵循下列步驟來設定並部署 Configuration Manager 使用就地升級為 Windows 10 Enterprise 圖像。</span><span class="sxs-lookup"><span data-stu-id="bbee1-111">Follow these steps to configure and deploy a Windows 10 Enterprise image using Configuration Manager as an in-place upgrade.</span></span>

## <a name="part-1-verify-readiness-to-upgrade-windows"></a><span data-ttu-id="bbee1-112">第 1 部分： 準備升級 [Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="bbee1-112">Part 1: Verify readiness to upgrade Windows</span></span>

<span data-ttu-id="bbee1-p103">首先，使用 Windows 分析升級整備功能提供強大的見解與建議電腦、 應用程式以及驅動程式在您的組織在無需額外成本並沒有其他基礎結構需求。此新服務會引導您完成使用 Microsoft 建議的做法為基礎的工作流程的升級與功能的更新專案。最新的庫存資料可讓您以平衡成本與升級專案中的風險。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p103">First, use the Upgrade Readiness capability of Windows Analytics to provide powerful insights and recommendations about the computers, applications, and drivers in your organization, at no extra cost and without additional infrastructure requirements. This new service guides you through upgrade and feature update projects using a workflow based on Microsoft recommended practices. Up-to-date inventory data allows you to balance cost and risk in your upgrade projects.</span></span>

<span data-ttu-id="bbee1-116">請參閱 ＜[管理 Windows 升級以升級整備](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness)深入了解、 快速入門、 使用與疑難排解升級整備。</span><span class="sxs-lookup"><span data-stu-id="bbee1-116">See [Manage Windows upgrades with Upgrade Readiness](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) to learn more, get started, use, and troubleshoot Upgrade Readiness.</span></span>

<span data-ttu-id="bbee1-p104">接下來，遵循指南 （英文） Windows 7 或更新版本的作業系統升級至 Windows 10 使用 System Center Configuration Manager （目前分公司）。就像任何高風險的部署，建議您備份再繼續進行的使用者資料。OneDrive 雲端儲存空間可供使用的授權的 Microsoft 365 使用者及可以用來安全地儲存其檔案。如需詳細資訊，請參閱[OneDrive 快速啟動指南 》](https://aka.ms/ODfBquickstartguide)。若要存取此頁面上，您必須租用戶系統管理員或 Office 365 或 Microsoft 365 租用戶中的全域管理員身分登入。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p104">Next, follow the guide to use System Center Configuration Manager (Current Branch) to upgrade Windows 7 or later operating system to Windows 10. As with any high-risk deployment, we recommend backing up user data before proceeding. OneDrive cloud storage is ready to use for licensed Microsoft 365 users and can be used to securely store their files. For more info, see [OneDrive quick start guide](https://aka.ms/ODfBquickstartguide). To access this page, you must sign in as a tenant admin or global admin in an Office 365 or Microsoft 365 tenant.</span></span>

<span data-ttu-id="bbee1-122">Configuration Manager 版本和支援的相對應 Windows 10 用戶端版本的清單，請參閱[支援的 Windows 10 的 System Center Configuration Manager](https://aka.ms/supportforwin10sccm)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-122">For a list of Configuration Manager versions and the corresponding Windows 10 client versions that are supported, see [Support for Windows 10 for System Center Configuration Manager](https://aka.ms/supportforwin10sccm).</span></span>

<span data-ttu-id="bbee1-123">**若要確認升級 Windows 整備**</span><span class="sxs-lookup"><span data-stu-id="bbee1-123">**To verify readiness to upgrade Windows**</span></span>

<span data-ttu-id="bbee1-124">啟動 Windows 10 部署前檢閱這些需求：</span><span class="sxs-lookup"><span data-stu-id="bbee1-124">Review these requirements before starting your Windows 10 deployment:</span></span>

- <span data-ttu-id="bbee1-p105">**適合的 Windows 版本升級**-您的裝置必須執行 Windows 7 或 Windows 8.1 的版本升級為 Windows 10 Enterprise 合格。如需支援版本的清單，請參閱[Windows 10 升級路徑](https://aka.ms/win10upgradepaths)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p105">**Windows editions eligible for upgrade** - Your devices must be running editions of Windows 7 or Windows 8.1 that are eligible for upgrade to Windows 10 Enterprise. For a list of supported editions, see [Windows 10 upgrade paths](https://aka.ms/win10upgradepaths).</span></span> 
- <span data-ttu-id="bbee1-p106">**支援的裝置**與 Windows 8.1 相容的大部分電腦會與 Windows 10 相容。您可能需要 Windows 10 更新發行的驅動程式安裝您的裝置正常運作。如需詳細資訊，請參閱[Windows 10 規格](https://aka.ms/windows10specifications)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p106">**Supported devices** - Most computers that are compatible with Windows 8.1 will be compatible with Windows 10. You may need to install updated drivers in Windows 10 for your devices to properly function. See [Windows 10 specifications](https://aka.ms/windows10specifications) for more info.</span></span>
- <span data-ttu-id="bbee1-130">**部署準備**-請確定您有下列再開始設定部署：</span><span class="sxs-lookup"><span data-stu-id="bbee1-130">**Deployment preparation** - Make sure you have the following before you start configuring the deployment:</span></span>
    - <span data-ttu-id="bbee1-p107">Windows 10 安裝媒體的安裝媒體必須位於與已經裝載 ISO 不同的磁碟機。您可以取得 ISO 從[MSDN 訂閱者下載](https://aka.ms/msdn-subscriber-downloads)或從[大量授權服務中心](https://aka.ms/mvlsc)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p107">Windows 10 installation media - The installation media must be located on a separate drive, with the ISO already mounted. You can obtain the ISO from [MSDN Subscriber Downloads](https://aka.ms/msdn-subscriber-downloads) or from the [Volume Licensing Service Center](https://aka.ms/mvlsc).</span></span>
    - <span data-ttu-id="bbee1-p108">使用者資料-備份雖然將的升級、 移轉使用者資料最佳做法是設定備份的案例。例如，將所有使用者資料都匯出至 OneDrive 帳戶、 移 BitLocker 加密 USB 快閃磁碟機或網路檔案伺服器。如需詳細資訊，請參閱[備份或傳輸 Windows 中的資料](https://aka.ms/backuptransferdatawindows)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p108">Backups of user data - Although user data will be migrated in the upgrade, best practice is to configure a backup scenario. For example, export all user data to a OneDrive account, BitLocker To Go-encrypted USB flash drive, or network file server. For more information, see [Back up or transfer data in Windows](https://aka.ms/backuptransferdatawindows).</span></span>
- <span data-ttu-id="bbee1-p109">**環境準備**-您要用以作業系統部署準備現有的 Configuration Manager 伺服器結構。除了基底的安裝程式、 Configuration Manager 環境中可供下列設定：</span><span class="sxs-lookup"><span data-stu-id="bbee1-p109">**Environment preparation** - You will use an existing Configuration Manager server structure to prepare for operating system deployment. In addition to the base setup, the following configurations should be made in the Configuration Manager environment:</span></span>
    1. <span data-ttu-id="bbee1-138">[擴充 Active Directory 架構](https://aka.ms/extendadschema)和[建立管理系統容器](https://aka.ms/createsysmancontainer)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-138">[Extend the Active Directory Schema](https://aka.ms/extendadschema) and [create a System Management container](https://aka.ms/createsysmancontainer).</span></span>
    2. <span data-ttu-id="bbee1-p110">啟用 Active Directory 樹系搜索與 Active Directory 系統探索。如需詳細資訊，請參閱 ＜ [Configure 探索方法的 System Center Configuration Manager](https://aka.ms/configurediscoverymethods)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p110">Enable Active Directory Forest Discovery and Active Directory System Discovery. For more info, see [Configure discovery methods for System Center Configuration Manager](https://aka.ms/configurediscoverymethods).</span></span>
    3. <span data-ttu-id="bbee1-p111">建立 IP 範圍限制與界限群組的內容與網站的工作分派。如需詳細資訊，請參閱[定義網站限制與界限群組的 System Center Configuration Manager](https://aka.ms/definesiteboundaries)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p111">Create IP range boundaries and boundary group for content and site assignment. For more info, see [Define site boundaries and boundary groups for System Center Configuration Manager](https://aka.ms/definesiteboundaries).</span></span>
    4. <span data-ttu-id="bbee1-p112">新增並設定 reporting services 點角色 Configuration Manager。如需詳細資訊，請參閱[設定報表的 Configuration Manager](https://aka.ms/configurereporting)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p112">Add and configure the Configuration Manager reporting services point role. For more info, see [Configuring Reporting in Configuration Manager](https://aka.ms/configurereporting).</span></span>
    5. <span data-ttu-id="bbee1-145">建立套件檔案系統資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="bbee1-145">Create a file system folder structure for packages.</span></span>
    6. <span data-ttu-id="bbee1-146">建立套件的 Configuration Manager console] 資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="bbee1-146">Create a Configuration Manager console folder structure for packages.</span></span>
    7. <span data-ttu-id="bbee1-147">安裝 System Center Configuration Manager （目前分支） 更新及任何其他 Windows 10 必要條件。</span><span class="sxs-lookup"><span data-stu-id="bbee1-147">Install System Center Configuration Manager (Current Branch) updates and any additional Windows 10 prerequisites.</span></span>

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a><span data-ttu-id="bbee1-148">第 2 部分： 新增使用 Configuration Manager Windows 10 作業系統映像</span><span class="sxs-lookup"><span data-stu-id="bbee1-148">Part 2: Add a Windows 10 OS image using Configuration Manager</span></span>
<span data-ttu-id="bbee1-p113">現在您需要建立包含完整的 Windows 10 安裝媒體作業系統升級封裝。下列步驟，您將使用 Configuration Manager for Windows 10 Enterprise x64 建立升級的封裝。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p113">Now you'll need to create an operating system upgrade package that contains the full Windows 10 installation media. In the following steps, you’ll use Configuration Manager to create an upgrade package for Windows 10 Enterprise x64.</span></span>

<span data-ttu-id="bbee1-151">**若要新增使用 Configuration Manager Windows 10 作業系統映像**</span><span class="sxs-lookup"><span data-stu-id="bbee1-151">**To add a Windows 10 OS image using Configuration Manager**</span></span>

1. <span data-ttu-id="bbee1-152">使用 [Configuration Manager console、**軟體文件庫**工作區中，[**作業系統升級封裝**] 節點上按一下滑鼠右鍵，然後選取 [**新增作業系統升級封裝**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-152">Using the Configuration Manager console, in the **Software Library** workspace, right-click the **Operating System Upgrade Packages** node, and then select **Add Operating System Upgrade Package**.</span></span>
2. <span data-ttu-id="bbee1-153">在 [**資料來源**] 頁面指定 Windows 10 Enterprise x64 媒體的 UNC 路徑，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-153">On the **Data Source** page, specify the UNC path to the Windows 10 Enterprise x64 media, and then select **Next**.</span></span>
3. <span data-ttu-id="bbee1-154">在 [**一般**] 頁面上指定**Windows 10 Enterprise x64 升級**，然後再選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-154">On the **General** page, specify **Windows 10 Enterprise x64 Upgrade**, and then select **Next**.</span></span> 
4. <span data-ttu-id="bbee1-155">在 [**摘要**] 頁面上選取 [**下一步**，，然後選取 [**關閉**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-155">On the **Summary** page, select **Next**, and then select **Close**.</span></span> 
5. <span data-ttu-id="bbee1-156">以滑鼠右鍵按一下建立的**Windows 10 Enterprise x64 更新**封裝，然後再選取 [**發佈內容**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-156">Right-click the created **Windows 10 Enterprise x64 Update** package, and then select **Distribute Content**.</span></span> 
6. <span data-ttu-id="bbee1-157">選擇您的發佈點。</span><span class="sxs-lookup"><span data-stu-id="bbee1-157">Choose your distribution point.</span></span>

## <a name="part-3-configure-deployment-settings"></a><span data-ttu-id="bbee1-158">第 3 部分： 部署設定</span><span class="sxs-lookup"><span data-stu-id="bbee1-158">Part 3: Configure deployment settings</span></span>
<span data-ttu-id="bbee1-p114">在此步驟中，您將設定包含設定 Windows 10 升級的升級工作順序。您將然後找出要升級的裝置，然後將那些裝置的部署工作順序。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p114">In this step, you'll configure an upgrade task sequence that contains the settings for the Windows 10 upgrade. You'll then identify the devices to upgrade, and then deploy the task sequence to those devices.</span></span>

### <a name="create-a-task-sequence"></a><span data-ttu-id="bbee1-161">建立工作順序</span><span class="sxs-lookup"><span data-stu-id="bbee1-161">Create a task sequence</span></span>
<span data-ttu-id="bbee1-162">若要建立升級工作順序，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bbee1-162">To create an upgrade task sequence, perform the following steps:</span></span>
  
1. <span data-ttu-id="bbee1-163">在 [Configuration Manager console、**軟體文件庫**工作區中展開 [**作業系統**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-163">In the Configuration Manager console, in the **Software Library** workspace, expand **Operating Systems**.</span></span> 
2. <span data-ttu-id="bbee1-164">以滑鼠右鍵按一下 [**工作順序**] 節點，然後選取 [**建立工作順序**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-164">Right-click the **Task Sequences** node, and then select **Create Task Sequence**.</span></span>
3. <span data-ttu-id="bbee1-165">在 [**建立新的工作順序**] 頁面上選取 [**升級作業系統升級的封裝**、，，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-165">On the **Create a new task sequence** page, select **Upgrade an operating system from upgrade package**, and then select **Next**.</span></span>
4. <span data-ttu-id="bbee1-166">**工作順序資訊**] 頁面上指定**Windows 10 Enterprise x64 升級**，然後再選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-166">On the **Task Sequence Information** page, specify **Windows 10 Enterprise x64 Upgrade**, and then select **Next**.</span></span>
5. <span data-ttu-id="bbee1-167">在**Windows 作業系統升級**] 頁面上選取 [**瀏覽**和選擇**Windows 10 Enterprise x64 升級作業系統升級封裝**、 選取 **[確定**]，然後選取**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-167">On the **Upgrade the Windows operating system** page, select **Browse** and choose the **Windows 10 Enterprise x64 Upgrade operating system upgrade package**, select **OK**, and then select **Next**.</span></span>
6. <span data-ttu-id="bbee1-168">繼續執行其餘的精靈頁面，然後再選取 [**關閉**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-168">Continue through the remaining wizard pages, and then select **Close**.</span></span>

### <a name="create-a-device-collection"></a><span data-ttu-id="bbee1-169">建立裝置集合</span><span class="sxs-lookup"><span data-stu-id="bbee1-169">Create a device collection</span></span>
<span data-ttu-id="bbee1-170">建立升級工作順序之後，您需要建立包含您要升級之裝置的集合。</span><span class="sxs-lookup"><span data-stu-id="bbee1-170">After you create the upgrade task sequence, you'll need to create a collection that contains the devices you will upgrade.</span></span>

> [!NOTE]
> <span data-ttu-id="bbee1-p115">使用下列設定以測試部署的單一裝置。您可以使用不同的成員資格規則當您準備好包含一組裝置。如需詳細資訊，請參閱 ＜[如何建立在 System Center Configuration Manager 的集合](https://aka.ms/sccm-create-collections)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p115">Use the following settings to test the deployment on a single device. You can use different membership rules to include groups of devices when you are ready. For more info, see [How to create collections in System Center Configuration Manager](https://aka.ms/sccm-create-collections).</span></span>

1. <span data-ttu-id="bbee1-174">在 [Configuration Manager console、**資產和規範**工作區中用滑鼠右鍵按一下 [**裝置集合**，然後選取**建立裝置集合**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-174">In the Configuration Manager console, in the **Assets and Compliance** workspace, right-click **Device Collections**, and then select **Create Device Collection**.</span></span> 
2. <span data-ttu-id="bbee1-175">在建立裝置集合精靈] 的 [**一般**] 頁面上輸入下列設定值，然後選取 [**下一步**：</span><span class="sxs-lookup"><span data-stu-id="bbee1-175">In the Create Device Collection wizard, on the **General** page, enter the following settings and then select **Next**:</span></span>
    - <span data-ttu-id="bbee1-176">名稱： Windows 10 Enterprise x64 升級</span><span class="sxs-lookup"><span data-stu-id="bbee1-176">Name: Windows 10 Enterprise x64 Upgrade</span></span>
    - <span data-ttu-id="bbee1-177">限制集合： 的所有系統</span><span class="sxs-lookup"><span data-stu-id="bbee1-177">Limiting Collection: All Systems</span></span>
3. <span data-ttu-id="bbee1-178">在 [**成員資格規則**] 頁面上選取 [**新增規則** > **直接規則**以啟動 [建立直接成員資格規則精靈]。</span><span class="sxs-lookup"><span data-stu-id="bbee1-178">On the **Membership Rules** page, select **Add Rule** > **Direct rule** to launch the Create Direct Membership Rule Wizard.</span></span>
4. <span data-ttu-id="bbee1-179">在 [建立直接成員資格規則精靈]**歡迎**頁面中，選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="bbee1-179">On the **Welcome** page of the Create Direct Membership Rule Wizard, select **Next**.</span></span>
5. <span data-ttu-id="bbee1-180">**搜尋的資源**] 索引標籤上輸入下列設定以您要升級之裝置的名稱取代預留位置文字**值**：</span><span class="sxs-lookup"><span data-stu-id="bbee1-180">On the **Search for Resources** page, enter the following settings, replacing the placeholder **Value** text with the name of the device you are upgrading:</span></span> 
    - <span data-ttu-id="bbee1-181">資源類別： 系統資源</span><span class="sxs-lookup"><span data-stu-id="bbee1-181">Resource Class: System Resource</span></span>
    - <span data-ttu-id="bbee1-182">屬性名稱： 名稱</span><span class="sxs-lookup"><span data-stu-id="bbee1-182">Attribute Name: Name</span></span>
    - <span data-ttu-id="bbee1-183">值： *PC0003*</span><span class="sxs-lookup"><span data-stu-id="bbee1-183">Value: *PC0003*</span></span>
6. <span data-ttu-id="bbee1-184">**選取 [資源**] 索引標籤上選取您的裝置，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-184">On the **Select Resources** page, select your device, and select **Next**.</span></span>
7. <span data-ttu-id="bbee1-185">完成 [建立直接成員資格規則精靈] 和 [建立裝置集合精靈]。</span><span class="sxs-lookup"><span data-stu-id="bbee1-185">Complete the Create Direct Membership Rule wizard and the Create Device Collection Wizard.</span></span>  
8. <span data-ttu-id="bbee1-p116">檢閱 Windows 10 Enterprise x64 升級集合。請勿繼續直到您看到機器您加入集合中。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p116">Review the Windows 10 Enterprise x64 Upgrade collection. Do not continue until you see the machines you added in the collection.</span></span>

### <a name="create-an-operating-system-deployment"></a><span data-ttu-id="bbee1-188">建立作業系統部署</span><span class="sxs-lookup"><span data-stu-id="bbee1-188">Create an operating system deployment</span></span>
<span data-ttu-id="bbee1-189">請遵循下列步驟建立的部署工作順序。</span><span class="sxs-lookup"><span data-stu-id="bbee1-189">Follow these steps to create a deployment for the task sequence.</span></span>

1. <span data-ttu-id="bbee1-190">在 [Configuration Manager console、**軟體文件庫**工作區中用滑鼠右鍵按一下您在上一個步驟中建立工作順序，然後選取**部署**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-190">In the Configuration Manager console, in the **Software Library** workspace, right-click the task sequence you created in a previous step, and then select **Deploy**.</span></span>
2. <span data-ttu-id="bbee1-191">在 [**一般**] 頁面上選取**Windows 10 Enterprise x64 升級**集合，然後再選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-191">On the **General** page, select the **Windows 10 Enterprise x64 Upgrade** collection, and then select **Next**.</span></span>
3. <span data-ttu-id="bbee1-192">在 [**內容**] 頁面上選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="bbee1-192">On the **Content** page, select **Next**.</span></span>
4. <span data-ttu-id="bbee1-193">在 [**部署設定**] 頁面上選取下列設定，然後選取**下一個**：</span><span class="sxs-lookup"><span data-stu-id="bbee1-193">On the **Deployment Settings** page, select the following settings, and then select **Next**:</span></span>

    > [!NOTE]
    > <span data-ttu-id="bbee1-p117">針對這個測試部署，您將會設為**有空**，需要使用者介入以啟動部署的用途。在實際執行環境中，您可能會想要自動化使用所需的用途，需要設定其他選項，例如排程執行部署時的部署。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p117">For this test deployment, you'll set the purpose to **Available**, which requires user intervention to start the deployment. In a production environment, you may wish to automate the deployment using the Required purpose, which involves configuring additional options such as scheduling when the deployment is run.</span></span> 

    - <span data-ttu-id="bbee1-196">巨集指令： 安裝</span><span class="sxs-lookup"><span data-stu-id="bbee1-196">Action: Install</span></span>
    - <span data-ttu-id="bbee1-197">目的： 可用</span><span class="sxs-lookup"><span data-stu-id="bbee1-197">Purpose: Available</span></span>

5. <span data-ttu-id="bbee1-198">在 [**排程**] 頁面上，接受預設設定，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-198">On the **Scheduling** page, accept the default settings, and then select **Next**.</span></span>
6. <span data-ttu-id="bbee1-199">在**使用者經驗**] 頁面上，接受預設設定，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-199">On the **User Experience** page, accept the default settings, and then select **Next**.</span></span>
7. <span data-ttu-id="bbee1-200">在 [**提醒**] 頁面上，接受預設設定，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-200">On the **Alerts** page, accept the default settings, and then select **Next**.</span></span>
8. <span data-ttu-id="bbee1-201">在 [**摘要**] 頁面上選取 [**下一步**，，然後選取 [**關閉**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-201">On the **Summary** page, select **Next**, and then select **Close**.</span></span>

## <a name="part-5-start-the-windows-10-upgrade-task-sequence"></a><span data-ttu-id="bbee1-202">第 5 部分： Windows 10 開始升級工作順序</span><span class="sxs-lookup"><span data-stu-id="bbee1-202">Part 5: Start the Windows 10 upgrade task sequence</span></span>
<span data-ttu-id="bbee1-203">請遵循下列步驟，在您要升級之裝置上啟動 Windows 10 升級工作順序。</span><span class="sxs-lookup"><span data-stu-id="bbee1-203">Follow these steps to start the Windows 10 Upgrade task sequence on the device that you are upgrading.</span></span>
 
1. <span data-ttu-id="bbee1-204">登入 Windows 電腦和啟動**軟體中心**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-204">Log on to the Windows computer and start **Software Center**.</span></span>
2. <span data-ttu-id="bbee1-205">選取您在上一個步驟中建立工作順序，然後選取 [**安裝**。</span><span class="sxs-lookup"><span data-stu-id="bbee1-205">Select the task sequence that you created in a previous step, and then select **Install**.</span></span>
3. <span data-ttu-id="bbee1-206">當工作順序開始時，它自動會起始就地升級程序所叫用與所需的命令列參數來執行自動的升級會保留所有的資料、 設定、 應用程式，Windows 安裝程式 (Setup.exe) 和發行的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="bbee1-206">When the task sequence begins, it automatically initiates the in-place upgrade process by invoking the Windows setup program (Setup.exe) with the necessary command-line parameters to perform an automated upgrade, which preserves all data, settings, apps, and drivers.</span></span>
4. <span data-ttu-id="bbee1-207">工作順序成功完成之後，電腦將完整升級為 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="bbee1-207">After the task sequence completes successfully, the computer will be fully upgraded to Windows 10.</span></span>

<span data-ttu-id="bbee1-p118">如果您在企業環境中使用 Windows 10 時遇到問題，您可以查閱[的最常見的問題的最佳 Microsoft 技術支援人員解決方案](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)。下列資源包含 KB 文章、 更新及文件庫文章。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p118">If you experience issues when using Windows 10 in an enterprise environment, you can consult [top Microsoft Support solutions for the most common issues](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). These resources include KB articles, updates, and library articles.</span></span>

<span data-ttu-id="bbee1-p119">更新整個組織的首度發行期間使用 Windows 分析更新規範的功能提供 OS 更新規範、 更新部署進度以及疑難排解 Windows 10 裝置失敗的整體檢視。此新服務使用包括安裝進度、 Windows Update 設定及其他資訊的診斷資料提供這類前瞻，在沒有額外成本並沒有其他基礎結構需求。是否搭配使用 Windows Update 商務或其他管理工具，您可以確保正確更新您的裝置。</span><span class="sxs-lookup"><span data-stu-id="bbee1-p119">During the rollout of updates across your organization, use the Update Compliance capability of Windows Analytics to provide a holistic view of OS update compliance, update deployment progress, and failure troubleshooting for Windows 10 devices. This new service uses diagnostic data including installation progress, Windows Update configuration and other information to provide such insights, at no extra cost and without additional infrastructure requirements. Whether it's used with Windows Update for Business or other management tools, you can be assured that your devices are properly updated.</span></span>

<span data-ttu-id="bbee1-213">請參閱[監視 Windows Update 及更新規範與 Windows 防禦者防毒深入了解、 開始，並使用更新規範。](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor)</span><span class="sxs-lookup"><span data-stu-id="bbee1-213">See [Monitor Windows Updates and Windows Defender Antivirus with Update Compliance](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) to learn more, get started, and use Update Compliance.</span></span>

<span data-ttu-id="bbee1-214">作為過渡期的檢查點，您可以看到此步驟的[允出準則](windows10-exit-criteria.md#crit-windows10-step2)。</span><span class="sxs-lookup"><span data-stu-id="bbee1-214">As an interim checkpoint, you can see the [exit criteria](windows10-exit-criteria.md#crit-windows10-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="bbee1-215">下一步</span><span class="sxs-lookup"><span data-stu-id="bbee1-215">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="bbee1-216">部署 Windows 10 Enterprise 與 Windows 自動駕駛儀上的新裝置</span><span class="sxs-lookup"><span data-stu-id="bbee1-216">Deploy Windows 10 Enterprise for new devices with Windows Autopilot</span></span>](windows10-deploy-autopilot.md) |



<!--

| Phases | Description |
|:--- |:--- |
| [Phase 1: Consideration phase](#phase-1-consideration-phase) | TBD |
| [Phase 2: Testing phase](#phase-2-testing-phase) | TBD |
| [Phase 3: Deployment phase](#phase-3-deployment-phase) | TBD |

## Phase 1: Consideration phase
Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process.

For in-place upgrade with Configuration Manager, these are the infrastructure you need to take into account:

#### Group Policy
Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which you need to test and implement as part of a Windows 10 migration. Use the examples from the following resources to assess current group policies for Windows, including Group Policy Objects in the Active Directory structure:
* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise

> [!NOTE]
> If you are considering moving to modern management by using MDM instead of Group Policy to manage device configurations, you can start by using the [MDM Migration Analysis Tool (MMAT)](https://github.com/WindowsDeviceManagement/MMAT) to determine what Group Policies are set on the device and report the corresponding settings, if available.

#### Data management
Although in-place upgrades shouldn’t affect user data and apps, a best practice is to configure a backup scenario and back up user data. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more details, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

#### System Center Configuration Manager
This guide assumes you are following Microsoft recommendations and have one of the following versions of System Center Configuration Manager 2012 onward:
* System Center 2012 Configuration Manager with SP2
* System Center 2012, 2012 R2 Configuration Manager with SP1, Current Branch, 1706
    * [Run an in-place upgrade to the latest Configuration Manager](https://go.microsoft.com/fwlink/?linkid=839406)
    * [Updates for Configuration Manager](https://go.microsoft.com/fwlink/?linkid=620343)
* Core Configuration Manager configuration:
    * CONFIGURATION MANAGER accounts
    * Active Directory permissions
    * Source folder structure
    * Active Directory schema
* Configure the following [necessary Configuration Manager components for Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860245):
    * **State migration point** - Stores user state migration data during computer replace scenarios
    * **Distribution point** - Stores all packages in Configuration Manager
    * **Software update point** - Updates an OS as part of the deployment process
    * **Reporting services point** - Monitors the OS deployment process
    * **Boot images** - Are Windows Preinstallation Environment (PE) images used by Configuration Manager to start deployments
    * **OS images** - Denotes the production deployment image (mounted OS)
    * **OS installers** - Creates reference images using Microsoft Deployment Toolkit (MDT) Light Touch
    * **Drivers** - Denotes a repository of managed device drivers
    * **Task Sequence** - Is delivered automatically to the client as a policy

#### Network bandwidth
This guide assumes you have enough network bandwidth to support the deployment of Windows 10 Enterprise and Office 365 ProPlus as a unit. As a bundle, network bandwidth is a significant factor.

#### Client machines and in-place upgrade scenario
* Disk encryption - Third-party disk encryption isn't supported in an in-place upgrade scenario.
* User profiles - Only the standard user profile type is supported.
* Legacy BIOS to Unified Extensible Firmware Interface (UEFI) booting - Changing from legacy BIOS to UEFI booting isn't supported.
* Dual-boot - This scenario is not covered in the guide. If you have the FastTrack Benefit, it only covers devices running a single OS.
* Virtual desktop infrastructure (VDI) environments - This scenario is not covered in the guide. If you have the FastTrack Benefit, it doesn't cover configuration or deployment on VDI environments.
* x64 and x86 - Changing from a 32-bit OS to a 64-bit isn't supported. For more info, see [Windows 10 deployment scenario > In-place upgrade](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios#in-place-upgrade).

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostic data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs
In-place upgrades have have limitations when it comes to language packs. The language stays consistent throughout the upgrade. Verify the language version and make sure it stays consistent. For example, Windows 7 with English as the default won’t change when upgraded to Windows 10. For more info, see:
* [Default language pack on your OS](https://go.microsoft.com/fwlink/?linkid=860282)
* [Finding language packs on each Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860283)

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see:
* [Choose between 64-bit or 32-bit version of Office](https://go.microsoft.com/fwlink/?linkid=862361) - Helps you decide which version of Office is right for you.
* [Language accessory pack for Office](https://go.microsoft.com/fwlink/?linkid=860280) - Follow the steps to install the language accessory pack for Office.
* [Add an additional language pack](https://go.microsoft.com/fwlink/?linkid=860281) - Get step-by-step info on adding a language or setting language preferences in Office.

### Step 3: Governance and business processes

#### Windows as a service
Windows 10 introduced the concept of Windows as a service. This greatly changes the frequency and style of updates to Windows. Instead of new versions being released every 3-5 years, a more incremental model is used where two smaller updates (Feature Updates) are released yearly. For more info, see:
* [Windows as a service on the Windows IT Pro Center](https://www.microsoft.com/itpro/windows-10/windows-as-a-service)
* [Overview of Windows as a service](https://go.microsoft.com/fwlink/?linkid=860288)
* [Update Windows 10 in the enterprise](https://go.microsoft.com/fwlink/?linkid=860285)

#### Pilot users and deployment rings
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. This affects future Windows updates as well (including features and quality). You need to create and edit device collections by deployment rings to help minimize the effect on network bandwidth and simplify future updates. 

For the group of pilot users, create a device collection on Configuration Manager. The list of devices should correspond to the list of the first users upgraded to Windows 10. 

**Windows 10 deployment rings**

There are three servicing channels for OS deployment rings:
* Windows Insider Program - Provides organizations with the opportunity to test and provide feedback on features that are shipped in the next feature update.
* Semi-Annual Channel - Provides new functionality with twice-per-year feature update releases. Organizations can choose when to deploy updates from the Semi-Annual Channel.
* Long-Term Servicing Channel (LTSC) - Used for specialized devices and receives new feature releases about every three years.

For more info, see:
* [Windows Insider Program, Semi-Annual Channel, and Long-Term Servicing Channel](https://go.microsoft.com/fwlink/?linkid=860293)
* [Build deployment rings for Windows 10 updates](https://go.microsoft.com/fwlink/?linkid=860294)
* [Manage software updates using Intune in Azure Portal](https://docs.microsoft.com/intune/windows-update-for-business-configure)

**Office 365 ProPlus**

For Microsoft 365 powered devices, you must also be able to support the six-month update channel for both IT and business users. One way to do so is to have three groups:
* Current Channel
* Deferred Channel
* First-release for Deferred Channel

Each group has different configuration files, as users from the Current Channel are used as a pilot to test earlier updates. For more info, see:
* [Update process for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860299)
* [Manage updates to Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860300)
* [Configure update settings for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860301)
* [Update channels for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860302)
* [Version and build numbers of update channel releases](https://go.microsoft.com/fwlink/?linkid=860304)

For more info, see [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md).

## Phase 2: Testing phase
Once you've completed the scenarios and requirements in [Step 1: Consideration phase](#step-1-consideration-phase), you can move to this stage.
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [System Center Configuration Manager](#step-4-system-center-configuration-manager)
* [Diagnostic data](#step-5-diagnostic-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part your in-place upgrade, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of your in-place upgrade, make sure you complete these tasks:
1. [Add a domain and users to Office 365](http://go.microsoft.com/fwlink/?LinkID=526338).
2. [Install and run the Office 365 IdFix tool](http://go.microsoft.com/fwlink/?LinkId=733662), which scans your on-premises Active Directory environment and identifies problems that might impact directory synchronization and slow your migration to Office 365.
3. Configure Active Directory for directory synchronization with Office 365 and [integrate on-premises directories with Azure AD](http://go.microsoft.com/fwlink/?LinkId=733661).
4. [Prepare to provision users through directory synchronization to Office 365](http://go.microsoft.com/fwlink/?LinkId=733659).
5. Know the [prerequisites for Azure AD Connect](http://go.microsoft.com/fwlink/?LinkId=733663), then install and run the Azure AD Connect tool to synchronize your on-premises Active Directory to the Azure AD service used by Office 365.
6. Determine custom installation of Azure AD Connect (full version of SQL Server for directory synchronization, if required).
7. [Integrate your on-premises identities with Azure AD](http://go.microsoft.com/fwlink/?LinkID=733485).
8. [Sync a list of required attributes with AD Connect](https://go.microsoft.com/fwlink/?linkid=860363) to get all the features in Office 365 and Windows 10.
9. Activate Windows 10 Enterprise licenses, which are checked based on Azure AD credentials.

    This provides a systematic way to assign licenses to end users and groups in your organization. For more info, see [Windows 10 Subscription Activation](https://go.microsoft.com/fwlink/?linkid=860365) and [Deploy Windows 10 licenses](https://go.microsoft.com/fwlink/?linkid=860367).

### Step 3: Client readiness

#### System requirements for Office 365
Confirm that Windows 10 works with Office 365. Be sure you're using the latest OS version and browsers with Office 365 and have updated them with the latest service packs. For more info on Office requirements, see [System requirements for Office](http://go.microsoft.com/fwlink/?LinkID=394412).

### Step 4: System Center Configuration Manager
See [System Center Configuration Manager](#system-center-configuration-manager).

### Step 5: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. 

**Windows 10 operating system diagnostic data levels**

You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.

Use the appropriate value in the table below when you configure the management policy.

| Level | Data gathered | Value |
|:--- |:--- |:--- |
| Security | Security data only. | 0 |
| Basic | Security data, and basic system and quality data. | 1 |
| Enhanced | Security data, basic system and quality data, and enhanced insights and advanced reliability data. | 2 |
| Full | Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data. | 3 |

You can enable diagnostics data through these methods:
* Microsoft Intune - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).
* Registry Editor - You can use the Registry Editor to manually enable diagnostic data on each device in your organization, or write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.
* Group Policy - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.
* Command prompt - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.

See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:
* [In-place upgrade to Windows 10 Enterprise](#31-in-place-upgrade-to-windows-10-enterprise)
* [Windows Defender Antivirus](#32-windows-defender-antivirus)

### Step 1: In-place upgrade to Windows 10 Enterprise
1. Integrate System Center Configuration Manager with Microsoft Deployment Tool.

    Be sure to use the Microsoft Deployment Toolkit (MDT) in conjunction with Configuration Manager when deploying an updated version of Windows 10. MDT brings Zero Touch Installation and Light Touch Installation enhancements to help with deployments at no cost to the customer. For more info, see:
    * [Download the latest MDT](https://go.microsoft.com/fwlink/?linkid=860465)
    * [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://go.microsoft.com/fwlink/?linkid=860466)

2. Prepare for zero touch installation.

    As part of zero touch installation, you are responsible for preparing the following:
    * Configuration Manager service accounts
    * Active Directory permissions
    * Source folder structure

    Then, [integrate Configuration Manager with MDT](https://go.microsoft.com/fwlink/?linkid=860035).

3. Create a custom Windows Preinstallation Environment boot image.

    Windows Preinstallation Environment (PE) is a pre-installation environment required for OS deployments. It’s used to prepare a client machine for Windows installation, to copy disk images from a network file server, and to initiate Windows Setup. It’s used for Windows 10 Enterprise editions. For more info, see:
    * [Overview of Windows PE](https://go.microsoft.com/fwlink/?linkid=860468)
    * [Windows PE features, hardware requirements, and limitations](https://go.microsoft.com/fwlink/?linkid=860469)
    * [Create a custom Windows PE boot image with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860470)

4. Add a Windows 10 OS upgrade image.

    You need to create a Windows 10 reference image with MDT (as needed). Reference images are the foundation of what each of the client machine’s OS looks like. The image should be in a separate folder located with the already-mounted ISO file. The task sequence looks for and then runs “setup.exe”. 

    Follow the steps to create and add a Windows 10 OS upgrade image on Configuration Manager:
    * [Create a Windows 10 reference image](https://go.microsoft.com/fwlink/?linkid=860500)
    * [Add a Windows 10 OS image using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860501)

5. Create an app to deploy with Windows 10.

    For a Microsoft 365 powered device, you can deploy Office 365 ProPlus with Windows 10 Enterprise using Configuration Manager. You can also add other apps as needed.

    To deploy Office 365 ProPlus, follow the steps in [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md). During this phase, make sure you complete these steps:
    
    1. Download the Office 2016 Deployment Tool (ODT) in conjunction with Configuration Manager to help with Office 365 ProPlus deployments. 
    2. Edit the configuration XML file to fit specific deployment needs (like version, language, and product element). 
    
    You can then create apps with Configuration Manager. For more info, see:
    * [Configuration options for ODT](https://go.microsoft.com/fwlink/?linkid=860504)
    * [Create apps in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=761079)
    * [Deploy Office 365 ProPlus with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860506)

6. Add drivers to a Windows 10 deployment using Windows PE.

    Network drivers need to be created for both Windows PE and Windows 10 to connect deployment shares and storage drivers with local storage on a client computer. Use Configuration Manager to create these drivers required for deployment. For more info, see [Add drivers to a Windows 10 deployment with Windows PE using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860036).

7. Create a task sequence.

    A task sequence (a collection of commands) is required for MDT Lite Touch Installation (LTI). You need to create and then edit the task sequence for optimal deployment experience. One of the configurations enable support for Unified Extensible Firmware Interface (UEFI). The UEFI environment is a minimal boot OS where devices are booted and the Windows 10 OS runs. For more info, see:
    * [Overview of Windows Boot Manager](https://go.microsoft.com/fwlink/?linkid=860696)
    * [Create the task sequence in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697)

8. Finalize the OS configuration for Windows 10 deployment.

    **To finalize the OS configuration**

    1. Enable MDT monitoring
    2. Create and share the Logs folder
    3. Configure the rules
    4. Distribute content to the distribution point (a server running Configuration Manager)
    5. Create a deployment for the task sequence

   For more info, see [Finalize OS configuration with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

9. Deploy the Windows 10 Enterprise image to a UEFI machine.

    For more info, see [Deploy Windows 10 using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

10. Monitor the Windows 10 deployment.

    Use Configuration Manager and MDT to monitor your deployment. Deployment Workbench enables access to the computer remotely using the Diagnostics and Recovery Toolset (DaRT) (optional). Deployments can be monitored in Configuration Manager. For more info, see [Monitor the Windows 10 deployment with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860705).

### Step 2: Windows Defender Antivirus
See [Enable Windows 10 Enterprise security features > Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus)

-->
