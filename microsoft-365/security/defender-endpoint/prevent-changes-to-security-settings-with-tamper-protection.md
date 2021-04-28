---
title: 使用竄改防護來保護安全性設定
ms.reviewer: shwjha, hayhov
manager: dansimp
description: 使用防篡改保護，防止惡意應用程式變更重要的安全性設定。
keywords: 惡意程式碼、defender、防毒程式和防篡改保護
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ff98b78d113a67ad6bd816753c691e8afe71dd77
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065070"
---
# <a name="protect-security-settings-with-tamper-protection"></a>使用竄改防護來保護安全性設定

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

對執行下列其中一個 Windows 版本的裝置可使用防篡改保護：

- Windows 10
- Windows Server 2019
- Windows Server 版本 1803 或更新版本
- Windows Server 2016

## <a name="overview"></a>概觀

在某些網路攻擊中，不良的演員會嘗試停用電腦上的安全性功能，例如防防毒保護。 不良的演員，例如停用您的安全性功能，以更輕鬆地存取資料、安裝惡意程式碼，或利用您的資料、身分識別及裝置。 防篡改保護可協助避免發生這類問題。

使用防篡改保護時，惡意應用程式無法採取下列動作：

- 停用病毒和威脅防護
- 停用即時保護
- 關閉行為監控
- 停用防病毒 (例如 IOfficeAntivirus (IOAV) ) 
- 停用雲端傳送保護
- 移除安全性智慧更新

### <a name="how-it-works"></a>運作方式

防篡改保護基本上會鎖定 Microsoft Defender 防病毒，並防止您的安全性設定透過應用程式和方法加以變更，例如：

- 在 Windows 裝置上設定登錄編輯程式中的設定
- 透過 PowerShell Cmdlet 變更設定
- 透過「群組原則」編輯或移除安全性設定

防篡改保護不會使您無法查看安全性設定。 而且，篡改保護不會影響協力廠商防病毒應用程式如何在 Windows 安全性應用程式中註冊。 如果您的組織使用 Windows 10 企業版 E5，個別的使用者就無法變更不可篡改的保護設定。在這種情況下，安全小組會管理防篡改保護。



### <a name="what-do-you-want-to-do"></a>您要執行的工作

| 若要執行此工作 .。。 | 請參閱本節 .。。 |
|:---|:---|
| 在 Microsoft Defender 安全中心的 (或關閉) 開啟防篡改保護 <p>管理整個租使用者的防篡改保護 | [使用 Microsoft Defender 安全中心管理組織的篡改保護](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| 使用 Intune 針對所有或部分組織的 (或關閉) 開啟防篡改保護 <p>微調組織中防篡改的保護設定 | [使用 Intune 管理組織的篡改保護](#manage-tamper-protection-for-your-organization-using-intune) |
| 使用 Configuration Manager 對組織的 (或關閉) 開啟防篡改保護 | [使用 Configuration Manager 的承租人附加程式管理組織的篡改保護，版本2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| 針對個別裝置 (或關閉) 開啟防篡改保護 | [管理個別裝置上的非篡改保護](#manage-tamper-protection-on-an-individual-device) |
| 在裝置上查看有關篡改嘗試的詳細資料 | [查看有關篡改嘗試的資訊](#view-information-about-tampering-attempts) |
| 回顧安全性建議 | [檢查安全性建議](#review-your-security-recommendations) |
| 複查 (FAQs 的常見問題解答清單)  | [流覽 FAQs](#view-information-about-tampering-attempts) |

根據您用來啟用防篡改保護的方法或管理工具，可能會對對應 (雲端傳送保護) 上的依賴性。 

下表提供方法、工具和相依性的詳細資料。



|     啟用防篡改保護的方式                                         |     對地圖的相依性 (雲端提供的保護)     |
|------------------------------------------------------------------------------|--------------------------------------------------------|
|     Microsoft Intune                                                         |     否                                                 |
| Microsoft Endpoint Configuration Manager + 租使用者附加                     |     否                                                 |
|     Microsoft Defender for Endpoint 入口 (securitycenter.microsoft.com)     |     是                                                |
|     Microsoft 365 Defender 入口網站 (security.microsoft.com)                    |     是                                                |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a>使用 Microsoft Defender 安全中心管理組織的篡改保護

您可以使用 Microsoft Defender Security Center () ，為您的租使用者開啟或關閉不可篡改的保護 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。 以下是一些需要謹記的要點：

- 目前，在 Microsoft Defender Security Center 中管理防篡改保護的選項預設是針對新的部署。 針對現有的部署，可在自願加入時進行防篡改保護，讓計畫在近期使用此預設方法。  (若要自願加入，請在 Microsoft Defender Security Center 中，選擇 [**設定**] [  >  **高級功能** 未  >  **篡改保護**]。 )  

- 當您使用 Microsoft Defender 安全中心管理防篡改保護時，您不需要使用 Intune 或租使用者附加方法。

- 當您在 Microsoft Defender Security Center 中管理防篡改保護時，此設定會套用租使用者寬度，影響所有執行 Windows 10、Windows Server 2016 或 Windows Server 2019 的裝置。 若要微調防篡改保護 (例如對某些裝置進行未篡改的保護，但對某些裝置關閉) 了防篡改保護，請使用 [Intune](#manage-tamper-protection-for-your-organization-using-intune) 或 [Configuration Manager with 承租人 attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)。

- 如果您有混合式環境，則在 Intune 中設定的防篡改防護設定會優先于 Microsoft Defender Security Center 中設定的設定。 




### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a>在 Microsoft Defender 安全中心管理防篡改保護的需求

- 您必須具有適當的 [許可權](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全域管理員、安全性管理員或安全性作業。

- 您的 Windows 裝置必須執行下列其中一個 Windows 版本：
   - Windows 10
   - [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
   - Windows Server，版本 [1803](/windows/release-health/status-windows-10-1803) 或更新版本
   - [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
   - 如需有關版本的詳細資訊，請參閱 [Windows 10 版本資訊](/windows/release-health/release-information)。

- 您的裝置必須 [架至 Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint/onboarding)。

- 您的裝置必須使用反惡意程式碼平臺版本 4.18.2010.7 (或以上版本) 和反惡意程式碼引擎版本 1.1.17600.5 (或以上) 。  ([管理 Microsoft Defender 防病毒更新並套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 ) 

- 必須開啟[雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)。

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a>在 Microsoft Defender 安全中心的 (或關閉) 開啟防篡改保護 

![在 Microsoft Defender Security Center 中開啟防篡改保護](images/mde-turn-tamperprotect-on.png)

1. 請移至 Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。

2. 選擇 [ **設定**]。

3. 移至 **[一般**  >  **高級功能**]，然後開啟 [防篡改保護]。

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a>使用 Intune 管理組織的篡改保護

如果您是組織的安全小組的一部分，且您的訂閱包含 [Intune](/intune/fundamentals/what-is-intune)，您可以在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com) 入口網站的 (或關閉) 中開啟防篡改保護。 當您想要微調防篡改防護設定時，請使用 Intune。 例如，如果您想要在某些裝置上啟用防篡改保護，但不是全部，請使用 Intune。

### <a name="requirements-for-managing-tamper-protection-in-intune"></a>在 Intune 中管理防篡改保護的需求

- 您必須具有適當的 [許可權](/microsoft-365/security/defender-endpoint/assign-portal-access)，例如全域管理員、安全性管理員或安全性作業。

- 您的組織使用 [Intune 管理裝置](/intune/fundamentals/what-is-device-management)。 需要 ([Intune 授權](/intune/fundamentals/licenses) ;Intune 隨附于 Microsoft 365 E5。 ) 

- 您的 Windows 裝置必須執行 Windows 10 作業系統 [1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)、 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) 或更新版本。  (如需有關版本的詳細資訊，請參閱 [Windows 10 版本資訊](/windows/release-health/release-information)。 ) 

- 您必須使用 Windows 安全性搭配 [安全性情報](https://www.microsoft.com/wdsi/definitions) 更新為版本 1.287.60.0 (或以上) 。

- 您的裝置必須使用反惡意程式碼平臺版本 4.18.1906.3 (或以上版本) 和反惡意程式碼引擎版本 1.1.15500 (或以上版本) 。  ([管理 Microsoft Defender 防病毒更新並套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 ) 

### <a name="turn-tamper-protection-on-or-off-in-intune"></a>在 Intune 中 (或關閉) 開啟防篡改保護

![使用 Intune 開啟防篡改保護](images/turnontamperprotect-MEM.png)

1. 請移至 [Microsoft 端點](https://endpoint.microsoft.com) 管理員系統管理中心，並以您的公司或學校帳戶登入。

2. 選取 [**裝置** 設定  >  **設定檔**]。

3. 建立設定檔，其中包含下列設定：
    - **平臺： Windows 10 和更新版本**
    - **配置檔案類型： Endpoint protection**
    - **類別： Microsoft Defender 安全中心**
    - **防篡改保護：已啟用**

4. 將設定檔指派給一或多個群組。

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a>您使用的是 Windows 作業系統1709、1803或1809嗎？

如果您使用的是 Windows 10 作業系統 [1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)或 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)，您將無法在 Windows 安全性應用程式中看到 **防篡改的保護** 。 相反地，您可以使用 PowerShell 來判斷是否已啟用防篡改保護。

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a>使用 PowerShell 來判斷是否已開啟防篡改保護

1. 開啟 [Windows PowerShell] app。

2. 使用 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell Cmdlet。

3. 在結果清單中，尋找 `IsTamperProtected` 。  (*true* 值表示已啟用 [未篡改保護]。 ) 

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>使用 Configuration Manager 管理組織的篡改保護，版本2006

如果您使用 [的是版本2006的 Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)，您可以使用稱為 *租使用者附加* 的方法，管理 Windows 10、Windows Server 2016 及 windows server 2019 上的防篡改保護設定。 承租人附加可讓您將內部部署的設定管理員裝置同步處理至 Microsoft 端點管理員系統管理中心，然後將端點安全性設定原則傳送至內部部署集合 & 裝置。

![端點管理員的 Windows 安全性體驗](images/win-security- exp-policy-endpt-security.png)

> [!NOTE]
> 此程式可用於將防篡改保護擴充至執行 Windows 10 和 Windows Server 2019 的裝置。 請務必複查此程式所述資源中的必要條件和其他資訊。

1. 設定租使用者附加。 若要取得此相關說明，請參閱 [Microsoft 端點管理員租使用者附加：裝置同步處理和裝置動作](/mem/configmgr/tenant-attach/device-sync-actions)。

2. 在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心中，移至 **端點安全性**  >  **防病毒**，然後選擇 [ **+ 建立原則**]。<br/> 
   - 在 [ **平臺** ] 清單中，選取 [ **Windows 10 和 windows Server (] ConfigMgr)**]。  
   - 在 [ **設定檔** ] 清單中，選取 [ **Windows 安全性體驗 (預覽])**。 <br/>

3. 將原則部署至您的裝置集合。

### <a name="need-help-with-this-method"></a>需要此方法的協助嗎？ 

請參閱下列資源：

- [Microsoft Intune 中 Windows 安全經驗設定檔的設定](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [技術社區博客：宣佈 Configuration Manager 租使用者附加用戶端的篡改保護](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>管理個別裝置上的非篡改保護

> [!NOTE]
> 防篡改保護封鎖會嘗試透過登錄修改 Microsoft Defender 防病毒設定。
>
> 為了協助確保防篡改保護不會干擾協力廠商的安全性產品或可修改這些設定的企業安裝腳本，請移至 [ **Windows 安全性** ] 並將 **安全性情報** 更新為版本1.287.60.0 或更新版本。  (參閱 [安全性智慧更新](https://www.microsoft.com/wdsi/definitions)。 ) 
>
> 當您完成此更新後，防篡改保護會繼續保護您的登錄設定，而記錄會嘗試修改這些設定，而不會傳回錯誤。

如果您是家庭使用者，或不受安全性小組所管理的設定的制約，您可以使用 Windows 安全性應用程式來管理無法篡改的保護。 您必須具備裝置的適當系統管理員許可權，才能執行變更安全性設定，例如防篡改的保護。

以下是您在 Windows 安全性應用程式中看到的內容：

![在 Windows 10 首頁中開啟防篡改保護](images/tamperprotectionturnedon.png)

1. 選取 [ **開始**]，然後開始輸入 *安全性*。 在搜尋結果中，選取 [ **Windows 安全性**]。

2. 選取 [**病毒 & 威脅防護**]  >  **病毒 & 威脅防護設定**。

3. 設定 **防篡改保護** 為 **開啟** 或 **關閉**。



## <a name="view-information-about-tampering-attempts"></a>查看有關篡改嘗試的資訊

篡改嘗試通常表示較大的 cyberattacks。 不良的演員會嘗試變更安全性設定，以保留並保持未被發現的方式。 如果您是組織的安全性小組的一部分，您可以查看有關這些嘗試的資訊，然後採取適當的動作來緩解威脅。

偵測到篡改嘗試時，會在 [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) () 中產生警示 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。

![Microsoft Defender 安全中心](images/tamperattemptalert.png)

在 Microsoft Defender for Endpoint 中使用 [端點偵測和回應](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 及 [高級搜尋](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) 功能，您的安全性作業小組可以調查並處理此類嘗試。

## <a name="review-your-security-recommendations"></a>回顧安全性建議

防篡改防護會與 [威脅 & 漏洞管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 功能整合。 [安全性建議](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 包括確定已開啟防篡改保護。 例如，您可以搜尋未 *篡改* 的，如下圖所示：

![安全建議中的防篡改保護結果](/images/securityrecs-tamperprotect.jpg)

在結果中，您可以選取 [ **開啟防篡改防護** ] 以深入瞭解及開啟。

![開啟防篡改保護](images/tamperprotectsecurityrecos.png)

若要深入瞭解威脅 & 漏洞管理的相關資訊，請參閱 [Microsoft Defender Security Center 中的威脅 & 漏洞管理](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a>適用于哪些 Windows 作業系統版本設定防篡改保護？

Windows 10 作業系統 [1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)、 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)或更新版本，以及 [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)。

如果您使用的是 Configuration Manager，版本2006，使用租使用者附加，可將防篡改保護功能延伸至 Windows Server 2019。 請參閱「租使用者」 [：從系統管理中心建立及部署端點安全性防病毒原則 (預覽) ](/mem/configmgr/tenant-attach/deploy-antivirus-policy)。

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a>防篡改保護是否會影響協力廠商防病毒註冊？

否。 協力廠商的防病毒產品將繼續使用 Windows 安全性應用程式進行註冊。

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>當裝置上的 Microsoft Defender 防毒程式不在使用中時，會發生什麼情況？

架至 Microsoft Defender for Endpoint 的裝置將會在被動模式下執行 Microsoft Defender 防毒軟體。 防篡改保護將繼續保護服務及其功能。 

### <a name="how-can-i-turn-tamper-protection-onoff"></a>如何開啟/關閉防篡改保護？

如果您是家庭使用者，請參閱 [管理個別裝置上的非篡改保護](#manage-tamper-protection-on-an-individual-device)。

如果您是使用 [Microsoft Defender For Endpoint 的](/microsoft-365/security/defender-endpoint)組織，您應該可以在 Intune 中管理防篡改保護，類似管理其他 Endpoint protection 功能的方式。 請參閱本文的下列各節： 

- [使用 Intune 管理防篡改保護](#manage-tamper-protection-for-your-organization-using-intune)
- [使用 Configuration Manager 管理防篡改保護，版本2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- 使用目前在預覽中[的 Microsoft Defender Security Center (管理防篡改保護](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center)) 

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a>如何在 Intune 中設定無法篡改的保護，會影響如何透過「我的群組原則」管理 Microsoft Defender 防病毒？

您的一般群組原則不會套用到防篡改保護，當防篡改保護開啟時，將會忽略對 Microsoft Defender 防病毒設定所做的變更。 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a>針對 Microsoft Defender for Endpoint，在僅針對整個組織的 Intune 中，是否要設定防篡改保護？

在 Intune 或 Microsoft 端點管理員中設定防篡改保護，可成為整個組織及特定裝置和使用者群組的目標。

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a>我是否可以在 Microsoft 端點 Configuration Manager 中設定防篡改保護？

如果您使用租使用者附加，您可以使用 Microsoft 端點 Configuration Manager。 請參閱下列資源：
- [使用 Configuration Manager 管理組織的篡改保護，版本2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [技術社區博客：宣佈 Configuration Manager 租使用者附加用戶端的篡改保護](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>我有 Windows E3 註冊。 我是否可以在 Intune 中使用設定防篡改保護？

目前，在 Intune 中設定防篡改保護只適用于具有 [Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint)的客戶。

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>如果在裝置上啟用防篡改保護功能時，嘗試變更 Intune、Microsoft Endpoint Configuration Manager 和 Windows Management Instrumentation 中的 Microsoft Defender for Endpoint 設定會發生什麼情況？

您將無法變更受到防篡改保護的功能;這類變更要求會被忽略。

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>我是企業客戶。 本機系統管理員是否可以變更其裝置上的篡改保護？

否。 本機系統管理員無法變更或修改無法篡改的保護設定。

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>如果我的裝置使用 Microsoft Defender for Endpoint 架，然後進入 boarded 狀態，會發生什麼情況？

如果從 Microsoft Defender for Endpoint boarded 裝置，則會開啟防篡改防護，這是非管理裝置的預設狀態。 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a>在 Microsoft Defender Security Center 中是否會產生有關篡改防篡改狀態變更的警示？

是。 警示會顯示在 [ [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **警示**] 底下。

您的安全性運作小組也可以使用搜尋查詢，例如下列範例：

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

[查看有關篡改嘗試的資訊](#view-information-about-tampering-attempts)。

## <a name="see-also"></a>另請參閱

[使用 Microsoft Intune 的 Endpoint Protection 來協助保護 Windows 電腦](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[深入瞭解 Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)

[相得益彰：Microsoft Defender 防毒軟體與適用於端點的 Microsoft Defender](why-use-microsoft-defender-antivirus.md)