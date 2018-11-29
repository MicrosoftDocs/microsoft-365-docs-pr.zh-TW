---
title: 一般身分識別與裝置存取原則-Microsoft 365 企業版 |Microsoft 文件
description: 描述如何套用身分識別和裝置存取原則和設定之 Microsoft 建議的原則。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866754"
---
# <a name="common-identity-and-device-access-policies"></a>一般身分識別與裝置存取原則
本文說明建議的原則保護存取雲端服務的一般包括內部應用程式發佈與 Azure AD 應用程式 Proxy。 

本指南討論如何部署新佈建環境中的建議原則。 在個別實驗室環境中設定這些原則可讓您先了解和評估建議原則，再讓首度發行進入生產階段前和生產環境。 您新佈建的環境可能僅限雲端或混合式。  

## <a name="policy-set"></a>原則設定 

下圖說明建議的設定的原則。該顯示哪個層保護於一身的每個原則套用至和原則是否套用至 Pc、 手機與平板電腦或裝置這兩種類別。它也會指出所設定這些原則。

![設定身分識別與裝置的存取權的一般原則](../images/Identity_device_access_policies_byplan.png)


本文的其餘部分說明如何設定這些原則。 

之前將 Intune 註冊裝置的裝置在預定使用者所持有的保證建議您不要使用多重要素驗證。與您必須將 Intune 註冊裝置之前強制執行裝置規範遵守原則。

若要授與您若要完成這些工作的時間、 建議的基準原則實作的順序列出此表格中。不過，保護機密和高度規範 MFA 原則可實作任何時候。


|保護層級|Policies|詳細資訊|
|:---------------|:-------|:----------------|
|**基準**|[登入風險為*medium*或*high*時需要 MFA](#require-mfa-based-on-sign-in-risk)| |
|        |[不支援經過驗證的封鎖用戶端](#block-clients-that-dont-support-modern-authentication)|不使用經過驗證的用戶端可略過條件式存取規則，因此請務必封鎖這些。|
|        |[高風險使用者必須變更密碼](#high-risk-users-must-change-password)|強制使用者在登入其帳戶偵測到高風險活動時時變更其密碼。|
|        |[定義應用程式保護原則](#define-app-protection-policies)|每個平台 (iOS、 Android、 Windows) 的一個原則。|
|        |[需要核准的應用程式](#require-approved-apps)|強制執行電話與平板電腦的行動裝置應用程式保護|
|        |[定義裝置規範遵守原則](#define-device-compliance-policies)|針對每個平台的一個原則。|
|        |[需要相容的 Pc](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|強制執行 Pc Intune 的管理|
|**敏感性**|[登入風險為*低*、 *medium*或*high*時需要 MFA](#require-mfa-based-on-sign-in-risk)| |
|         |[需要相容的 Pc*和*行動裝置](#require-compliant-pcs-and-mobile-devices)|強制執行 Pc 與電話/平板電腦 Intune 的管理。|
|**高管制**|[*永遠*需要 MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>將原則指派給使用者
設定原則之前, 識別 Azure AD 群組所使用的每一層的保護。通常比較基準保護套用至組織中的每一個人。比較基準和機密保護包含使用者必須套用的所有比較基準原則加上機密的原則。保護累計且最嚴格的原則會強制執行。 

建議的做法是建立的設定格式化的條件存取排除 Azure AD 群組。將這個群組新增至所有"排除"下您設定格式化的條件存取規則。這可讓您提供給使用者的存取時疑難排解存取問題的方法。這被建議為暫時方案。監視變更這個群組並確定排除群組已採用僅如預期。 

下圖提供使用者工作分派及排除的範例。

![範例使用者工作分派及排除 MFA 規則](../images/identity-access-policies-assignment.png)

圖中 「 上方秘密 project X 小組 」 被指派 MFA*一律*需要的設定格式化的條件存取原則。套用至使用者的較高等級時則是保護的審慎。需要此專案小組成員將提供兩種形式的驗證每次登入，即使這些沒有檢視高度規範的內容。  

 所有這些建議的過程中建立的 Azure AD 群組必須建立為 Office 365 群組。這是特別重要的部署 Azure 資訊保護 (AIP) 時保護文件中的 SharePoint Online。

![建立 Office 365 群組的螢幕擷取畫面](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a>需要 MFA 根據登入風險
要求 MFA、 之前先使用身分識別保護 MFA 註冊原則 MFA 註冊的使用者。使用者註冊後您可以強制 MFA 登入。[必要的工作](identity-access-prerequisites.md)包括 MFA 登錄的所有使用者。

若要建立新的條件式存取原則： 

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇**新的原則**如下列螢幕擷取畫面所示：

![基準 CA 原則](./media/secure-email/CA-EXO-policy-1.png)

 下表說明實作此原則的設定格式化的條件存取原則設定。

**指派**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|使用者和群組|Include|選取使用者和群組 - 選取包含目標使用者的特定安全性群組|從包含試驗使用者的安全性群組開始。|
||排除|例外狀況安全性群組；服務帳戶 (應用程式身分識別)|視需要暫時修改成員資格|
|雲端應用程式|Include|選取您想要套用到此規則的應用程式。例如，選取 [Office 365 Exchange Online||
|條件|已設定|是|進行您環境和需求的特定設定|
|登入風險|風險層級||請參閱下表中的指引|

**登入風險**

適用於根據您所採用的保護層級的設定。

|屬性|保護層級|值|附註|
|:---|:---------|:-----|:----|
|風險層級|基準|高、中|檢查兩者|
| |敏感性|高、 中、 低|三個全選|
| |高管制| |保留所有選項未核取一律強制執行 MFA|

**存取控制**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|授與|授予存取|True|已選取|
||需要 MFA|True|Check|
||需要要標示為相容的裝置|False||
||需要混合 Azure AD 加入的裝置|False||
||需要核准的用戶端應用程式|False||
||需要所有選取的控制項|True|已選取|

> [!NOTE]
> 請務必按一下**上**的 [啟用此原則。也請考慮使用[怎麼辦](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則



## <a name="block-clients-that-dont-support-modern-authentication"></a>不支援經過驗證的封鎖用戶端
1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

下表說明實作此原則的設定格式化的條件存取原則設定。

**指派**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|使用者和群組|Include|選取使用者和群組 - 選取包含目標使用者的特定安全性群組|從包含試驗使用者的安全性群組開始。|
||排除|例外狀況安全性群組；服務帳戶 (應用程式身分識別)|視需要暫時修改成員資格|
|雲端應用程式|Include|選取您想要套用到此規則的應用程式。例如，選取 [Office 365 Exchange Online||
|條件|已設定|是|設定用戶端應用程式|
|用戶端應用程式|已設定|是|行動應用程式和桌面用戶端 (選取 [兩者) 其他用戶端|

**存取控制**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|授與|封鎖存取|True|已選取|
||需要 MFA|False||
||需要要標示為相容的裝置|False||
||需要混合 Azure AD 加入的裝置|False||
||需要核准的用戶端應用程式|False||
||需要所有選取的控制項|True|已選取|

> [!NOTE]
> 請務必按一下**上**的 [啟用此原則。也請考慮使用[怎麼辦](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則



## <a name="high-risk-users-must-change-password"></a>高風險使用者必須變更密碼
若要確保強制執行所有高風險使用者遭盜用的帳戶在登入時變更密碼，您必須套用下列原則。

登入[Microsoft Azure 入口網站 (http://portal.azure.com)](http://portal.azure.com/)使用您的系統管理員認證，然後瀏覽至**Azure AD 身分識別保護 > 使用者風險原則**。

**指派**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|使用者|Include|所有使用者|已選取|
||排除|無||
|條件|使用者風險|高|已選取|

**控制項**

| 類型 | 屬性 | 值                  | 附註 |
|:-----|:-----------|:------------------------|:------|
|      | 存取     | 允許存取            | True  |
|      | 存取     | 需要密碼變更 | True  |

**檢閱：** 不適用

> [!NOTE]
> 請務必按一下**上**的 [啟用此原則。也請考慮使用[怎麼辦](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則

## <a name="define-app-protection-policies"></a>定義應用程式保護原則
應用程式保護原則定義允許哪些應用程式和其可採取的動作與您組織的資料。保護原則與 Azure 入口網站內建立 Intune 應用程式。 

建立每個平台的原則：
- iOS
- Android
- Windows 10

若要建立新的應用程式保護原則，Microsoft Azure 入口網站與 administer 認證，登入及瀏覽至 [**行動應用程式 > 應用程式保護原則**。按一下 [**新增原則**。

有稍微之間的差異的應用程式保護 iOS 及 android （英文） 之間的原則選項。下列原則是特別為 android （英文）。使用此做為指南的其他原則。

應用程式的建議的清單會包含下列：
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio Viewer
- OneDrive
- OneNote
- Outlook

下表說明建議的設定：

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|資料重新配置|禁止 Android 備份|是|在 iOS 上，這會特別呼叫 iTunes 和 iCloud|
||允許應用程式將資料傳送到其他應用程式|受原則管理的應用程式||
||[允許應用程式接收其他應用程式的資料]|受原則管理的應用程式||
||禁止執行 [另存新檔]|是||
||選取可儲存公司資料的儲存體服務|OneDrive for Business，SharePoint||
||[限制利用其他應用程式剪下、複製及貼上]|使用中的貼上的受管理的原則應用程式||
||限制 Web 內容以顯示於受管理的瀏覽器中|否||
||加密應用程式資料|是|在 iOS 上，選取選項：當裝置鎖定時|
||啟用裝置時停用應用程式的加密|是|停用此設定可避免雙重加密|
||停用聯絡人同步|否||
||停用列印|否||
|存取|需要 PIN 碼才可存取|是||
||選取類型|數字||
||允許簡單的 PIN|否||
||PIN 長度|6||
||允許指紋而非 PIN|是||
||受管理的裝置 PIN 時停用應用程式 PIN|是||
||需要存取公司認證|否||
||重新檢查存取需求前等候時間 (分鐘)|30||
||封鎖螢幕擷取及 Android 助手|否|在 iOS 上，這不是可用的選項|
|登入安全性需求|最大 PIN 嘗試次數|5|重設 Pin|
||離線寬限期|720|封鎖存取|
||離線間隔幾天後抹除 App 資料|90|清除資料|
||根目錄 Jailbroken/裝置| |清除資料|

完成時，請記得按一下 [建立]。 重複上述步驟，並將選取的平台 (下拉式清單) 取代為 iOS。 這會建立兩個應用程式原則，因此在您建立原則之後，請將群組指派給原則，並進行部署。

若要編輯原則並將這些原則指派給使用者，請參閱 ＜[如何建立和指派應用程式保護原則](https://docs.microsoft.com/intune/app-protection-policies)。 

## <a name="require-approved-apps"></a>需要核准的應用程式
若要要求核准的應用程式：

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

5. 輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。

6. 選擇 [雲端應用程式]。

7. 選擇 [**選取應用程式**、 從**雲端應用程式**清單中選取所需的應用程式。例如，選取 [Office 365 Exchange Online。按一下 [**選取 [** **完成**]。

8. 選擇 [存取控制] 區段中的 [授與]。

9. 選擇 [**授與存取權**，請選取 [**需要核准用戶端應用程式**。 多個控制項，選取 [**需要在選定的控制項**，然後選擇 [**選取**。 

10. 按一下 [建立]****。

## <a name="define-device-compliance-policies"></a>定義裝置規範遵守原則

裝置規範遵守原則定義的裝置必須遵守才能加以標示為相容的需求。建立 Intune 裝置 Azure 入口網站內的規範原則。 

建立每個平台的原則：
- Android
- Android 企業
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1 及更新版本
- Windows 10 及更新版本

若要建立裝置規範遵守原則，Microsoft Azure 入口網站與 administer 認證，登入及瀏覽至 [ **Intune > 裝置規範**。按一下 [**建立原則**。

Windows 10 會建議使用下列設定值。

**裝置狀況： Windows 狀況審查服務評估規則**

|屬性|值|附註|
|:---------|:-----|:----|
|需要 BitLocker|需要||
|需要在裝置上啟用安全開機|需要||
|需要的程式碼完整性|需要||


**裝置內容**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|作業系統版本|全部|尚未設定||

針對所有要視為已部署的上述原則，必須將它們的目標設為使用者群組。 做法是建立此原則 (在儲存時)，或稍後選取 [原則] 區段中的 [管理部署] (層級與 [新增] 相同)。

**系統安全性**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|Password|需要密碼來解除鎖定行動裝置|需要||
||簡單密碼|封鎖||
||密碼類型|裝置預設值||
||密碼最小長度|6||
||最大分鐘的閒置時間前都需要 password|15 |此設定為支援 Android 版本 4.0 及上方或 KNOX 4.0 及以上。IOS 裝置已支援 iOS 8.0 及上方。|
||密碼到期 (天數)|41||
||若要防止重複使用舊密碼數目|5||
||裝置會傳回從閒置狀態 （行動電話和 Holographic） 時需要密碼|需要|供 Windows 10 及更新版本。|
|加密|在裝置上的資料存放區的加密|需要||
|裝置安全性|防火牆|需要||
||防毒|需要||
||反間諜軟體|需要|此設定需要登錄於 Windows 安全性中心反間諜軟體解決方案。|
|防禦者|Windows 防禦者反惡意程式碼|需要||
||Windows 防禦者反惡意程式碼的最小版本||僅支援 Windows 10 桌面。Microsoft 建議版本不超過五後方從最新版本。|
||最新的 Windows 防禦者反惡意程式碼簽章|需要||
||[即時保護]|需要|僅支援 Windows 10 桌面。|

**Windows Defender ATP**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|Windows 防禦者進階威脅保護規則|需要裝置是在或下機器風險分數|中||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>需要相容的 Pc （但不是相容的電話與平板電腦）
之前加入至需要相容的 Pc 的原則，請務必註冊管理到 Intune 的裝置。之前將 Intune 註冊裝置的裝置在預定使用者所持有的保證建議您不要使用多重要素驗證。 

若要要求相容的 Pc：

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

5. 輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。

6. 選擇 [雲端應用程式]。

7. 選擇 [**選取應用程式**、 從**雲端應用程式**清單中選取所需的應用程式。例如，選取 [Office 365 Exchange Online。按一下 [**選取 [** **完成**]。

8. 若要要求相容的 Pc，但不是相容的電話與平板電腦，請選擇 [**條件**和**裝置平台**。選擇 「 選取裝置平台 」，並選取 [ **Windows**和**macOS**。

9. 選擇 [存取控制] 區段中的 [授與]。

10. 選擇 [**授與存取權**，請選取 [**需要標示為相容的裝置**。 多個控制項，選取 [**需要所有選取的控制項**，然後選擇 [**選取**。 

11. 按一下 [建立]****。

如果您的目標為何需要相容的 Pc*和*行動裝置，請勿選取平台。這會強制執行的所有裝置相容。 




## <a name="require-compliant-pcs-and-mobile-devices"></a>需要相容的 Pc*和*行動裝置

若要要求規範的所有裝置：

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

5. 輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。

6. 選擇 [雲端應用程式]。

7. 選擇 [**選取應用程式**、 從**雲端應用程式**清單中選取所需的應用程式。例如，選取 [Office 365 Exchange Online。按一下 [**選取 [** **完成**]。

8. 選擇 [存取控制] 區段中的 [授與]。

9. 選擇 [**授與存取權**，請選取 [**需要標示為相容的裝置**。多個控制項，選取 [**需要所有選取的控制項**，然後選擇 [**選取**。 

10. 按一下 [建立]****。

建立此原則，請勿選取平台。這會強制執行相容的裝置。















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a>接下來的步驟

[了解保護電子郵件的原則建議](secure-email-recommended-policies.md)
