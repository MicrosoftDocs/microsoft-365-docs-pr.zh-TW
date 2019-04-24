---
title: 準備您的組織，Windows 10 企業版
description: 針對 Microsoft 365 企業版的一部分部署在電腦上的 Windows 10 企業版所需的步驟提供高階指導。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 文件、 Windows 10 企業版部署
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 9b09f21c71f578c45a71149cedfd67a8ea9104e6
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289400"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>步驟 1： 準備您的組織，Windows 10 企業版

*本文適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

之前將您的裝置升級到 Windows 10 企業版，請考慮下列各項：

- **您的網域必須新增及驗證** <br>
  Microsoft 365 訂閱，您可以取得結束於 onmicrosoft.com (例如，contoso.onmicrosoft.com) 中的預設網域名稱。 大多數的組織偏好使用一或多個讓他們的電子郵件地址以自己的網域名稱 （例如 username@contoso.com) 結尾的自己的網域。 若要使用您自己的網域，您需要將其新增至 Microsoft 365，並確認您擁有該。 我們建議您新增，並讓他們已準備好繼續每當您設定 Microsoft 365 服務，例如電子郵件和商務用 Skype 時，立即驗證您的網域。
- **您不需要這一次新增使用者** <br>
  若要使用 Microsoft 365 服務，或安裝 Microsoft 365 產品，使用者需要 Microsoft 365 中的帳戶，他們需要產品授權。 如何將使用者新增至 Microsoft 365，取決於使用者數目以及您是否目前已 Active Directory 的內部。 如果您沒有 Active Directory （或您具有 Active Directory，但不想要將它同步處理至 Microsoft 365），您可以直接向 Microsoft 365 新增使用者，並指派授權，個別或大量。 <br>
  如果您有 Active Directory 內部部署，您可以在 Azure AD，使用 Microsoft 365 雲端目錄中建立使用者帳戶的 [[同步處理，Microsoft 365 使用](identity-azure-ad-connect.md#identity-sync)。 使用此方法之後，您可以建立帳戶的使用者和安全性群組您用來管理資源 （例如 SharePoint Online 網站集合或文件） 的權限。 與 Microsoft 365 進行同步處理您的 Active Directory 不會將授權指派給使用者。
- **您不需要授權的使用者在此階段** <br>
  使用者可以使用 Microsoft 365 服務，或從 Microsoft 365 入口網站安裝的軟體之前，他們會需要產品授權。 全域或使用者管理系統管理員，您可以直接將指派 Microsoft 365 中的產品授權個別或大量。 您也可以使用[群組為基礎的授權](identity-self-service-group-management.md#identity-group-license)會自動將授權指派給特定群組新增使用者時。 
- **您個別安裝 Office 365 專業增強版** <br>
  取得 Microsoft 365 授權不會自動安裝 Office 365 專業增強版用戶端電腦上。 請參閱[階段 4: Office 365 專業增強版](office365proplus-infrastructure.md)如需詳細資訊。 

## <a name="set-windows-diagnostics-data-level"></a>設定 Windows 診斷資料層級

若要協助保護的 Windows 裝置來識別惡意程式碼趨勢和其他威脅保護，並協助我們改進 Windows 和 Microsoft 服務的品質，Microsoft 會使用診斷資料。 您必須確定診斷服務已啟用的基本貴組織中的所有端點上的最低層級。 *根據預設，此服務已啟用，且設為增強層級。* 不過，它是很好的作法檢查並確定他們正在接收感應資料。 將透過原則層級會覆寫裝置層級設定。 

**Windows 10 作業系統診斷資料層級**

您可以設定您使用您已使用，例如群組原則、 MDM，或 Windows 佈建的管理工具的作業系統診斷資料設定。 您可以手動變更您使用登錄編輯程式的設定。 將您的診斷資料層級，透過 [管理原則會覆寫任何裝置層級設定。

當您設定的管理原則下表中使用適當的值。

| 層級 | 收集資料 | 值 |
|:--- |:--- |:--- |
| 安全性 | 僅限安全性資料。 | 0 |
| 基本 | 安全性資料，以及基本系統和品質資料。 | 1 |
| 增強型 | 安全性資料、 基本系統和品質資料，並增強的見解和進階的可靠性資料。 | 2 |
| Full | 安全性資料、 基本系統和品質資料、 增強型的見解和進階的可靠性資料和完整的診斷資料。 | 3 |

您可以透過任何一種方法來啟用診斷資料：

* **Microsoft Intune** -如果您打算使用 Intune 來管理您的裝置，您可以建立設定 」 原則以啟用診斷資料設定<a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a>系統原則。 如需設定原則設定的詳細資訊，請參閱[管理設定及使用 Microsoft Intune 原則裝置上的功能](https://aka.ms/intuneconfigpolicies)。
* **登錄編輯程式**-您可以使用 [登錄編輯程式，以手動啟用您的組織中的 [每個裝置上的診斷資料。 或者，您可以撰寫指令碼，以編輯登錄。 如果管理原則已存在，例如群組原則或 MDM，它會覆寫這個登錄設定。
* **群組原則**-如果您不打算註冊在 Intune 中的裝置，您可以使用群組原則物件設定貴組織的診斷資料層級。
* **命令提示字元處**-您可以設定 Windows 10 診斷資料與服務設為自動啟動 [命令提示字元使用。 這個方法適合如果您正在測試只有幾個裝置上的服務。 啟用的服務為自動啟動使用此命令將不會設定診斷資料層級。 如果您未設定診斷資料層級使用管理工具，服務增強層級會與預設值來操作。

請參閱 <<c0>在您的組織中設定 Windows 診斷資料若要深入了解 Windows 診斷資料與如何可以讓您根據您選擇的方法。

作為過渡期的檢查點，您可以看到對應至此步驟的[允出準則](windows10-exit-criteria.md#crit-windows10-step1)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [將 Windows 10 企業版的現有裝置部署為就地升級](windows10-deploy-inplaceupgrade.md) |






