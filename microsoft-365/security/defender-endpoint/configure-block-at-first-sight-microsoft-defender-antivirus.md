---
title: 啟用第一次看見時即封鎖功能，以在數秒內偵測到惡意程式碼
description: 第一見看見時即開啟封鎖之功能，以在數秒內偵測並封鎖惡意程式碼。
keywords: 掃描，第一次看見時即封鎖，惡意程式碼，第一次看見，雲端，防禦程式，防毒軟體
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/15/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 3a5f766e21afcb29d3503345a49637061b5f0e38
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964696"
---
# <a name="turn-on-block-at-first-sight"></a>第一次看見時即開啟封鎖

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

本文會詳述名為「第一次看見時即封鎖」的防毒/反惡意軟體之功能，並說明如何為貴組織啟用第一次看見時即封鎖之功能。 

> [!TIP]
> 本文適用于管理組織安全性設定的企業系統管理員和 IT 專業人員。 如果您不是企業系統管理員或 IT 專業人員，但若您對 [第一次看見時即封鎖] 功能有疑問，請參閱 [不是企業系統管理員或 IT 專業人員？](#not-an-enterprise-admin-or-it-pro) 章節。

## <a name="what-is-block-at-first-sight"></a>什麼是 [第一次看見時即封鎖]？

[第一次看見時即封鎖] 是新一代防護的威脅防護功能，可偵測到新的惡意程式碼，並能在幾秒內將之封鎖。 啟用特定安全性設定時，便會啟用 [第一次看見時即封鎖] 功能。 這些設定包含：

- 雲端提供的保護； 
- 指定的樣本提交超時 (例如 50 秒)；和 
- 高度檔案封鎖層級。 

在大部分的企業組織中，啟用 [第一次看見時即封鎖] 功能需要使用 Microsoft Defender 防病毒軟體部署進行設定。 

## <a name="how-it-works"></a>運作方式

當 Microsoft Defender 防毒軟體遇到可疑但無法偵測的檔案時，它會查詢我們的雲端保護後端。 雲端後端會針對檔案進行啟發學習、機器學習和自動化分析，以判斷檔案是否為惡意檔案或者為威脅。

Microsoft Defender 防毒軟體使用多個偵測和防護技術，以提供準確、智慧型且即時的保護。 

![Microsoft Defender 防毒軟體工程清單](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> 若要深入瞭解，請參閱 [(部落格) 瞭解適用於端點的 Microsoft Defender 新一代保護功能核心的進階技術](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>關於 [第一次看見時即封鎖] 功能的一些資訊

- 在 Windows 10 版本 1803 或更新版本中，[第一次看見時即封鎖] 可以封鎖不可攜式可執行檔案 (例如 JS、VBS 或巨集) 和可執行檔案。

- [第一次看見時即封鎖] 只會針對從網際網路下載或源自網際網路區域之可執行檔案和非可攜式可執行檔案使用雲端保護後端。 .exe 檔案的雜湊值會透過雲端後端檢查，以判斷檔案是否先前未被偵測到。

- 如果雲端後端無法判斷，Microsoft Defender 防毒軟體會鎖定檔案，並上傳副本至雲端。 雲端會執行更多分析以判斷是否允許檔案執行，或在未來遇到時阻擋該檔案，取決於它是否將檔案判定為惡意檔案或非威脅檔案。

- 在許多情況下，此程式可以將新惡意軟體的回應時間從小時縮短為秒鐘。

- 當雲端式保護服務分析檔案時，您可以 [指定防止檔案執行的時間長度](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。 此外，您也可以在檔案被封鎖時，[自訂使用者桌面上所顯示的訊息](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md)。 您可以變更公司名稱、連絡人資訊和郵件 URL。

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>使用 Microsoft Intune 開啟 [第一次看見時即封鎖] 功能

> [!TIP]
> Microsoft Intune (現在是 Microsoft 端點管理員的一部分)。

1. 在 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))，瀏覽至 **[裝置]** > **[組態設定檔]**。

2. 使用 **[裝置限制]** 設定檔類型，選取或建立設定檔。

3. 在裝置限制設定檔的 **[組態設定]** 中，設定或確認以下 **Microsoft Defender 防毒軟體** 下方的設定：

   - **雲端提供的保護**：啟動
   - **檔案封鎖層級**：高
   - **雲端掃描檔案的時間延長**：50
   - **在提交範例之前提示使用者**：在不進行提示的情況下，傳送所有資料

   ![Intune Config](images/defender/intune-block-at-first-sight.png)

4. 儲存您的設定。

> [!TIP]
> - 將檔案封鎖層級設定為 **高** 會套用高偵測層級。 在某些意外情況下，檔案封鎖造成合法檔案被誤偵測為錯誤檔案類型，您的安全性作業小組可以 [還原隔離的檔案](./restore-quarantined-files-microsoft-defender-antivirus.md)。
> - 如需更多在 Intune 中設定 Microsoft Denfender 防毒軟體裝置限制的相關資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。
> - 有關 Intune 中 Microsoft Defender 防毒軟體裝置限制的清單，請參閱 [Intune 中的 Windows 10 (及更新版本) 的裝置限制設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>使用 Microsoft 端點管理員開啟 [第一次看見時即封鎖] 功能

> [!TIP]
> 如果您要尋找 Microsoft Endpoint Configuration Manager，它現在是 Microsoft 端點管理員的一部分。

1. 在 Microsoft 端點管理員 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 中，移至 **端點安全性** > **防毒軟體**。

2. 選取現有的原則，或使用 **Microsoft Defender 防毒軟體** 設定檔類型建立新原則。

3. 設定或確認下列組態設定：

   - **開啟雲端提供的保護**：是
   - **雲端提供的保護層級**：高
   - **Defender 雲端延伸逾時 (以秒為單位)**：50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="端點管理員中的 [第一次看見時即封鎖] 設定":::

4. 將 Microsoft Defender 防毒軟體設定檔套用到群組，例如 **[所有使用者]**、 **[所有裝置]** 或 **[所有使用者和裝置]**。

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>使用群組原則開啟 [第一次看見時即封鎖] 功能

> [!NOTE]
> 我們建議您使用 Intune 或 Microsoft 端點管理員來開啟 [第一次看見時即封鎖] 功能。 

1. 在您的群組原則管理電腦上，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，以滑鼠右鍵按一下您要設定的群組原則物件，然後選擇 **[編輯]**。 

2. 使用 **群組原則管理編輯器**，移至 **[電腦設定]** > **[系統管理範本]** > **[Windows 元件]** > **[Microsoft Defender 防毒軟體]** > **[MAPS]**。 

3. 在 MAPS 區段中，按兩下 **[設定第一次看見時即封鎖功能]**，然後將它設定為 **[已啟用]**，並選取 **[確定]**。

    > [!IMPORTANT]
    > 設定為 **永遠提示 (0)** 將會降低裝置的保護狀態。 設定為 **永不傳送 (2)** 表示第一次看見時即封鎖功能將無法運作。

4. 在 MAPS 區段按兩下 **[在需要進一步分析時，傳送檔案樣本]**，並將其設定為 **[已啟用]**。 在 **[在需要進一步分析時，傳送檔案樣本]** 底下，選取 **[傳送所有樣本]**，然後選取 **[確定]**。

5. 如常在整個網路中，重新部署您的群組原則物件。

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>確認個別用戶端裝置上已啟用 [第一次看見時即封鎖] 功能

您可以使用 Windows 安全性應用程式，確認個別用戶端裝置已啟用 [第一次看見時即封鎖] 功能。 只要開啟 **[雲端提供的保護]** 及 **[自動樣本提交]**，就會自動啟用「第一次看見時封鎖」。

1. 開啟 Windows 安全性應用程式。

2. 選取 **[病毒與威脅防護]**，然後在 **[病毒與威脅防護設定]** 底下，選取 **[管理設定]**。

   ![Windows 安全性應用程式中的病毒與威脅防護設定標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. 確認已開啟 **[雲端提供的保護]** 和 **[自動樣本提交]**。

> [!NOTE]
> - 如果先決條件設定是使用群組原則進行設定和部署，本節所述的設定會以灰色顯示，且無法用於個別端點。 
> - 必須先將透過群組原則物件進行的變更部署到個別端點，才能在 Windows 設定中更新設定。

## <a name="validate-block-at-first-sight-is-working"></a>驗證 [第一次看見時即封鎖] 功能是否有效

若要驗證該功能是否正常運作，請下載 [[第一次看見時即封鎖] 樣本檔案](https://demo.wd.microsoft.com/Page/BAFS)。 若要下載該檔案，你需要在 Azure AD 中擁有一個已被指派安全性系統管理員或全域管理員角色的帳戶。

若要驗證該已啟用雲端的保護是否正常運作，請遵循 [[驗證您的網路與雲端間的連結]](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud) 指南。 

## <a name="turn-off-block-at-first-sight"></a>關閉 [第一次看見時即封鎖] 功能

> [!CAUTION]
> 關閉 [第一次看見時即封鎖] 功能會降低裝置和網路的保護狀態。

如果您想要保留先決條件設定而不實際使用 [第一次看見時即封鎖] 保護，您可以選擇停用 [第一次看見時即封鎖] 功能。 您可以暫時關閉 [第一次看見時即封鎖] 功能，以查看此功能對您的網路有何影響。 不過，我們不建議永久停用 [第一次看見時即封鎖] 保護。

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>使用 Microsoft 端點管理員關閉 [第一次看見時即封鎖] 功能

1. 移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。

2. 移至 **端點安全性** > **防毒軟體**，然後選取您的 Microsoft Defender 防毒軟體原則。

3. 在 **[管理]** 底下，選擇 **[內容]**。

4. 在 **[組態設定]** 旁邊，選擇 **[編輯]**。

5. 變更下列其中一項或多項設定：

   - 將 **[開啟雲端式保護]** 設定為 **[否]** 或 **[未設定]**。
   - 將 **[雲端式保護層級]** 設定為 **[未設定]**。
   - 取消勾選 **Defender 雲端延伸逾時 (以秒為單位)** 的核取方塊。

6. 檢視並儲存設定。

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>使用群組原則關閉 [第一次看見時即封鎖] 功能

1. 在您的群組原則管理電腦上，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，以滑鼠右鍵按一下您要設定的群組原則物件，然後選擇 **[編輯]**。

2. 使用 **[群組原則管理編輯器]**，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。

3. 展開 **Windows 元件** > **Microsoft Defender 防毒軟體** > **MAPS** 的整體樹狀結構。

4. 按兩下 **設定 [第一次看見時即封鎖] 功能** ，然後設定選項為 **[停用]** 該設定。

    > [!NOTE]
    > 停用 [第一次看見時即封鎖] 功能不會停用或變更先決條件群組原則。

## <a name="not-an-enterprise-admin-or-it-pro"></a>不是企業系統管理員或 IT 專業人員？

如果您不是企業系統管理員或 IT 專業人員，但若您對 [第一次看見時即封鎖] 功能有疑問，請參閱這一章節。 [第一次看見時即封鎖] 是威脅防護功能，可偵測到惡意程式碼，並能在幾秒內將之封鎖。 雖然沒有名為「第一次看見時即封鎖」的特定設定，但當您的裝置上設定了特定設定時，便會啟用此功能。

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>如何在您自己的裝置上管理 [第一次看見時即封鎖] 功能

如果您有非由組織管理的個人裝置，您可能會想知道如何開啟或關閉 [第一次看見時即封鎖] 功能。 您可以使用 Windows 安全性應用程式來管理 [第一次看見時即封鎖] 功能。

1. 在 Windows 10 電腦上，開啟 Windows 安全性應用程式。

2. 選取 **病毒與威脅防護**。

3. 在 **[病毒與威脅防護設定]** 下方，選取 **[管理設定]**。

4. 請執行下列任一步驟：

   - 若要啟動 [第一次看見時即封鎖] 功能，請務必確定 **[雲端提供的保護]** 及 **[自動樣本提交]** 皆處於開啟狀態。

   - 若要停用 [第一次看見時即封鎖]，請關閉 **[雲端提供的保護]** 或 **[自動樣本提交]**。 <br/>
    
     > [!CAUTION]
     > 關閉 [第一次看見時即封鎖] 會降低您裝置的保護層級。 我們不建議永久停用 [第一次看見時即封鎖] 功能。 


## <a name="see-also"></a>另請參閱

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
- [啟動雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md)
- [使用 Windows 安全性，隨時處於保護狀態](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
