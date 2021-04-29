---
title: 在第幾秒內啟用封鎖以偵測惡意程式碼
description: 開啟塊狀的「初次看到」功能，以在幾秒內偵測並封鎖惡意程式碼。
keywords: 掃描、封鎖第一次看到、惡意程式碼、第一次看到、雲端、defender、防毒程式
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079200"
---
# <a name="turn-on-block-at-first-sight"></a>第一次看見時開啟封鎖

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

本文說明防毒軟體/反惡意軟體功能（稱為「初次看到時封鎖」），並說明如何在第一次看到的組織中啟用區塊。 

> [!TIP]
> 本文適用于管理組織安全性設定的 enterprise admins 和 IT 專業人員。 如果您不是企業系統管理員或 IT 專業人員，但在初次看到時會有有關封鎖的問題，請參閱 [not enterprise admin OR It 專業人員？](#not-an-enterprise-admin-or-it-pro)。

## <a name="what-is-block-at-first-sight"></a>「初次看到」為何？

「第一次看到的封鎖」是下一代保護的威脅防護功能，可偵測新的惡意程式碼並在幾秒內封鎖。 啟用某些安全性設定時，第一次看到的封鎖會啟用。 這些設定包含：

- 雲端提供的保護; 
- 指定的範例提交超時 (例如50秒) ;和 
- 高的檔封鎖層級。 

在大多數企業組織中，第一次看到的啟用封鎖所需的設定是透過 Microsoft Defender 防病毒部署設定。 

## <a name="how-it-works"></a>運作方式

當 Microsoft Defender 防病毒遇到可疑但未偵測到的檔案時，它會查詢我們的雲端保護後端。 雲端後端套用檔的試探法、機器學習和自動分析，以判斷檔案是否惡意或不是威脅。

Microsoft Defender 防病毒會使用多個偵測及防護技術，以提供準確、智慧和即時的保護。 

![Microsoft Defender AV 引擎清單](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> 若要深入瞭解，請參閱下列博客： [深入瞭解 Microsoft Defender 的核心的高級技術，以供端點下一代保護](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>在第一次看到區塊時，需要瞭解的一些事項

- 在 Windows 10 版本1803或更新版本中，第一次看到的封鎖可以封鎖不可移植的可執行檔 (例如 .JS、VBS 或宏) 和可執行檔。

- 在第一次看到時，封鎖只會對從網際網路下載的可執行檔和不可移植的可執行檔（從網際網路區域產生）使用雲端保護後端。 .Exe 檔案的雜湊值是透過雲端後端檢查，以判斷該檔案是否為先前未檢查過的檔案。

- 若 cloud 後端無法判斷，Microsoft Defender 防毒程式會鎖定檔案，並將副本上傳至雲端。 雲端會執行更多分析，以達到判斷，直到所有未來都能執行或封鎖該檔案，取決於它是否決定要成為惡意或不是威脅的檔案。

- 在許多情況下，此程式可將新惡意程式碼的回應時間從數小時縮短為秒。

- 您可以指定雲端式保護服務分析檔案時， [應防止檔案執行的時間長度](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) 。 而且，您可以在封鎖檔時， [自訂使用者桌面上顯示的訊息](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) 。 您可以變更公司名稱、連絡人資訊及消息 URL。

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>在初次看到 Microsoft Intune 時開啟區塊

> [!TIP]
> Microsoft Intune 現在是 Microsoft 端點管理員的一部分。

1. 在 Microsoft 端點管理員管理中心 () 中 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ，流覽至 [**裝置** 設定配置  >  **檔**]。

2. 使用 **裝置限制** 配置檔案類型選取或建立設定檔。

3. 在裝置限制設定檔的 **設定設定** 中，在 [ **Microsoft Defender 防病毒**] 下設定或確認下列設定：

   - **雲端提供的保護**：已啟用
   - **檔封鎖層級**：高
   - **雲端的檔案掃描時間分機**：50
   - **在提交範例之前提示使用者**：不經提示傳送所有資料

   ![Intune config](images/defender/intune-block-at-first-sight.png)

4. 儲存您的設定。

> [!TIP]
> - 將檔封鎖層級設為 **高** 會套用強層次的偵測。 在發生不理想的情況下，由於檔封鎖導致合法檔案的誤報偵測，您的安全性作業小組可以 [還原隔離](./restore-quarantined-files-microsoft-defender-antivirus.md)的檔案。
> - 如需在 Intune 中設定 Microsoft Defender 防病毒裝置限制的詳細資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。
> - 如需 Intune 中 Microsoft Defender 防病毒裝置限制的清單，請參閱 [intune 中 Windows 10 (和更新) 設定的裝置限制](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>在初次看到 Microsoft 端點管理員時開啟區塊

> [!TIP]
> 如果您正在尋找 Microsoft 端點 Configuration Manager，它現在是 Microsoft 端點管理員的一部分。

1. 在 Microsoft 端點管理員 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 中，移至 **端點安全性**  >  **防病毒**。

2. 選取現有的原則，或使用 **Microsoft Defender 防病毒** 配置檔案類型建立新的原則。

3. 設定或確認下列設定：

   - **開啟雲端傳送保護**：是
   - **雲端提供的保護層級**：高
   - **Defender Cloud 延伸超時秒**：50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="端點管理員中首次看到的設定封鎖":::

4. 將 Microsoft Defender 防病毒設定檔套用至群組，例如 **所有使用者**、 **所有裝置** 或 **所有使用者和裝置**。

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>在第一次使用群組原則時開啟區塊

> [!NOTE]
> 我們建議您在第一次看到封鎖時，使用 Intune 或 Microsoft 端點管理員開啟封鎖。 

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。 

2. 使用 **群組原則管理編輯器** 移至 [**電腦設定] 系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **對應**。 

3. 在 [對應] 區段中，按兩下 **[設定第一次看到的封鎖] 功能**，並將其設定為 [ **啟用**]，然後選取 **[確定]**。

    > [!IMPORTANT]
    > 設定為 **Always prompt (0)** 會降低裝置的保護狀態。 設定為 **永不傳送 (2)** 表示第一次看到的區塊將無法運作。

4. 在 [對應] 區段中，在 **需要進一步分析時**，按兩下 [傳送檔案範例]，並將其設定為 [ **啟用**]。 在 [ **需要進一步分析時傳送檔範例**] 底下，選取 [ **傳送所有範例**]，然後選取 **[確定]**。

5. 以您通常的方式，在您的網路上重新部署群組原則物件。

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>在個別用戶端裝置上啟用第一次看到時，確認封鎖

您可以在個別的用戶端裝置上使用 Windows 安全性應用程式，確認第一次看到的組塊已啟用。 只要已開啟 **雲端提供的保護** 和 **自動範例提交** ，便會自動啟用封鎖初次看到的功能。

1. 開啟 [Windows 安全性應用程式]。

2. 選取 [ **病毒 & 威脅防護**]，然後在 [ **病毒 & 威脅防護設定**] 底下，選取 [ **管理設定**]。

   ![Windows 安全性應用程式中的病毒 & 威脅防護設定] 標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. 確認已開啟 **雲端提供的保護** 和 **自動範例提交** 。

> [!NOTE]
> - 如果使用群組原則來設定及部署必要條件設定，本節中所述的設定將會變灰，且無法在個別端點上使用。 
> - 您必須先將透過「群組原則」物件所做的變更部署到個別的端點，然後才會在 [Windows 設定] 中更新設定。

## <a name="validate-block-at-first-sight-is-working"></a>第一次看到的驗證區塊運作正常

若要驗證功能是否正常運作，請遵循 [驗證網路與雲端之間](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)連線的指導方針。

## <a name="turn-off-block-at-first-sight"></a>在第一次看到封鎖時關閉封鎖

> [!CAUTION]
> 在第一次看到時關閉區塊，將會降低裝置 (s) 和您的網路的保護狀態。

如果您想要保留必要條件設定，而不實際在第一次看到保護時使用區塊，您可以選擇停用 [在第一次看到時封鎖]。 您可能會在第一次看到封鎖時暫時關閉封鎖，以查看此功能對您的網路有何影響。 不過，我們不建議您在初次看到保護時停用封鎖。

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>在第一次使用 Microsoft 端點管理員時關閉封鎖

1. 移至 [Microsoft 端點管理員管理中心] ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入]。

2. 請移至 **端點安全性**  >  **防病毒**，然後選取您的 Microsoft Defender 防病毒原則。

3. 在 [ **管理**] 下，選擇 [ **屬性**]。

4. 在 [ **設定設定**] 旁，選擇 [ **編輯**]。

5. 變更一或多個下列設定：

   - 將 **雲端傳送保護開啟** 為 [ **否** ] 或 [ **未設定**]。
   - 將 **雲端傳送的保護等級** 設為 [ **未設定**]。
   - 清除 [ **Defender Cloud 擴充超時的秒數**] 核取方塊。

6. 檢查並儲存您的設定。

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>在第一次使用群組原則時關閉封鎖

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

2. 使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。

3. 透過 **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **對應** 展開樹狀目錄。

4. 按兩下 [設定 **第一次看到的封鎖] 功能** ，並將此選項設定為 [ **停用**]。

    > [!NOTE]
    > 停用區塊初次看到時，不會停用或變更必要條件群組原則。

## <a name="not-an-enterprise-admin-or-it-pro"></a>不是企業系統管理員或 IT 專業人員？

如果您不是企業系統管理員或 IT 專業人員，但您在第一次看到封鎖時有問題，請參閱本節。 「第一次看到的封鎖」是威脅防護功能，可在幾秒內偵測並封鎖惡意程式碼。 雖然在「初次看到時封鎖」沒有特定設定，但在裝置上設定某些設定時會啟用該功能。

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>操作方法：在您自己的裝置上初次看到或關閉封鎖

如果您有未由組織管理的個人裝置，您可能想知道如何在第一次看到或關閉時關閉封鎖功能。 您可以使用 Windows 安全性應用程式，在初次看到時管理區塊。

1. 在您的 Windows 10 電腦上，開啟 [Windows 安全性應用程式]。

2. 選取 [ **病毒 & 威脅防護**]。

3. 在 [ **病毒 & 威脅防護設定**] 底下，選取 [ **管理設定**]。

4. 請執行下列任一步驟：

   - 若要在初次看到時啟用封鎖，請確定已同時開啟 **雲端傳送保護** 和 **自動範例提交** 。

   - 若要在第一次看到時停用封鎖，請關閉已 **提供雲端保護** 或 **自動範例提交**。 <br/>
    
     > [!CAUTION]
     > 在初次看到時關閉區塊，會降低裝置的保護層級。 我們不建議您在初次看到時，永久停用區塊。 


## <a name="see-also"></a>另請參閱

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [啟用雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)
- [使用 Windows 安全性保持受保護](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)