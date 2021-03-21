---
title: Microsoft Teams
description: 如何在裝置上安裝團隊以及如何在以後更新
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、應用程式、企業營運服務應用程式、LOB 應用程式
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920653"
---
# <a name="microsoft-teams"></a><span data-ttu-id="67882-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67882-104">Microsoft Teams</span></span>

<span data-ttu-id="67882-105">[團隊](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) 是組織的 [郵件應用程式](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) ，也為您的組織提供即時共同作業和通訊、會議，以及檔案與應用程式共用的工作區。</span><span class="sxs-lookup"><span data-stu-id="67882-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="67882-106">初始部署</span><span class="sxs-lookup"><span data-stu-id="67882-106">Initial deployment</span></span>

<span data-ttu-id="67882-107">大多數的硬體廠商尚未加入小組做為影像的一部分，因此 Microsoft Managed Desktop 會使用 Microsoft Intune 將小組部署至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="67882-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="67882-108">所有受管理的裝置皆已安裝 [團隊 .msi 套件](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) ，以確保登入裝置的所有使用者都有準備好使用的 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="67882-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="67882-109">當套件第一次完成安裝時，小組會自動啟動並新增桌面的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="67882-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="67882-110">Microsoft Intune 變更</span><span class="sxs-lookup"><span data-stu-id="67882-110">Microsoft Intune changes</span></span>

<span data-ttu-id="67882-111">Microsoft Managed Desktop 將兩個應用程式新增至您的 Microsoft 小組 Azure AD 組織。</span><span class="sxs-lookup"><span data-stu-id="67882-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="67882-112">將其部署到適用于裝置的64位或32位用戶端：</span><span class="sxs-lookup"><span data-stu-id="67882-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="67882-113">新式的工作場所–小組電腦內安裝程式 x64</span><span class="sxs-lookup"><span data-stu-id="67882-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="67882-114">新式工作區-小組電腦範圍的安裝 x32</span><span class="sxs-lookup"><span data-stu-id="67882-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="67882-115">更新</span><span class="sxs-lookup"><span data-stu-id="67882-115">Updates</span></span>

<span data-ttu-id="67882-116">小組遵循來自 Microsoft 365 應用程式的不同更新路徑，而且桌面用戶端會自動更新自身。</span><span class="sxs-lookup"><span data-stu-id="67882-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="67882-117">小組每隔幾小時檢查一次更新，下載這些更新，然後等候電腦閒置，再無訊息安裝更新。</span><span class="sxs-lookup"><span data-stu-id="67882-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="67882-118">「小組」產品群組不允許系統管理員控制更新，所以 Microsoft 受管理的桌面會使用標準的「 [自動更新」通道](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。</span><span class="sxs-lookup"><span data-stu-id="67882-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="67882-119">手動更新團隊</span><span class="sxs-lookup"><span data-stu-id="67882-119">Manually updating Teams</span></span>

<span data-ttu-id="67882-120">個別使用者也可以從   應用程式右上角的 [ **設定檔**] 下拉式功能表中選取 [檢查更新]，以下載更新   。</span><span class="sxs-lookup"><span data-stu-id="67882-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="67882-121">如果有可用的更新，當電腦閒置時，它會被下載並以無訊息方式安裝。</span><span class="sxs-lookup"><span data-stu-id="67882-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="67882-122">更新的傳遞優化</span><span class="sxs-lookup"><span data-stu-id="67882-122">Delivery optimization of updates</span></span>

<span data-ttu-id="67882-123">小組的傳遞優化預設會開啟，且不需要系統管理員或使用者採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="67882-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>