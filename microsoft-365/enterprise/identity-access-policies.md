---
title: 一般身分識別和裝置存取原則-Microsoft 365 企業版 |Microsoft 檔
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
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 322da1ccfbd0cf8b5070894580b06fb5b0283f40
ms.sourcegitcommit: 1d5fc181036b673c4f0b9e161e19395dbfe5a304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2019
ms.locfileid: "35411647"
---
# <a name="common-identity-and-device-access-policies"></a>一般身分識別與裝置存取原則
本文說明用於保護雲端服務存取的常見建議原則, 包括以 Azure AD 應用程式 Proxy 發佈的內部部署應用程式。 

本指南討論如何在新布建的環境中部署建議的原則。 在個別的實驗室環境中設定這些原則, 可讓您瞭解並評估建議的原則, 然後再將推廣作業轉移至您的預製和實際執行環境。 您剛布建的環境可能是僅限雲端或混合式。  

## <a name="policy-set"></a>原則集 

下圖說明建議的原則集合。 它會顯示每個原則適用的保護層, 以及這些原則是套用至電腦或電話和平板電腦, 或是這兩類裝置。 它也會指出設定這些原則的位置。

![設定身分識別與裝置存取的一般原則](../images/Identity_device_access_policies_byplan.png)


本文的其餘部分將說明如何設定這些原則。 

在將裝置註冊到 Intune 之前, 建議使用多重要素驗證, 以確保裝置屬於預定的使用者。 您也必須在強制裝置規範原則之前, 將裝置註冊至 Intune。

為讓您完成這些工作的時間, 建議您依下表所列的順序來執行基準原則。 不過, 機密和高度管制保護的 MFA 原則可以在任何時候執行。


|保護層級|規則|詳細資訊|
|:---------------|:-------|:----------------|
|**Baseline**|[當登入風險為*中等*或*高*時, 需要 MFA](#require-mfa-based-on-sign-in-risk)| |
|        |[封鎖不支援新式驗證的用戶端](#block-clients-that-dont-support-modern-authentication)|未使用新式驗證的用戶端可以略過條件式存取規則, 因此請務必封鎖這些規則。|
|        |[高風險使用者必須變更密碼](#high-risk-users-must-change-password)|在為其帳戶偵測到高風險活動時, 強制使用者變更其密碼。|
|        |[定義應用程式保護原則](#define-app-protection-policies)|每個平臺有一個原則 (iOS、Android、Windows)。|
|        |[需要核准的應用程式](#require-approved-apps)|強制執行手機和平板電腦的行動裝置應用程式保護|
|        |[定義裝置合規性原則](#define-device-compliance-policies)|每個平臺的一個原則|
|        |[需要相容的電腦](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|強制執行電腦的 Intune 管理|
|**敏感性**|[當登入風險為*低*、*中*或*高*時, 需要 MFA](#require-mfa-based-on-sign-in-risk)| |
|         |[需要相容*的電腦和*行動裝置](#require-compliant-pcs-and-mobile-devices)|強制執行電腦和電話/平板電腦的 Intune 管理|
|**高管制**|[*永遠*需要 MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>指派原則給使用者
設定原則之前, 請先識別您對每個保護層所使用的 Azure AD 群組。 一般來說, 基準保護會套用至組織中的每個人。 包含在基線和敏感保護中的使用者, 將套用所有的基準原則加上敏感原則。 保護是累計的, 而且會強制執行最具限制性的原則。 

建議的作法是建立 Azure AD 群組以設定條件式存取排除。 將此群組新增至 [Exclude] 底下的所有條件式存取規則。 這可讓您在對存取問題進行疑難排解時提供存取權給使用者的方法。 建議做為暫時的解決方案。 監視此群組的變更, 並確定排除群組的使用方式只是預期。 

下圖提供使用者指派和排除的範例。

![MFA 規則的使用者指派和排除的範例](../images/identity-access-policies-assignment.png)

在圖中, 會將需要*一定*的條件式存取原則指派給「主要機密專案 X 小組」。 將較高的保護等級套用至使用者時, 請務必合理。 此專案小組的成員必須在每次登入時都提供兩種形式的驗證, 即使他們沒有查看高度規範的內容也是一樣。  

在這些建議中建立的所有 Azure AD 群組, 都必須建立為 Office 365 群組。 在 SharePoint Online 中保護文件時，這對於部署 Azure 資訊保護 (AIP) 特別重要。

![建立 Office 365 群組的螢幕擷取畫面](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>需要根據登入風險的 MFA
在要求 MFA 之前, 請先使用身分識別保護 MFA 註冊原則, 為 MFA 註冊使用者。 註冊使用者後, 您可以強制進行 MFA 以進行登入。 必要條件[工作](identity-access-prerequisites.md)包括向 MFA 註冊所有使用者。

若要建立新的條件式存取原則： 

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 在您成功登入之後, 您會看到 Azure 儀表板。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

![基準 CA 原則](./media/secure-email/CA-EXO-policy-1.png)

 下表說明要為此原則執行的條件式存取原則設定。

**指派**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|使用者和群組|Include|選取使用者和群組 - 選取包含目標使用者的特定安全性群組|從包含試驗使用者的安全性群組開始|
||排除|例外狀況安全性群組；服務帳戶 (應用程式身分識別)|在需要的暫存基礎上修改成員資格|
|雲端應用程式|Include|選取您要套用此規則的應用程式。 例如, 選取 [Office 365 Exchange Online]||
|條件|已設定|是|進行您環境和需求的特定設定|
|登入風險|風險層級||請參閱下表中的指導方針|

**登入風險**

根據目標的保護層級套用設定。

|屬性	|保護層級|值|附註|
|:---|:---------|:-----|:----|
|風險層級|基準|高、中|檢查兩者|
| |敏感性|高、中、低|三個全選|
| |高管制| |將所有選項保留為未選取狀態, 以永遠強制執行 MFA|

**存取控制**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|授與|授予存取|True|已選取|
||需要 MFA|True|Check|
||需要將裝置標示為合規性|False||
||需要混合式 Azure AD 加入的裝置|False||
||需要核准的用戶端應用程式|False||
||需要所有選取的控制項|True|已選取|

> [!NOTE]
> 請選擇 [啟用], 以確定啟用**** 此原則。 此外, 請考慮使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則。



## <a name="block-clients-that-dont-support-modern-authentication"></a>封鎖不支援新式驗證的用戶端
1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 在您成功登入之後, 您會看到 Azure 儀表板。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

下表說明要為此原則執行的條件式存取原則設定。

**指派**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|使用者和群組|Include|選取使用者和群組 - 選取包含目標使用者的特定安全性群組|從包含試驗使用者的安全性群組開始|
||排除|例外狀況安全性群組；服務帳戶 (應用程式身分識別)|視需要暫時修改成員資格|
|雲端應用程式|Include|選取您要套用此規則的應用程式。 例如, 選取 [Office 365 Exchange Online]||
|條件|已設定|是|設定用戶端應用程式|
|用戶端應用程式|已設定|是|行動裝置應用程式和桌面用戶端, 其他用戶端 (選取兩者)|

**存取控制**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|授與|封鎖存取|True|已選取|
||需要 MFA|False||
||需要將裝置標示為合規性|False||
||需要混合式 Azure AD 加入的裝置|False||
||需要核准的用戶端應用程式|False||
||需要所有選取的控制項|True|已選取|

> [!NOTE]
> 請選擇 [啟用], 以確定啟用**** 此原則。 此外, 請考慮使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則。



## <a name="high-risk-users-must-change-password"></a>高風險使用者必須變更密碼
若要確保所有高風險使用者遭到破壞的帳戶強制在登入時執行密碼變更, 您必須套用下列原則。

Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.

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

**回顧:** 不適用

> [!NOTE]
> 請選擇 [啟用], 以確定啟用**** 此原則。 此外, 請考慮使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則

## <a name="define-app-protection-policies"></a>定義應用程式保護原則
應用程式保護原則會定義所允許的應用程式, 以及可對您組織的資料採取的動作。 從 Azure 入口網站中建立 Intune 應用程式保護原則。 

建立每個平臺的原則:
- 適用
- Android
- Windows 10

若要建立新的應用程式保護原則, 請使用您的管理員認證登入 Microsoft Azure 入口網站, 然後流覽至行動**應用程式 > 應用程式保護原則**。 選擇 [**新增原則**]。

iOS 與 Android 的應用程式防護原則選項有些許差異。 下列原則專用於 Android。 請以此做為其他原則的指南。

建議的應用程式清單包括下列專案:
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio Viewer
- OneDrive
- OneNote
- Outlook

下表說明建議的設定:

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|資料重新配置|禁止 Android 備份|是|在 iOS 上，這會特別呼叫 iTunes 和 iCloud|
||允許應用程式將資料傳送到其他應用程式|受原則管理的應用程式||
||[允許應用程式接收其他應用程式的資料]|受原則管理的應用程式||
||禁止執行 [另存新檔]|是||
||選取可儲存公司資料的儲存體服務|商務用 OneDrive、SharePoint||
||限制利用其他應用程式剪下、複製及貼上|使用貼上的原則管理應用程式||
||限制 Web 內容以顯示於受管理的瀏覽器中|否||
||加密應用程式資料|是|在 iOS 上，選取選項：當裝置鎖定時|
||啟用裝置時停用應用程式加密|是|停用此設定以避免雙加密|
||停用聯絡人同步|否||
||停用列印|否||
|存取|需要 PIN 碼才可存取|是||
||選取類型|數值||
||允許簡單的 PIN|否||
||PIN 長度|第||
||允許指紋而非 PIN|是||
||管理裝置 PIN 碼時停用應用程式 PIN 碼|是||
||需要公司認證才能存取|否||
||重新檢查存取需求前等候時間 (分鐘)|30||
||封鎖螢幕擷取及 Android 助手|否|在 iOS 上，這不是可用的選項|
|登入安全性需求|最大 PIN 嘗試次數|分|重設 Pin 碼|
||離線寬限期|720|封鎖存取|
||離線間隔幾天後抹除 App 資料|90|清除資料|
||已越獄/根的裝置| |清除資料|

完成時, 請記得選取 [建立]。 重複上述步驟，並將選取的平台 (下拉式清單) 取代為 iOS。 這會建立兩個應用程式原則，因此在您建立原則之後，請將群組指派給原則，並進行部署。

若要編輯原則並將這些原則指派給使用者, 請參閱[如何建立及指派應用程式保護原則](https://docs.microsoft.com/intune/app-protection-policies)。 

## <a name="require-approved-apps"></a>需要核准的應用程式
若要要求核准的應用程式:

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 在您成功登入之後, 您會看到 Azure 儀表板。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

5. 輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。

6. 選擇 [雲端應用程式]。

7. 選擇 [**選取應用程式**], 從 [**雲端應用程式**] 清單中選取所需的應用程式。 例如, 選取 [Office 365 Exchange Online]。 選擇 [**選取**並**完成**]。

8. 選擇 [**條件**], 選取 [**裝置平臺**], 然後選擇 [**設定**]

9. 在 [**包含**] 下, 選擇 [**選取裝置平臺**], 選取 [ **Android**和**iOS**]。 按一下 [**完成**] 並重新**執行**

10. 選擇 [存取控制] 區段中的 [授與]。

11. 選擇 **[授與存取**], 選取 [**要求核准的用戶端 app**]。 如果是多個控制項, 請選取 **[需要選取的控制項**], 然後選擇 [**選取**]。 

12. 	選擇 **[建立]**。

## <a name="define-device-compliance-policies"></a>定義裝置合規性原則

裝置合規性原則定義裝置必須遵守的需求, 才能標示為合規性。 從 Azure 入口網站建立 Intune 裝置合規性原則。 

建立每個平臺的原則:
- Android
- Android 企業版
- 適用
- macOS
- 此設定適用於下列類型的裝置：
- Windows 8.1 和更新版本
- Windows 10 及更新版本

若要建立裝置合規性原則, 請使用您的管理員認證登入 Microsoft Azure 入口網站, 然後流覽至**Intune > 裝置合規性**。 選取 [**建立原則**]。

Windows 10 建議使用下列設定。

**裝置健康情況: Windows 健康認證服務評估規則**

|屬性|值|附註|
|:---------|:-----|:----|
|需要 BitLocker|必要||
|需要在裝置上啟用安全啟動|必要||
|需要程式碼完整性|必要||


**裝置內容**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|作業系統版本|全部|尚未設定||

針對所有要視為已部署的上述原則，必須將它們的目標設為使用者群組。 若要執行此作業, 您可以在 [**原則**] 區段中選取 [**管理部署**] (與 [新增] 層級), 以建立原則 (在儲存時) 或更新版本。

**系統安全性**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|密碼|需要密碼才能解除鎖定行動裝置|必要||
||簡單密碼|批||
||密碼類型|裝置預設值||
||密碼最小長度|第||
||要求密碼之前的最長閒置時間 (以分鐘為單位)|15 |此設定支援 Android 版本4.0 及更新版本, 或在 KNOX 4.0 和更新版本。 對於 iOS 裝置, 支援 iOS 8.0 和更新版本|
||密碼到期 (天)|41||
||要防止重複使用的先前密碼數目|分||
||當裝置從空閒狀態 (Mobile 和全息) 傳回時, 需要密碼|必要|適用于 Windows 10 及更新版本|
|加密|裝置上資料儲存區的加密|必要||
|裝置安全性|防火牆|必要||
||防毒|必要||
||防|必要|此設定需要使用 Windows 安全中心註冊的反間諜軟體解決方案|
|Defender|Windows Defender 反惡意軟體|必要||
||Windows Defender 反惡意軟體的最低版本||僅支援 Windows 10 桌上出版。 Microsoft 建議版本不超過最新版本五個|
||Windows Defender 反惡意程式碼簽章為最新狀態|必要||
||即時保護|必要|僅支援 Windows 10 桌上出版|

**Windows Defender ATP**

|類型|屬性|值|附註|
|:---|:---------|:-----|:----|
|Windows Defender Advanced 威脅防護規則|要求裝置位於或低於機器風險分數|中||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>需要相容的電腦 (但不相容的電話和平板電腦)
將原則新增至需要相容的電腦之前, 請務必在 Intune 中註冊裝置進行管理。 在將裝置註冊到 Intune 之前, 建議使用多重要素驗證, 以確保裝置屬於預定的使用者。 

若要需要相容的電腦:

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 在您成功登入之後, 您會看到 Azure 儀表板。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

5. 輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。

6. 選擇 [雲端應用程式]。

7. 選擇 [**選取應用程式**], 從 [**雲端應用程式**] 清單中選取所需的應用程式。 例如, 選取 [Office 365 Exchange Online]。 選擇 [**選取**並**完成**]。

8. 若要需要相容的電腦, 但不相容的電話和平板電腦, 請選擇 [**條件**] 和 [**裝置平臺**]。 選擇 [**選取裝置平臺**], 然後選取 [ **Windows** ] 和 [ **macOS**]。

9. 選擇 [存取控制] 區段中的 [授與]。

10. 選擇 **[授與存取**], 選取 [**要求裝置被標示為合規性**]。 如果是多個控制項, 請選取 **[需要所有選取的控制項**], 然後選擇 [**選取**]。 

11. 	選擇 **[建立]**。

如果您的目標是需要相容*的電腦和*行動裝置, 請勿選取 [平臺]。 這會強制執行所有裝置的相容性。 

## <a name="require-compliant-pcs-and-mobile-devices"></a>需要相容*的電腦和*行動裝置

若要要求所有裝置符合性:

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 在您成功登入之後, 您會看到 Azure 儀表板。

2. 從左功能表選擇 [Azure Active Directory]。

3. 在 [安全性] 區段下，選擇 [條件式存取]。

4. 選擇 [新增原則]。

5. 輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。

6. 選擇 [雲端應用程式]。

7. 選擇 [**選取應用程式**], 從 [**雲端應用程式**] 清單中選取所需的應用程式。 例如, 選取 [Office 365 Exchange Online]。 選擇 [**選取**並**完成**]。

8. 選擇 [存取控制] 區段中的 [授與]。

9. 選擇 **[授與存取**], 選取 [**要求裝置被標示為合規性**]。 如果是多個控制項, 請選取 **[需要所有選取的控制項**], 然後選擇 [**選取**]。 

10. 	選擇 **[建立]**。

建立此原則時, 請勿選取 [平臺]。 這會強制執行相容的裝置。


## <a name="next-steps"></a>後續步驟

[了解保護電子郵件的原則建議](secure-email-recommended-policies.md)
