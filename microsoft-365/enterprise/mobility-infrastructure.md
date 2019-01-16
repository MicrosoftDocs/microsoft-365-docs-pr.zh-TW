---
title: 階段 5-行動裝置管理
description: Microsoft 365 企業版包含使用 Microsoft Intune 的行動裝置管理。檢閱需求和先決條件、 設定使用 Azure Active Directory 資源的 Intune、 註冊 iOS、 macOS、 Android、 及 Windows 裝置部署應用程式、 建立設定設定檔、 使用規範原則，並啟用的行動裝置的設定格式化的條件存取裝置管理與 Microsoft 365 企業版。
keywords: Microsoft 365、 Microsoft 365 企業版、 Microsoft 365 文件、 行動裝置管理 Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: 3afc28f0d21918c027a6a1622a40318e333f7ab4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866776"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a><span data-ttu-id="1b663-105">階段 5： 行動裝置管理的 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="1b663-105">Phase 5: Mobile device management for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

<span data-ttu-id="1b663-106">*此功能適用於 Microsoft 365 企業版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="1b663-106">*This feature applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="1b663-p102">Microsoft 365 企業版包含可協助您管理裝置和其應用程式]，在組織內的功能。您可以使用 Microsoft Intune，管理 iOS、 Android、 macOS、 及 Windows 裝置來保護您的組織資源，包括您的資料的存取權。Intune 與 Azure Active Directory (Azure AD)、 整合及 Microsoft 365 會啟用下列商務案例：</span><span class="sxs-lookup"><span data-stu-id="1b663-p102">Microsoft 365 Enterprise includes features to help manage devices, and their apps, within your organization. Using Microsoft Intune, you can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data. Intune integrates with Azure Active Directory (Azure AD), and enables the following business scenarios for Microsoft 365:</span></span>

- <span data-ttu-id="1b663-110">在組織內外部儲存及共用檔案，順暢地跨越組織界限工作</span><span class="sxs-lookup"><span data-stu-id="1b663-110">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="1b663-111">隨時隨地在裝置上安全地工作，以達成更多目標，同時維持彈性的工作方式</span><span class="sxs-lookup"><span data-stu-id="1b663-111">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="1b663-112">通過產業驗證符合合規性的全球標準，提供控制和可見度讓您安心</span><span class="sxs-lookup"><span data-stu-id="1b663-112">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="1b663-113">保護您的資訊，並降低資料遺失風險</span><span class="sxs-lookup"><span data-stu-id="1b663-113">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="1b663-114">偵測及防範外部威脅</span><span class="sxs-lookup"><span data-stu-id="1b663-114">Detect and protect against external threats</span></span>
- <span data-ttu-id="1b663-115">監控、 報告及分析活動回應立即提供組織的安全性</span><span class="sxs-lookup"><span data-stu-id="1b663-115">Monitor, report, and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="1b663-116">保護您的使用者和其帳戶</span><span class="sxs-lookup"><span data-stu-id="1b663-116">Protect your users and their accounts</span></span>

<span data-ttu-id="1b663-117">如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。</span><span class="sxs-lookup"><span data-stu-id="1b663-117">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

<span data-ttu-id="1b663-p103">在此階段中，您註冊您的裝置在 Intune，並建立並強制執行原則，以協助保護您的資料安全無虞且受保護。Intune 文件的整個文件庫[提供線上](https://docs.microsoft.com/intune)。它也是很好的作法您開始之前檢閱[Intune 部署規劃、 設計及實作指南](https://docs.microsoft.com/intune/planning-guide)。</span><span class="sxs-lookup"><span data-stu-id="1b663-p103">In this phase, you enroll your devices in Intune, and create and enforce policies to help keep your data secure and protected. The entire library of Intune documentation is [available online](https://docs.microsoft.com/intune). It's also good practice to review the [Intune deployment planning, design and implementation guide](https://docs.microsoft.com/intune/planning-guide) before you get started.</span></span>

## <a name="step-1-plan-for-your-scenario"></a><span data-ttu-id="1b663-121">步驟 1： 規劃您的案例</span><span class="sxs-lookup"><span data-stu-id="1b663-121">Step 1: Plan for your scenario</span></span>

<span data-ttu-id="1b663-p104">其中一個來管理行動裝置的主要原因是安全性和保護組織的資源。[若要使用 Microsoft Intune 的常見方法](https://docs.microsoft.com/intune/common-scenarios)會列出一些真實世界範例，包括保護 Office 365 電子郵件和資料。</span><span class="sxs-lookup"><span data-stu-id="1b663-p104">One of the main reasons to manage mobile devices is to secure and protect your organization's resources. [Common ways to use Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) lists some real-world examples, including securing Office 365 email and data.</span></span>

<span data-ttu-id="1b663-p105">Intune 可讓您管理存取權使用[行動裝置管理 (MDM) 或行動應用程式管理 」 (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions)您組織的選項。使用者的 「 註冊"Intune 在其裝置時 MDM。一旦註冊，它們是受管理的裝置，並可以收到任何原則、 規則及貴組織所使用的設定。例如，您可以安裝在您的應用程式建立密碼原則、 安裝 VPN 連線，等。</span><span class="sxs-lookup"><span data-stu-id="1b663-p105">Intune gives you options to manage access to your organization using [Mobile Device Management (MDM) or Mobile Application Management (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions). MDM is when users "enroll" their devices in Intune. Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization. For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="1b663-p106">使用自己的個人裝置的使用者可能不想要註冊裝置，或由 Intune 與您的原則管理。但是，您仍然需要保護組織的資源和資料。您可以在此案例中，來保護您的應用程式使用 MAM。例如，您可以使用需要使用者在裝置上存取 SharePoint 時輸入 PIN MAM 原則。</span><span class="sxs-lookup"><span data-stu-id="1b663-p106">Users with their own personal devices may not want to enroll their devices, or be managed by Intune and your policies. But, you still need to protect your organization's resources and data. In this scenario, you can protect your apps using MAM. For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="1b663-p107">您也將決定您要管理個人或組織擁有的裝置的方式。若要以不同方式，將根據其使用的裝置。例如，您可能想使用者不同的計劃人力資源 (HR) 或銷售中的使用者。[身分識別行動裝置管理的使用案例案例](https://docs.microsoft.com/intune/planning-guide-scenarios)可讓您從開始，並包含一些這些不同案例的指導。</span><span class="sxs-lookup"><span data-stu-id="1b663-p107">You'll also determine how you're going to manage personal or organization-owned devices. You may want to treat devices differently, depending on their use. For example, you may want different plans for users in Human Resources (HR) or users in Sales. [Identify mobile device management use-case scenarios](https://docs.microsoft.com/intune/planning-guide-scenarios) can get you started, and includes some guidance on these different scenarios.</span></span>

## <a name="step-2-get-your-prerequisites"></a><span data-ttu-id="1b663-136">步驟 2： 取得您的必要條件</span><span class="sxs-lookup"><span data-stu-id="1b663-136">Step 2: Get your prerequisites</span></span>

<span data-ttu-id="1b663-p108">接下來，取得您根據自己的必要條件與您在上一個步驟中建立的情況。[實作您計劃](https://docs.microsoft.com/intune/planning-guide-onboarding)列出所有的需求。以下是您需要的 Microsoft 365 Intune 的重要項目：</span><span class="sxs-lookup"><span data-stu-id="1b663-p108">Next, get your prerequisites based on your requirements and your scenarios created in the previous step. [Implement your plan](https://docs.microsoft.com/intune/planning-guide-onboarding) lists all the requirements. Here are the significant items you need for Intune with Microsoft 365:</span></span>

- <span data-ttu-id="1b663-140">**Intune 訂閱**： 隨附於 Microsoft 365，以及可讓您存取 Microsoft Intune [Azure 入口網站](https://portal.azure.com)中</span><span class="sxs-lookup"><span data-stu-id="1b663-140">**Intune subscription**: Included with Microsoft 365, and gives you access to Microsoft Intune in the [Azure portal](https://portal.azure.com)</span></span>
- <span data-ttu-id="1b663-141">**Office 365 訂閱**： 隨附於 Microsoft 365 並可用於 Office 的應用程式，包括電子郵件</span><span class="sxs-lookup"><span data-stu-id="1b663-141">**Office 365 subscription**: Included with Microsoft 365, and is used for Office apps, including email</span></span>
- <span data-ttu-id="1b663-p109">**Azure Active Directory (AD) premium**： 隨附於 Microsoft 365 和用以建立使用者或安全性群組。這些群組會收到 Intune 原則的建立，例如強迫裝置解除鎖定的密碼長度。您建立的群組[階段 2： identity 為](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)可用。</span><span class="sxs-lookup"><span data-stu-id="1b663-p109">**Azure Active Directory (AD) premium**: Included with Microsoft 365, and is used to create user or security groups. These groups receive Intune policies that you create, such as forcing a password length to unlock a device. The groups you create in [Phase 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) can be used.</span></span>

<span data-ttu-id="1b663-p110">可能會有一些其他需求，根據貴組織的需求而定。例如，如果您將管理 iOS 裝置，您將需要 Apple MDM 推入的憑證。如果您使用內部部署 Exchange，則您需要在內部部署 Exchange 連接器。這些額外的需求所概述當您取得這些步驟。</span><span class="sxs-lookup"><span data-stu-id="1b663-p110">There may be some additional requirements, depending on your organization's needs. For example, if you'll be managing iOS devices, you'll need an Apple MDM Push certificate. If you're using on-premises Exchange, then you'll need the on-premises Exchange connector. These additional requirements are outlined when you get to those steps.</span></span>

## <a name="step-3-set-up-intune"></a><span data-ttu-id="1b663-149">步驟 3： 設定 Intune</span><span class="sxs-lookup"><span data-stu-id="1b663-149">Step 3: Set up Intune</span></span>

<span data-ttu-id="1b663-p111">Intune Azure AD，包括您的網域、 您的使用者及群組中使用許多功能。您也可以建立新的使用者與新的群組以符合您公司的需求。例如，您可以建立一個稱為 「 **iOS 裝置**或**所有 HR 使用者**群組。 善用[動態群組](https://docs.microsoft.com/intune/groups-add)，可讓您建立使用者或裝置群組基礎周圍簡單或進階的規則。</span><span class="sxs-lookup"><span data-stu-id="1b663-p111">Intune uses many features in Azure AD, including your domain, your users, and your groups. You can also create new users and new groups to fit your company needs. For example, you can create a group called **iOS devices**, or **All HR users**.  Take advantage of [Dynamic Groups](https://docs.microsoft.com/intune/groups-add) that lets you build either user or device groups based around simple or advanced rules.</span></span>

<span data-ttu-id="1b663-154">此步驟著重於 Intune、 設定與取得備妥可供您管理您的裝置。</span><span class="sxs-lookup"><span data-stu-id="1b663-154">This step focuses on setting up Intune, and getting it ready for you to manage your devices.</span></span>

1. <span data-ttu-id="1b663-p112">**[確認您的裝置支援](https://docs.microsoft.com/intune/supported-devices-browsers)**。確認您的 iOS macOS、 Android、 Galaxy、 和 Windows 裝置支援的 Intune。如果您的組織包含不受支援的裝置，原則不會套用至這些裝置。</span><span class="sxs-lookup"><span data-stu-id="1b663-p112">**[Confirm your devices are supported](https://docs.microsoft.com/intune/supported-devices-browsers)**. Confirm your iOS, macOS, Android, Galaxy, and Windows devices are supported by Intune. If your organization includes devices that aren't supported, then the policies aren't applied to those devices.</span></span>

2. <span data-ttu-id="1b663-p113">**[自訂您的網域名稱](https://docs.microsoft.com/intune/custom-domain-name-configure)**。根據預設，在網域名為像是**your domain.onmicrosoft.com**會自動建立的 Azure AD。**onmicrosoft.com**可以自訂您的組織。當您自訂它也提供使用者熟悉的網域連線時 Intune 及使用的資源。</span><span class="sxs-lookup"><span data-stu-id="1b663-p113">**[Customize your domain name](https://docs.microsoft.com/intune/custom-domain-name-configure)**. By default, a domain named something like **your-domain.onmicrosoft.com** is automatically created in Azure AD. **onmicrosoft.com** can be customized for your organization. When you customize, it also gives users a familiar domain when connecting to Intune and using resources.</span></span>

3. <span data-ttu-id="1b663-p114">**[登入 Intune](https://docs.microsoft.com/intune/account-sign-up)**。當您登入時，您可能會提示您輸入組織的相關資訊。Intune 功能隨附於 Microsoft 365 並可以直接從[Office 365 系統入口網站](https://portal.office.com/)開啟。您也可以直接從[Azure 入口網站](https://portal.azure.com)開啟 Intune。</span><span class="sxs-lookup"><span data-stu-id="1b663-p114">**[Sign in to Intune](https://docs.microsoft.com/intune/account-sign-up)**. When you sign in, you may be prompted to enter information about your organization. Intune is included with Microsoft 365, and can be opened directly from the [Office 365 Admin portal](https://portal.office.com/). You can also open Intune directly from the [Azure portal](https://portal.azure.com).</span></span>

4. <span data-ttu-id="1b663-p115">**[選擇您的行動裝置管理設定](https://docs.microsoft.com/intune/mdm-authority-set)**。第一次使用 Intune，您必須啟用裝置管理。Intune 可以做僅限雲端服務時，使用 Intune 和 System Center Configuration Manager，或使用行動裝置管理 Office 365 的混合式。您可以選擇的安裝程式最適用於您的組織。</span><span class="sxs-lookup"><span data-stu-id="1b663-p115">**[Choose your mobile device management configuration](https://docs.microsoft.com/intune/mdm-authority-set)**. The first time you use Intune, you must enable device management. Intune can be used as a cloud-only service, a hybrid with Intune and System Center Configuration Manager, or using Mobile Device Management for Office 365. You can choose which setup works best for your organization.</span></span>

5. <span data-ttu-id="1b663-170">**[新增使用者](https://docs.microsoft.com/intune/users-add)** 並**[加入群組](https://docs.microsoft.com/intune/groups-add)**。</span><span class="sxs-lookup"><span data-stu-id="1b663-170">**[Add users](https://docs.microsoft.com/intune/users-add)** and **[add groups](https://docs.microsoft.com/intune/groups-add)**.</span></span> 

   <span data-ttu-id="1b663-p116">可以手動新增使用者或連線至同步處理使用者 intune 的 Azure AD。您也可以提供給特定使用者的系統管理員角色。除非您的裝置是"userless"的裝置，例如 kiosk 裝置的使用者是必要的。</span><span class="sxs-lookup"><span data-stu-id="1b663-p116">You can manually add users, or connect to Azure AD to sync users with Intune. You can also give Admin roles to specific users. Users are required unless your devices are "userless" devices, such as kiosk devices.</span></span>

   <span data-ttu-id="1b663-p117">Azure AD 群組用以簡化如何管理裝置和 Intune 中的使用者。使用群組，您可以執行許多不同的工作。例如，您的組織想要需要 Android 裝置上的特定應用程式。您可以建立 Android 裝置] 群組中，以及部署至群組與此應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="1b663-p117">Azure AD groups are used to simplify how you manage devices and users in Intune. Using groups, you can do many different tasks. For example, your organization wants to require a specific app on Android devices. You can create an Android devices group, and deploy a policy with this app to the group.</span></span>

    <span data-ttu-id="1b663-178">您可以在 Intune，新增您建立的使用者或群組[階段 2： identity 為](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)</span><span class="sxs-lookup"><span data-stu-id="1b663-178">In Intune, you can add users or groups that you create in [Phase 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)</span></span>

6. <span data-ttu-id="1b663-p118">**[指派授權](https://docs.microsoft.com/intune/licenses-assign)**。使用者或裝置在 Intune 中註冊，他們必須在裝置上的授權。每個使用者或 userless 裝置需要存取 Intune service Intune 授權。這些授權包含 Microsoft 365，必須具有 Intune。</span><span class="sxs-lookup"><span data-stu-id="1b663-p118">**[Assign licenses](https://docs.microsoft.com/intune/licenses-assign)**. For users or devices to enroll in Intune, they need a license on the device. Each user or userless device requires an Intune license to access the Intune service. These licenses are included with Microsoft 365, and must be assigned in Intune.</span></span>

## <a name="step-4-enroll-devices"></a><span data-ttu-id="1b663-183">步驟 4： 註冊裝置</span><span class="sxs-lookup"><span data-stu-id="1b663-183">Step 4: Enroll devices</span></span>

<span data-ttu-id="1b663-p119">若要管理裝置，裝置必須註冊參與 Intune。身為管理員，您將設定註冊限制和原則的使用者和裝置。每個裝置的平台 （iOS、 Android、 macOS、 及 Windows） 具有各種選項。您可以讓您註冊自己的使用者。或者，您可以讓使用者直接登入裝置自動化註冊。</span><span class="sxs-lookup"><span data-stu-id="1b663-p119">To manage devices, the devices must be enrolled in Intune. As an administrator, you’ll set up enrollment restrictions and policies for your users and devices. Each device platform (iOS, Android, macOS, and Windows) has a variety of options. You can have your users enroll themselves. Or, you can automate enrollment so users simply sign in to the device.</span></span>

<span data-ttu-id="1b663-p120">註冊使用 Intune 時的關鍵步驟。[註冊裝置](https://docs.microsoft.com/intune/device-enrollment)列出不同裝置的步驟。</span><span class="sxs-lookup"><span data-stu-id="1b663-p120">Enrollment is a key step when using Intune. [Enroll devices](https://docs.microsoft.com/intune/device-enrollment) lists the steps for the different devices.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="1b663-192">Test Lab Guide: iOS 及 Android 裝置註冊</span><span class="sxs-lookup"><span data-stu-id="1b663-192">Test Lab Guide: iOS and Android device enrollment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a><span data-ttu-id="1b663-193">步驟 5： 新增及部署應用程式</span><span class="sxs-lookup"><span data-stu-id="1b663-193">Step 5: Add and deploy apps</span></span>

<span data-ttu-id="1b663-194">在行動裝置上的應用程式通常會最快的讓使用者取得貴公司資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="1b663-194">Apps on mobile devices are often the quickest way users get access to your corporate resources.</span></span> 

<span data-ttu-id="1b663-p121">挑戰當使用應用程式]，如有有不同的裝置，包括個人裝置和公司的裝置。然後您想要同時確保使用者會提高工作效率保護組織的資源和其資料。</span><span class="sxs-lookup"><span data-stu-id="1b663-p121">There are challenges when using apps, as there are different devices, including personal devices and corporate devices. And, you want to protect your organization's resources and its data while also making sure users are productive.</span></span>

<span data-ttu-id="1b663-p122">Intune 可以管理應用程式，包括新增應用程式、 指派給不同的使用者或群組，以及檢閱其他重要詳細資料。例如，您可以看到應用程式無法安裝，並檢查應用程式及更多的版本。</span><span class="sxs-lookup"><span data-stu-id="1b663-p122">Intune can manage apps, including add apps, assign them to different users or groups, and review other key details. For example, you can see which apps fail to install, check the version of an app, and more.</span></span>

<span data-ttu-id="1b663-p123">當使用者能在行動裝置時，其中第一個工作是存取組織的電子郵件和文件。使用 Intune，您可以[建立和部署電子郵件設定](https://docs.microsoft.com/intune/email-settings-configure)在裝置上使用預先安裝的電子郵件應用程式。</span><span class="sxs-lookup"><span data-stu-id="1b663-p123">When users get a mobile device, one of the first tasks is to access organizational email and documents. Using Intune, you can [create and deploy email settings](https://docs.microsoft.com/intune/email-settings-configure) using email apps that are pre-installed on the devices.</span></span> 

<span data-ttu-id="1b663-201">[新增應用程式](https://docs.microsoft.com/intune/app-management)清單新增、 部署、 監視、 設定及保護貴組織內的裝置上的應用程式的步驟</span><span class="sxs-lookup"><span data-stu-id="1b663-201">[Add apps](https://docs.microsoft.com/intune/app-management) lists the steps to add, deploy, monitor, configure, and protect apps on devices within your org.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="1b663-203">Test Lab Guide： 裝置規範遵守原則</span><span class="sxs-lookup"><span data-stu-id="1b663-203">Test Lab Guide: Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a><span data-ttu-id="1b663-204">步驟 6： 開啟規範及設定格式化的條件的存取</span><span class="sxs-lookup"><span data-stu-id="1b663-204">Step 6: Turn on compliance and conditional access</span></span>

<span data-ttu-id="1b663-p124">在先前步驟中，您可以設定您的環境，並啟用 Intune。現在，即準備好建立一些使用規範與條件式存取的原則。</span><span class="sxs-lookup"><span data-stu-id="1b663-p124">In the previous steps, you set up your environment, and enabled Intune. Now, you're ready to create some policies using compliance and conditional access.</span></span>

<span data-ttu-id="1b663-p125">規範與條件式存取至關重要管理裝置。若要協助保護組織的資源建立**[規範遵守原則](https://docs.microsoft.com/intune/device-compliance-get-started)**。當您建立規範原則時、 您定義的標準版或裝置必須具備的"基準"。例如，您可以選擇可接受 （或無法接受） 的威脅層級、 封鎖 jailbroken 裝置、 需要的密碼長度、 等等。如果這些裝置不符合您的規則，這表示它們不相容，您可以在資源封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="1b663-p125">Compliance and conditional access are important to managing devices. **[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started)** are created to help protect your organization's resources. When you create a compliance policy, you're defining the standard or the "baseline" of what a device must have. For example, you can choose an acceptable (or unacceptable) threat level, block jailbroken devices, require a password length, and more. If these devices don't meet your rules, meaning they aren't compliant, then you can block access to your resources.</span></span>

<span data-ttu-id="1b663-p126">此 「 封鎖 」 引進**[設定格式化的條件的存取](https://docs.microsoft.com/intune/conditional-access)**。如果裝置會被視為不相容的您可以封鎖存取電子郵件、 SharePoint 及其他。</span><span class="sxs-lookup"><span data-stu-id="1b663-p126">This "blocking" introduces **[Conditional access](https://docs.microsoft.com/intune/conditional-access)**. If a device is considered not-compliant, then you can block access to email, SharePoint, and more.</span></span>

<span data-ttu-id="1b663-p127">[Azure 入口網站](https://portal.azure.com)中的 Intune 可讓您建立這些原則，並將其套用至您的使用者和裝置。最佳作法是啟動小型，並使用分段的方法。例如，建立封鎖 jailbroken 裝置 iOS 原則。（稱為 「 指派 」 中 Intune） 原則套用至試驗或測試群組。在初始測試之後將更多使用者加入試驗群組。使用分段的方法，您可以透過各種使用者類型取得意見反應。</span><span class="sxs-lookup"><span data-stu-id="1b663-p127">Intune in the [Azure portal](https://portal.azure.com) lets you create these policies, and apply them to your users and devices. As a best practice, start small, and use a staged approach. For example, create an iOS policy that blocks jailbroken devices. Apply (called "assign" in Intune) the policy to a pilot or test group. After initial testing, add more users to the pilot group. Using a staged approach, you can get feedback from a wide range of user types.</span></span>

<span data-ttu-id="1b663-220">[開始使用裝置規範遵守原則](https://docs.microsoft.com/intune/device-compliance-get-started)和[什麼是設定格式化的條件存取？](https://docs.microsoft.com/intune/conditional-access)可協助您開始。</span><span class="sxs-lookup"><span data-stu-id="1b663-220">[Get started with device compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) and [What's conditional access?](https://docs.microsoft.com/intune/conditional-access) can help you get started.</span></span>

## <a name="step-7-apply-features-and-settings"></a><span data-ttu-id="1b663-221">步驟 7： 適用於功能和設定</span><span class="sxs-lookup"><span data-stu-id="1b663-221">Step 7: Apply features and settings</span></span>

<span data-ttu-id="1b663-p128">這些功能和設定通常被視為 Intune，"相當酷"組件和非常強大。一旦您已成功強制執行使用設定格式化的條件 access 一些規範遵守原則，即準備好建立**裝置設定檔**。</span><span class="sxs-lookup"><span data-stu-id="1b663-p128">These features and settings are often considered the "cool" part of Intune, and are very powerful. Once you've successfully enforced some compliance policies using conditional access, you're ready to create **Device profiles**.</span></span>

<span data-ttu-id="1b663-p129">[Azure 入口網站](https://portal.azure.com)中的 Intune 可讓您建立不同的設定檔根據您的裝置平台-iOS、 macOS、 Android、 及 Windows。例如，您可以：</span><span class="sxs-lookup"><span data-stu-id="1b663-p129">Intune in the [Azure portal](https://portal.azure.com) lets you create different profiles based on your device platform - iOS, macOS, Android, and Windows. For example, you can:</span></span>

- <span data-ttu-id="1b663-226">使用 Windows 10 裝置上的端點保護啟用不同 BitLocker 選項，包括加密。</span><span class="sxs-lookup"><span data-stu-id="1b663-226">Use Endpoint protection on Windows 10 devices to enable different BitLocker options, including encryption.</span></span>
- <span data-ttu-id="1b663-p130">使用 iOS 裝置上的受限制的應用程式功能來建立可安裝的已核准應用程式的清單。或者，建立禁止的應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="1b663-p130">Use the Restricted apps feature on iOS devices to create a list of approved apps that can be installed. Or, create a list of prohibited apps.</span></span>
- <span data-ttu-id="1b663-229">使用 Kiosk 設定，選擇 [應用程式可用於直在 kiosk 模式中執行 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="1b663-229">Use the Kiosk settings to choose which apps can be used on Android devices running in kiosk mode.</span></span>
- <span data-ttu-id="1b663-230">適用於 Wi-fi 連線以及其設定，包括安全性類型執行 macOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="1b663-230">Apply a Wi-Fi connection and its settings, including the security type, on devices running macOS.</span></span>
- <span data-ttu-id="1b663-231">等等</span><span class="sxs-lookup"><span data-stu-id="1b663-231">And more</span></span>

<span data-ttu-id="1b663-232">[什麼是 Microsoft Intune 裝置設定檔？](https://docs.microsoft.com/intune/device-profiles)會將閱讀設定檔的相關資訊，請參閱 ＜ 如何建立設定檔、 等等。</span><span class="sxs-lookup"><span data-stu-id="1b663-232">[What are Microsoft Intune device profiles?](https://docs.microsoft.com/intune/device-profiles) is a great place to read about profiles, see how to create a profile, and more.</span></span>

<span data-ttu-id="1b663-p131">請記住、 啟動小，並使用分段的方法。將設定檔指派給試驗或測試群組。然後將該設定檔指派給多個試驗群組。</span><span class="sxs-lookup"><span data-stu-id="1b663-p131">Remember, start small, and use a staged approach. Assign the profile to a pilot or test group. Then, assign the profile to more pilot groups.</span></span>

## <a name="step-8-get-to-know-the-other-features"></a><span data-ttu-id="1b663-236">步驟 8： 取得知道其他功能</span><span class="sxs-lookup"><span data-stu-id="1b663-236">Step 8: Get to know the other features</span></span>

<span data-ttu-id="1b663-p132">Intune 是功能強大的服務，並提供了許多功能。以下是一些您可以使用 Intune 的工作：</span><span class="sxs-lookup"><span data-stu-id="1b663-p132">Intune is a powerful service, and includes many features. Here are some other tasks you can do using Intune:</span></span>

- <span data-ttu-id="1b663-239">管理軟體和 Windows[裝置](https://docs.microsoft.com/intune/windows-update-for-business-configure)上的更新 & [Pc](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)、 和[iOS](https://docs.microsoft.com/intune/software-updates-ios)裝置</span><span class="sxs-lookup"><span data-stu-id="1b663-239">Manage software and updates on Windows [devices](https://docs.microsoft.com/intune/windows-update-for-business-configure) & [PCs](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune), and [iOS](https://docs.microsoft.com/intune/software-updates-ios) devices</span></span>
- <span data-ttu-id="1b663-240">在您的 Windows 10 裝置上開啟[Windows 防禦者進階威脅保護 (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection)並使用保護存取公司資源，例如 SharePoint 或 Exchange Online 的規範與條件式存取</span><span class="sxs-lookup"><span data-stu-id="1b663-240">Turn on [Windows Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) on your Windows 10 devices, and use compliance and conditional access to protect access to corporate resources, such as SharePoint or Exchange Online</span></span>
- <span data-ttu-id="1b663-241">使用[瞭望台](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector)、 [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)、 和其他行動裝置的防禦威脅協力廠商</span><span class="sxs-lookup"><span data-stu-id="1b663-241">Use [Lookout](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector), and other mobile defense threat partners</span></span>
- <span data-ttu-id="1b663-242">新增[協力廠商憑證授權單位 (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview)核發及更新的憑證</span><span class="sxs-lookup"><span data-stu-id="1b663-242">Add a [partner certificate authority (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) to issue and renew certificates</span></span>
- <span data-ttu-id="1b663-243">[為一般使用者提供指引](https://docs.microsoft.com/intune/end-user-educate)上的公司入口網站應用程式、 快速應用程式] 及其他</span><span class="sxs-lookup"><span data-stu-id="1b663-243">[Provide guidance to your end users](https://docs.microsoft.com/intune/end-user-educate) on the Company Portal app, getting apps, and more</span></span>
- <span data-ttu-id="1b663-p133">監視[應用程式](https://docs.microsoft.com/intune/apps-monitor)、 監視器[裝置規範](https://docs.microsoft.com/intune/compliance-policy-monitor)、 監視[設定設定檔](https://docs.microsoft.com/intune/compliance-policy-monitor)及更多遙測使用稽核記錄檔。您也可以連線至[Intune 資料倉儲](https://docs.microsoft.com/intune/reports-nav-create-intune-reports)並使用更多的報表需求的 Power BI。</span><span class="sxs-lookup"><span data-stu-id="1b663-p133">Monitor [apps](https://docs.microsoft.com/intune/apps-monitor), monitor [device compliance](https://docs.microsoft.com/intune/compliance-policy-monitor), monitor [configuration profiles](https://docs.microsoft.com/intune/compliance-policy-monitor), and more telemetry using the audit logs. You can also connect to the [Intune Data Warehouse](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) and use Power BI for even more reporting needs.</span></span>


## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="1b663-246">身分識別與裝置存取建議</span><span class="sxs-lookup"><span data-stu-id="1b663-246">Identity and device access recommendations</span></span>

<span data-ttu-id="1b663-p134">Microsoft 提供建議以確保安全並提高工作效率的人力的[身分識別與裝置存取](microsoft-365-policies-configurations.md)的一的組。裝置存取使用建議和設定步驟以及下列文章中本階段中：</span><span class="sxs-lookup"><span data-stu-id="1b663-p134">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For device access, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="1b663-249">必要條件</span><span class="sxs-lookup"><span data-stu-id="1b663-249">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="1b663-250">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="1b663-250">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="1b663-251">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="1b663-251">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1b663-252">了解如何在 Microsoft 的 IT 專家為規劃及部署這些資源的 EMS 與裝置管理：</span><span class="sxs-lookup"><span data-stu-id="1b663-252">Learn how IT experts at Microsoft planned for and deployed EMS and device management with these resources:</span></span>

- <span data-ttu-id="1b663-253">[使用企業行動力 + 安全性管理現代行動生產力](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security) (英文)</span><span class="sxs-lookup"><span data-stu-id="1b663-253">[Managing modern mobile productivity with Enterprise Mobility + Security](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)</span></span>
- <span data-ttu-id="1b663-254">[使用 Microsoft Intune 連線到公司的 Windows 10 裝置](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune) (英文)</span><span class="sxs-lookup"><span data-stu-id="1b663-254">[Connecting to work on your Windows 10 device with Microsoft Intune](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)</span></span>
- <span data-ttu-id="1b663-255">[為 Microsoft 的 iOS、OS X 和 Android 設備啟用移動生產力](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft) (英文)</span><span class="sxs-lookup"><span data-stu-id="1b663-255">[Enabling mobile productivity for iOS, OS X, and Android devices at Microsoft](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="1b663-256">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="1b663-256">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1b663-257">請參閱[部署其行動裝置管理基礎結構](contoso-mdm.md)與 Microsoft 365 Contoso Corporation 虛構但代表性多重國民 business 雲端服務的方式。</span><span class="sxs-lookup"><span data-stu-id="1b663-257">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="1b663-258">下一步</span><span class="sxs-lookup"><span data-stu-id="1b663-258">Next step</span></span>

[<span data-ttu-id="1b663-259">行動裝置管理基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="1b663-259">Mobile device management infrastructure exit criteria</span></span>](mobility-infrastructure-exit-criteria.md)

