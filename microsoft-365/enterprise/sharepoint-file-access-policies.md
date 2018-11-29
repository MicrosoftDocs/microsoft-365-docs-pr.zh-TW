---
title: 建議的安全文件原則 - Microsoft 365 企業版 | Microsoft Docs
description: 描述如何保護 SharePoint 檔案存取之 Microsoft 建議的原則。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 2f5658146df3da7cc28c907b33e5035a84628fc5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866404"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>保護 SharePoint 網站和檔案的原則建議
本文說明如何實作的建議的身分識別和來保護 SharePoint Online 和 OneDrive for Business 的裝置存取原則。這份指導建立之[一般身分識別與裝置存取的原則](identity-access-policies.md)。 


這些建議根據三種不同的層的安全性與保護 SharePoint 檔案可以套用根據您的需要的層次：**基準**、**機密**、 和**高度規範**。您可以深入了解這些安全性各層和建議的用戶端作業系統與這些建議[概觀 （英文)](microsoft-365-policies-configurations.md)中所參照。

中實作這份指導以及，因此請務必設定 SharePoint 網站與右量的保護，包括確保機密及高度規範內容的適當的權限。如需建立網站的比較基準 」、 機密、 和高度規範保護功能的詳細資訊，請參閱[Secure SharePoint Online 網站及檔案](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)。 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>更新加入 SharePoint 和 OneDrive for Business 的一般原則
下圖說明設定的建議原則保護 SharePoint Online 和 OneDrive for Business 的檔案。它會指出哪些原則將會更新或新建要新增的 SharePoint Online 和 OneDrive for Business 的保護。

![SharePoint Online 與 OneDrive 原則的摘要](../images/identity-access-ruleset-sharepoint.png)

如果當您建立通用原則包含 SharePoint Online，只需要建立新的原則。當設定條件式存取規則，SharePoint Online 包含 OneDrive for Business。

新的原則套用至指定的 SharePoint 網站的特定存取需求實作裝置保護機密和高度規範的內容。 

 下表列出您也需要檢閱和更新或建立新的 SharePoint Online 的原則。一般原則連結至[一般身分識別與裝置存取的原則](identity-access-policies.md)文章 （即將推出的連結） 中的關聯的設定指示。


|保護層級|Policies|詳細資訊|
|:---------------|:-------|:----------------|
|**基準**|[登入風險為*medium*或*high*時需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|包含 SharePoint Online 中的雲端應用程式的工作分派。|
|        |[不支援經過驗證的封鎖用戶端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|包含 SharePoint Online 中的雲端應用程式的工作分派。|
|        |[定義應用程式保護原則](identity-access-policies.md#define-app-protection-policies)|請務必的應用程式清單中包括所有建議的應用程式。請務必更新每個平台 (iOS、 Android、 Windows) 的原則。|
|        |[需要相容的 Pc](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|包含 SharePoint Online 中的雲端應用程式清單。|
|        |[在 SharePoint Online 中使用強制執行的應用程式限制](#use-app-enforced-restrictions-in-sharepoint-online)|新增此新原則。這會告知 Azure AD 使用 SharePoint Online 中所指定的設定。此規則套用至所有使用者，但只會影響包含在 SharePoint Online 存取原則的網站存取權。
|**敏感性**|[登入風險為*低*、 *medium*或*high*時需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| 包含 SharePoint Online 中的雲端應用程式的工作分派。|
|         |[需要相容的 Pc*和*行動裝置](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|包含 SharePoint Online 中的雲端應用程式清單。|
||[SharePoint Online 的存取控制原則](#sharepoint-online-access-control-policies)： 允許從未受管理的裝置僅供瀏覽器存取特定的 SharePoint 網站|這可防止編輯及下載的檔案。若要指定網站的使用者 PowerShell。|
|**高管制**|[*永遠*requrie MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|包含 SharePoint Online 中的雲端應用程式的工作分派。 |
||[SharePoint Online 的存取控制原則](#use-app-enforced-restrictions-in-sharepoint-online)： 從未受管理的裝置封鎖特定的 SharePoint 網站的存取|使用 PowerShell 來指定的網站。|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>在 SharePoint Online 中使用強制執行的應用程式限制
如果您在 SharePoint Online 中實作存取控制項，您必須建立此設定格式化的條件存取原則以告訴您在 SharePoint Online 中設定的原則強制執行的 Azure AD 的 Azure AD。此規則套用至所有使用者，但只會影響您指定當您在 SharePoint Online 中建立存取控制項使用 PowerShell 網站存取權。

若要在本文中設定此原則，請參閱 「 封鎖] 或 [限制存取特定的 SharePoint 網站集合或 OneDrive 帳戶":[控制存取來自未受管理的裝置](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。


## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online 的存取控制原則
Microsoft 建議您保護敏感和高度規範內容的裝置存取控制項使用在 SharePoint 網站內容。您執行這項作業來建立指定的保護及套用來保護所有網站層級的原則。 
- 機密的網站-允許瀏覽器唯讀存取。這樣會讓使用者編輯及下載檔案。
- 高度規範網站 — 封鎖來自未受管理的裝置的存取。

請參閱本文中的"封鎖] 或 [限制存取特定的 SharePoint 網站集合或 OneDrive 帳戶":[控制存取來自未受管理的裝置](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。 

## <a name="how-these-policies-work-together"></a>這些原則如何搭配運作
請務必了解 SharePoint 網站權限通常根據網站存取權的業務需求。這些權限由網站擁有者管理，可高度動態。使用裝置存取原則可確保這些網站，不論是否將使用者指派至 Azure AD 群組來保護 SharePoint 基準、 機密、 相關聯或高度規範保護。 

下圖提供範例 SharePoint 裝置存取原則如何保護網站存取權。

![SharePoint 裝置存取原則如何保護的網站](../images/SharePoint-rules-scenario.png)

在此圖例中：
- James 指派給與比較基準保護相關聯的設定格式化的條件存取原則，但他可以授與存取權敏感或高度規範保護相關聯的 SharePoint 網站。 
- 如果 James 存取專為機密或高度規範他是使用其電腦的成員，其授與存取只要其電腦是相容。
- 如果 James 存取機密網站他的成員使用其未受管理的電話，允許基準使用者，他就會收到僅供瀏覽器存取機密網站因為針對此網站設定的裝置存取原則。 
- 如果 James 可存取他是使用其未受管理的電話成員的高度規範的網站，他將會封鎖因為設定此網站的存取原則。他只可以存取此網站使用其受管理與相容的 PC。


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a>後續步驟
[保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
