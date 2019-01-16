---
title: 行動裝置管理基礎結構允出準則
description: Microsoft 365 企業版包含使用 Microsoft Intune 的行動裝置管理。檢閱需求和先決條件、 設定使用 Azure Active Directory 資源的 Intune、 註冊 iOS、 macOS、 Android、 及 Windows 裝置部署應用程式、 建立設定設定檔、 使用規範原則，並啟用的行動裝置的設定格式化的條件存取裝置管理與 Microsoft 365 企業版。
keywords: Microsoft 365、 Microsoft 365 企業版、 Microsoft 365 文件、 行動裝置管理 Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866290"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="ccecf-105">行動裝置管理基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="ccecf-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="ccecf-106">*這適用於 Microsoft 365 企業版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="ccecf-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="ccecf-107">將移至下一個階段式部署程序之前，請確定您的設定符合的行動裝置管理基礎結構需求如下。</span><span class="sxs-lookup"><span data-stu-id="ccecf-107">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="ccecf-108">已設定 Intune，包括建立 Azure AD 使用者和群組，以對裝置套用貴組織的規則。</span><span class="sxs-lookup"><span data-stu-id="ccecf-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="ccecf-109">您已在 Intune 中註冊裝置，以便這些裝置可以收到您建立的原則。</span><span class="sxs-lookup"><span data-stu-id="ccecf-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="ccecf-110">已將應用程式新增至裝置，讓您的使用者能夠存取貴組織的 Microsoft 365 雲端服務，例如 Exchange Online 和 Sharepoint。</span><span class="sxs-lookup"><span data-stu-id="ccecf-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="ccecf-111">已使用您建立的 Azure AD 使用者和群組，來設定功能和設定，並將它們套用到您的裝置，其中可能包含啟用防毒程式和限制特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="ccecf-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="ccecf-p102">已有適當的合規性原則，要求裝置上有防火牆或密碼長度限制。如果裝置不符合規範，則條件式存取封鎖區可存取貴組織的資料。</span><span class="sxs-lookup"><span data-stu-id="ccecf-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>

## <a name="next-phase"></a><span data-ttu-id="ccecf-114">下一個階段</span><span class="sxs-lookup"><span data-stu-id="ccecf-114">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="ccecf-115">在 Microsoft 365 企業版的端對端部署程序中的下一個階段是[資訊保護](infoprotect-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="ccecf-115">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [information protection](infoprotect-infrastructure.md).</span></span> |
