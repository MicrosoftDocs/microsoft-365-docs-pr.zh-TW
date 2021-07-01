---
title: 在 iOS 功能上設定 Microsoft Defender for Endpoint
description: 說明如何在 iOS 功能上部署 Microsoft Defender for Endpoint
keywords: microsoft，defender，Microsoft Defender for Endpoint，ios，configure，features，ios
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
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230004"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>在 iOS 功能上設定 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> IOS 上的 Defender for Endpoint 會使用 VPN，以便提供 Web 保護功能。 這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>在 iOS 上使用 Defender for Endpoint 進行條件式存取  
Microsoft Defender for Endpoint on iOS 隨 Microsoft Intune 和 Azure Active Directory 可根據裝置風險分數強制強制執行裝置合規性和條件式存取原則。 Defender for Endpoint 是行動威脅防護 (MTD) 解決方案，您可以透過 Intune 部署此功能，以利用這項功能。

如需如何設定 iOS 上的使用 Defender for Endpoint 的條件式存取的相關資訊，請參閱 [Defender For endpoint And Intune](/mem/intune/protect/advanced-threat-protection)。

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 的 Jailbreak 偵測
Microsoft Defender for Endpoint 具備偵測已越獄之受管理和受管理裝置的能力。 如果偵測到裝置已越獄，將會向安全中心報告 **高** 風險警示，而且如果根據裝置風險分數設定條件式存取，則系統會封鎖裝置以存取公司資料。

## <a name="web-protection-and-vpn"></a>Web 保護和 VPN

根據預設，iOS 上的 Defender for Endpoint 會包含並啟用 web 保護功能。 [Web 保護](web-protection-overview.md) 可協助保護裝置免受網頁威脅，並保護使用者免受網路釣魚攻擊。 IOS 上的 Defender for Endpoint 會使用 VPN，以提供此保護。 請注意，這是本機 VPN，與傳統 VPN 不同，網路流量不會傳送到裝置外。

預設為啟用時，可能需要停用 VPN。 例如，當設定 VPN 時，您想要執行一些無法運作的應用程式。 在這種情況下，您可以依照下列步驟，從裝置上的應用程式中選擇停用 VPN：

1. 在您的 iOS 裝置上，開啟 **設定** 應用程式，按一下或點擊 **[一般**]，然後再按一下 [ **VPN**]。
1. 按一下或點擊 Microsoft Defender for Endpoint 的「i」按鈕。
1. 關閉連線停用 VPN 的 **要求**。

    > [!div class="mx-imgBorder"]
    > ![需要時 VPN 設定連接](images/ios-vpn-config.png)

> [!NOTE]
> 停用 VPN 時，將無法使用 Web 保護。 若要重新啟用 Web 保護，請開啟裝置上的 Microsoft Defender for Endpoint app，然後按一下或點擊 [ **啟動 VPN**]。

## <a name="co-existence-of-multiple-vpn-profiles"></a>共同存在多個 VPN 設定檔

Apple iOS 不支援多個全裝置的 Vpn 同時作用中。 雖然裝置上可以有多個 VPN 設定檔，但一次只能有一個 VPN 可用。

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>在應用程式防護原則 (MAM) 中設定 Microsoft Defender 的 Endpoint 危險信號

Microsoft Defender for Endpoint 可以設定成傳送威脅信號，以用於應用程式保護原則 (APP，也稱為 iOS/iPadOS 上的 MAM) 。 使用此功能，您可以使用 Microsoft Defender for Endpoint 來保護對 unenrolled 裝置中公司資料的存取。

使用 Microsoft Defender for Endpoint 安裝應用程式保護原則的步驟如下：

1. 設定從 Microsoft 端點管理員租使用者至 Microsoft Defender for Endpoint 的連線。 在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心中，移 **至 [** 跨平臺) ] 底下的 [  >    >  **microsoft defender for endpoint] 的 [microsoft defender for** endpoint (] 或 [安裝) 下的 endpoint **Security**  >  **microsoft defender** ] (]，然後開啟 **設定的應用程式保護原則 iOS** 下的切換。
1. 選取 [儲存]。 您應該會看到 [ **線上狀態** ] 現在已設定為 [ **啟用**]。
1. 建立應用程式保護原則：在您的 Microsoft Defender Endpoint connector 安裝程式完成後，請流覽至 [原則]) 底下 (的 [**應用**  >  **程式 app protection 原則**]，以建立新的原則或更新現有的原則。
1. 針對您的原則，選取您的組織所需的平臺、 **應用程式、資料保護和存取需求** 設定。
1. 在 [**條件式啟動**  >  **裝置條件**] 底下，您會發現設定 **允許的裝置威脅層級上限**。 這將需要設定為 [低]、[中]、[高] 或 [安全]。 您可以使用的動作會 **封鎖存取權** 或 **清除資料**。 您可能會看到 [資訊] 對話方塊，確定在此設定之前設定好您的連接器會生效。 如果您的連接器已設定好，您可以忽略此對話方塊。
1. 完成工作分派並儲存原則。

如需 MAM 或 app protection 原則的詳細資訊，請參閱 [iOS app protection 原則設定](/mem/intune/apps/app-protection-policy-settings-ios)。

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>為 MAM 或 unenrolled 裝置部署 Microsoft Defender for Endpoint

IOS 上的 Microsoft Defender for Endpoint 會啟用應用程式保護原則案例，並可在 Apple 應用程式存放區中取得。

使用者應直接從 Apple app store 安裝最新版的應用程式。

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>設定已越獄裝置的相容性原則

為了保護公司資料無法在已越獄的 iOS 裝置上存取，我們建議您在 Intune 上設定下列符合性原則。

> [!NOTE]
> Jailbreak 偵測是 Microsoft Defender for Endpoint on iOS 所提供的功能。 不過，我們建議您將此原則設定為其他防禦層級，以防禦 jailbreak 案例。

請遵循下列步驟，建立對已越獄裝置的相容性原則。

1. 在 [Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，移至 [**裝置**  ->  **規範原則**] [  ->  **建立原則**]。 選取 "iOS/iPadOS" 作為平臺，然後按一下 [ **建立**]。

    > [!div class="mx-imgBorder"]
    > ![建立原則](images/ios-jb-policy.png)

2. 指定原則的名稱，例如「Jailbreak 的合規性原則」。
3. 在 [規範設定] 頁面上，按一下以展開 [**裝置健全**] 區段，然後按一下 [封鎖 **裝置** 的 **封鎖**] 欄位。

    > [!div class="mx-imgBorder"]
    > ![原則設定](images/ios-jb-settings.png)

4. 在 [不 **符合之動作** ] 區段中，根據您的需求選取動作，然後選取 **[下一步]**。

    > [!div class="mx-imgBorder"]
    > ![原則動作](images/ios-jb-actions.png)

5. 在 [ **工作分派** ] 區段中，選取您要包含此原則的使用者群組，然後選取 **[下一步]**。
6. 在 [ **複查 + 建立** ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。

## <a name="configure-custom-indicators"></a>設定自訂指示器

IOS 上的 Defender for Endpoint 可讓系統管理員也在 iOS 裝置上設定自訂指示器。 如需如何設定自訂指示器的詳細資訊，請參閱 [管理指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。

> [!NOTE]
> IOS 上的 Defender for Endpoint 支援只為 IP 位址和 URLs/網域建立自訂指示器。

## <a name="report-unsafe-site"></a>報告不安全的網站

網路釣魚網站會為了取得您的個人或財務資訊，模仿可信的網站。 如果您想要報告可能是網路釣魚網站的網站，請造訪 [ [提供有關網路保護的意見](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 反應] 頁面。

