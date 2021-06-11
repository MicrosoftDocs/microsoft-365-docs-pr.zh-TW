---
title: 在 Microsoft Defender for Endpoint 中設定高級功能
description: 在 Microsoft Defender for Endpoint 中開啟諸如封鎖檔等高級功能。
keywords: 「高級功能」、「設定」、「封鎖檔案」、「自動調查」、「自動解析」、skype、microsoft defender 身分識別、office 365、azure 資訊保護、intune
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7fd9ec25c21b2d70238bd5b0d6b58b60731088ea
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845471"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>在 Defender for Endpoint 中設定高級功能

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

根據您使用的 Microsoft 安全產品，有些高級功能可能可讓您將 Defender 與的端點整合。

## <a name="enable-advanced-features"></a>啟用高級功能

1. 在功能窗格中，選取 [**喜好設定**] [  >  **高級功能**]。
2. 選取您要設定的高級功能，並 **在開啟** 和 **關閉** 之間切換設定。
3. 按一下 [ **儲存喜好** 設定]。

使用下列高級功能，以更好地抵禦潛在的惡意檔案，並在安全性調查期間取得更佳的洞察力。

## <a name="automated-investigation"></a>自動調查

開啟此功能以利用服務的自動化調查和修正功能。 如需詳細資訊，請參閱 [自動化調查](automated-investigations.md)。

## <a name="live-response"></a>即時回應

開啟此功能，讓具有適當許可權的使用者可以在裝置上啟動即時回應會話。

如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。

## <a name="live-response-for-servers"></a>伺服器的即時回應
開啟此功能，讓具有適當許可權的使用者可以在伺服器上啟動即時回應會話。

如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。


## <a name="live-response-unsigned-script-execution"></a>Live response 未簽署的腳本執行

啟用此功能可讓您在即時回應會話中執行未簽署的腳本。

## <a name="always-remediate-pua"></a>永遠修正 PUA
可能有害的應用程式 (PUA) 是一種軟體類別，可導致您的機器執行緩慢、顯示未預期的廣告，或是最壞的軟體安裝可能是意外或不需要的軟體。 

開啟此功能，以便在租使用者中的所有裝置上修正 (PUA) 可能有害的應用程式，即使裝置上未設定 PUA 保護也是一樣。 這有助於防止使用者不小心在其裝置上安裝不需要的應用程式。 關閉時，修正取決於裝置設定。 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a>限制範圍內裝置群組的關聯
這種設定可用於本機 SOC 作業只想要將警示關聯限制為可以存取之裝置群組的情況。 開啟此設定，就不會再視為單一事件，由跨裝置群組的警示所組成的事件。 然後，本機 SOC 便可對該事件採取動作，因為他們有權存取相關的其中一個裝置群組。 不過，全域 SOC 會透過設備群組（而不是一個事件）看到數種不同的事件。 建議您不要開啟此設定，除非這麼做超過整個組織內的事件關聯的優點
>[!NOTE]
>變更此設定只會影響未來的警示關聯。

## <a name="enable-edr-in-block-mode"></a>在封鎖模式中啟用 EDR
端點偵測和回應 (EDR) 在封鎖模式中時，即使 Microsoft Defender 防毒軟體是以被動模式執行，也可以保護惡意的惡意資料。 開啟時，以封鎖模式 EDR 會封鎖在裝置上偵測到的惡意的偽像或行為。 block 模式中的 EDR 會在幕後運作，以修正偵測到破壞後偵測到的惡意作品。


## <a name="autoresolve-remediated-alerts"></a>自動解析修正的警示

針對在 Windows 10 或之後建立的承租人，版本1809會預設設定自動調查和修正功能，以解決自動分析結果狀態為「沒有發現威脅」或「修正」的警示。  如果您不想要自動解決的提醒，您必須手動關閉該功能。

> [!TIP]
> 針對在該版本之前建立的承租人，您必須從 [ [高級功能](https://securitycenter.windows.com/preferences2/integration) ] 頁面手動開啟此功能。

> [!NOTE]
>
> - 自動解決動作的結果可能會影響以裝置上所找到之主動警示為基礎的裝置風險等級計算。
> - 如果安全作業分析員手動將警示的狀態設定為「正在進行中」或「已解析」，則自動解析功能不會覆寫。

## <a name="allow-or-block-file"></a>允許或封鎖檔

只有當您的組織符合這些需求時，才可使用封鎖：

- 使用 Microsoft Defender 防毒軟體作為使用中的反惡意程式碼解決方案，並
- 已啟用雲端式保護功能

這項功能可讓您在網路中封鎖可能有害的檔案。 封鎖檔會使其無法在組織中的裝置上讀取、寫入或執行。

在下列情況開啟 **允許或封鎖** 檔案：

1. 在功能窗格中，選取 [**設定**  >  **高級功能**  >  **允許或封鎖檔**]。

1. 切換設定為 **開啟** 或 **關閉**。

    ![封鎖檔功能的高級設定影像](images/atp-preferences-setup.png)

1. 選取頁面底部的 [ **儲存喜好** 設定]。

開啟此功能後，您可以透過檔案的設定檔頁面面上的 [**新增指示器**] 索引標籤來 [封鎖](respond-file-alerts.md#allow-or-block-file)檔案。

## <a name="custom-network-indicators"></a>自訂網路指示器

開啟此功能可讓您為 IP 位址、網域或 URLs 建立指示器，以根據您的自訂指示器清單，判斷是否允許或封鎖這些指標。

若要使用此功能，裝置必須執行 Windows 10 版本1709或更新版本。 他們也應以封鎖模式進行網路保護，以及反惡意程式碼平臺的版本4.18.1906.3 或更新版本， [請參閱 KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834)。

如需詳細資訊，請參閱 [管理指示器](manage-indicators.md)。

> [!NOTE]
> 網路保護會利用信譽服務處理要求的位置，這些位置可能位於您為您的 Defender for Endpoint data 所選取的位置以外。

## <a name="tamper-protection"></a>防篡改保護
在某些網路攻擊中，不良的演員會嘗試停用電腦上的安全性功能，例如防防毒保護。 不良的演員，例如停用您的安全性功能，以更輕鬆地存取資料、安裝惡意程式碼，或利用您的資料、身分識別及裝置。

防篡改保護實質上會鎖定 Microsoft Defender 防毒軟體，並防止您的安全性設定透過應用程式和方法進行變更。

如果您的組織使用 Microsoft Defender 防毒軟體和雲端型防護，則可以使用此功能。 如需詳細資訊，請參閱[使用下一代技術在 Microsoft Defender 防毒軟體中透過雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)。

使防篡改保護保持開啟，以避免安全性解決方案及其基本功能的不想要的變更。


## <a name="show-user-details"></a>顯示使用者詳細資料

開啟此功能，讓您能看到儲存在 Azure Active Directory 中的使用者詳細資料。 詳細資料包括調查使用者帳戶實體時，使用者的圖片、名稱、標題及部門資訊。 您可以在下列視圖中尋找使用者帳戶資訊：

-  安全性操作儀表板
- 警示佇列
- 裝置詳細資料頁面

如需詳細資訊，請參閱 [調查使用者帳戶](investigate-user.md)。


## <a name="skype-for-business-integration"></a>商務用 Skype 整合

啟用商務用 Skype 整合功能可讓您使用商務用 Skype、電子郵件或電話與使用者進行通訊。 當您需要與使用者通訊並減輕風險時，這會很便利。

> [!NOTE]
> 當裝置與網路隔離時，會有一個快顯視窗，您可以在其中選擇啟用 Outlook 和 Skype 通訊，以便在使用者與網路中斷連線的情況下，與使用者通訊。 此設定適用于裝置處於隔離模式時 Skype 和 Outlook 通訊。

## <a name="microsoft-defender-for-identity-integration"></a>Microsoft Defender 用於身分識別整合

與 Microsoft Defender 身分識別的整合，可讓您直接在 Microsoft Identity security 產品中直接旋轉。 Microsoft Defender for Identity 會以其他有關可疑已遭破壞之帳戶和相關資源之深入瞭解的觀點來增強調查。 透過啟用這項功能，您就可以透過從識別的觀點來切換網路，來充實裝置型調查功能。

> [!NOTE]
> 您必須具有適當的授權，才能啟用此功能。

## <a name="office-365-threat-intelligence-connection"></a>Office 365威脅智慧連接

只有當您具有使用中 Office 365 E5 或威脅情報附加元件時，才可使用此功能。 如需詳細資訊，請參閱 Office 365 企業版 E5 產品頁面。

當您開啟此功能時，您可以將 Microsoft Defender 中 Office 365 的資料合併成 Microsoft Defender 資訊安全中心，以跨 Office 365 信箱及 Windows 裝置進行全面的安全性調查。

> [!NOTE]
> 您必須具有適當的授權，才能啟用此功能。

若要在 Office 365 威脅情報中接收上下文相關的裝置整合，您必須在安全性 & 規範儀表板中啟用 [Endpoint for Endpoint] 設定。 如需詳細資訊，請參閱 [威脅調查和回應](/microsoft-365/security/office-365-security/office-365-ti)。

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Microsoft 威脅專家目標攻擊通知

除了兩個 Microsoft 威脅專家元件，已設定目標攻擊通知是在正式發行時。 專家隨選功能仍在預覽中。 如果您已套用預覽，且已核准您的應用程式，您只能使用專家隨選功能。 您可以從 Microsoft 威脅專家透過您的端點入口網站的 [警示] 儀表板，以及透過電子郵件（如果您設定它）來接收目標攻擊通知。

> [!NOTE]
> Microsoft 威脅專家的 Defender for Endpoint 的功能可與[Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)的 E5 授權搭配使用。
## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

啟用此設定時，會將 Defender 的端點信號轉寄至 Microsoft Cloud App Security，以提供 Cloud 應用程式使用的深入瞭解。 轉寄的資料會儲存並處理雲端 App 安全性資料所在的相同位置。

> [!NOTE]
> 在執行 Windows 10 的裝置上，將會有[Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)的 E5 授權、版本 1709 (os 組建16299.1085 （含[KB4493441](https://support.microsoft.com/help/4493441)) 、Windows 10、版本 1803 (os 組建17134.704 搭配[KB4493464](https://support.microsoft.com/help/4493464)) 、Windows 10、版本 1809 (os 組建17763.379 搭配[KB4489899](https://support.microsoft.com/help/4489899)) （或更新版本）。

## <a name="microsoft-secure-score"></a>Microsoft 安全分數

在 Microsoft 365 security center 中，將 microsoft Defender for Endpoint 信號轉寄給 microsoft 安全評分。 開啟此功能可讓 Microsoft 安全分數看到裝置的安全性狀況。 轉寄的資料會與您的 Microsoft 安全分數資料儲存在相同的位置。


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>從 Microsoft Defender for Identity 入口網站啟用 Microsoft Defender for Endpoint 整合

若要在 Microsoft Defender for Identity 中接收與內容相關的設備整合，您也需要啟用 Microsoft Defender for Identity 入口網站中的功能。

1. 使用全域系統管理員或安全性管理員角色，登入 [Microsoft Defender 的身分識別入口網站](https://portal.atp.azure.com/) 。

2. 按一下 [ **建立您的實例**]。

3. 將 Integration 設定切換為 [ **開啟** ]，然後按一下 [ **儲存**]。

完成這兩個入口網站的整合步驟之後，您可以在 [裝置詳細資料] 或 [使用者詳細資料] 頁面看到相關的警示。

## <a name="web-content-filtering"></a>Web 內容篩選
封鎖包含有害內容之網站的存取，並追蹤所有網域中的 web 活動。 若要指定您要封鎖的 web 內容類別別，請建立 [web 內容篩選原則](https://security.microsoft.com/preferences2/web_content_filtering_policy)。 在部署 [Microsoft Defender For Endpoint security 基準](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)時，確保您具有封鎖模式中的網路保護。


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>與 Microsoft 規範中心共用端點警示
將端點安全性警示和其會審狀態轉寄給 Microsoft 規範中心，讓您能夠使用預警增強內幕風險管理原則，並在內部風險造成損害之前加以修正。 轉寄的資料會處理並儲存在與 Office 365 資料相同的位置。

在「內幕風險管理」設定中設定 [安全性原則違規指示器](/microsoft-365/compliance/insider-risk-management-settings#indicators) 後，就會與適用使用者的「內部使用者風險管理」共用端點警示。



## <a name="microsoft-intune-connection"></a>Microsoft Intune 連接

可以將 Endpoint for 端點與[Microsoft Intune](/intune/what-is-intune)整合，以[啟用裝置風險的條件式存取](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。 當您 [開啟此功能](configure-conditional-access.md)時，您可以使用 Intune 與 Intune 共用 Defender 裝置資訊，進而增強原則的執行能力。

> [!IMPORTANT]
> 您必須在 Intune 和 Defender for Endpoint 上啟用整合，才能使用此功能。 如需特定步驟的詳細資訊，請參閱 [在 Defender For Endpoint 中設定條件式存取](configure-conditional-access.md)。

只有在下列情況下，才可使用此功能：

- 企業行動力 + 安全性 E3 的授權租使用者，以及 Windows e5 (或 Microsoft 365 企業版 e5) 
- 使用 Intune 管理 Windows 10 裝置的作用中 Microsoft Intune 環境會[連接 Azure AD](/azure/active-directory/devices/concept-azure-ad-join/)。


### <a name="conditional-access-policy"></a>條件式存取原則

當您啟用 Intune 整合時，Intune 會自動建立傳統的條件式存取 (CA) 原則。 這項傳統 CA 原則是設定狀態報表至 Intune 的必要條件。 不應該刪除。

> [!NOTE]
> Intune 所建立的傳統 CA 原則與新式條件式 [存取原則](/azure/active-directory/conditional-access/overview/)不同，用來設定端點。


## <a name="device-discovery"></a>裝置探索
協助您找出連接至公司網路的非管理裝置，不需要額外裝置或繁瑣的處理常式變更。 使用架裝置，您可以在網路中尋找未受管理的裝置，並評估漏洞和風險。 如需詳細資訊，請參閱 [Device discovery](device-discovery.md)。

> [!NOTE]
> 您永遠可以套用篩選器，以從裝置庫存清單中排除未受管理的裝置。 您也可以在 API 查詢上使用 [上架狀態] 欄，以篩選出未受管理的裝置。 

## <a name="preview-features"></a>預覽功能

瞭解適用于 Defender 的端點預覽版本中的新功能。 開啟預覽體驗，嘗試即將推出的功能。

您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。




## <a name="related-topics"></a>相關主題

- [更新資料保留設定](data-retention-settings.md)
- [設定警示通知](configure-email-notifications.md)
