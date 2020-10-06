---
title: 設定試用實驗室或試驗環境的 Microsoft 威脅防護支柱
description: 針對您的試用實驗室或試驗環境，設定 Microsoft 威脅防護支柱，例如 Office 365 ATP、Azure ATP、Microsoft Cloud App Security 和 Microsoft Defender ATP。
keywords: 設定 Microsoft 威脅防護試用版、Microsoft 威脅防護試用版設定、設定 Microsoft 威脅防護試驗專案、設定 microsoft 威脅防護支柱、Microsoft 威脅防護支柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 79e141ad85eecab827e0caa98fe022f88335c671
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368146"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a>為您的試用實驗室或試驗環境設定 Microsoft 威脅防護支柱

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護


建立 Microsoft 威脅防護試用實驗室或試驗環境並加以部署時，會有三個階段的處理常式：

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="準備您的 Microsoft 威脅防護試用實驗室或試驗環境" />
      <br/>階段1：準備 </a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="設定您的 Microsoft 威脅防護試用實驗室或試驗環境" />
      <br/>階段2：設定 </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="針對您的 Microsoft 威脅防護試用實驗室或試驗環境和板載端點設定每個 Microsoft 威脅防護 pillar" />
      <br/>階段3：設定板載 & </a><br>
</td>
  </tr>
</table>

您目前正在設定階段。


準備工作是任何成功部署的關鍵。 在本文中，您將指導您準備部署 Microsoft Defender ATP 時所需考慮的事項。


## <a name="microsoft-threat-protection-pillars"></a>Microsoft 威脅防護的支柱
Microsoft 威脅防護包含四個支柱。 雖然一個 pillar 可以為您的網路組織的安全性提供價值，但是啟用四個 Microsoft 威脅防護的分項會使組織發揮最大的價值。

![影像 of_Microsoft 威脅防護解決方案，適用于使用者、Azure 高級威脅防護、端點 Microsoft Defender 高級威脅防護、雲端應用程式、Microsoft Cloud App 安全性及資料，Office 365 高級威脅防護  ](../../media/mtp-eval-31.png)

本節會引導您設定下列專案：
-   Office 365 進階威脅防護
-   Azure 進階威脅防護 
-   Microsoft Cloud App Security
-   Microsoft Defender 進階威脅防護


## <a name="configure-office-365-advanced-threat-protection"></a>設定 Office 365 的高級威脅防護

>[!NOTE]
>如果您已啟用 Office 365 的高級威脅防護，請略過此步驟。 

有一個稱為「 *Office 365 高級威脅防護 * 」的 PowerShell 模組 (ORCA) 可協助判斷部分設定。 當您在租使用者中以系統管理員身分執行時，ORCAReport 將協助產生反垃圾郵件、反網路釣魚和其他郵件衛生設定的評估。 您可以從下載此模組 https://www.powershellgallery.com/packages/ORCA/ 。 

1. 流覽至[Office 365 Security & 合規性中心](https://protection.office.com/homepage)  >  **威脅管理**  >  **原則**。

   ![Image of_Office 365 Security & 合規性中心威脅管理原則頁面](../../media/mtp-eval-32.png)
 
2. 按一下 [ **ATP 反網路釣魚**]，選取 [ **建立** 並填入原則名稱和描述]。 按 **[下一步]**。

   ![Image of_Office 365 Security & 合規性中心反網路釣魚原則頁面，您可以在其中命名原則](../../media/mtp-eval-33.png)

   > [!NOTE]
   > 編輯您的高級 ATP 反網路釣魚原則。 將 **高級網路釣魚閥值** 變更為 **2-嚴格**。

3. 按一下 [ **新增條件** ] 下拉式功能表，然後選取您的網域 (s) 做為收件者網域。 按 **[下一步]**。

   ![Image of_Office 365 Security & 合規性中心反網路釣魚原則頁面，您可以在其中新增其應用程式的條件](../../media/mtp-eval-34.png)
 
4. 請複查您的設定。 按一下 [ **建立這個原則** ] 以確認。 

   ![Image of_Office 365 Security & 相容性中心反網路釣魚原則頁面，您可以在其中檢查您的設定，然後按一下 [建立這個原則] 按鈕](../../media/mtp-eval-35.png)
 
5. 選取 [ **ATP 安全附件** ]，然後選取 [ **開啟 SharePoint]、[OneDrive] 和 [Microsoft 小組** ] 選項的 atp。

   ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在其中開啟 SharePoint、OneDrive 及 Microsoft 小組的 ATP](../../media/mtp-eval-36.png)

6. 按一下 [+] 圖示，以建立新的安全附件原則，並將其套用為網域的收件者網域。 按一下 **[儲存]**。

   ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在此頁面上建立新的安全附件原則](../../media/mtp-eval-37.png)
 
7. 接下來，選取 [ **ATP 安全連結** 原則]，然後按一下鉛筆圖示以編輯預設原則。

8. 請確定未選取 [ **不要在使用者按一下安全連結時進行追蹤** ] 選項，而會選取其餘的選項。 如需詳細資訊，請參閱 [安全連結設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 。 按一下 **[儲存]**。 

   ![Image of_Office 365 Security & 相容性中心] 頁面，顯示未選取 [使用者按一下安全時不會追蹤] 選項](../../media/mtp-eval-38.png)

9. 接下來選取 **反惡意** 代碼原則，選取預設值，然後選擇 [鉛筆] 圖示。

10. 按一下 [ **設定** ]，然後選取 **[是] 並使用預設通知文字** ，以啟用 **惡意程式碼偵測回應**。 開啟 **通用附件類型 Filter** 。 按一下 **[儲存]**。

    ![Image of_Office 365 Security & 合規性中心] 頁面，顯示惡意程式碼偵測回應開啟時會啟用預設通知，而一般附件類型篩選已開啟](../../media/mtp-eval-39.png)
  
11. 流覽至[Office 365 Security & 合規性中心](https://protection.office.com/homepage)  >  **搜尋**  >  **審核記錄檔搜尋**，然後開啟審計。

    ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在此開啟審核記錄搜尋](../../media/mtp-eval-40.png)

12. 將 Office 365 ATP 與 Microsoft Defender ATP 整合。 流覽至[Office 365 Security & 合規性中心](https://protection.office.com/homepage)  >  **威脅管理**  >  **瀏覽器**，然後選取螢幕右上角的 [ **WDATP 設定**]。 在 [Microsoft Defender ATP connection] 對話方塊中，開啟 **[連線到 WINDOWS ATP**]。

    ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在此頁面上開啟 Windows Defender ATP 連接](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a>設定 Azure 高級威脅防護

>[!NOTE]
>如果您已經啟用 Azure 高級威脅防護，請略過此步驟。

1. 流覽至[Microsoft 365 Security Center](https://security.microsoft.com/info) > 選取**其他資源**  >  **Azure 高級威脅防護**。

   ![影像 of_Microsoft 365 Security Center 頁面，其中有開啟 Azure 高級威脅防護的選項](../../media/mtp-eval-42.png)

2. 按一下 [ **建立** ]，啟動 Azure 高級威脅防護嚮導。 

   ![影像 of_Azure 高級威脅防護嚮導] 頁面，您應該按一下此頁面上的 [建立] 按鈕](../../media/mtp-eval-43.png)

3. 選擇 [ **提供使用者名稱和密碼] 以連線至您的 Active Directory 樹**系。  

   ![影像 of_Azure 高級威脅防護歡迎頁面](../../media/mtp-eval-44.png)

4. 輸入您的 Active Directory 內部部署認證。 這可以是具有 Active Directory 讀取權限的任何使用者帳戶。

   ![影像 of_Azure 高級威脅防護目錄服務] 頁面，您應該在這裡放置您的認證](../../media/mtp-eval-45.png)

5. 接下來，選擇 [將 **感應器安裝** 和傳輸檔案下載到您的網域控制站]。

   ![影像 of_Azure 高級威脅防護] 頁面，您可以在其中選取 [下載感應器設定]](../../media/mtp-eval-46.png)

6. 執行 Azure ATP 感應器設定，然後開始遵循嚮導。

   ![影像 of_Azure 高級威脅防護] 頁面，您應該在此按一下 [下一步] 依照 Azure ATP 感應器嚮導](../../media/mtp-eval-47.png)
 
7. 在感應器部署類型中按 **[下一步]** 。

   ![影像 of_Azure 高級威脅防護] 頁面，您應該在此頁面上，按一下 [下一步] 以移至下一頁](../../media/mtp-eval-48.png)
 
8. 複製存取機碼，因為您需要在嚮導的下一步輸入它。

   ![影像 of_the 感應器頁面，您應該在此頁面上複製您需要在下一個 Azure ATP 感應器安裝精靈中輸入的訪問金鑰。](../../media/mtp-eval-49.png)
 
9. 將存取機碼複製到嚮導，然後按一下 [ **安裝**]。 

   ![Image of_Azure Advanced 威脅防護 Azure ATP 感應器嚮導] 頁面，您應該在此頁面上提供存取機碼，然後按一下 [安裝] 按鈕](../../media/mtp-eval-50.png)

10. 恭喜，您已在您的網域控制站上成功設定 Azure 高級威脅防護。

    ![影像 of_Azure 高級威脅防護 Azure ATP 感應器嚮導安裝完成，您應該按一下 [完成] 按鈕](../../media/mtp-eval-51.png)
 
11. 在 [ [Azure AZURE ATP](https://go.microsoft.com/fwlink/?linkid=2040449) 設定] 區段中，選取 [ **Windows Defender atp**]，然後開啟切換。 按一下 **[儲存]**。 

    ![Image of_the Azure Azure ATP 設定頁面，您應該在此頁面上開啟 Windows Defender ATP 切換](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP 已 rebranded 為 Microsoft Defender ATP。 所有的入口網站上的 ..org 變更都會針對一致性加以匯總。


## <a name="configure-microsoft-cloud-app-security"></a>設定 Microsoft Cloud App Security

>[!NOTE]
>如果您已啟用 Microsoft Cloud App 安全性，請略過此步驟。 

1. 流覽至[microsoft](https://security.microsoft.com/info)  >  **More Resources**  >  **Cloud App security**的 microsoft 365 Security Center More Resources。

   ![Image of_Microsoft 365 Security Center 頁面，您可以在其中看到 Microsoft Cloud App 卡片，應該按一下 [開啟] 按鈕](../../media/mtp-eval-53.png)

2. 在資訊提示中，整合 Azure ATP，選取 [ **啟用 AZURE atp 資料整合**]。
  
   ![Image of_the information prompt 整合 Azure ATP 應選取 [啟用 Azure ATP 資料整合] 連結](../../media/mtp-eval-54.png)

   > [!NOTE]
   > 如果您未看到此提示，這可能表示您的 Azure ATP 資料整合已經啟用。 不過，如果您不確定，請與您的 IT 系統管理員聯繫以確認。 

3. 移至 [ **設定**]，開啟 **Azure ATP 整合** 切換，然後按一下 [ **儲存**]。 

   ![您應開啟 Azure ATP 整合切換的 [影像 of_the 設定] 頁面，然後按一下 [儲存]](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > 針對新的 Azure ATP 實例，此整合切換功能會自動開啟。 在您繼續下一個步驟之前，請確認您的 Azure ATP 整合已啟用。
 
4. 在 [雲端探索設定] 底下，選取 [ **Microsoft DEFENDER ATP 整合**]，然後啟用整合。 按一下 **[儲存]**。

   ![Unsanctioned Microsoft Defender ATP 頁面上的 of_the 影像，其中會選取 [Microsoft Defender ATP 整合] 底下的 [封鎖應用程式] 核取方塊。 按一下 [儲存]。](../../media/mtp-eval-56.png)

5. 在 [雲端探索設定] 底下，選取 [ **使用者豐富**]，然後啟用與 Azure Active Directory 的整合。

   ![[使用者豐富] 區段中的 [濃縮已發現使用者識別碼與 Azure Active Directory 使用者識別碼] 核取方塊的影像](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a>設定 Microsoft Defender 高級威脅防護

>[!NOTE]
>如果您已啟用 Microsoft Defender 高級威脅防護，請略過此步驟。

1. 流覽至 microsoft Defender security center 的[microsoft 365 Security center](https://security.microsoft.com/info)  >  **More Resources**  >  ** **。 按一下 [開啟]****。

   ![Microsoft 365 Security Center 頁面中的影像 of_Microsoft Defender Security Center 選項](../../media/mtp-eval-58.png)
 
2. 遵循 Microsoft Defender 高級威脅防護嚮導。 按 **[下一步]**。 

   ![Microsoft Defender 安全中心歡迎使用嚮導頁面上的影像 of_the](../../media/mtp-eval-59.png)

3. 選擇 [根據您慣用的資料儲存位置]、[資料保留原則]、[組織大小] 和 [加入宣告預覽] 功能。

   ![Image of_the] 頁面上，選取您的資料儲存國家、保留原則及組織規模。 完成選取之後，請按 [下一步]。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > 您無法變更某些設定，例如，以後的資料儲存位置。 

   按 **[下一步]**。 

4. 按一下 [ **繼續** ]，它會布建您的 MICROSOFT Defender ATP 租使用者。

   ![影像 of_the 頁面提示您按一下 [繼續] 按鈕以建立您的雲端實例](../../media/mtp-eval-61.png)

5. 透過「群組原則」、「Microsoft 端點管理員」或執行本機腳本至 Microsoft Defender ATP，將您的端點上架在一起。 為了簡便起見，本指南使用本機腳本。

6. 按一下 [ **下載套件** ]，然後將上架腳本複製到端點 (s) 。

   ![影像 of_page 提示您按一下 [下載套件] 按鈕，將上架腳本複製到您的端點或端點](../../media/mtp-eval-62.png)

7. 在您的端點上，以系統管理員身分執行上架腳本，然後選擇 [Y]。 

   ![Image of_the 命令列，您可以在其中執行上架腳本，然後選擇 [Y] 繼續](../../media/mtp-eval-63.png)

8. 恭喜，您已架您的第一個端點。

   ![Image of_the 命令列，您可以在其中取得您已架第一個端點的確認。 按任意鍵繼續](../../media/mtp-eval-64.png)

9. 從 Microsoft Defender ATP 嚮導複製並貼上偵測測試。

   ![影像 of_the 執行偵測測試步驟，您應該按一下 [複製] 以複製您應該在命令提示字元中貼上的偵測測試腳本。](../../media/mtp-eval-65.png)

10. 將 PowerShell 腳本複製到提升許可權的命令提示字元，然後執行它。 

    ![影像 of_command 提示，您應該將 PowerShell 腳本複製到提升許可權的命令提示字元，然後執行它](../../media/mtp-eval-66.png)

11. 從嚮導選取 [ **開始使用 Microsoft DEFENDER ATP** ]。

    ![在您應該按一下 [開始使用 Microsoft Defender ATP] 的嚮導中 of_the 確認提示](../../media/mtp-eval-67.png)
 
12. 流覽 [Microsoft Defender 安全中心](https://securitycenter.windows.com/)。 移至 [ **設定** ]，然後選取 [ **高級功能**]。 

    ![您應選取 [高級功能] 的 [of_Microsoft Defender 安全性中心設定] 功能表中的影像](../../media/mtp-eval-68.png)

13. 開啟與 **Azure 高級威脅防護**的整合。  

    ![Image of_Microsoft Defender Security Center Advanced 功能，需要開啟的 Azure 高級威脅防護選項切換功能](../../media/mtp-eval-69.png)

14. 開啟與 **Office 365 威脅情報**的整合。

    ![Image of_Microsoft Defender Security Center Advanced features，Office 365 威脅情報選項切換，您必須開啟](../../media/mtp-eval-70.png)

15. 開啟與 **Microsoft Cloud App Security**的整合。

    ![Image of_Microsoft Defender Security Center Advanced 功能，您需要開啟的 Microsoft Cloud App Security 選項切換功能](../../media/mtp-eval-71.png)

16. 向中按向下方，然後按一下 [ **儲存偏好** 設定] 以確認新的整合。

    ![您需要按一下的影像 of_Save 偏好設定按鈕](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a>啟動 Microsoft 威脅防護服務

>[!NOTE]
>從2020年6月1日開始，Microsoft 會自動為所有合格的承租人啟用 Microsoft 威脅防護功能。 如需詳細資訊，請參閱此 [Microsoft 技術小組文章](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 。 


移至 [Microsoft 365 Security Center](https://security.microsoft.com/homepage)。 流覽至 [ **設定** ]，然後選取 [ **Microsoft 威脅防護**]。

![Microsoft 365 安全性中心設定頁面中的影像 of_Microsoft 威脅防護選項螢幕擷取畫面 ](../../media/mtp-eval-72b.png) <br>

如需更完整的指導，請參閱 [開啟 Microsoft 威脅防護](mtp-enable.md)。 

恭喜！ 您剛剛建立的是 Microsoft 威脅防護試用實驗室或試驗環境！ 現在，您可以熟悉 Microsoft 威脅防護使用者介面！ 查看您可以從下列 Microsoft 威脅防護互動指南中學到的內容，並瞭解如何使用每個儀表板做為日常安全性作業工作。


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

接下來，您可以模擬攻擊，並查看「向量積」功能如何偵測、建立提醒，以及自動回應端點上的 fileless 攻擊。

## <a name="next-step"></a>下一步
|![攻擊模擬階段](../../media/mtp/run-sim.png) <br>[攻擊模擬階段](mtp-pilot-simulate.md) | 針對您的 Microsoft 威脅防護試驗環境執行攻擊模擬。
|:-------|:-----|
