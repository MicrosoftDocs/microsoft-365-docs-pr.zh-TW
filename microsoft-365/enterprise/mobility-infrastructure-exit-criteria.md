---
title: 行動裝置管理基礎結構允出準則
description: Microsoft 365 企業版包含使用 Microsoft Intune 行動裝置管理。 檢閱需求和先決條件，設定 Intune 使用 Azure Active Directory 資源，註冊 iOS、 macOS、 Android 和 Windows 裝置，部署應用程式、 建立設定檔、 使用合規性政策，並啟用的行動裝置條件式存取使用 Microsoft 365 企業版的裝置管理。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 文件、 行動裝置管理、 Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: daf7bcf6525f30b7b52065e4f6bf2ff335f4ea4b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600880"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="6b512-105">行動裝置管理基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="6b512-105">Mobile device management infrastructure exit criteria</span></span>

![階段 5：行動裝置管理](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="6b512-107">*這適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="6b512-107">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6b512-108">請確定您的設定符合下列需求適用於行動裝置管理基礎結構。</span><span class="sxs-lookup"><span data-stu-id="6b512-108">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="6b512-109">已設定 Intune，包括建立 Azure Active Directory (Azure AD) 使用者和群組，將套用的裝置貴組織的規則。</span><span class="sxs-lookup"><span data-stu-id="6b512-109">Intune is set up, including the creation of Azure Active Directory (Azure AD) users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="6b512-110">您已在 Intune 中註冊裝置，以便這些裝置可以收到您建立的原則。</span><span class="sxs-lookup"><span data-stu-id="6b512-110">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="6b512-111">已將應用程式新增至裝置，讓您的使用者能夠存取貴組織的 Microsoft 365 雲端服務，例如 Exchange Online 和 Sharepoint。</span><span class="sxs-lookup"><span data-stu-id="6b512-111">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="6b512-112">已使用您建立的 Azure AD 使用者和群組，來設定功能和設定，並將它們套用到您的裝置，其中可能包含啟用防毒程式和限制特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="6b512-112">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="6b512-113">合規性原則已備妥需要防火牆或裝置上的密碼長度。</span><span class="sxs-lookup"><span data-stu-id="6b512-113">Compliance policies are in place to require a firewall or a password length on a device.</span></span> <span data-ttu-id="6b512-114">如果裝置不相容，條件式存取封鎖您的組織資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="6b512-114">If devices aren't compliant, Conditional Access blocks access to your organization's data.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="6b512-115">結果和後續步驟</span><span class="sxs-lookup"><span data-stu-id="6b512-115">Results and next steps</span></span>

<span data-ttu-id="6b512-116">您的裝置已在 Intune 中註冊，並具有適當的原則設定。</span><span class="sxs-lookup"><span data-stu-id="6b512-116">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![階段 6：資訊保護](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="6b512-118">如果您正在追蹤的 Microsoft 365 企業版端對端部署階段下, 一個階段是[資訊保護](infoprotect-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="6b512-118">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
