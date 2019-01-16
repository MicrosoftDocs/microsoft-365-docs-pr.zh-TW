---
title: 準備您的組織 Windows 10 Enterprise
description: 提供高階指導您部署的 Pc 上的 Windows 10 Enterprise 做為 Microsoft 365 企業版的一部分所需的步驟。
keywords: Microsoft 365、 Microsoft 365 企業版、 Microsoft 365 文件、 Windows 10 企業部署
author: JoeDavies-MSFT
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 21a4198c688e1865a029f18ff3ceeb2155d419e4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866653"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a><span data-ttu-id="22a51-104">步驟 1： 準備您的組織 Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="22a51-104">Step 1: Prepare your organization for Windows 10 Enterprise</span></span>

<span data-ttu-id="22a51-105">*本文適用於 Microsoft 365 企業版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="22a51-105">*This article applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="22a51-106">升級您的裝置為 Windows 10 Enterprise、 之前考量下列項目：</span><span class="sxs-lookup"><span data-stu-id="22a51-106">Before upgrading your devices to Windows 10 Enterprise, consider the following:</span></span>

- <span data-ttu-id="22a51-107">**您的網域必須新增及驗證**</span><span class="sxs-lookup"><span data-stu-id="22a51-107">**Your domains must be added and verified**</span></span> <br><span data-ttu-id="22a51-p101">與 Microsoft 365 訂閱，則取得結束於 onmicrosoft.com (例如 contoso.onmicrosoft.com) 的預設網域名稱。大部分組織偏好使用一或多個讓其電子郵件地址結束他們自己的網域名稱 （例如 username@contoso.com) 中其所擁有的網域。若要使用您自己的網域，您需要將其新增至 Microsoft 365 並確認您擁有該。我們建議您新增與因此他們準備好要移每當您設定 Microsoft 365 服務，例如電子郵件和 Skype 的商務現在確認您的網域。</span><span class="sxs-lookup"><span data-stu-id="22a51-p101"> With a Microsoft 365 subscription, you get a default domain name that ends in onmicrosoft.com (for example, contoso.onmicrosoft.com). Most organizations prefer to use one or more of the domains they own so their email addresses end in their own domain name (like username@contoso.com). To use your own domain, you need to add it to Microsoft 365 and verify that you own it. We recommend that you add and verify your domains now so they're ready to go whenever you set up Microsoft 365 services, like email and Skype for Business.</span></span>
- <span data-ttu-id="22a51-112">**您不需要在此階段中新增使用者**</span><span class="sxs-lookup"><span data-stu-id="22a51-112">**You don't need to add users at this time**</span></span> <br><span data-ttu-id="22a51-p102">若要使用 Microsoft 365 服務或安裝 Microsoft 365 產品，使用者需要 Microsoft 365 的帳戶及所需產品授權。如何將使用者新增至 Microsoft 365 取決於使用者數目及您目前具有 Active Directory 內部是否。如果您沒有 Active Directory] （或您擁有 Active Directory，但不想要將它同步處理至 Microsoft 365） 您可以將使用者新增至 Microsoft 365 直接與個別或大量指派授權。</span><span class="sxs-lookup"><span data-stu-id="22a51-p102"> To use Microsoft 365 services or install Microsoft 365 products, users need accounts in Microsoft 365 and they need product licenses. How you add users to Microsoft 365 depends on the number of users and whether you currently have Active Directory on-premises. If you don’t have Active Directory (or you have Active Directory but don’t want to synchronize it to Microsoft 365), you can add users directly to Microsoft 365 and assign licenses, either individually or in bulk. </span></span><br><span data-ttu-id="22a51-p103">如果您有 Active Directory 內部部署，您還可以[同步處理其 Microsoft 365](identity-azure-ad-connect-health.md) Azure AD、 Microsoft 365 所使用的雲端目錄中建立使用者帳戶。使用此方法之後，您可以建立帳戶的使用者和安全性群組的您用以管理資源 （例如 SharePoint Online 網站集合或文件） 的權限。使用 Microsoft 365 同步處理您的 Active Directory 不會將授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="22a51-p103"> If you have Active Directory on-premises, you can [sync it with Microsoft 365](identity-azure-ad-connect-health.md) to create user accounts in Azure AD, the cloud directory used by Microsoft 365. With this method, you can create accounts for users and for security groups you use to manage permissions to resources (like SharePoint Online site collections or documents). Synchronizing your Active Directory with Microsoft 365 won’t assign licenses to the users.</span></span>
- <span data-ttu-id="22a51-119">**您不需要授權使用者在此階段**</span><span class="sxs-lookup"><span data-stu-id="22a51-119">**You don't need to license users at this time**</span></span> <br><span data-ttu-id="22a51-p104">使用者可以使用 Microsoft 365 服務或從 Microsoft 365 入口網站安裝軟體之前，他們會需要產品授權。身為通用或使用者管理管理員，可以直接指派 Microsoft 365 中的產品授權個別或大量。您也可以使用[群組型授權](identity-group-based-licensing.md)的使用者新增至特定的群組時自動指派授權。</span><span class="sxs-lookup"><span data-stu-id="22a51-p104"> Before users can use Microsoft 365 services or install software from the Microsoft 365 portal, they need product licenses. As a global or user management admin, you can directly assign products licenses in Microsoft 365 either individually or in bulk. You can also use [group-based licensing](identity-group-based-licensing.md) to automatically assign licenses when users are added to a particular group.</span></span> 
- <span data-ttu-id="22a51-123">**分開安裝 Office 365 ProPlus**</span><span class="sxs-lookup"><span data-stu-id="22a51-123">**You install Office 365 ProPlus separately**</span></span> <br><span data-ttu-id="22a51-p105">取得 Microsoft 365 授權不會自動安裝 Office 365 ProPlus 用戶端電腦上。請參閱[階段 4： Office 365 ProPlus](office365proplus-infrastructure.md)如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="22a51-p105"> Obtaining a Microsoft 365 license does not automatically install Office 365 ProPlus on your client computers. See [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md) for more information.</span></span> 

## <a name="set-windows-diagnostics-data-level"></a><span data-ttu-id="22a51-126">設定 Windows 診斷資料層級</span><span class="sxs-lookup"><span data-stu-id="22a51-126">Set Windows diagnostics data level</span></span>

<span data-ttu-id="22a51-p106">Microsoft 使用診斷資料以協助保護的 Windows 來識別惡意程式碼趨勢和其他威脅保護裝置，並協助我們改善 Windows 與 Microsoft 服務品質。您必須確定診斷服務已啟用基本您組織中所有的端點上的最低層級。*根據預設，此服務已啟用且設為增強層級。* 不過，它是很好的作法以檢查並確定他們已接收接收器資料。設定透過原則層級會覆寫裝置層級的設定。</span><span class="sxs-lookup"><span data-stu-id="22a51-p106">Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. *By default, this service is enabled and set to the Enhanced level.* However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings.</span></span> 

<span data-ttu-id="22a51-132">**Windows 10 作業系統診斷資料層級**</span><span class="sxs-lookup"><span data-stu-id="22a51-132">**Windows 10 operating system diagnostic data levels**</span></span>

<span data-ttu-id="22a51-p107">您可以設定您的作業系統診斷資料使用您已經使用，例如群組原則、 MDM，或 Windows 佈建 「 管理工具。您可以手動變更您使用登錄編輯程式的設定。設定您的診斷資料層級透過管理原則會覆寫任何裝置層級設定。</span><span class="sxs-lookup"><span data-stu-id="22a51-p107">You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.</span></span>

<span data-ttu-id="22a51-136">當您設定的管理原則下表中使用適當的值。</span><span class="sxs-lookup"><span data-stu-id="22a51-136">Use the appropriate value in the table below when you configure the management policy.</span></span>

| <span data-ttu-id="22a51-137">層級</span><span class="sxs-lookup"><span data-stu-id="22a51-137">Level</span></span> | <span data-ttu-id="22a51-138">資料收集</span><span class="sxs-lookup"><span data-stu-id="22a51-138">Data gathered</span></span> | <span data-ttu-id="22a51-139">值</span><span class="sxs-lookup"><span data-stu-id="22a51-139">Value</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="22a51-140">安全性</span><span class="sxs-lookup"><span data-stu-id="22a51-140">Security</span></span> | <span data-ttu-id="22a51-141">僅限安全性資料。</span><span class="sxs-lookup"><span data-stu-id="22a51-141">Security data only.</span></span> | <span data-ttu-id="22a51-142">0</span><span class="sxs-lookup"><span data-stu-id="22a51-142">0</span></span> |
| <span data-ttu-id="22a51-143">基本</span><span class="sxs-lookup"><span data-stu-id="22a51-143">Basic</span></span> | <span data-ttu-id="22a51-144">安全性資料基本的系統和品質資料。</span><span class="sxs-lookup"><span data-stu-id="22a51-144">Security data, and basic system and quality data.</span></span> | <span data-ttu-id="22a51-145">1</span><span class="sxs-lookup"><span data-stu-id="22a51-145">1</span></span> |
| <span data-ttu-id="22a51-146">增強型</span><span class="sxs-lookup"><span data-stu-id="22a51-146">Enhanced</span></span> | <span data-ttu-id="22a51-147">安全性資料、 基本的系統和品質資料及增強的觀點及進階的可靠性的資料。</span><span class="sxs-lookup"><span data-stu-id="22a51-147">Security data, basic system and quality data, and enhanced insights and advanced reliability data.</span></span> | <span data-ttu-id="22a51-148">2</span><span class="sxs-lookup"><span data-stu-id="22a51-148">2</span></span> |
| <span data-ttu-id="22a51-149">Full</span><span class="sxs-lookup"><span data-stu-id="22a51-149">Full</span></span> | <span data-ttu-id="22a51-150">安全性資料、 基本的系統和品質資料、 增強的見解與進階的可靠性資料及完整的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="22a51-150">Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data.</span></span> | <span data-ttu-id="22a51-151">3</span><span class="sxs-lookup"><span data-stu-id="22a51-151">3</span></span> |

<span data-ttu-id="22a51-152">您可以透過任何一種方法來啟用診斷資料：</span><span class="sxs-lookup"><span data-stu-id="22a51-152">You can enable diagnostics data through any of these methods:</span></span>

* <span data-ttu-id="22a51-p108">**Microsoft Intune** -如果您打算使用 Intune 來管理您的裝置，您可以建立設定 」 原則以設定<a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a>系統原則來啟用診斷資料。在設定設定原則的詳細資訊，請參閱[管理設定與您的裝置與 Microsoft Intune 原則的功能](https://aka.ms/intuneconfigpolicies)。</span><span class="sxs-lookup"><span data-stu-id="22a51-p108">**Microsoft Intune** - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).</span></span>
* <span data-ttu-id="22a51-p109">**登錄編輯程式**-您可以使用登錄編輯程式中以手動啟用您組織中的每個裝置上的診斷資料。或者，您可以撰寫指令碼來編輯登錄。如果管理原則已經存在，例如群組原則或 MDM，它會覆寫此登錄設定。</span><span class="sxs-lookup"><span data-stu-id="22a51-p109">**Registry Editor** - You can use the Registry Editor to manually enable diagnostic data on each device in your organization. Alternately, you can write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.</span></span>
* <span data-ttu-id="22a51-158">**群組原則**-如果您不想註冊 Intune 的裝置，您可以使用群組原則物件設定您的組織診斷資料層級。</span><span class="sxs-lookup"><span data-stu-id="22a51-158">**Group Policy** - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.</span></span>
* <span data-ttu-id="22a51-p110">**命令提示字元處**-您可以設定 Windows 10 診斷資料與服務自動啟動命令提示字元使用。這個方法是最佳如果您要測試只有幾個裝置上的服務。啟用的服務為自動啟動此命令將會不需設定的診斷資料層級。如果您沒有已設定使用管理工具的診斷資料層級、 服務增強層級會以預設值來操作。</span><span class="sxs-lookup"><span data-stu-id="22a51-p110">**Command prompt** - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.</span></span>

<span data-ttu-id="22a51-163">請參閱[設定 Windows 您組織中的診斷資料](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization)若要深入了解 Windows 診斷資料以及如何啟用它根據您選擇的方法。</span><span class="sxs-lookup"><span data-stu-id="22a51-163">See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.</span></span>

<span data-ttu-id="22a51-164">作為過渡期的檢查點，您可以看到此步驟的[允出準則](windows10-exit-criteria.md#crit-windows10-step1)。</span><span class="sxs-lookup"><span data-stu-id="22a51-164">As an interim checkpoint, you can see the [exit criteria](windows10-exit-criteria.md#crit-windows10-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="22a51-165">下一步</span><span class="sxs-lookup"><span data-stu-id="22a51-165">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="22a51-166">現有裝置的 Windows 10 企業部署為就地升級</span><span class="sxs-lookup"><span data-stu-id="22a51-166">Deploy Windows 10 Enterprise for existing devices as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) |






