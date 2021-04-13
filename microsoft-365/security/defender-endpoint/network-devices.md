---
title: 網路設備探索和弱點管理
description: 現在，安全性建議和弱點偵測可供交換器、路由器、WLAN 控制器及防火牆的作業系統使用。
keywords: 網路裝置、網路裝置弱點偵測、交換器的作業系統、路由器、WLAN 控制器及防火牆
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 43ade52e18ffc8e5db890cb0776090e9b32419e2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687670"
---
# <a name="network-device-discovery-and-vulnerability-management"></a>網路設備探索和弱點管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威脅與弱點管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **掃描和管理網路裝置目前是公開預覽**<br>
> 此預覽版本提供時沒有服務等級協定，不建議用於實際執行工作負載。 某些功能可能不受支援，或可能具有有限的功能。
> 如需詳細資訊，請參閱 [Microsoft Defender For Endpoint preview 功能](preview.md)。

>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

網路探索功能可在 Microsoft 365 安全性中心和 Microsoft Defender 安全性中心主控台的 [ **裝置庫存** ] 區段中取得。  

會在每個網段上使用指定的 Microsoft Defender for Endpoint 裝置，對預先設定的網路裝置執行定期驗證掃描。 一旦探索，Defender 的威脅和弱點管理功能會提供整合的工作流程，以保護探索到的交換器、路由器、WLAN 控制器、防火牆和 VPN 閘道。  

一旦發現網路裝置並分類，安全性系統管理員就能接收最新的安全性建議，並在其組織中的網路裝置上回顧最近發現的漏洞。

## <a name="approach"></a>方法

由於 Endpoint 的 Defender 沒有內置於網路裝置中的感應器，因此不會將網路裝置當作標準端點進行管理。 這些類型的裝置需要一種無代理的方式，遠端掃描會從裝置取得所需的資訊。 根據網路拓撲及特性，架至 Microsoft Defender for Endpoint 的單一裝置或少數裝置會使用 SNMP (唯讀) 來執行網路裝置的驗證掃描。

有兩種類型的裝置需要謹記：

- **評估裝置**：已架的裝置，可供您用來掃描網路裝置。
- **網路裝置**：您要掃描和上架的網路裝置。

### <a name="vulnerability-management-for-network-devices"></a>網路裝置的弱點管理 

一旦發現網路裝置並分類，安全性系統管理員就能接收最新的安全性建議，並在其組織中的網路裝置上回顧最近發現的漏洞。  

## <a name="operating-systems-that-are-supported"></a>支援的作業系統

目前支援下列作業系統：

- Cisco IOS，IOS-XE，NX-OS
- 刺柏 JUNOS
- HPE ArubaOS，Procurve 切換軟體
- Palo Alto 網路 PAN-OS

更多的網路廠商和作業系統會隨著時間而新增，根據客戶的使用量收集的資料而定。 因此，您建議您設定所有網路裝置，即使這些裝置未在此清單中指定也是一樣。

## <a name="how-to-get-started"></a>如何開始使用

第一步是選取將執行已驗證網路掃描的裝置。

1. 決定架裝置的 Defender for Endpoint 裝置 (用戶端或伺服器) ，其具有您規劃掃描之網路裝置的網路連線。 

2. 在端點評估裝置和目標網路裝置之間的 SNMP 流量必須 (例如，由防火牆) 使用。

3. 決定要評估哪些網路裝置以取得漏洞 (例如： Cisco 交換器或 Palo Alto 網路防火牆) 。  

4. 確定所有設定之網路裝置上都已啟用 SNMP 唯讀功能，以允許 Endpoint Endpoint 評估裝置查詢已設定的網路裝置。 這項功能的適當功能不需要「SNMP 寫入」。

5. 取得要掃描之網路裝置的 IP 位址 (或) 部署這些裝置的子網。

6. 取得網路裝置的 SNMP 認證 (例如：社團字串、noAuthNoPriv、authNoPriv、authPriv) 。 設定新的評估工作時，您必須提供認證。  

7. Proxy 用戶端設定：除了 Defender for Endpoint 裝置 proxy 需求以外，不需要額外的設定。

8. 若要允許網路掃描器驗證並正確運作，您必須新增下列網域/URLs：

    - login.windows.net  
    - securitycenter.windows.com
    - login.microsoftonline.com
    - * blob.core.windows.net/networkscannerstable/*

    附注：並非所有 URLs 都是在 Defender for Endpoint 記錄的資料收集清單中指定的。

## <a name="permissions"></a>權限

若要設定評估工作，需要下列使用者許可權選項： **管理安全性中心的安全性設定**。 您可以移至 [**設定**] 角色，找到該許可權  >  ****。 如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](user-roles.md)

## <a name="install-the-network-scanner"></a>安裝網路掃描程式

1. 移至「網路評估」 )  (底下的 **Microsoft 365 安全性**  >  **設定**  >  **端點**  >  **評估工作**。
    1. 在 Microsoft Defender Security Center 中，移至 [設定] > 評估工作] 頁面。

2. 下載網路掃描程式，並將其安裝在「指定的 Defender for Endpoint 評估」裝置上。

![下載掃描器按鈕](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a>網路掃描器安裝 & 註冊

您可以在指定的評估裝置自身或任何其他裝置上完成登入程式，例如，您的個人用戶端裝置)  (。

若要完成網路掃描程式註冊程式：

1. 複製並追蹤出現在命令列上的 URL，並使用提供的安裝程式碼完成註冊程式。
    - 附注：您可能需要變更命令提示字元設定，才能複製 URL。

2. 使用「管理安全性中心的安全性設定」許可權的 Microsoft 帳戶輸入程式碼並登入。

3. 完成後，您應該會看到一則確認已登入的郵件。

## <a name="configure-a-new-assessment-job"></a>設定新的評估工作  

在 [ **設定**] 中的 [評估工作] 頁面上，選取 [ **新增網路評估工作**]。 依照設定程式選擇要定期掃描的網路裝置，並將其新增至設備清查。

若要防止網路設備清查中的裝置重複，請確定每個 IP 位址在多個評估裝置中只設定一次。

![新增網路評估工作按鈕](images/assessment-jobs-add.png)

新增網路評估工作步驟：

1. 選擇「評估工作」名稱和安裝網路掃描器的「評估裝置」。 此裝置會執行定期驗證掃描。 
2. 新增要掃描的目標網路裝置的 IP 位址 (或) 部署這些裝置的子網。 
3. 新增目標網路裝置所需的 SNMP 認證。 
4. 儲存新設定的網路評估工作，以啟動定期網路掃描。 

### <a name="scan-and-add-network-devices"></a>掃描及新增網路裝置

在設定過程中，您可以執行一次測試掃描，以確認：

- 在端點評估裝置和設定的目標網路裝置之間，有連線能力。
- 設定的 SNMP 認證正確無誤。

每個評估裝置可支援最多1500個成功的 IP 位址掃描。 例如，如果您掃描10個不同的子網，其中只有 100 IP 位址會傳回成功的結果，您就可以從相同評估裝置上的其他子網掃描 1400 IP 其他位址。  

如果有多個 IP 位址範圍/子網可供掃描，測試掃描結果將需要數分鐘的時間才能顯示。 測試掃描可用於最多1024個位址。

結果顯示後，您可以選擇要包含在定期掃描中的裝置。 如果您略過查看掃描結果，不論裝置的回應) 為何，所有設定的 IP 位址都會新增至網路評估工作 (。 也可以匯出掃描結果。

## <a name="device-inventory"></a>裝置清單

新發現的裝置會顯示在 [**裝置庫存**] 頁面的 [新增 **網路裝置**] 索引標籤底下。 在新增評估工作之前，可能需要長達兩小時，直到裝置更新為止。

![裝置庫存中的 [網路裝置] 區段](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a>疑難排解

### <a name="network-scanner-installation-has-failed"></a>網路掃描器安裝失敗

確認所需的 URLs 已新增至防火牆設定中的允許網域。 此外，請確定已依照[設定裝置 proxy 和網際網路連線設定](configure-proxy-internet.md)中所述的方式設定 proxy 設定

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a>未顯示 Microsoft.com/devicelogin 網頁

確認所需的 URLs 已新增至防火牆中的允許網域。 此外，請確定已依照 [設定裝置 proxy 和網際網路連線設定](configure-proxy-internet.md)中所述的方式來設定 proxy 設定。

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a>在幾個小時後，網路裝置不會顯示在設備清查中

在完成評估工作設定之後所發生的初始掃描後，應在幾小時之後更新掃描結果。

如果仍未顯示裝置，請確認服務 ' MdatpNetworkScanService ' 已在您安裝網路掃描程式的評估裝置上執行，並在相關的評估工作設定中執行「執行掃描」。  

如果5分鐘之後仍未取得結果，請重新開機服務。  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a>裝置上次看到時間超過24小時

驗證掃描器是否正常運作。 然後移至 [掃描定義]，然後選取 [執行測試]。 檢查相關 IP 位址傳回的錯誤訊息。

### <a name="required-threat-and-vulnerability-management-user-permission"></a>必要威脅和弱點管理使用者許可權

註冊完成時出現錯誤：「似乎您沒有足夠的許可權可以新增代理程式。 必要的許可權是「管理安全性中心的安全性設定」。

按任意鍵退出。

請系統管理員為您指派必要的許可權。 或者，您可以透過提供登入程式碼和連結，讓另一個相關成員協助您進行登入處理常式。

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a>註冊程式在註冊程式的命令列中使用提供的連結失敗

嘗試其他瀏覽器或將登入連結和程式碼複製到不同的裝置。

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a>文字太小或無法從命令列複製文字

變更裝置上的命令列設定，以允許複製及變更文字大小。

## <a name="related-articles"></a>相關文章

- [裝置清單](machines-view-overview.md)
- [設定進階功能](advanced-features.md)
