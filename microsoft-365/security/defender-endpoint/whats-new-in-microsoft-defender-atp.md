---
title: 適用於端點的 Microsoft Defender 新功能
description: 請參閱最新版 Microsoft Defender for Endpoint 中 (GA) 可用的功能，以及 Windows 10 和 Windows 伺服器的安全性功能。
keywords: Microsoft Defender for Endpoint 中的新功能，ga，一般可用，功能，可用，新
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
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
ms.openlocfilehash: 7bb231049815da12ef6e5e48c88d79f5263f8708
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53277010"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint"></a>適用於端點的 Microsoft Defender 新功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink)

在最新版的 Microsoft Defender for Endpoint 和 Windows 10 和 Windows 伺服器中的安全性功能)  (，下列功能一般皆可使用。

如需預覽功能的詳細資訊，請參閱 [預覽功能](preview.md)。


> [!TIP]
> RSS 摘要：將下列 URL 複製並貼到您的摘要讀取器時，獲得此頁面的通知：
>
> ```https
> /api/search/rss?search=%22features+are+generally+available+%28GA%29+in+the+latest+release+of+Microsoft+Defender+for+Endpoint%22&locale=en-us&facet=
> ```

## <a name="june-2021"></a>2021 年 6 月

- [增量匯出軟體漏洞評估](get-assessment-methods-properties.md#31-methods) Api <br> 對 [漏洞與安全](get-assessment-methods-properties.md) 設定 API 集合的出口評估的補充。 <br> 與完整的軟體漏洞評估 (JSON 回應) （用來取得組織的軟體漏洞評估整個快照）不同之處在于，使用增量匯出 API 呼叫只是用於提取選取日期和目前日期之間所發生的變更， ("delta" API 呼叫) 。 您不需要每次獲得大量資料的完整匯出，只會取得新的、已修復和更新之弱點的特定資訊。 Delta export API 通話也可以用來計算不同的 KPIs 例如「已修復多少個漏洞」或「已新增多少個新的漏洞至組織」。

- [匯出安全性漏洞與安全設定的評估](get-assessment-methods-properties.md) Api <br> 會新增 APIs 的集合，以在每個裝置上拉威脅與弱點管理的資料。 有不同的 API 呼叫可取得不同類型的資料：安全的設定評估、軟體清查評估和軟體漏洞評估。 每個 API 通話包含組織中裝置的必要資料。

- [修復活動](get-remediation-methods-properties.md) Api <br>  新增包含回應的 APIs 集合，其中包含已在您的租使用者中建立威脅與弱點管理修復活動。 回應資訊類型包括一個依識別碼的修復活動、所有修復活動，以及一個修正活動的公開裝置。

- [裝置探索](device-discovery.md) <br> 協助您找出連接至公司網路的非管理裝置，不需要額外裝置或繁瑣的處理常式變更。 使用架裝置，您可以在網路中尋找未受管理的裝置，並評估漏洞和風險。 然後，您可以將已探索的裝置上架，以降低網路中具有非受管理端點的相關風險。

   > [!IMPORTANT]
   > Standard discovery 會成為從2021年7月19日開始之所有客戶的預設模式。 您可以選擇透過 [設定] 頁面保留基本模式。

- [裝置群組定義](/microsoft-365/security/defender-endpoint/machine-groups) 現在可以包含每個條件的多個值。 您可以將多個標記、裝置名稱和網域設定為單一裝置群組的定義。

## <a name="march-2021"></a>2021 年 3 月

- [使用 Microsoft Defender 資訊安全中心管理無法篡改的保護](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) <br> 您可以使用稱為 *租使用者附加* 的方法，在 Windows 10、Windows Server 2016 及 Windows Server 2019 上管理防篡改保護設定。

## <a name="january-2021"></a>2021 年 1 月

- [Windows 虛擬桌面](https://azure.microsoft.com/services/virtual-desktop/) <br> Microsoft Defender for Endpoint 現在新增 Windows 虛擬機器的支援。

## <a name="december-2020"></a>2020 年 12 月

- [iOS 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-ios.md) <br> Microsoft Defender for Endpoint 現在新增 iOS 的支援。 瞭解如何在 iOS 上安裝、設定、更新及使用 Microsoft Defender for Endpoint。

## <a name="september-2020"></a>2020 年 9 月

- [Android 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-android.md) <br> Microsoft Defender for Endpoint 現在新增了 Android 的支援。 瞭解如何在 Android 上安裝、設定、更新及使用 Microsoft Defender for Endpoint。
- [威脅及弱點管理 macOS 支援](tvm-supported-os.md)<br> macOS 的威脅和弱點管理現在位於公開預覽中，它會持續偵測 macOS 裝置上的漏洞，以協助您著重于風險，以協助您排定修正優先順序。 若要深入瞭解，請參閱[Microsoft Tech Community 博客文章](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-for-endpoint-adds-depth-and-breadth-to-threat/ba-p/1695824)。

## <a name="august-2020"></a>2020 年 8 月

- [Android 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-android.md) <br> Microsoft Defender for Endpoint 現在新增了 Android 的支援。 瞭解如何在 Android 上安裝、設定及使用 Microsoft Defender for Endpoint。

## <a name="july-2020"></a>2020 年 7 月

- [建立憑證的指示器](manage-indicators.md) <br> 建立指示器以允許或封鎖憑證。

## <a name="june-2020"></a>2020 年 6 月

- [Linux 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-linux.md) <br> Microsoft Defender for Endpoint 現在新增了對 Linux 的支援。 瞭解如何在 Linux 上安裝、設定、更新及使用 Microsoft Defender for Endpoint。

- [評估實驗室中的攻擊模擬器](evaluation-lab.md#threat-simulator-scenarios) <br> Microsoft Defender for Endpoint 已與各種威脅模擬平臺產生合作，讓您能輕鬆地從入口網站中測試平臺的功能。

## <a name="april-2020"></a>2020 年 4 月

- [威脅 & 漏洞管理 API 支援](exposed-apis-list.md) <BR>執行威脅 & 漏洞管理相關 API 通話，例如，取得組織面臨威脅洩密分數或裝置安全分數、軟體和裝置弱點、軟體版本發行、裝置弱點資訊、安全性建議資訊等。 若要深入瞭解，請參閱[Microsoft Tech Community 博客文章](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。

## <a name="november-december-2019"></a>November-December 2019

- [macOS 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-mac.md) <BR> MacOS 上的 Microsoft Defender for Endpoint 會將下一代保護帶入 Mac 裝置。 整合端點安全性平臺的核心元件現在可用於 Mac 裝置，包括 [端點偵測和回應](microsoft-defender-endpoint-mac.md)。

- [威脅 & 弱點管理應用程式和應用程式版本的週期結束資訊](tvm-security-recommendation.md) <BR>已到達生命週期結束的應用程式和應用程式版本會加以標記或標示為如此，這樣您就會發現不再支援這些應用程式和應用程式，而且可以採取動作進行卸載或更換。 這樣做有助於減少因未修補的應用程式而造成的各種弱點洩密相關的風險。

- [威脅 & 弱點管理的高級搜尋架構](advanced-hunting-schema-reference.md) <BR>使用高級搜尋架構中 & 弱點管理表的威脅，以查詢軟體清查、弱點知識庫、安全性設定評估及安全性設定知識庫。

 - [威脅 & 漏洞管理角色型存取控制](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) <BR>使用新的許可權可讓您最大的彈性建立以 SecOps 為導向的角色、威脅 & 漏洞管理的角色或混合角色，因此只有授權的使用者才能存取特定資料，以執行其工作。 您也可以指定威脅 & 漏洞管理角色是否可以只查看弱點相關的資料，或建立及管理修正及例外狀況，以進一步進一步細化。

- [裝置健康情況與合規性報告](machine-reports.md) <br/> 裝置健康情況和合規性報告可提供組織中裝置的高層級資訊。

## <a name="october-2019"></a>2019 年 10 月

- [IP 位址、URLs/網域的指標](manage-indicators.md) <BR> 您現在可以使用您自己的威脅情報，允許或封鎖 URLs/網域。

- [Microsoft 威脅專家-依需求的專家](microsoft-threat-experts.md) <BR> 您現在可以選擇從入口網站中的數個地方 Microsoft 威脅專家，以協助您進行調查的內容。

- [連線的 Azure AD 應用程式](connected-applications.md)<br> [連線的應用程式] 頁面會提供連線至您組織中之端點之 Azure AD 應用程式的相關資訊。

- [API Explorer](api-explorer.md)<br> API explorer 可讓您輕鬆地為任何可用的 Microsoft Defender API 端點構造和執行 API 查詢、測試及傳送要求。

## <a name="september-2019"></a>2019 年 9 月

- [使用 Intune 篡改保護設定](prevent-changes-to-security-settings-with-tamper-protection.md) <br/> 您現在可以在 Microsoft 365 裝置管理入口網站 (Intune) 中，為組織 (或關閉) 開啟防篡改保護。

- [即時回應](live-response.md) <BR> 使用遠端命令介面連線來立即存取裝置。 進行深入調查工作並採取立即回應動作，及時包含已識別的威脅（即時）。

- [評估實驗室](evaluation-lab.md) <BR> Microsoft Defender for Endpoint 評估實驗室的設計是為了消除裝置和環境設定的複雜性，使您能夠專注于評估平臺的功能、執行模擬，以及查看動作中的預防、偵測和修正功能。

- [Windows Server 2008 R2 SP1](configure-server-endpoints.md) <BR> 您現在可以將 Windows Server 2008 R2 SP1 上架。

## <a name="june-2019"></a>2019 年 6 月

- [威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md) <BR> 新的內建功能，使用以風險為基礎的方法來探索、優先順序和修正端點漏洞與錯誤配置。

- [裝置健康情況和符合性報告](machine-reports.md)  裝置健康情況和合規性報告可提供組織中裝置的高層級資訊。

## <a name="may-2019"></a>2019 年 5 月

- [威脅防護報告](threat-protection-reports.md)<BR>「威脅防護」報告提供組織中所產生之提醒的高層級資訊。

- [Microsoft 威脅專家](microsoft-threat-experts.md)<BR> Microsoft 威脅專家是 Microsoft Defender for Endpoint 中新的受管理威脅搜尋服務，可提供主動搜尋、優先順序及其他內容與深入瞭解，以進一步讓安全性運作中心 (SOCs) 可快速且正確地識別及回應威脅。 它提供額外的專業知識及光纖，以供 Microsoft 客戶在 Microsoft 365 中擴充安全性運作功能。

- [指標](ti-indicator.md) <BR> 指示器的 APIs 現在一般可用。

- [互通性](partner-applications.md) <BR> Microsoft Defender for Endpoint 支援協力廠商應用程式，協助增強平臺的偵測、調查和威脅智慧功能。

## <a name="april-2019"></a>2019 年 4 月

- [Microsoft 威脅專家目標攻擊通知功能](microsoft-threat-experts.md) <BR> Microsoft 威脅專家 ' 針對組織提供的目標攻擊通知警示，可提供盡可能快的資訊，使其能在其網路中吸引重要威脅（包括時程表、破壞範圍及入侵方法）。

- [適用於端點的 Microsoft Defender API](apis-intro.md) <BR> Microsoft Defender for Endpoint 會透過一組程式設計 APIs 公開其資料和動作。 這些 APIs 可讓您根據 Microsoft Defender for Endpoint 功能來自動化工作流程及創新。

## <a name="february-2019"></a>2019 年 2 月

- [事件](view-incidents-queue.md) <BR> 事件是 Microsoft Defender for Endpoint 中的新實體，它會將所有相關的警示和相關實體組合在一起，以敘述更廣泛的攻擊案例，讓分析員更深入瞭解複雜威脅的 purview。

- [將上一版 Windows 上線](onboard-downlevel.md)<BR> 板載支援的 Windows 裝置版本，使其可將感應器資料傳送至 Microsoft Defender for Endpoint 感應器。

## <a name="october-2018"></a>2018 年 10 月

- [受攻擊面縮小規則](attack-surface-reduction.md)<BR>所有攻擊面降低規則現在都支援 Windows Server 2019。

- [受控資料夾存取權](enable-controlled-folders.md)<BR> 目前 Windows Server 2019 支援受控資料夾存取。

- [自訂偵測](manage-indicators.md)<BR>使用自訂偵測，您可以建立自訂查詢，以監視任何行為（例如可疑或新興威脅）的事件。 可透過建立自訂偵測規則，利用高級搜尋的威力來做到這一點。

- [與 Azure Defender 整合](configure-server-endpoints.md)<BR> Microsoft Defender for Endpoint 會與 Azure Defender 整合，以提供全面的伺服器保護解決方案。 透過這項整合，Azure defender 可利用 Microsoft Defender for Endpoint 的功能，為 Windows 伺服器提供增強的威脅偵測。

- [受管理的安全性服務提供者 (MSSP) 支援](mssp-support.md)<BR> Microsoft Defender for Endpoint 會提供 MSSP 整合，為此案例新增支援。 整合可讓 MSSPs 採取下列動作：透過安全性資訊和事件管理 (SIEM) 工具，取得 MSSP 客戶 Microsoft Defender 資訊安全中心入口網站的存取權、取得電子郵件通知，以及取得警示。

- [可移除裝置控制項](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)<BR>Microsoft Defender for Endpoint 提供多個監視和控制功能，以協助防止可移除裝置的威脅，包括允許或封鎖特定硬體識別碼s 的新設定。

- [支援 iOS 和 Android 裝置](configure-endpoints-non-windows.md)<BR> 現在支援 iOS 和 Android 裝置，而且可以架至服務。

- [威脅分析](threat-analytics.md)<BR>
威脅分析是一組互動式報告，由 Microsoft Defender for Endpoint research 小組所發佈，可在識別新興威脅和病毒發作時立即使用。 報告可協助安全性運作小組評估其環境的影響，並提供建議的動作，以包含、增加組織的恢復能力，以及防止特定威脅。

- Windows 10 版本1809中的新功能，有兩個新的攻擊面降低規則：
  - 封鎖 Adobe Reader，以建立子流程
  - 封鎖 Office 通訊應用程式以建立子流程。

- [Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
  - 反惡意軟體掃描介面 (AMSI) 已擴充為同時涵蓋 Office VBA 宏。 [Office VBA + AMSI：在惡意的宏上分型 veil](https://cloudblogs.microsoft.com/microsoftsecure/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/)。
  - Microsoft Defender 防毒軟體 Windows 10 版本1809中的新功能，現在可以在沙箱 (預覽) [中執行](https://www.microsoft.com/security/blog/2018/10/26/windows-defender-antivirus-can-now-run-in-a-sandbox)，以提升其安全性。
  - 設定 Microsoft Defender 防毒軟體掃描的[CPU 優先順序設定](configure-advanced-scan-types-microsoft-defender-antivirus.md)。

## <a name="march-2018"></a>2018 年 3 月

- [進階搜捕](advanced-hunting-overview.md)

   使用 Microsoft Defender for Endpoint 中的高級搜尋查詢資料。

- [受攻擊面縮小規則](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)

  新的攻擊面減少規則：

  - 使用勒索軟體的高級防護
  - 封鎖 Windows 本機安全性群組子系統 (lsass.exe 中的認證竊取) 
  - 封鎖來自 PSExec 和 WMI 命令的進程建立
  - 封鎖從 USB 執行的不受信任和未簽署程式
  - 從電子郵件客戶程式和 web 郵件封鎖可執行檔內容

- [自動化調查和修正](automated-investigations.md)<BR> 使用自動調查以調查和修正威脅。

    > [!NOTE]
    > 可從 Windows 10 版本1803或更新版本。

- [條件式存取](conditional-access.md) <br> 啟用條件式存取，以更好地保護使用者、裝置和資料。

- [Microsoft Defender for Endpoint Community center](community.md)<BR>
    Microsoft Defender for Endpoint Community Center 是一個地方，可讓社區成員瞭解、共同作業及分享產品的經驗。

- [受控資料夾存取權](enable-controlled-folders.md)<BR>
您現在可以封鎖不受信任的處理常式，不需要使用可控資料夾存取寫入磁片區。

- [將非 Windows 裝置上線](configure-endpoints-non-windows.md)<BR>
    Microsoft Defender for Endpoint 為 Windows 和非 Windows 平臺提供集中的安全性作業體驗。 您可以在 Microsoft Defender 資訊安全中心中查看不同支援作業系統 (OS) 中的警示，也能更好地保護組織的網路。

- [角色型存取控制 (RBAC)](rbac.md)<BR>
    使用以角色為基礎的存取控制 (RBAC) ，您可以在安全性作業小組中建立角色和群組，以授與入口網站的適當存取權。


- [Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)<BR>
Microsoft Defender 防毒軟體現在會共用 Microsoft 365 服務之間的偵測狀態，並與 Microsoft Defender for Endpoint 進行交互操作。 如需詳細資訊，請參閱[在 Microsoft Defender 防毒軟體中透過雲端提供的保護使用下一代技術](cloud-protection-microsoft-defender-antivirus.md)。

    封鎖第一次看到可以封鎖不可移植的可執行檔 (例如 .JS、VBS 或宏) 以及可執行檔。 如需詳細資訊，請參閱 [在第一次看到時啟用區塊](configure-block-at-first-sight-microsoft-defender-antivirus.md)。
