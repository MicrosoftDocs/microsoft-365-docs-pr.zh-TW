---
title: 最常見的12個任務，可供安全性小組用來支援在家運作
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: 保護您的商務電子郵件和網路威脅中的資料，包括勒索軟體、網路釣魚和惡意附件。
ms.openlocfilehash: 109ba05b21ce9c1355be73dbdfb000d6eb8c4e4d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930468"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>最常見的12個任務，可供安全性小組用來支援在家運作

如果您喜歡 [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) ，並突然找到您一開始支援主要的工作力員工，我們需要協助您確保您的組織盡可能安全地運作。 這篇文章會將工作加以劃分，以協助安全小組盡可能快地執行最重要的安全性功能。

![執行這些首要工作以支援從家裡工作。](../media/security/security-support-remote-work.png)

如果您是使用 Microsoft 商務版方案中的小型組織或大中型組織，請參閱下列資源：

- [安全 Office 365 和 Microsoft 365 商務方案的前10種方式](../admin/security-and-compliance/secure-your-business-data.md)
- [Microsoft 365 針對市場活動](../campaigns/index.md) (包含 Microsoft 365 商務版) 的建議安全性設定

針對使用我們企業方案的客戶，Microsoft 建議您完成下表中所列的工作，以套用至您的服務方案。 若要將訂閱合併，而不是購買 Microsoft 365 企業方案，請注意下列事項：

- Microsoft 365 E3 包括 Enterprise Mobility + Security (EMS) E3 和 Azure AD P1
- Microsoft 365 E5 包括 EMS E5 和 Azure AD P2

****

|步驟|工作|所有 Office 365 企業版方案|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1|[ (MFA) 啟用 Azure AD Multi-Factor 驗證 ](#1-enable-azure-ad-multi-factor-authentication-mfa)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|第|[防範威脅](#2-protect-against-threats)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|個|[為 Office 365 設定 Microsoft Defender](#3-configure-microsoft-defender-for-office-365)|||![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[設定 Microsoft Defender 身分識別](#4-configure-microsoft-defender-for-identity)|||![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[開啟 Microsoft 365 Defender](#5-turn-on-microsoft-365-defender)|||![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[設定電話和平板電腦的 Intune 行動裝置應用程式保護](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[設定來賓的 MFA 和條件式存取（包括 Intune 應用程式保護）](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[將電腦登記到裝置管理並要求相容的電腦](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[針對 cloud connectivity 優化網路](#9-optimize-your-network-for-cloud-connectivity)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[訓練使用者](#10-train-users)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|第|[開始使用 Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security)|||![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12 |[監視威脅並採取動作](#12-monitor-for-threats-and-take-action)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

開始之前，請先檢查 Microsoft 365 安全中心的[Microsoft 365 安全評分](./defender/microsoft-secure-score.md)。 您可以從集中式儀表板監視及提高 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。 您可以在設定建議的安全性功能、執行安全性相關工作 (例如查看報告) 或使用協力廠商應用程式或軟體解決建議等方面提供積分。 本文中的建議工作將會提升您的分數。

![Microsoft 安全分數的螢幕擷取畫面](../media/secure-score.png)

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1：啟用 Azure AD Multi-Factor 驗證 (MFA) 

您可以採取哪一項最佳做法，以提升在家運作的員工安全性，以開啟 MFA。 如果您還沒有適當的處理常式，請將此視為緊急試驗，並確定您有支援人員準備好協助員工停滯。 如您可能無法散佈硬體安全裝置，請使用 Windows Hello 生物特徵和 smartphone 驗證應用程式（如 Microsoft Authenticator）。

一般情況下，Microsoft 建議您在要求 MFA 之前，為使用者提供14天的時間來註冊其裝置以進行 Multi-Factor 驗證。 不過，如果您的員工突然從家裡運作，請繼續進行，並將 MFA 視為安全性優先順序，並準備好協助需要該員工的使用者。

套用這些原則只需要數分鐘，但準備好在今後數天內為您的使用者提供支援。

****

|方案|建議|
|---|---|
|沒有 Azure AD P1 或 P2) 的 Microsoft 365 方案 (|[在 Azure AD 中啟用安全性預設](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD 中的安全性預設包含了適用於使用者和系統管理員的 MFA。|
|使用 Azure AD P1 Microsoft 365 E3 () |使用[常見的條件式存取原則](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)來設定下列原則： <br/>- [要求系統管理員使用 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [要求所有使用者使用 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [封鎖舊版驗證](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|使用 Azure AD P2 Microsoft 365 E5 () |利用 Azure AD Identity Protection，藉由建立下列兩種原則來開始實作 Microsoft [建議的一組條件式存取和相關原則](./office-365-security/identity-access-policies.md)：<br/> - [登入風險為中或高時，需要 MFA](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [封鎖不支援新式驗證的用戶端](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [高風險使用者必須變更密碼](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|
|

## <a name="2-protect-against-threats"></a>2：防禦威脅

所有 Microsoft 365 方案都包含各種威脅防護功能。 Bumping 這些功能的保護只需要數分鐘的時間。

- 反惡意程式碼保護
- 保護惡意 URLs 和檔案
- 防網路釣魚保護
- 反垃圾郵件保護

請參閱[防範 Office 365 中的威脅](office-365-security/protect-against-threats.md)，以取得您可以做為起點的指導方針。

## <a name="3-configure-microsoft-defender-for-office-365"></a>3：為 Office 365 設定 Microsoft Defender

適用于 Office 365 的 Microsoft Defender （包含 Microsoft 365 E5 和 Office 365 E5）會保護您的組織免受電子郵件訊息、連結 (URLs) 和協同工具帶來的惡意威脅。 這可能需要數小時才能完成設定。

Microsoft Defender Office 365：

- 使用可檢查附件和惡意內容連結的智慧系統，即時保護您的組織免受未知電子郵件威脅。 這些自動化的系統包括強健的引爆平臺、啟發式和機器學習模型。
- 透過識別及封鎖小組網站和文件庫中的惡意檔案，在使用者共同作業及共用檔案時，保護您的組織。
- 套用機器學習模型和高級模擬偵測演算法，以防止網路釣魚攻擊。

如需概要，包含計畫的摘要，請參閱[Office 365 的 Defender](./office-365-security/defender-for-office-365.md)。

您的全域系統管理員可以設定下列保護：

- [設定安全連結原則](office-365-security/set-up-safe-links-policies.md)
- [設定安全連結的通用設定](office-365-security/configure-global-settings-for-safe-links.md)
- [設定安全附件原則](office-365-security/set-up-safe-attachments-policies.md)

您必須與 Exchange Online 系統管理員合作，並 SharePoint 線上管理員為這些工作負載設定 Defender Office 365：

- [用於 SharePoint、OneDrive 及 Microsoft Teams 的 Microsoft Defender for Endpoint](office-365-security/mdo-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4：設定 Microsoft Defender 身分識別

[適用於身分識別的 Microsoft Defender](/azure-advanced-threat-protection/what-is-atp) 是利用內部部署 Active Directory 訊號的雲端型安全性解決方案，它會識別、偵測及調查貴組織中的進階威脅、遭入侵的身分識別，以及惡意內部攻擊動作。 請將重點放在下一個，因為它會保護您的部署和雲端基礎結構、沒有相依性或必要條件，而且可提供立即的益處。

- 請參閱 [Microsoft Defender For Identity 快速入門](/azure-advanced-threat-protection/install-atp-step1) 以快速取得設定
- 觀賞 [影片： Microsoft Defender 身分識別簡介](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- 查看 [Microsoft Defender 進行身分識別部署的三個階段](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-365-defender"></a>5：啟用 Microsoft 365 Defender

現在，您已設定 microsoft defender 的 Office 365 和 microsoft defender 的身分識別，您可以在一個儀表板中查看這些功能的合併信號。 [Microsoft 365 defender](./defender/microsoft-365-defender.md)會將警示、事件、自動化調查和回應，以及跨工作負載的高級搜尋 (Microsoft defender for Identity、Defender for Office 365、microsoft defender for Endpoint 及 Microsoft Cloud App Security) 變成單一窗格中的[security.microsoft.com](https://security.microsoft.com)。

![MTP 儀表板圖例](../media/top-ten-security-remote-work-mtp-dashboard.png)

在您為 Office 365 服務設定一或多個 Defender 後，請開啟 MTP。 新功能會持續新增至 MTP;請考慮改為接收預覽功能。

- [深入瞭解 MTP](./defender/microsoft-365-defender.md)
- [開啟 MTP](./defender/m365d-enable.md)
- [加入宣告預覽功能](./defender/preview.md)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6：設定電話和平板電腦的 Intune 行動裝置應用程式保護

Microsoft Intune行動應用程式管理 (MAM) 可讓您在不管理這些裝置的情況下，管理和保護您組織的電話和平板電腦上的資料。 以下為運作方式：

- 您可以建立應用程式保護原則 (APP) ，以決定裝置上的哪些應用程式受管理，以及允許哪些行為 (例如防止將受管理的應用程式的資料複製到非管理的應用程式) 。 您為每個平臺 (iOS Android) 建立一個原則。
- 建立應用程式保護原則之後，您可以在 Azure AD 中建立條件式存取規則，以要求核准的應用程式和應用程式資料保護，以強制執行這些原則。

應用程式保護原則包含許多設定。 幸運的是，您不需要深入瞭解每個設定並權衡選項。 Microsoft 可讓您輕鬆地透過建議起始點來套用設定的設定。 [使用應用程式保護原則的資料保護架構](/mem/intune/apps/app-protection-framework)包含三個您可以選擇的層級。

更好的是，Microsoft 會以一組條件式存取和相關原則協調此應用程式保護框架。我們建議所有組織都使用做為開始點。 如果您已使用本文中的指導方針實施 MFA，您會有這麼的做法！

若要設定行動應用程式保護，請使用 [常見身分識別和裝置存取](./office-365-security/identity-access-policies.md)原則中的指導方針：

 1. 使用 [套用 [應用程式資料保護](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies) 原則] 指導方針為 IOS 和 Android 建立原則。 第2級 (增強型資料保護) 建議用於基準保護。
 2. 建立條件式存取規則，以 [要求核准的應用程式和應用程式保護](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)。

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7：設定來賓的 MFA 和條件式存取（包括 Intune 行動應用程式保護）

接下來，讓我們確定您可以繼續共同作業和使用客人。 如果您正在使用 Microsoft 365 E3 計畫，而且您為所有使用者實施了 MFA，則會設定。

如果您使用的是 Microsoft 365 E5 計畫，而且已利用 azure 身分識別保護以進行風險型 MFA，您需要進行一些調整 (因為 azure AD 身分識別保護未擴充至來賓) ：

- 建立新的條件式存取規則，以要求對來賓和外部使用者進行 MFA。
- 更新以排除來賓和外部使用者為基礎之風險的 MFA 條件式存取規則。

使用更新共同原則的指導方針， [允許和保護來賓和外部存取](./office-365-security/identity-access-policies-guest-access.md) ，以瞭解來賓存取如何與 Azure AD 搭配運作，以及如何更新受影響的原則。

您建立的 Intune 行動裝置應用程式保護原則，以及要求核准的應用程式和應用程式保護的條件式存取規則，都可以套用到來賓帳戶，並協助保護您的組織資料。

> [!NOTE]
> 如果您已註冊電腦進入裝置管理以要求相容的電腦，您也需要從強制執行裝置規範的條件式存取規則中排除來賓帳戶。

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8：將電腦登記到裝置管理並要求相容的電腦

有幾種方法可以註冊工作力的裝置。 每個方法都取決於裝置的擁有權 (個人或公司)、裝置類型 (iOS、Windows、Android) 及管理需求 (重設、同質、鎖定)。 這可能需要一些時間才能完成排序。請參閱：[在 Microsoft Intune 中註冊裝置](/mem/intune/enrollment/)。

最快速的方式是[設定 Windows 10 裝置的自動註冊](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

您也可以利用下列教程：

- [使用 Autopilot 在 Intune 中登記 Windows 裝置](/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [使用 apple Business Manager (ABM) 在 Intune 中登記 iOS/iPadOS 裝置的 apple 公司裝置註冊功能](/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

註冊裝置後，請使用一般身分 [識別和裝置存取原則](./office-365-security/identity-access-policies.md) 中的指導方針來建立下列原則：

- [定義裝置相容性原則](./office-365-security/identity-access-policies.md#define-device-compliance-policies)-Windows 10 的建議設定包括需要病毒防護。 如果您有 Microsoft 365 E5，請使用 Microsoft Defender for Endpoint 來監視員工裝置的健康情況。 請確定其他作業系統的相容性原則包括防防毒保護和端點保護軟體。
- [需要相容的電腦](./office-365-security/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) -這是 Azure AD 中強制執行裝置合規性原則的條件式存取規則。

只有一個組織可以管理裝置，因此請務必從 Azure AD 中的條件式存取規則中排除來賓帳戶。 如果您未從需要裝置規範的原則中排除來賓和外部使用者，這些原則將會封鎖這些使用者。 如需詳細資訊，請參閱 [更新共同原則以允許及保護來賓和外部存取](./office-365-security/identity-access-policies-guest-access.md)。

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9：針對 cloud connectivity 優化您的網路

如果您要快速讓員工大量員工運作，這種突然的連線模式交換器可能會對公司網路基礎結構產生重大影響。 在採用雲端服務之前，許多網路都已經過縮放及設計。 在許多情況下，網路可容忍遠端工作者，但未設計為同時供所有使用者遠端使用。

網路元素（如 VPN 集中式、中央網路出口裝置 (例如 proxy 和資料遺失防護裝置）) 、中央網際網路頻寬、backhaul MPLS 電路、NAT 功能等等，突然因使用其負載的整個公司而面臨大量的壓力。 最終結果是不良效能和生產力，以及對在家工作進行調整的使用者不佳的使用者經驗。

使用者所存取的雲端應用程式會提供傳統中透過公司網路傳送流量的某些保護。 如果您已在本文中達成這項步驟，您已針對 Microsoft 365 服務和資料，執行了一組複雜的雲端安全性控制。 使用這些控制措施後，您就可以將遠端使用者的流量直接路由傳送至 Office 365。 如果您仍需要 VPN 連結才能存取其他應用程式，您可以執行分割隧道，以大幅改善效能和使用者體驗。 在您的組織達成合約後，您就可以在一天內由合理的網路小組完成。

如需詳細資訊，請參閱這些檔上的資源：

- [概述：使用 VPN 分割隧道為遠端使用者優化連線能力](/Office365/Enterprise/office-365-vpn-split-tunnel)
- [實作 Office 365 的 VPN 分割通道](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

本主題最近的博客文章：

- [如何快速優化遠端員工的流量 & 減少基礎結構的負載](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [安全性專業人員的替代方法，可在當今獨特的遠端工作案例中取得新式的安全性控制措施](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10：訓練使用者

訓練使用者可將您的使用者與安全性作業小組儲存大量的時間和不滿。 聰明的使用者不太可能開啟附件或按一下可疑電子郵件訊息中的連結，也很可能避免可疑的網站。

Harvard 甘迺迪 School [Cybersecurity 活動手冊](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) 提供好的指導方針，可為組織內的安全性感知建立強大的文化，包括訓練使用者來識別網路釣魚攻擊。

Microsoft 365 提供下列資源，協助您在組織中告知使用者：

****

|概念|資源|
|---|---|
|Microsoft 365|[可自訂的教學路徑](/office365/customlearning/) <p>這些資源可協助您將組織中使用者的訓練放在一起|
|Microsoft 365 安全性|[學習模組：利用內建的內建、智慧的安全性來保護您的組織 Microsoft 365](/learn/modules/security-with-microsoft-365) <p>此模組可讓您描述 Microsoft 365 安全性功能如何協同運作，並闡明這些安全性功能的優點。|
|多重要素驗證|[雙步驟驗證：其他驗證頁面為何？](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>本文可協助使用者瞭解哪些多重要素驗證，以及如何在您的組織中使用它。|
|

除了這項指導之外，Microsoft 也建議您的使用者採取本文所述的動作： [保護您的帳戶和裝置免受駭客和惡意](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)代碼的攻擊。 這些動作包括：

- 使用強式密碼
- 保護裝置
- 啟用非管理裝置的 Windows 10 和 Mac 電腦 (上的安全性功能) 

Microsoft 也建議您採取下列文章中建議的動作來保護其個人電子郵件帳戶：

- [協助保護您的 Outlook .com 電子郵件帳戶](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [使用2步驟驗證保護您的 Gmail 帳戶](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11：開始使用 Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security)提供豐富的知名度、控制資料旅行和複雜的分析，以在所有雲端服務之間識別及打擊 cyberthreats。 開始使用雲端 App 安全性後，系統會自動啟用反常狀況偵測原則，但雲端 App 安全性會有七天的初始學習週期，但不會引發所有的反常偵測警報。

立即開始使用雲端 App 安全性。 稍後您可以設定更複雜的監控和控制項。

- [快速入門：開始使用雲端 App 安全性](/cloud-app-security/getting-started-with-cloud-app-security)
- [取得暫態的行為分析和反常狀況偵測](/cloud-app-security/anomaly-detection-policy)
- [深入瞭解 Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [查看新的功能與功能](/cloud-app-security/release-notes)
- [請參閱基本設定指示](/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12：監控威脅並採取動作

Microsoft 365 包括多種監視狀態和採取適當動作的方式。 您最好的起點是 Microsoft 365 的安全性中心 ([https://security.microsoft.com](https://security.microsoft.com)) ，您可以在其中查看組織的[Microsoft 安全分數](./defender/microsoft-secure-score.md)，以及需要您注意的任何警示或實體。

- [開始使用 Microsoft 365 的安全性中心](./defender/overview-security-center.md)
- [監視及檢視報告](./defender/overview-security-center.md)
- [請參閱 Microsoft 365 中的安全性入口網站](./defender/portals.md)

## <a name="next-steps"></a>後續步驟

恭喜！ 您很快就會執行一些最重要的安全性保護，而且您的組織會有更安全的安全性。 現在，您已準備好繼續進行威脅防護功能 (包括 Microsoft Defender for Endpoint) 、資料分類及保護功能，以及保護系統管理帳戶。 如需 Microsoft 365 的更深入、一組安全性建議，請參閱[Microsoft 365 security for Business 決策者 (bdm) ](Microsoft-365-security-for-bdm.md)。

另外，請 [docs.microsoft.com/security](/security)中的 Microsoft 新的安全性中心。