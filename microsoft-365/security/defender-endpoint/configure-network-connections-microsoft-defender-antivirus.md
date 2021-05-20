---
title: 設定及驗證 Microsoft Defender 防毒軟體網路連線
description: 設定和測試您與 Microsoft Defender 防毒軟體 cloud protection service 的連接。
keywords: 防病毒，Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，cloud，入侵，保護層級
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572522"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>設定及驗證 Microsoft Defender 防毒軟體網路連線

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

為了確保已 Microsoft Defender 防毒軟體雲端傳送保護的運作是否正常，您必須設定網路以允許端點和某些 Microsoft 伺服器之間的連線。 本文列出必須允許的連線，例如使用防火牆規則，並提供驗證連線的指示。 正確設定保護可協助確保您從雲端提供的保護服務中取得最佳價值。

如需網路連線的某些詳細資料，請參閱博客文章 [重要變更 Microsoft Active Protection Services 端點](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 。

> [!TIP]
> 您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範網站，以確認下列功能正在運作：
>
> - 雲端提供的保護
> - Fast 教學 (包括第一次看到區塊) 
> - 可能有害的應用程式封鎖

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>允許連線至 Microsoft Defender 防毒軟體雲端服務

Microsoft Defender 防毒軟體 cloud service 為您的端點提供快速、強大的保護。 啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和整個網路提供重要的防護。

> [!NOTE]
> Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞到網路和端點。 雖然它稱為雲端服務，但並不只是保護儲存在雲端中的檔案，而是使用分散式資源和機器學習功能，以比傳統的安全性智慧更新速度更快的速率來提供對端點的保護。

請參閱[啟用雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)，以取得使用 Intune、Microsoft Endpoint Configuration Manager、群組原則、PowerShell 指令程式或 Windows 安全性應用程式中個別用戶端上啟用服務的詳細資訊。 

在您啟用服務之後，您可能需要設定網路或防火牆，以允許其和您的端點之間的連線。

因為您的保護是雲端服務，所以電腦必須能夠存取網際網路，並接觸 Microsoft Defender for a machine 教學 services Office 365。 請勿 `*.blob.core.windows.net` 從任何類型的網路檢查中排除 URL。 

下表列出服務及其相關聯的 URLs。 請確定沒有任何防火牆或網路篩選規則拒絕存取這些 URLs，否則您可能需要建立專用的 allow 規則 (排除 URL `*.blob.core.windows.net`) 。 以下提及 URLs 使用埠443進行通訊。


| **服務**| **描述** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender 防毒軟體雲端提供的保護服務，也稱為 Microsoft Active Protection Service (對應) |用於 Microsoft Defender 防毒軟體以提供雲端提供的保護|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Microsoft Update Service (MU)  <br/> WindowsUpdate Service (WU) |  安全性智慧及產品更新   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> 如需詳細資訊，請參閱[Windows 更新的連接端點](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|安全性智慧更新替代下載位置 (ADL) |   如果已安裝的安全性情報已過期，則為 Microsoft Defender 防毒軟體 Security 情報更新的替代位置)  (7 天以上或以上天數|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| 惡意程式碼提交存放區|透過提交表單或自動範例提交，將檔案提交給 Microsoft 的 Upload 位置    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
|  (CRL) 的憑證吊銷清單|在建立對應的 SSL 連線以更新 CRL 時使用 Windows   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| 符號儲存區|由 Microsoft Defender 防毒軟體用來在修正流程期間還原某些重要檔案  | `https://msdl.microsoft.com/download/symbols` |
| 通用遙測用戶端| 由 Windows 用來傳送用戶端診斷資料;Microsoft Defender 防毒軟體使用遙測進行產品品質監控的目的   | 更新使用 SSL (TCP 埠 443) 下載資訊清單，並將使用下列 DNS 端點的診斷資料上傳至 Microsoft：   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>驗證網路與雲端之間的連線

允許上述 URLs 之後，您可以測試是否已連線到 Microsoft Defender 防毒軟體雲端服務，並正確報告和接收資訊，以確保您受到完全保護。

**使用 cmdline 工具來驗證雲端提供的保護：**

在 Microsoft Defender 防毒軟體命令列公用程式 () 使用下列引數， `mpcmdrun.exe` 以確認您的網路能夠與 Microsoft Defender 防毒軟體雲端服務通訊：

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 您必須開啟命令提示字元的系統管理員層級版本。 在 [開始] 功能表中，以滑鼠右鍵按一下專案，按一下 [以 **系統管理員身分執行** ]，然後在許可權提示中按一下 **[是]** 。 這個命令只會在 Windows 10 版本1703或更高版本上運作。

如需詳細資訊，請參閱[使用 mpcmdrun.exe 命令列工具管理 Microsoft Defender 防毒軟體](command-line-arguments-microsoft-defender-antivirus.md)。

**嘗試從 Microsoft 下載虛假惡意程式碼檔：**

您可以下載範例檔案，當您已正確連接至雲端時，Microsoft Defender 防毒軟體會偵測並封鎖。

透過訪問下載檔案 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 。

> [!NOTE]
> 此檔案不是惡意程式碼的實際部分。 這是一個偽檔案，其設計目的是為了測試您是否已正確連接至雲端。

正確連接後，您會看到警告 Microsoft Defender 防毒軟體通知。

如果您正在使用 Microsoft Edge，您也會看到通知訊息：

![Microsoft Edge 告知使用者發現惡意程式碼](images/defender/wdav-bafs-edge.png)

當您使用 Internet Explorer 時，會發生類似的訊息：

![Microsoft Defender 防毒軟體通知，告知使用者發現惡意程式碼](images/defender/wdav-bafs-ie.png)

您也會在 Windows 安全性應用程式的 [掃描歷程 **記錄**] 區段中看到 [**隔離威脅**] 下的偵測：

1. 按一下工作列中的盾牌圖示，或搜尋 [**安全性**] 的 [開始] 功能表，開啟 Windows 安全性應用程式。

2. 選取 [ **病毒 & 威脅防護**]，然後選取 [ **保護歷程記錄**]。

3. 在 [ **隔離威脅** ] 區段中，選取 [ **查看完整的史** ]，以查看偵測到的虛假惡意程式碼。

   > [!NOTE]
   > 版本1703之前的 Windows 10 版本都具有不同的使用者介面。 請參閱[Windows 安全性應用程式中的 Microsoft Defender 防毒軟體](microsoft-defender-security-center-antivirus.md)。

   Windows 事件記錄也會顯示[Windows Defender 用戶端事件識別碼 1116](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="related-articles"></a>相關文章

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)

- [啟動雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)

- [命令列引數](command-line-arguments-microsoft-defender-antivirus.md)

- [Microsoft Active Protection Services 端點的重要變更](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
