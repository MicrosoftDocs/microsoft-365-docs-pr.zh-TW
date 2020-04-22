---
title: 為 Windows 10 企業版準備您的組織
description: 提供在 Microsoft 365 Enterprise 的一部分上部署 Windows 10 企業版時所需步驟的高階指導方針。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 檔，Windows 10 企業版，部署
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: josephd
ms.openlocfilehash: 74c8dc4a0d4e2d457462320999ed79e80b372b7a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636660"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>步驟1：為 Windows 10 企業版準備您的組織

*本文適用于 Microsoft 365 企業版的 E3 和 E5 版本*

![階段 3：Windows 10 企業版](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

將裝置升級到 Windows 10 Enterprise 之前，請考慮下列各項：

- **您必須新增及驗證您的網域** <br>
  使用 Microsoft 365 訂閱時，您會取得以 onmicrosoft.com 結尾的預設功能變數名稱（例如，contoso.onmicrosoft.com）。 大多陣列織喜歡使用一或多個擁有的網域，使其電子郵件地址以自己的功能變數名稱結尾（如 username@contoso.com）。 若要使用您自己的網域，您必須將其新增至 Microsoft 365，並確認您擁有該網域。 建議您立即新增及驗證您的網域，這樣當您設定 Microsoft 365 服務（例如電子郵件和商務用 Skype）時，他們就可以開始進行。
- **您不需要在這個時間新增使用者** <br>
  若要使用 Microsoft 365 服務或安裝 Microsoft 365 產品，使用者需要 Microsoft 365 中的帳戶，且需要產品授權。 如何將使用者新增至 Microsoft 365 取決於使用者數目，以及您目前是否在內部部署 Active Directory。 如果您沒有 Active Directory （或您有 Active Directory 但不想要將其同步處理至 Microsoft 365），您可以直接將使用者新增至 Microsoft 365 並指派授權（個別或大量）。 <br>
  如果您有內部部署的 Active Directory，您可以將[它與 microsoft 365 同步處理](identity-add-user-accounts.md#identity-sync)，以在 Azure AD 中建立使用者帳戶（Microsoft 365 使用的雲端目錄）。 使用此方法，您可以為使用者和您用來管理資源許可權（如 SharePoint 線上網站集合或檔）的安全性群組建立帳戶。 同步處理 Active Directory 與 Microsoft 365 不會將授權指派給使用者。
- **您目前不需要授權使用者** <br>
  在使用者可以使用 Microsoft 365 服務或從 Microsoft 365 入口網站安裝軟體之前，他們需要產品授權。 做為全域或使用者管理的系統管理員，您可以直接在 Microsoft 365 中個別或大量指派產品授權。 您也可以使用以[群組為基礎的授權](identity-use-group-management.md#identity-group-license)，在使用者新增至特定群組時，自動指派授權。 
- **您可以分別安裝 Microsoft 365 應用程式的企業應用程式** <br>
  取得 Microsoft 365 授權不會自動在用戶端電腦上安裝適用于企業的 Microsoft 365 應用程式。 如需詳細資訊，請參閱[階段4： Microsoft 365 應用程式 for enterprise](office365proplus-infrastructure.md) 。 

## <a name="set-windows-diagnostics-data-level"></a>設定 Windows 診斷資料層級

Microsoft 會使用診斷資料，以找出惡意程式碼趨勢及其他威脅，並協助我們改善 Windows 和 Microsoft 服務的品質，以確保保護 Windows 裝置。 您必須確定已在組織中的所有端點上，以最低的基本層級啟用診斷服務。 *根據預設，此服務會啟用並設定為增強層級。* 不過，建議您檢查並確認他們收到感應器資料。 透過原則設定層級會覆寫裝置層級設定。 

**Windows 10 作業系統診斷資料層級**

您可以使用您已在使用的管理工具（例如群組原則、MDM 或 Windows 布建）來設定作業系統診斷資料設定。 您也可以使用登錄編輯程式手動變更設定。 透過管理原則設定診斷資料層級，會覆寫任何裝置層級設定。

當您設定管理原則時，請使用下表中適當的值。

| 層級 | 收集的資料 | 值 |
|:--- |:--- |:--- |
| 安全性 | 僅限安全性資料。 | 0 |
| 基本 | 安全性資料和基本系統和品質資料。 | 1  |
| 增強 | 安全性資料、基本系統和品質資料，以及增強的真知灼見和 advanced 可靠性資料。 | 2  |
| Full | 安全性資料、基本系統和品質資料、增強的真知灼見和 advanced 可靠性資料，以及完整的診斷資料。 | 3  |

您可以透過下列其中一種方法來啟用診斷資料：

* **Microsoft Intune** -如果您想要使用 Intune 來管理裝置，您可以設定<a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a>系統原則，以建立啟用診斷資料的設定原則。 如需設定原則的詳細資訊，請參閱[使用 Microsoft Intune 原則管理裝置上的設定和功能](https://aka.ms/intuneconfigpolicies)。
* **登錄編輯程式**-您可以使用登錄編輯程式，在組織中的每台裝置上手動啟用診斷資料。 或者，您也可以撰寫腳本，以編輯註冊表。 如果管理原則已存在（如群組原則或 MDM），它會覆寫此登錄設定。
* **群組原則**-如果您不打算在 Intune 中註冊裝置，您可以使用「群組原則」物件設定組織的診斷資料層級。
* **命令提示**字元-您可以將 Windows 10 診斷資料和服務設定為以命令提示字元自動啟動。 這種方法最適合於只在幾個裝置上測試服務。 使用此命令讓服務自動啟動，將不會設定診斷資料層級。 如果您未使用管理工具設定診斷資料層級，該服務將以預設的增強層級運作。

請參閱[設定組織中的 Windows 診斷資料](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization)以深入瞭解 Windows 診斷資料，以及如何根據您所選擇的方法來啟用它。

作為過渡期的檢查點，您可以看到此步驟的[允出準則](windows10-exit-criteria.md#crit-windows10-step1)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 2](../media/stepnumbers/Step2.png)| [部署 Windows 10 企業版作為就地升級的現有裝置](windows10-deploy-inplaceupgrade.md) |






