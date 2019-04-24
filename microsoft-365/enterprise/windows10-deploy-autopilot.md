---
title: 新裝置透過 Windows Autopilot 部署 Windows 10 企業版
description: 針對設定及部署 Windows 10 企業版與 Windows Autopilot 提供指導。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 文件、 Windows 10 企業版部署，Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: f173bd2357d445b502a4b28b60399d5cdb087cd0
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289253"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a><span data-ttu-id="a02db-104">步驟 3： 為新的裝置，透過 Windows Autopilot 部署 Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="a02db-104">Step 3: Deploy Windows 10 Enterprise for new devices with Windows Autopilot</span></span>

<span data-ttu-id="a02db-105">*本文適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a02db-105">*This article applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="a02db-106">如果您有新的 Windows 10 電腦，您可以使用 Windows Autopilot 自訂您的組織外的-全新體驗 (OOBE) 及部署新的系統應用程式與已設定的設定。</span><span class="sxs-lookup"><span data-stu-id="a02db-106">If you have new Windows 10 PCs, you can use Windows Autopilot to customize the out-of-box-experience (OOBE) for your organization and deploy a new system with apps and settings already configured.</span></span> <span data-ttu-id="a02db-107">有任何影像部署、 要插入，沒有驅動程式及任何基礎結構，以管理。</span><span class="sxs-lookup"><span data-stu-id="a02db-107">There are no images to deploy, no drivers to inject, and no infrastructure to manage.</span></span> <span data-ttu-id="a02db-108">使用者可以移到部署程序獨立，而不需要連絡其 IT 管理員。</span><span class="sxs-lookup"><span data-stu-id="a02db-108">Users can go through the deployment process independently, without the need consult their IT administrator.</span></span>

<span data-ttu-id="a02db-109">您可以設定和預先設定新的 Windows 10 裝置，並且讓使用者準備好使用 Windows Autopilot 的產能使用。</span><span class="sxs-lookup"><span data-stu-id="a02db-109">You can set up and pre-configure new Windows 10 devices and get them ready for productive use using Windows Autopilot.</span></span> <span data-ttu-id="a02db-110">若要深入了解 Windows Autopilot，包括優點和 Windows Autopilot 案例，請參閱 < <b0>Windows Autopilot 概觀</b0>。</span><span class="sxs-lookup"><span data-stu-id="a02db-110">To learn more about Windows Autopilot, including benefits and Windows Autopilot scenarios, see [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot).</span></span> <span data-ttu-id="a02db-111">準備好時，請遵循這些組件，以啟動新的裝置設定。</span><span class="sxs-lookup"><span data-stu-id="a02db-111">When ready, follow these parts to start setting up new devices.</span></span>

## <a name="part-1-start-windows-autopilot-deployment"></a><span data-ttu-id="a02db-112">第 1 部分： 開始 Windows Autopilot 部署</span><span class="sxs-lookup"><span data-stu-id="a02db-112">Part 1: Start Windows Autopilot deployment</span></span>
<span data-ttu-id="a02db-113">請參閱 < <b0>Overview of Windows Autopilot</b0>來：</span><span class="sxs-lookup"><span data-stu-id="a02db-113">See [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) to:</span></span>

1. <span data-ttu-id="a02db-114">了解並完成 Windows Autopilot 部署的必要條件。</span><span class="sxs-lookup"><span data-stu-id="a02db-114">Learn about and complete the prerequisites for Windows Autopilot deployment.</span></span> <span data-ttu-id="a02db-115">必要條件包括：</span><span class="sxs-lookup"><span data-stu-id="a02db-115">The prerequisites include:</span></span>
    - <span data-ttu-id="a02db-116">**裝置註冊和 OOBE 自訂**</span><span class="sxs-lookup"><span data-stu-id="a02db-116">**Device registration and OOBE customization**</span></span>

        <span data-ttu-id="a02db-117">若要註冊裝置，您必須取得其硬體識別碼，並將其登錄。</span><span class="sxs-lookup"><span data-stu-id="a02db-117">To register devices, you need to acquire their hardware ID and register it.</span></span> <span data-ttu-id="a02db-118">我們目前正在使用各種硬體廠商，以讓他們所需的資訊提供給您，或將其代替您上傳。</span><span class="sxs-lookup"><span data-stu-id="a02db-118">We are actively working with various hardware vendors to enable them to provide the required information to you, or upload it on your behalf.</span></span> <span data-ttu-id="a02db-119">您也可以選擇使用 PowerShell 指令碼，就會產生.csv 檔案具有裝置的硬體識別碼自行擷取這項資訊</span><span class="sxs-lookup"><span data-stu-id="a02db-119">You also have the option to capture this information by yourself using a PowerShell script that generates a .csv file with the device's hardware ID.</span></span>

        <span data-ttu-id="a02db-120">一旦註冊裝置，有 OOBE 自訂選項，您可以設定包括略過的隱私權設定與使用者授權合約。</span><span class="sxs-lookup"><span data-stu-id="a02db-120">Once devices are registered, there are OOBE customization options that you can configure including skipping privacy settings and EULA.</span></span>

    - <span data-ttu-id="a02db-121">**OOBE 公司品牌推廣**</span><span class="sxs-lookup"><span data-stu-id="a02db-121">**Company branding for OOBE**</span></span>

        <span data-ttu-id="a02db-122">這可讓您將商標新增至在裝置 OOBE 期間出現。</span><span class="sxs-lookup"><span data-stu-id="a02db-122">This allows you to add branding to appear during device OOBE.</span></span>

    - <span data-ttu-id="a02db-123">**Microsoft Intune 中的 MDM 自動註冊**</span><span class="sxs-lookup"><span data-stu-id="a02db-123">**MDM auto-enrollment in Microsoft Intune**</span></span>
        
        <span data-ttu-id="a02db-124">自動註冊可讓他們的裝置連線到 Azure AD 註冊裝置管理其 Windows 10 裝置在 Intune 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="a02db-124">Automatic enrollment lets users enroll their Windows 10 devices in Intune for device management when they connect their devices to Azure AD.</span></span> <span data-ttu-id="a02db-125">若要註冊，使用者將其公司帳戶新增至其個人擁有的裝置，或公司擁有裝置加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="a02db-125">To enroll, users add their work account to their personally-owned devices or join corporate-owned devices to Azure AD.</span></span> <span data-ttu-id="a02db-126">在背景，也是使用 Intune 管理註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="a02db-126">In the background, the device is also enrolled for management with Intune.</span></span>

    - <span data-ttu-id="a02db-127">**Windows Autopilot 所用雲端服務的網路連線能力**</span><span class="sxs-lookup"><span data-stu-id="a02db-127">**Network connectivity to cloud services used by Windows Autopilot**</span></span>

        <span data-ttu-id="a02db-128">Windows Autopilot Deployment 方案使用，以取得您的裝置能夠生產力狀態的雲端服務的數字，這些服務必須能夠從登錄為 Windows Autopilot 裝置的裝置存取。</span><span class="sxs-lookup"><span data-stu-id="a02db-128">The Windows Autopilot Deployment Program uses a number of cloud services to get your devices to a productive state and these services must be accessible from devices registered as Windows Autopilot devices.</span></span> 

    - <span data-ttu-id="a02db-129">**裝置必須與 Windows 10 (版本 1703 或更新版本) 一起預先安裝**</span><span class="sxs-lookup"><span data-stu-id="a02db-129">**Devices must be pre-installed with Windows 10, version 1703 or later**</span></span>

2. <span data-ttu-id="a02db-130">了解，然後選取 [Windows Autopilot Deployment 方案，為您的組織。</span><span class="sxs-lookup"><span data-stu-id="a02db-130">Learn about and select the Windows Autopilot Deployment Program for your organization.</span></span> <span data-ttu-id="a02db-131">您可以選取這些部署程式：</span><span class="sxs-lookup"><span data-stu-id="a02db-131">You can select from these deployment programs:</span></span>
    - <span data-ttu-id="a02db-132">**商務用 Microsoft Store**</span><span class="sxs-lookup"><span data-stu-id="a02db-132">**Microsoft Store for Business**</span></span>
    - <span data-ttu-id="a02db-133">**Microsoft Intune**</span><span class="sxs-lookup"><span data-stu-id="a02db-133">**Microsoft Intune**</span></span>
    - <span data-ttu-id="a02db-134">**合作夥伴中心**</span><span class="sxs-lookup"><span data-stu-id="a02db-134">**Partner Center**</span></span>

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a><span data-ttu-id="a02db-135">第 2 部分： 設定 Windows 10 裝置適用於 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a02db-135">Part 2: Set up a Windows 10 device for Microsoft 365</span></span>
<span data-ttu-id="a02db-136">您可以設定為 Microsoft 365 使用者的 Windows 裝置之前，請確定所有 Windows 裝置皆都執行 Windows 10，版本 1703 (Creators Update) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="a02db-136">Before you can set up Windows devices for Microsoft 365 users, make sure all the Windows devices are running Windows 10, version 1703 (Creators Update) or later.</span></span>

<span data-ttu-id="a02db-137">組織中的所有 Windows 裝置可以都已升級至 Windows 10 Creators Update，或已在執行 Windows 10 Creators Update 之後，您可以將這些裝置加入貴組織的 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="a02db-137">After all Windows devices in your organization have either been upgraded to Windows 10 Creators Update or are already running Windows 10 Creators Update, you can join these devices to your organization’s Azure Active Directory.</span></span>

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a><span data-ttu-id="a02db-138">設定全新或新升級的 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="a02db-138">Set up a brand new or newly-upgraded Windows 10 device</span></span>
<span data-ttu-id="a02db-139">請遵循下列步驟來設定在執行 Windows 10 Creators Update 的全新裝置上使用 Windows 10 OOBE 裝置 （或更新版本） 或已升級到 Windows 10 Creators Update （或更新版本），但未經過現成可用的安裝程式在裝置上。</span><span class="sxs-lookup"><span data-stu-id="a02db-139">Follow these steps to set up a device using the Windows 10 OOBE on a brand new device running Windows 10 Creators Update (or later) or on a device that was upgrade to Windows 10 Creators Update (or later) but has not gone through out-of-box setup.</span></span>

1. <span data-ttu-id="a02db-140">如果您沒有設定無線網路，請確定將裝置連接到網際網路，透過有線或乙太網路連線。</span><span class="sxs-lookup"><span data-stu-id="a02db-140">If you don't have a wireless network configured, make sure you connect the device to the internet through a wired or Ethernet connection.</span></span>
2. <span data-ttu-id="a02db-141">經過 Windows 裝置安裝體驗。</span><span class="sxs-lookup"><span data-stu-id="a02db-141">Go through the Windows device setup experience.</span></span> <span data-ttu-id="a02db-142">在新的或重設裝置上，安裝程式體驗開頭為**讓我們開始與地區。是此權限？** 螢幕。</span><span class="sxs-lookup"><span data-stu-id="a02db-142">On a new or reset device, the setup experience starts with the **Let's start with region. Is this right?** screen.</span></span>
3. <span data-ttu-id="a02db-143">移到 Windows 10 裝置設定，直到到達**您要如何設定？** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a02db-143">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> <span data-ttu-id="a02db-144">在這裡，選取 [**組織設定**。</span><span class="sxs-lookup"><span data-stu-id="a02db-144">Here, select **Set up for an organization**.</span></span>
4. <span data-ttu-id="a02db-145">使用 Microsoft 365 使用者帳戶和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="a02db-145">Sign in using the Microsoft 365 user's account and password.</span></span> <span data-ttu-id="a02db-146">根據使用者密碼設定，可能會提示您更新密碼。</span><span class="sxs-lookup"><span data-stu-id="a02db-146">Depending on the user password setting, you may be prompted to update the password.</span></span> 
5. <span data-ttu-id="a02db-147">完成 Windows 10 裝置設定。</span><span class="sxs-lookup"><span data-stu-id="a02db-147">Finish Windows 10 device setup.</span></span>

<span data-ttu-id="a02db-148">完成後，裝置將已連接到貴組織的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="a02db-148">After you’re done, the device will be connected to your organization’s Azure AD.</span></span>

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a><span data-ttu-id="a02db-149">設定已完成的全新安裝的裝置</span><span class="sxs-lookup"><span data-stu-id="a02db-149">Set up a device that has already completed out-of-box setup</span></span>
<span data-ttu-id="a02db-150">如果您的裝置有 Windows 10 Creators Update （或更新版本），且已經過的現成可用的安裝，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="a02db-150">If your device has Windows 10 Creators Update (or later) and has already gone through the out-of-box setup, follow these steps.</span></span>

1. <span data-ttu-id="a02db-151">在使用者的 Windows 電腦是執行 Windows 10，版本 1703 (Creators Update)，選取 [ **Windows**標誌，，然後選取 [**設定**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="a02db-151">On your user's Windows PC that is running Windows 10, version 1703 (Creators Update), select the **Windows** logo, and then select the **Settings** icon.</span></span>
2. <span data-ttu-id="a02db-152">在 [**設定**] 中，移至 [**帳戶**。</span><span class="sxs-lookup"><span data-stu-id="a02db-152">In **Settings**, go to **Accounts**.</span></span>
3. <span data-ttu-id="a02db-153">在**您的資訊]** 頁面上，選取 [**存取公司或學校** > **連線**。</span><span class="sxs-lookup"><span data-stu-id="a02db-153">On the **Your info** page, select **Access work or school** > **Connect**.</span></span>
4. <span data-ttu-id="a02db-154">在 [**設定公司或學校帳戶**] 對話方塊中，[**其他動作**] 底下選取 [**加入至 Azure Active Directory 此裝置**]。</span><span class="sxs-lookup"><span data-stu-id="a02db-154">On the **Set up a work or school account** dialog, under **Alternate actions**, select **Join this device to Azure Active Directory**.</span></span>
5. <span data-ttu-id="a02db-155">在 [**讓我們協助您登入**] 頁面上，輸入您的工作或學校帳戶]，然後選取 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a02db-155">On the **Let's get you signed in** page, enter your work or school account, and select **Next**.</span></span>
6. <span data-ttu-id="a02db-156">在 [**輸入密碼**] 頁面中，輸入您的密碼，然後選取 [**登入**。</span><span class="sxs-lookup"><span data-stu-id="a02db-156">On the **Enter password** page, enter your password, and select **Sign in**.</span></span>
7. <span data-ttu-id="a02db-157">在 [**確認這是您的組織**] 頁面上，確認資訊正確，然後選取 [**加入**。</span><span class="sxs-lookup"><span data-stu-id="a02db-157">On the **Make sure this is your organization** page, verify that the information is correct, and select **Join**.</span></span>
8. <span data-ttu-id="a02db-158">在**一切就緒 ！**</span><span class="sxs-lookup"><span data-stu-id="a02db-158">On the **You're all set!**</span></span> <span data-ttu-id="a02db-159">] 頁面上，選取 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="a02db-159">page, select **Done**.</span></span>

<span data-ttu-id="a02db-160">完成後，就會連線到您組織的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="a02db-160">After you're done, the user will be connected to your organization's Azure AD.</span></span>

### <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="a02db-161">驗證裝置已連線到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="a02db-161">Verify the device is connected to Azure AD</span></span>
<span data-ttu-id="a02db-162">遵循下列步驟來驗證與 Azure AD 裝置的同步處理狀態，然後啟動 [在裝置上使用 Microsoft 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a02db-162">Follow these steps to verify the device’s sync status with Azure AD, and then start using your Microsoft 365 account on the device.</span></span> 

1. <span data-ttu-id="a02db-163">開啟 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="a02db-163">Open **Settings**.</span></span>
2. <span data-ttu-id="a02db-164">在 [**存取公司或學校資源**] 頁面上，選取 [**連接至<organization name>** 區域，以公開 [**資訊**] 以及 [**中斷連線**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a02db-164">On the **Access work or school** page, select the **Connected to <organization name>** area to expose the buttons **Info** and **Disconnect**.</span></span>
3. <span data-ttu-id="a02db-165">選取 [**資訊**]，以取得您同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="a02db-165">Select **Info** to get your synchronization status.</span></span>
4. <span data-ttu-id="a02db-166">在 [**同步處理狀態**] 頁面上，選取**同步處理**以取得最新的行動裝置管理原則至電腦。</span><span class="sxs-lookup"><span data-stu-id="a02db-166">On the **Sync status** page, select **Sync** to get the latest mobile device management policies onto the PC.</span></span>
5. <span data-ttu-id="a02db-167">若要開始使用 Microsoft 365 帳戶，請移至 Windows [**開始**] 按鈕以滑鼠右鍵按一下您目前的帳戶圖片，然後選取 [**切換**帳戶。</span><span class="sxs-lookup"><span data-stu-id="a02db-167">To start using the Microsoft 365 account, go to the Windows **Start** button, right-click your current account picture and then select **Switch** account.</span></span>
6. <span data-ttu-id="a02db-168">使用您的組織電子郵件和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="a02db-168">Sign in by using your organization email and password.</span></span>

<span data-ttu-id="a02db-169">如果您遇到問題，在企業環境中使用 Windows 10 時，您可以請洽詢[上方的 Microsoft 支援服務解決方案的最常見的問題](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)。</span><span class="sxs-lookup"><span data-stu-id="a02db-169">If you experience issues when using Windows 10 in an enterprise environment, you can consult [top Microsoft Support solutions for the most common issues](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions).</span></span> <span data-ttu-id="a02db-170">這些資源包括 KB 文章、 更新和文件庫文章。</span><span class="sxs-lookup"><span data-stu-id="a02db-170">These resources include KB articles, updates, and library articles.</span></span>

<span data-ttu-id="a02db-171">作為過渡期的檢查點，您可以看到對應至此步驟的[允出準則](windows10-exit-criteria.md#crit-windows10-step3)。</span><span class="sxs-lookup"><span data-stu-id="a02db-171">As an interim checkpoint, you can see the [exit criteria](windows10-exit-criteria.md#crit-windows10-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a02db-172">下一步</span><span class="sxs-lookup"><span data-stu-id="a02db-172">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="a02db-173">監控裝置健全狀況和合規性</span><span class="sxs-lookup"><span data-stu-id="a02db-173">Monitor device health and compliance</span></span>](windows10-enable-windows-analytics.md) |



<!--
## Phase 1: Consideration phase
This guide makes several assumptions regarding essential, business-critical considerations before upgrading an OS in an enterprise environment.

**Requirements**

Make sure you have the following requirements deployed and licensed.

| Product | License |
|:---|:---|
| Microsoft Intune | E3, E5, or Intune standalone |
| Azure AD Premium | E3 or E5 |
| Office 365 ProPlus | Business Premium, E3, E5, or Office 365 ProPlus standalone |

Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process. 

For Windows Autopilot, these are the infrastructure you need to take into account:

#### Group Policy
With Windows Autopilot, a device automatically joins their organization’s Azure AD group once a user signs into their organization from the device. The Group Policy policies (along with other customized settings and apps) are automatically pushed to the new device. It’s critical to understand that these policies must be properly configured within an organization before setting up Windows Autopilot profiles.

Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which need to be tested and implemented as part of a Windows 10 migration. The following resources provide examples on assessing current group policies for Windows, including Group Policy Objects in the Active Directory structure:

* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise


#### Data management
Be sure to back up user data if necessary. Because of the out-of-box experience (OOBE), user data isn't saved on a net-new computer. We recommend configuring a backup scenario as needed. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more info, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

We recommend using Windows Defender Antivirus and Windows Advanced Threat Protection (ATP). For more info, see [Enable Windows 10 Enterprise security features](windows10-enable-security-features.md)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostics data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see these resources:
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
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. You need to create deployment groups to help minimize the effect on network bandwidth.

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

To use Windows Autopilot, make sure you are ready to perform these tasks:
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [Diagnostics data](#step-4-diagnostics-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part of Windows deployment, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of Windows deployment, make sure you complete these tasks:
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

#### System requirements
To prepare for Windows 10 deployment through Windows Autopilot, make sure you meet these system requirements:
* Windows 10, version 1703 or later
* Intune licenses other mobile device management (MDM) services to manage devices
* Storage and bandwith requires minimal customization
* Diagnostic data (set at Basic level or above) - For more info, see [2.4 Diagnostic data](#24-diagnostic-data).
* Windows 10 Enterprise E3 or E5
* Devices must be registered to your organization - For more info, see [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
* Devices must be pre-installed with Windows 10, version 1703 or later
* Devices must have access to the Internet
* Azure AD Premium P1 or P2 is installed and configured and [automatic enrollment must be configured](https://go.microsoft.com/fwlink/?linkid=860700)

### Step 4: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in you organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. For more info, see:

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

See [Configure Windowsdiagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:

1. Enable auto-enrollment using Azure AD Premium.

    To allow this functionality, see [Enable Windows 10 automatic enrollment](https://go.microsoft.com/fwlink/?linkid=860990).

2. Register device ID.

    To register devices, you need to acquire their hardware IDs. Currently, we are working with hardware vendors to enable them to provide hardware IDs or upload them on their customer’s behalf.

    Currently, Surface supports Autopilot. Autopilot support from other hardware manufacturers are upcoming. 

    To capture the hardware ID information manually, use the Get-WindowsAutopilotInfo PowerShell script. The script generates a CSV file with the device's hardware ID. Install the PowerShellGet module, download the PowerShell script, run it, save the CSV file, and then upload it to the Microsoft Store for Business.

    For more info, see:
    * [Overview of registering devices to your organization](https://go.microsoft.com/fwlink/?linkid=860991)
    * [Install and upgrade PowerShellGet module](https://go.microsoft.com/fwlink/?linkid=861001)
    * [Use PowerShell to get the device hardware ID](https://go.microsoft.com/fwlink/?linkid=861007)

    By uploading this information to the [Microsoft Store for Business](https://go.microsoft.com/fwlink/?linkid=691471) or Partner Center admin portal, you'll be able to assign devices to your organization. These portals also provide additional options and customizations to configure your devices.

3. Deploy Office 365 ProPlus 2016 apps to Windows 10 devices using Intune.

    For a Microsoft 365 powered device, you'll need to deploy the Office 365 ProPlus 2016 suite to Windows 10 user groups. To do this:
    1. Configure the app suite by choosing specific Office 365 ProPlus apps.
    2. Configure app information, such as suite name, description, and category.
    3. Configure app settings, including versioning (32-bit versus 64-bit), the update channel, and languages.
    4. Save these configurations.

    The app suite should show up in the app panel. If you see an error message, see [Assign Office 365 ProPlus apps to devices that run Windows 10](https://go.microsoft.com/fwlink/?linkid=857153) to help troubleshoot the issue.

4. Deploy Windows Autopilot.

    You can manage devices for your organization and apply an Autopilot deployment profile to your devices. When people in your organization run the OOBE for the device, the profile configures Windows based on the Autopilot deployment profile you applied to the device. As part of the overall process, you need to perform these tasks:
    1. Add devices
    2. Group devices (optional)
    3. Create Autopilot deployment profile
    4. Apply Autopilot deployment profile

    For step-by-step guidance see [Manage Windows device deployment with Windows Autopilot](https://go.microsoft.com/fwlink/?linkid=852442).

    For end users, they can set up a device that's been configured through Autopilot by:
    1. Turning on the new Windows 10 device.
    2. Selecting the language.
    3. Connecting to a network.
    4. Entering their Azure AD email and password.

    Azure AD Join and MDM then automatically enroll the device. MDM also applies organization-configured policies, settings, and apps.

5. Manage Windows device deployment with Windows Autopilot deployment.

    You can manage new devices in the [Microsoft Store for Business](https://go.microsoft.com/fwlink/?linkid=691471). New devices must meet these requirements:
    * Have Windows 10, version 1703 or later installed
    * Have not been through Windows OOBE

    For more info, see [Manage Autopilot deployment profiles using Microsoft Store for Business](https://go.microsoft.com/fwlink/?linkid=852441).

-->


