---
title: 步驟 9：簡化密碼更新
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定混合式環境的密碼回寫。
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866301"
---
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="f36d0-103">步驟 9：簡化密碼更新</span><span class="sxs-lookup"><span data-stu-id="f36d0-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="f36d0-104">*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="f36d0-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="f36d0-p101">在此步驟中，您將允許使用者透過 Azure Active Directory (AD) 重設其密碼，然後密碼會複製到本機 Windows Server Active Directory (AD)。此程序稱為密碼回寫。使用密碼回寫，使用者不需要透過內部部署的 Windows Server AD (使用者的帳戶和屬性儲存於此) 更新他們的密碼。這對於漫遊或遠端使用者非常重要，因為他們沒有內部部署網路的遠端存取連線。</span><span class="sxs-lookup"><span data-stu-id="f36d0-p101">In this step, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). This process is known as password writeback. With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored. This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="f36d0-109">為了充分利用 Identity Protection 功能 (例如當偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，需要密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="f36d0-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="f36d0-110">如需詳細資訊和設定指示，請參閱 [Azure AD SSPR 密碼回寫](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。</span><span class="sxs-lookup"><span data-stu-id="f36d0-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="f36d0-p102">升級至最新版的 Azure AD Connect，以確保在新版本發行後能夠使用新功能並獲得最佳體驗。如需詳細資訊，請參閱 [Azure AD Connect 的自訂安裝](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。</span><span class="sxs-lookup"><span data-stu-id="f36d0-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

<span data-ttu-id="f36d0-113">作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-pw-writeback)。</span><span class="sxs-lookup"><span data-stu-id="f36d0-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f36d0-114">下一步</span><span class="sxs-lookup"><span data-stu-id="f36d0-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="f36d0-115">簡化使用者登入</span><span class="sxs-lookup"><span data-stu-id="f36d0-115">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

