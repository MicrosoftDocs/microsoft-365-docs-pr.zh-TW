---
title: 設定 iOS 功能端點的 Microsoft Defender
description: 說明如何部署 Microsoft Defender ATP 以取得 iOS 功能
keywords: microsoft，defender，atp，ios，設定，功能，ios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8f74d4799bcb02051cddd09b80ed6ab50258302b
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587224"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a>設定 iOS 功能端點的 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> IOS 的 Defender for the 會使用 VPN，以便提供 Web 保護功能。 這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a>使用 iOS 之 Defender for Endpoint 的條件式存取  
Microsoft Defender for iOS 與 Microsoft Intune 和 Azure Active Directory 可根據裝置風險層級強制實施裝置合規性和條件式存取原則。 Defender for Endpoint 是行動威脅防護 (MTD) 解決方案，您可以透過 Intune 部署此功能，以利用這項功能。

如需如何設定 iOS 的使用 Defender for Endpoint 的條件式存取的相關資訊，請參閱 [Defender For endpoint And Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)。

## <a name="web-protection-and-vpn"></a>Web 保護和 VPN

根據預設，iOS 的 Defender for Endpoint 會包含並啟用 web 保護功能。 [Web 保護](web-protection-overview.md) 可協助保護裝置免受網頁威脅，並保護使用者免受網路釣魚攻擊。 IOS 的 Defender for Endpoint 會使用 VPN，以提供此保護。 請注意，這是本機 VPN，與傳統 VPN 不同，網路流量不會傳送到裝置外。

預設為啟用時，可能需要停用 VPN。 例如，當設定 VPN 時，您想要執行一些無法運作的應用程式。 在這種情況下，您可以依照下列步驟，從裝置上的應用程式中選擇停用 VPN：

1. 在您的 iOS 裝置上，開啟 [ **設定** ] app，按一下或點擊 **[一般** ] 和 [ **VPN**]。
1. 按一下或點擊 Microsoft Defender ATP 的「i」按鈕。
1. 關閉 **[連線時開啟]** 以停用 VPN。

    > [!div class="mx-imgBorder"]
    > ![需要時 VPN 設定連接](images/ios-vpn-config.png)

> [!NOTE]
> 停用 VPN 時，將無法使用 Web 保護。 若要重新啟用 Web 保護，請開啟裝置上的 Microsoft Defender for Endpoint app，然後按一下或點擊 [ **啟動 VPN**]。

## <a name="co-existence-of-multiple-vpn-profiles"></a>共同存在多個 VPN 設定檔

Apple iOS 不支援多個全裝置的 Vpn 同時作用中。 雖然裝置上可以有多個 VPN 設定檔，但一次只能有一個 VPN 可用。


## <a name="configure-compliance-policy-against-jailbroken-devices"></a>設定已越獄裝置的相容性原則

為了保護公司資料無法在已越獄的 iOS 裝置上存取，我們建議您在 Intune 上設定下列符合性原則。

> [!NOTE]
> 在此情況下，iOS 的 Microsoft Defender for Endpoint 不會針對 jailbreak 案例提供防護。 若在已越獄的裝置上使用，則在特定案例中，如您公司的電子郵件識別碼及公司設定檔圖片，該應用程式所使用的資料會 (如果可以在本機公開可用) 

請遵循下列步驟，建立對已越獄裝置的相容性原則。

1. 在 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)中，移至 [**裝置**  ->  **規範原則**] [  ->  **建立原則**]。 選取 "iOS/iPadOS" 作為平臺，然後按一下 [ **建立**]。

    > [!div class="mx-imgBorder"]
    > ![建立原則](images/ios-jb-policy.png)

2. 指定原則的名稱，例如「Jailbreak 的合規性原則」。
3. 在 [規範設定] 頁面上，按一下以展開 [**裝置健全**] 區段，然後按一下 [封鎖 **裝置** 的 **封鎖**] 欄位。

    > [!div class="mx-imgBorder"]
    > ![原則設定](images/ios-jb-settings.png)

4. 在 [不 *符合之動作* ] 區段中，根據您的需求選取動作，然後選取 **[下一步]**。

    > [!div class="mx-imgBorder"]
    > ![原則動作](images/ios-jb-actions.png)

5. 在 [ *工作分派* ] 區段中，選取您要包含此原則的使用者群組，然後選取 **[下一步]**。
6. 在 [ **複查 + 建立** ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。

## <a name="configure-custom-indicators"></a>設定自訂指示器

IOS 的 Defender for Endpoint 可讓系統管理員也在 iOS 裝置上設定自訂指示器。 如需如何設定自訂指示器的詳細資訊，請參閱 [管理指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)。

> [!NOTE]
> IOS 的 Defender for a，只支援為 IP 位址和 URLs/網域建立自訂指示器。

## <a name="report-unsafe-site"></a>報告不安全的網站

網路釣魚網站會為了取得您的個人或財務資訊，模仿可信的網站。 如果您想要報告可能是網路釣魚網站的網站，請造訪 [ [提供有關網路保護的意見](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 反應] 頁面。

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a>安裝 Microsoft Defender for Endpoint 時 iOS 的電池消耗問題

應用程式的電池使用量是根據許多因素（包括 CPU 和網路使用量）計算而來。 Microsoft Defender for Endpoint 會在背景中使用本機/環路傳回 VPN，檢查任何惡意網站或連線的網頁流量。 任何應用程式的網路封包都會進行此項檢查，從而導致無法準確計算 Microsoft Defender for Endpoint 的電池使用量。 這為使用者提供了錯誤的印象。 Microsoft Defender for Endpoint 的實際電池消耗小於裝置上的 [電池設定] 頁面上顯示的數目。 這是以 Microsoft Defender for Endpoint app 所進行的測試為基礎，以瞭解電池消耗。

此外，使用的 VPN 也是本機 VPN，與傳統的 vpn 不同的是，網路流量不會傳送到裝置外。
