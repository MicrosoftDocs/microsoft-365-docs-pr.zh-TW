---
title: 設定及驗證 Microsoft Defender 防毒軟體網路連線
description: 設定並測試您與 Microsoft Defender 防病毒雲端保護服務的連線。
keywords: 防病毒，Microsoft Defender 防毒程式，反惡意程式碼，安全性，Defender，cloud，入侵，保護層級
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 6ccc2eb171e85793899a7862ed9a317815d89626
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007574"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>設定及驗證 Microsoft Defender 防毒軟體網路連線

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

為了確保 Microsoft Defender 防病毒雲端提供的保護運作正常，您的安全小組必須設定您的網路，以允許端點和某些 Microsoft 伺服器之間的連線。 本文列出必須允許的連線，例如使用防火牆規則，並提供驗證連線的指示。 正確設定保護可協助確保您從雲端提供的保護服務中取得最佳價值。

如需網路連線的某些詳細資料，請參閱博客文章 [重要變更 Microsoft Active Protection Services 端點](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 。

> [!TIP]
> 在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範網站，確認下列功能正在運作：
>
> - 雲端提供的保護
> - Fast 教學 (包括第一次看到區塊) 
> - 可能有害的應用程式封鎖

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>允許連線至 Microsoft Defender 防病毒雲端服務

Microsoft Defender 防毒軟體雲端服務為您的端點提供快速、強大的保護。 啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和整個網路提供重要的防護。 請參閱 [啟用雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md) ，以取得使用 Intune、Microsoft 端點設定管理員、群組原則、PowerShell Cmdlet 或 Windows 安全性應用程式中個別用戶端上啟用服務的詳細資訊。 

在您啟用服務之後，您可能需要設定網路或防火牆，以允許其和您的端點之間的連線。 因為您的保護是雲端服務，所以電腦必須能夠存取網際網路，並且到達 Microsoft Defender for Office 365 機器教學服務。 請勿 `*.blob.core.windows.net` 從任何類型的網路檢查中排除 URL。 

> [!NOTE]
> Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞到網路和端點。 雖然它稱為雲端服務，但並不只是保護儲存在雲端中的檔案，而是使用分散式資源和機器學習功能，以比傳統的安全性智慧更新速度更快的速率來提供對端點的保護。

## <a name="services-and-urls"></a>服務和 URLs

本節中的表格列出 (URLs) 的服務及其相關聯的網站位址。 

請確定沒有防火牆或網路篩選規則拒絕存取這些 URLs。 否則，您可能需要為 (排除 URL) 以外的使用者建立允許規則 `*.blob.core.windows.net` 。 下表中的 URLs 使用埠443進行通訊。

| 服務和描述 | URL |
|----|---- |
| Microsoft Defender 防病毒雲端提供的保護服務，也稱為 Microsoft Active Protection Service (MAPS) <p>Microsoft Defender 防毒程式會使用此服務提供雲端提供的保護|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) 和 Windows Update Service (WU)  <p>這些服務可讓安全性情報和產品更新   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> 如需詳細資訊，請參閱 [Windows Update 的連接端點](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|安全性智慧更新替代下載位置 (ADL) <p>如果已安裝的安全性情報已過期 (7 天以上或以上版本，則這是 Microsoft Defender 防病毒安全性情報更新的替代位置) |  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| 惡意程式碼提交存放區 <p>這是透過提交表單或自動範例提交提交給 Microsoft 的檔案上傳位置。 | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
|  (CRL) 的憑證吊銷清單 <p>當您建立連結至地圖的 SSL 連線以更新 CRL 時，Windows 會使用此清單。   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| 符號儲存區 <p>Microsoft Defender 防毒程式會使用符號存放區，在修正流程期間還原某些重要的檔案   | `https://msdl.microsoft.com/download/symbols` |
| 通用遙測用戶端 <p>Windows 使用此用戶端傳送用戶端診斷資料<p> Microsoft Defender 防病毒使用遙測進行產品品質監控的目的    | 更新使用 SSL (TCP 埠 443) 下載資訊清單，並將使用下列 DNS 端點的診斷資料上傳至 Microsoft： <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>驗證網路與雲端之間的連線

在允許上述 URLs 之後，您可以測試是否已連線至 Microsoft Defender 防毒軟體雲端服務，以及是否正確報告和接收資訊，以確保您受到完全保護。

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>使用 cmdline 工具來驗證雲端提供的保護

使用下列引數搭配 Microsoft Defender 防病毒命令列實用程式 (`mpcmdrun.exe`) ，以確認您的網路可以與 Microsoft Defender 防病毒雲端服務通訊：

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 您必須開啟命令提示字元的系統管理員層級版本。 在 [開始] 功能表中，以滑鼠右鍵按一下專案，按一下 [以 **系統管理員身分執行** ]，然後在許可權提示中按一下 **[是]** 。 這個命令只會在 Windows 10、版本1703或更高版本上運作。

如需詳細資訊，請參閱 [使用 mpcmdrun.exe 命令命令列工具管理 Microsoft Defender 防病毒](command-line-arguments-microsoft-defender-antivirus.md)。

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>嘗試從 Microsoft 下載虛假惡意程式碼檔

您可以下載一個範例檔案，當您已正確連接至雲端時，Microsoft Defender 防毒軟體會偵測並封鎖這些檔案。

透過訪問下載檔案 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 。

> [!NOTE]
> 此檔案不是惡意程式碼的實際部分。 這是一個偽檔案，其設計目的是為了測試您是否已正確連接至雲端。

如果您已正確連線，您會看到 Microsoft Defender 防病毒通知的警告。

如果您使用的是 Microsoft Edge，您也會看到一則通知訊息：

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="在 Edge 中找到惡意程式碼之通知的螢幕擷取畫面":::

當您使用 Internet Explorer 時，會發生類似的訊息：

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="找到惡意程式碼的 Microsoft Defender AV 通知":::

您也可以在 Windows 安全性應用程式的 [**掃描記錄**] 區段中看到 [**隔離威脅**] 下的偵測：

1. 按一下工作列中的盾牌圖示，或搜尋 [ **安全性**] 的 [開始] 功能表，以開啟 [Windows 安全性] 應用程式。

2. 選取 [ **病毒 & 威脅防護**]，然後選取 [ **保護歷程記錄**]。

3. 在 [ **隔離威脅** ] 區段中，選取 [ **查看完整的史** ]，以查看偵測到的虛假惡意程式碼。

   > [!NOTE]
   > 版本1703之前的 Windows 10 版本具有不同的使用者介面。 請參閱 [Windows 安全性應用程式中的 Microsoft Defender 防病毒](microsoft-defender-security-center-antivirus.md)。

   Windows 事件記錄也會顯示 [Windows Defender 用戶端事件識別碼 1116](troubleshoot-microsoft-defender-antivirus.md)。

