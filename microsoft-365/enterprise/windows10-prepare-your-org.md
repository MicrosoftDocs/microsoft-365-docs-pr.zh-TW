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
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866653"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>步驟 1： 準備您的組織 Windows 10 Enterprise

*本文適用於 Microsoft 365 企業版的 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

升級您的裝置為 Windows 10 Enterprise、 之前考量下列項目：

- **您的網域必須新增及驗證** <br>與 Microsoft 365 訂閱，則取得結束於 onmicrosoft.com (例如 contoso.onmicrosoft.com) 的預設網域名稱。大部分組織偏好使用一或多個讓其電子郵件地址結束他們自己的網域名稱 （例如 username@contoso.com) 中其所擁有的網域。若要使用您自己的網域，您需要將其新增至 Microsoft 365 並確認您擁有該。我們建議您新增與因此他們準備好要移每當您設定 Microsoft 365 服務，例如電子郵件和 Skype 的商務現在確認您的網域。
- **您不需要在此階段中新增使用者** <br>若要使用 Microsoft 365 服務或安裝 Microsoft 365 產品，使用者需要 Microsoft 365 的帳戶及所需產品授權。如何將使用者新增至 Microsoft 365 取決於使用者數目及您目前具有 Active Directory 內部是否。如果您沒有 Active Directory] （或您擁有 Active Directory，但不想要將它同步處理至 Microsoft 365） 您可以將使用者新增至 Microsoft 365 直接與個別或大量指派授權。<br>如果您有 Active Directory 內部部署，您還可以[同步處理其 Microsoft 365](identity-azure-ad-connect-health.md) Azure AD、 Microsoft 365 所使用的雲端目錄中建立使用者帳戶。使用此方法之後，您可以建立帳戶的使用者和安全性群組的您用以管理資源 （例如 SharePoint Online 網站集合或文件） 的權限。使用 Microsoft 365 同步處理您的 Active Directory 不會將授權指派給使用者。
- **您不需要授權使用者在此階段** <br>使用者可以使用 Microsoft 365 服務或從 Microsoft 365 入口網站安裝軟體之前，他們會需要產品授權。身為通用或使用者管理管理員，可以直接指派 Microsoft 365 中的產品授權個別或大量。您也可以使用[群組型授權](identity-group-based-licensing.md)的使用者新增至特定的群組時自動指派授權。 
- **分開安裝 Office 365 ProPlus** <br>取得 Microsoft 365 授權不會自動安裝 Office 365 ProPlus 用戶端電腦上。請參閱[階段 4： Office 365 ProPlus](office365proplus-infrastructure.md)如需詳細資訊。 

## <a name="set-windows-diagnostics-data-level"></a>設定 Windows 診斷資料層級

Microsoft 使用診斷資料以協助保護的 Windows 來識別惡意程式碼趨勢和其他威脅保護裝置，並協助我們改善 Windows 與 Microsoft 服務品質。您必須確定診斷服務已啟用基本您組織中所有的端點上的最低層級。*根據預設，此服務已啟用且設為增強層級。* 不過，它是很好的作法以檢查並確定他們已接收接收器資料。設定透過原則層級會覆寫裝置層級的設定。 

**Windows 10 作業系統診斷資料層級**

您可以設定您的作業系統診斷資料使用您已經使用，例如群組原則、 MDM，或 Windows 佈建 「 管理工具。您可以手動變更您使用登錄編輯程式的設定。設定您的診斷資料層級透過管理原則會覆寫任何裝置層級設定。

當您設定的管理原則下表中使用適當的值。

| 層級 | 資料收集 | 值 |
|:--- |:--- |:--- |
| 安全性 | 僅限安全性資料。 | 0 |
| 基本 | 安全性資料基本的系統和品質資料。 | 1 |
| 增強型 | 安全性資料、 基本的系統和品質資料及增強的觀點及進階的可靠性的資料。 | 2 |
| Full | 安全性資料、 基本的系統和品質資料、 增強的見解與進階的可靠性資料及完整的診斷資料。 | 3 |

您可以透過任何一種方法來啟用診斷資料：

* **Microsoft Intune** -如果您打算使用 Intune 來管理您的裝置，您可以建立設定 」 原則以設定<a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a>系統原則來啟用診斷資料。在設定設定原則的詳細資訊，請參閱[管理設定與您的裝置與 Microsoft Intune 原則的功能](https://aka.ms/intuneconfigpolicies)。
* **登錄編輯程式**-您可以使用登錄編輯程式中以手動啟用您組織中的每個裝置上的診斷資料。或者，您可以撰寫指令碼來編輯登錄。如果管理原則已經存在，例如群組原則或 MDM，它會覆寫此登錄設定。
* **群組原則**-如果您不想註冊 Intune 的裝置，您可以使用群組原則物件設定您的組織診斷資料層級。
* **命令提示字元處**-您可以設定 Windows 10 診斷資料與服務自動啟動命令提示字元使用。這個方法是最佳如果您要測試只有幾個裝置上的服務。啟用的服務為自動啟動此命令將會不需設定的診斷資料層級。如果您沒有已設定使用管理工具的診斷資料層級、 服務增強層級會以預設值來操作。

請參閱[設定 Windows 您組織中的診斷資料](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization)若要深入了解 Windows 診斷資料以及如何啟用它根據您選擇的方法。

作為過渡期的檢查點，您可以看到此步驟的[允出準則](windows10-exit-criteria.md#crit-windows10-step1)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [現有裝置的 Windows 10 企業部署為就地升級](windows10-deploy-inplaceupgrade.md) |






