---
title: 適用于系統管理員的 Office 365 應用程式防護
keywords: application guard、protection、隔離、隔離的容器、硬體隔離
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 取得最新的硬體隔離。 防止目前和新興的攻擊（如入侵或惡意連結）中斷員工生產力和企業安全性。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39d6a9c3a3c3a5e2c736025a26c22588f9f08bb0
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055260"
---
# <a name="application-guard-for-office-for-admins"></a>適用于系統管理員的 Office 應用程式防護

**適用于：** Word、Excel 及 Microsoft 365 PowerPoint，Windows 10 企業版

Microsoft Defender 應用程式防護 for Office (Application Guard for Office) 協助防止不可信的檔案存取受信任的資源，讓您的企業安全地抵禦新的和新興的攻擊。 本文指導管理員如何針對 Office 的應用程式防護，設定可預覽的裝置。 它提供有關系統需求和安裝步驟的資訊，以便在裝置上啟用 Office 的應用程式防護。

## <a name="prerequisites"></a>了解必要條件

### <a name="minimum-hardware-requirements"></a>最低硬體需求

* **CPU**：64位、4核心 (實體或虛擬) 、虛擬化擴充 (Intel VT-x 或 AMD-V) 、Core i5 對等建議或更高版本的建議
* **實體記憶體**： 8 GB RAM
* **硬碟**：系統磁片磁碟機上有 10 GB 的可用空間 (SSD 建議) 

### <a name="minimum-software-requirements"></a>基本軟體需求

* **Windows 10**： Windows 10 企業版 edition，用戶端組建版本 2004 (20H1) 組建19041或更新版本
* **Office**： Office 目前通道和每月 Enterprise 通道，組建版本 2011 16.0.13530.10000 或更新版本。 支援32位和64位版本的 Office。
* **更新套件**： Windows 10 累計每月安全性更新 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

如需詳細的系統需求，請參閱[Microsoft Defender 應用程式防護的系統需求](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。 此外，請參閱電腦製造商的指南，以瞭解如何啟用虛擬化技術。
若要深入瞭解 Office 更新通道，請參閱[Microsoft 365 的更新通道](/deployoffice/overview-update-channels)。

### <a name="licensing-requirements"></a>授權需求

* Microsoft 365 E5 或 Microsoft 365 E5 安全性

## <a name="deploy-application-guard-for-office"></a>為 Office 部署應用程式防護

### <a name="enable-application-guard-for-office"></a>啟用 Office 的應用程式防護

1. 下載和安裝 **Windows 10 累計每月安全性更新 KB4571756**。

2. 選取 [Windows 功能] 底下的 **Microsoft Defender 應用程式防護**，然後選取 **[確定]**。 啟用 Application Guard 功能時，會提示重新開機系統。 您可以選擇 [現在] 或 [在步驟3之後重新開機]。

   ![Windows顯示 AG 的 [功能] 對話方塊](../../media/ag03-deploy.png)

   您也可以以系統管理員身分執行下列 PowerShell 命令，以啟用此功能：

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. 在「**受管理模式**」中搜尋 Microsoft Defender 應用程式防護，在 [電腦設定系統管理範本] 中的群組原則 **\\ \\ Windows 元件 \\ Microsoft Defender 應用程式防護**。 將 [選項] 底下的值設定為 [ **2** ] 或 [ **3**]，然後選取 **[確定] 或 [套用]** ，以開啟此原則。 

   ![在受管理的模式中開啟 AG](../../media/ag04-deploy.png)

   相反地，您可以設定對應的 CSP 原則：

   > OMA URI： **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/設定/AllowWindowsDefenderApplicationGuard** <br> 資料類型： **Integer** <br> 值： **2**

4. 重新開機系統。

### <a name="set-diagnostics--feedback-to-send-full-data"></a>設定診斷 & 傳送完整資料的意見

> [!NOTE]
> 不過，這不是必要的，但設定選用的診斷資料將有助於診斷報告的問題。

此步驟可確保識別和修正問題所需的資料是在 Microsoft。 請遵循下列步驟，在 Windows 裝置上啟用診斷：

1. 從 [開始] 功能表開啟 **設定**。

   ![[開始] 功能表](../../media/ag05-diagnostic.png)

2. 在 **Windows 設定** 上，選取 [**隱私權**]。

   ![Windows 設定功能表](../../media/ag06-diagnostic.png)

3. 在 [隱私權] 底下，選取 [ **診斷 & 回饋** ]，然後選取 [ **選用診斷資料**]。

   ![診斷和回饋功能表](../../media/ag07a-diagnostic.png)

如需設定 Windows 診斷設定的詳細資訊，請參閱設定[組織中的 Windows 診斷資料](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>確認已啟用並運作 Office 的應用程式防護

確認已啟用 Office 的應用程式防護之前，請在已部署原則的裝置上啟動 Word、Excel 或 PowerPoint。 請確定已啟用 Office。 您可能需要先使用您的工作身分識別來啟用 Office 產品。

若要確認已啟用 Office 的應用程式防護，請啟動 Word、Excel 或 PowerPoint，然後開啟不受信任的檔。 例如，您可以開啟從網際網路下載的檔或來自組織外部人員的電子郵件附件。

當您第一次開啟不受信任的檔案時，您可能會看到 Office 閃屏，如下列範例所示。 它可能會在啟用 Office 的應用程式防護，且正在開啟檔案時顯示。 後續的不受信任檔案的開口應該會更快。

![Office 應用程式閃屏](../../media/ag08-confirm.png)

開啟檔案時，檔案應該會顯示一些視覺標記，指出檔案已在 Office 的應用程式防護中開啟：

* 功能區中的標注

  ![顯示小型應用程式防護附注的 Doc 檔案](../../media/ag09-confirm.png)

* 在工作列中帶有盾牌的應用程式圖示

  ![工作列中的圖示](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>設定 Office 的應用程式防護

Office 支援下列原則，可讓您設定 Office 應用程式防護的功能。 這些原則可以透過「群組原則」或「 [Office 雲端原則服務](/DeployOffice/overview-office-cloud-policy-service)」加以設定。


> [!NOTE]
> 設定這些原則之後，便可對 Office 的應用程式防護中開啟的檔案停用某些功能。

|原則|描述|
|---|---|
|不使用適用于 Office 的應用程式防護|啟用這個原則會強制 Word、Excel 和 PowerPoint 使用受保護的檢視隔離容器，而不是應用程式的 Office 防護。 這項原則可以用來暫時停用 Office 的應用程式防護，當您在 Microsoft Edge 中啟用它時，就會發生問題。|
|為 Office 容器預先建立設定 Application Guard|這個原則會判斷是否已預先建立用於隔離不受信任檔案的 Office 容器的應用程式防護，以提升執行時間效能。 如果您啟用此設定，您可以指定繼續建立容器的天數，或讓 Office 內建的啟發式預先建立容器。
|不允許複製/貼上用於 Office 應用程式防護中開啟的 Office 檔的複製/貼上|啟用此原則可防止使用者將內容從在應用程式防護開啟的檔中複製及貼上，以 Office 至其外開啟的檔。|
|停用 Office 的應用程式防護中的硬體加速|這個原則會控制 Office 的應用程式防護是否會使用硬體加速呈現圖形。 如果您啟用此設定，則 Office 的應用程式防護會使用以軟體為基礎的 (CPU) 轉譯，而且不會載入任何協力廠商的圖形驅動程式，也不會與任何連接的圖形硬體互動。
|停用 Office 的應用程式防護中不支援的檔案類型保護|此原則會控制 Office 的應用程式防護是否會封鎖未支援的檔案類型，或是否要啟用重新導向至受保護的檢視。
|關閉在 Office 的應用程式防護中開啟之檔的相機和麥克風存取權|啟用這個原則將會移除 Office 對 Office 的應用程式防護中的相機及麥克風的存取權。|
|限制在 Office 的應用程式防護中開啟的檔列印|啟用此原則會限制使用者可以從在 Office 的應用程式防護中開啟的檔案列印的印表機。 例如，您可以使用這個原則來限制使用者只能列印為 PDF。|
|防止使用者移除應用程式防護，以保護檔案上的 Office 檔|啟用此原則會在 Office 應用程式經驗) 中移除 (選項，以停用 Office 保護的應用程式防護，或開啟 Office 應用程式防護之外的檔案。 <p> **附注：** 使用者仍可略過此原則，方法是手動移除檔案中的 web 標記，或是將檔移至信任位置。|
|

> [!NOTE]
> 下列原則將需要使用者登出並重新登入，才能讓 Windows 生效：
>
> * 停用 Office 的應用程式防護中開啟之檔的複製/貼上
> * 限制為 Office 的應用程式防護開啟的檔列印
> * 關閉為 Office 的應用程式防護開啟的檔的相機和麥克風存取權

## <a name="submit-feedback"></a>提交意見反應

### <a name="submit-feedback-via-feedback-hub"></a>透過意見反應中心提交意見反應

如果您在為 Office 啟動應用程式防護時遇到任何問題，建議您透過意見反應中樞提交您的意見反應：

1. 開啟「 **回饋中樞」應用程式** 並登入。

2. 如果您在啟動應用程式防護時收到錯誤對話方塊，請在錯誤對話方塊中選取 [ **向 Microsoft 報告** ]，以啟動新的意見反應提交。 否則，請流覽至 <https://aka.ms/mdagoffice-fb> 以選取正確的應用程式防護類別類別，然後選取 [在右上方附近 **+ &nbsp; 新增新的意見** 反應]。

3. 在 [摘要您的 **意見** 反應] 方塊中輸入摘要（如果尚未填入）。

4. 在 [詳細 **資料** ] 方塊中，輸入您所遇到問題的詳細描述和您採取的步驟，然後選取 **[下一步]**。

5. 選取 [ **問題**] 旁邊的氣泡。 請確定選取的類別是「**安全性和隱私權 \> Microsoft Defender 應用程式防護– Office**，然後選取 **[下一步]**。

6. 選取 [ **新增** 反應]，然後選取 **[下一步]**。

7. 收集有關問題的追蹤：

   1. 展開 [ **重新建立我的問題** ] 磚。

   2. 如果您在執行應用程式防護時發生所遇到的問題，請開啟應用程式防護實例。 開啟實例允許從應用程式防護容器內收集其他追蹤。

   3. 選取 [ **開始錄製**]，等候拼貼停止旋轉，並說 *停止錄製*。

   4. 使用應用程式防護完全再現問題。 複製品可能包括嘗試啟動應用程式防護實例並等候失敗，或在執行中的應用程式防護實例中再現問題。

   5. 選取 [ **停止錄製** ] 磚。

   6. 保留任何執行中的應用程式防護 (實例) 開啟，甚至在提交之後幾分鐘後，也可以收集容器診斷。

8. 附加任何相關的螢幕擷取畫面或與問題相關的檔案。

9. 選取 **[提交]**。

### <a name="submit-feedback-via-office-customer-voice"></a>透過客戶語音 Office 提交意見反應

如果在應用程式防護中開啟 Office 檔時會發生問題，您也可以從 Office 提交意見反應。 請參閱[Office 的預覽人員手冊](https://insider.office.com/handbook)以取得意見反應。

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>與 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 整合

Office 的應用程式防護會與 Microsoft Defender for Endpoint 整合，以針對隔離環境中發生的惡意活動提供監控和警示。

[microsoft E365 E5 中的保管庫檔](/microsoft-365/security/office-365-security/safe-docs)是一種功能，可使用 microsoft Defender for Endpoint 掃描在 Office 的應用程式防護中開啟的檔。 若為其他保護層級，使用者在決定掃描的結果之後，就無法在 Office 留下應用程式防護。

Microsoft Defender for Endpoint 是一種安全性平臺，旨在協助商業網路避免、偵測、調查和回應高級威脅。 如需此平臺的詳細資訊，請參閱 [Microsoft Defender For Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)。 若要深入瞭解如何將裝置上架至此平臺，請參閱 [在 Microsoft Defender For Endpoint service 中的板載裝置](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。

您也可以將 Office 365 的 Microsoft Defender 設定為搭配使用 Defender for Endpoint。 如需詳細資訊，請參閱[整合 Defender for Office 365 搭配 Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md)。

## <a name="limitations-and-considerations"></a>限制和考慮

* Application Guard for Office 是一種受保護的模式，可隔離不受信任的檔，使其無法存取電腦上信任的公司資源、內部網路、使用者的身分識別及任意檔案。 因此，如果使用者嘗試存取的功能具有對此存取的相依性（例如，從磁片上的本機檔案插入圖片），access 就會失敗，並產生如下列範例所示的提示。 若要讓不可信的檔能夠存取受信任的資源，使用者必須從檔中移除 Application Guard protection。

  ![對話方塊說可協助您保護安全，但無法使用此功能](../../media/ag10-limitations.png)

  > [!NOTE]
  > 建議使用者只有在信任檔案及其來源或來源的位置時，才移除保護。

* 在適用于 Office 的應用程式防護中，會停用像宏及 ActiveX 控制項等檔中的活動內容。 使用者需要移除應用程式防護保護才能啟用 active 內容。

* 在應用程式防護中以唯讀方式開啟從不同組織 OneDrive、商務用 OneDrive 或 SharePoint 線上之網路共用或檔案所共用的不受信任檔案。 使用者可以儲存這類檔案的本機副本，以繼續在容器中工作或移除保護，以直接使用原始檔案。

* 預設會封鎖受資訊版權管理 (IRM) 所保護的檔案。 如果使用者想要在 [受保護的檢視] 中開啟這類檔案，系統管理員必須為組織設定不受支援的檔案類型的原則設定。

* 在使用者登出和登入後，或在裝置重新開機之後，對 Office 應用程式防護中 Office 應用程式的任何自訂功能都不會保留。

* 只有使用 UIA 架構的協助工具工具才能為 Office 的應用程式防護中開啟的檔案提供可存取的體驗。

* 安裝後第一次啟動應用程式防護時，必須具備網路連線能力。 為了讓應用程式防護驗證授權，必須連線。

* 在檔的 [資訊] 區段中，[ *上次修改者* ] 屬性可能會以使用者的身分顯示 **WDAGUtilityAccount** 。 WDAGUtilityAccount 是在 Application Guard 中設定的匿名使用者。 桌面使用者的身分識別不會在應用程式防護容器內共用。

## <a name="performance-optimizations-for-application-guard-for-office"></a>Office 的應用程式防護效能優化

本節提供應用程式防護中用於 Office 之效能優化的概述。 此資訊可協助系統管理員在啟用 Application Guard 時，向與 Office 或整體系統效能相關的使用者診斷報告。

Application Guard 會使用虛擬容器，將不受信任的檔與系統隔離。 建立容器及設定應用程式防護容器以開啟 Office 檔時，會有效能負荷，對使用者開啟不受信任的檔時，可能會對使用者的經驗造成負面影響。

若要為使用者提供預期的檔案開啟體驗，當系統符合下列啟發時，Application Guard 會使用邏輯來預先建立容器：使用者已于過去28天內，在受保護的 View 或 Application Guard 中開啟檔案。

當符合此啟發時，Office 會在使用者登入 Windows 後，預先為使用者建立應用程式防護容器。 在此預先建立作業進行中時，系統可能會遇到效能降低的情況，但在作業完成後，就會立即解決此影響。

> [!NOTE]
> 以使用者身分使用的方式 Office 應用程式，會產生試探法預先建立容器所需的暗示。 若使用者在已啟用 Application Guard 的新系統上安裝 Office，Office 在使用者第一次開啟系統上的不受信任的檔之前，不會預先建立容器。 使用者將會看到此第一個檔案在應用程式防護中所需的時間較長。

## <a name="known-issues"></a>已知問題

* 選取 [網路連結] (`http` 或 `https`) 並不會開啟瀏覽器。
* 複製型貼上保護原則的預設設定為僅啟用文字的剪貼簿存取。
* 不受支援的檔案類型保護原則的預設設定為封鎖開啟不受信任的受信任檔案類型（已加密或具備資訊版權管理 (IRM) 設定）。 這包括使用加密 (機密或高度機密) 的 Microsoft 資訊保護敏感度標籤的檔案。
* 目前不支援 CSV 和 HTML 檔案。
* 目前 Office 的應用程式防護無法搭配 NTFS 壓縮的磁片區。 如果您看到錯誤 "ERROR_VIRTUAL_DISK_LIMITATION" 請嘗試解壓縮該磁片區。
* 更新 .NET 可能會導致檔無法在應用程式防護中開啟。 作為解決方法，使用者可以在發生這種失敗時，重新開機其裝置。 深入瞭解在[嘗試開啟 Windows Defender 應用程式防護或 Windows 沙箱時，收到錯誤訊息時](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)出現問題的詳細資訊。
* 如需詳細資訊，請參閱[常見問題-Microsoft Defender 應用程式防護。](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 
