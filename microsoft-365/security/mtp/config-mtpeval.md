---
title: 為試驗實驗室或試驗環境設定 Microsoft 365 Defender 基礎
description: 針對您的試驗實驗室或試驗環境設定 Microsoft 365 Defender 基礎，例如適用于 Office 365 的 Microsoft Defender、Microsoft Defender for Identity、Microsoft Cloud App 安全性，以及 Microsoft Defender for Endpoint。
keywords: 設定 Microsoft 威脅防護試用版、Microsoft 威脅防護試用版設定、設定 Microsoft 威脅防護試驗專案、設定 Microsoft 威脅防護基礎、Microsoft 威脅防護基礎
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932235"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>針對您的試驗實驗室或試驗環境設定 Microsoft 365 Defender 基礎

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender


建立 Microsoft 365 Defender 試用版實驗室或試驗環境，並部署此為三階段程式：

|[![階段 1：準備](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[階段 1：準備](prepare-mtpeval.md) |[![階段 2：設定](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[階段 2：設定](setup-mtpeval.md) |![階段 3：上機](../../media/phase-diagrams/onboard.png)<br/>階段 3：上機 | [![返回試驗](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[回到試驗手冊](mtp-pilot.md) |
|--|--|--|--|
|| |*您目前在這裡！* | |

您目前處於組組階段。

準備是任何成功部署的關鍵。 本文將引導您瞭解部署 Microsoft Defender for Endpoint 時需要考慮的要點。


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender 柱柱
Microsoft 365 Defender 由四個石柱組成。 雖然一個石柱可以為網路組織的安全性提供值，但啟用四個 Microsoft 365 Defender 基礎會賦予貴組織最大的價值。

![適用于of_Microsoft使用者 、Microsoft Defender for Endpoint 端點、雲端應用程式、Microsoft Cloud App 安全性及資料之 Microsoft Defender for Office 365 之使用者的 365 Defender 解決方案影像](../../media/mtp/m365pillars.png)

本節將引導您進行設定：
-   適用於 Office 365 的 Microsoft Defender
-   適用於身分識別的 Microsoft Defender 
-   Microsoft Cloud App Security
-   適用於端點的 Microsoft Defender


## <a name="configure-microsoft-defender-for-office-365"></a>設定 Office 365 的 Microsoft Defender

>[!NOTE]
>如果您已經啟用 Office 365 的 Defender，請略過此步驟。 

有一個 PowerShell 模組稱為 *Office 365* 進位威脅防護建議組設定分析程式 (ORCA) ，可協助判斷其中一些設定。 當您在租使用者中以系統管理員的系統管理員角色執行時，get-ORCAReport 將可協助產生反垃圾郵件、防網路釣魚和其他郵件內容設定的評估。 您可以下載此模組 https://www.powershellgallery.com/packages/ORCA/ 。 

1. 流覽至 [Office 365 安全性&](https://protection.office.com/homepage)  >  **合規性中心的威脅管理**  >  **政策**。

   ![365 of_Office安全規範&威脅管理政策頁面的圖像](../../media/mtp-eval-32.png)
 
2. 按一下 **[防網路釣魚，** 選取 [ **建立** 並填入策略名稱與描述。 按 **[下一步]**。

   ![Of_Office 365 安全性&合規性中心防網路釣魚政策頁面的圖像，您可以在此命名您的政策](../../media/mtp-eval-33.png)

   > [!NOTE]
   > 在適用于 Office 365 的 Microsoft Defender 中編輯您的進位防網路釣魚政策。 將 **進位網路釣魚閾值變更** 為 **2 - 進一無二**。

3. 按一下 [ **新增條件** 下拉式功能表，然後選取您的網域 (收) 網域。 按 **[下一步]**。

   ![365 of_Office安全規範中心&網路釣魚政策頁面的圖像，您可以在其中新增其應用程式的條件](../../media/mtp-eval-34.png)
 
4. 檢查您的設定。 按一下 **[建立此策略>** 以確認。 

   ![圖像of_Office 365 安全性&合規性中心防網路釣魚政策頁面，您可以在其中檢查您的設定，然後按一下建立此政策按鈕](../../media/mtp-eval-35.png)
 
5. 選取 **[安全附件** ， **然後開啟 SharePoint、OneDrive** 和 Microsoft Teams 的 ATP 選項。

   ![可of_Office SharePoint、OneDrive 和 Microsoft Teams & ATP 的 365 安全規範中心頁面圖像](../../media/mtp-eval-36.png)

6. 按一下 + 圖示以建立新的安全附件原則，然後以收件者網域的網域方式將附件原則應用至您的網域。 按一下 **[儲存]**。

   ![可在 of_Office 365 安全&中心頁面建立新安全附件策略的影像](../../media/mtp-eval-37.png)
 
7. 接下來，選取 **[安全連結策略** ，然後按一下鉛筆圖示以編輯預設策略。

8. 請確定未 **選取 [** 不要追蹤使用者何時點選安全連結選項，同時選取其他選項。 請參閱 [安全連結設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 以瞭解詳細資料。 按一下 **[儲存]**。 

   ![顯示of_Office 365 安全性&規範中心頁面的圖像，顯示未選取 [使用者按一下安全時不要追蹤選項](../../media/mtp-eval-38.png)

9. 接著，選取 **反惡意攻擊** 策略，選取預設值，然後選擇鉛筆圖示。

10. 按一下 **[設定** >， **然後選取 [是，並使用預設通知** 文字啟用 **惡意攻擊偵測回應**。 開啟 **一般附件類型篩選** 。 按一下 **[儲存]**。

    ![365 of_Office安全&中心頁面的圖像，顯示已預設通知開啟惡意程式碼偵測回應，且一般附件類型篩選器已開啟](../../media/mtp-eval-39.png)
  
11. 流覽至 [Office 365 安全性&合規性中心](https://protection.office.com/homepage)  >  **搜尋**  >  **稽核記錄搜尋**，並開啟稽核。

    ![可在 of_Office 365 安全性&中心頁面開啟稽核記錄搜尋的圖像](../../media/mtp-eval-40.png)

12. 整合 Microsoft Defender for Office 365 與 Microsoft Defender for Endpoint。 流覽至 [Office 365](https://protection.office.com/homepage)安全性&合規性中心威脅管理總管，然後針對畫面右上角的端點設定選取  >    >  **** **Microsoft Defender。** 在 [端點的 Defender for Connection- 對話方塊中，開啟 [**連接至 Microsoft Defender for Endpoint。**

    ![可在 of_Office 365 安全性&中心頁面開啟 Microsoft Defender 端點連結的影像](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>設定 Microsoft Defender 的身分識別

>[!NOTE]
>如果您已經啟用 Microsoft Defender 的身分識別，請略過此步驟

1. 流覽至 [Microsoft 365 資訊安全中心，>](https://security.microsoft.com/info)**選取更多** Microsoft  >  **Defender 用於身分識別的資源**。

   ![365 of_Microsoft 365 資訊安全中心頁面上有開啟 Microsoft Defender 身分識別選項的影像](../../media/mtp-eval-42.png)

2. 按一下 **[建立** 以啟動 Microsoft Defender 的身分識別精靈。 

   ![[of_Microsoft識別精靈的 Defender 頁面圖像，您應該按一下 [建立按鈕](../../media/mtp-eval-43.png)

3. 選擇 **提供使用者名稱和密碼，以連接到您的 Active Directory 樹目錄**。  

   ![身分of_Microsoft Defender 歡迎頁面的圖像](../../media/mtp-eval-44.png)

4. 輸入 Active Directory 內部部署認證。 這可以是具有 Active Directory 讀取權限的任何使用者帳戶。

   ![身分of_Microsoft Defender for Identity Directory 服務頁面的圖像，您應該將認證放在這個頁面](../../media/mtp-eval-45.png)

5. 接下來，選擇 **下載感應器設定** ，然後傳輸檔案到您的網域控制站。

   ![圖像of_Microsoft識別的 Defender 頁面，您可以在此選取下載感應器設定](../../media/mtp-eval-46.png)

6. 執行 Microsoft Defender for Identity 感應器設定，然後按照精靈執行。

   ![身分of_Microsoft Defender 頁面的圖像，您應該按一下 [Microsoft Defender for Identity 感應器精靈，](../../media/mtp-eval-47.png)
 
7. 按一下 **感應器** 部署類型的 [下一步。

   ![身分of_Microsoft Defender 頁面的圖像，您應該按一下旁以前往下一頁](../../media/mtp-eval-48.png)
 
8. 複製便捷鍵，因為您需要在精靈中輸入下一個。

   ![影像of_the感應器頁面，您應該複製下一個 Microsoft Defender for Identity 感應器設定精靈頁面中輸入的存取鍵](../../media/mtp-eval-49.png)
 
9. 將便捷鍵複製到精靈，然後按一下 [ **安裝**。 

   ![[of_Microsoft識別感應器精靈頁面的影像，您應該在這裡提供便捷鍵，然後按一下安裝按鈕](../../media/mtp-eval-50.png)

10. 恭喜您，您已成功在網域控制站上針對身分識別將 Microsoft Defender 設成。

    ![[of_Microsoft識別感應器精靈安裝完成的圖像，您應該按一下完成按鈕](../../media/mtp-eval-51.png)
 
11. 在 Microsoft [Defender for Identity settings](https://go.microsoft.com/fwlink/?linkid=2040449) 區段下，選取 **Microsoft Defender for Endpoint **，然後開啟切換開關。 按一下 **[儲存]**。 

    ![影像of_the Microsoft Defender 的身分識別設定頁面，您應該將 Microsoft Defender for Endpoint 切換為開啟](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP 已重新組織為端點的 Microsoft Defender。 我們所有入口網站都推出重新建立變更的一致性。


## <a name="configure-microsoft-cloud-app-security"></a>設定 Microsoft 雲端 App 安全性

>[!NOTE]
>如果您已啟用 Microsoft Cloud App 安全性，請略過此步驟。 

1. 流覽至 [Microsoft 365 資訊安全中心](https://security.microsoft.com/info)  >  **其他資源** Microsoft 雲端  >  **App 安全性**。

   ![可在 of_Microsoft 365 資訊安全中心頁面看到 Microsoft Cloud App 卡片的影像，應該按一下開啟按鈕](../../media/mtp-eval-53.png)

2. 在整合 Microsoft Defender for Identity 的資訊提示中，選取啟用 **Microsoft Defender 進行身分識別資料整合**。
  
   ![影像of_the資訊提示以整合 Microsoft Defender 的身分識別，您應該在這裡選取啟用 Microsoft Defender 進行身分識別資料整合連結](../../media/mtp-eval-54.png)

   > [!NOTE]
   > 如果您沒看到這個提示，可能表示您的 Microsoft Defender 的身分識別資料整合功能已啟用。 不過，如果您不確定，請與您的 IT 系統管理員聯繫以確認。 

3. 請前往 [ **設定**，開啟 **Microsoft Defender 的** 身分識別整合切換開關，然後按一下 [ **儲存**。 

   ![影像of_the設定頁面，您應該開啟 Microsoft Defender 的身分識別整合切換，然後按一下 [儲存](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > 針對新的 Microsoft Defender 身分識別實例，此整合切換開關會自動開啟。 繼續下一個步驟之前，請確認您的 Microsoft Defender 身分識別整合功能已啟用。
 
4. 在雲端探索設定下，選取 **Microsoft Defender 進行端點整合**，然後啟用整合。 按一下 **[儲存]**。

   ![影像of_the Microsoft Defender for Endpoint 頁面，其中已選取 Microsoft Defender for Endpoint 整合下的封鎖未封鎖的應用程式核取方塊。 按一下 [儲存。](../../media/mtp-eval-56.png)

5. 在雲端探索設定下，選取 **使用者擴充**，然後啟用與 Azure Active Directory 的整合。

   ![使用者擴充區段的圖像，其中已選取 Azure Active Directory 使用者名稱核取方塊的豐富探索使用者識別碼](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>設定 Microsoft Defender 端點

>[!NOTE]
>如果您已經啟用端點的 Microsoft Defender，請略過此步驟。

1. 流覽至 [Microsoft 365 資訊安全中心](https://security.microsoft.com/info)  >  **其他資源** Microsoft  >  **Defender 資訊安全中心**。 按一下 [開啟]。

   ![Microsoft 365 of_Microsoft中 Defender 資訊安全中心的影像選項](../../media/mtp-eval-58.png)
 
2. 請遵循 Microsoft Defender for Endpoint 精靈。 按 **[下一步]**。 

   ![Microsoft Defender of_the歡迎精靈頁面的影像](../../media/mtp-eval-59.png)

3. 根據您的偏好資料儲存位置、資料保留政策、組織規模，以及選擇參加預覽功能來選擇。

   ![選取of_the儲存國家/地區、保留規定和組織大小的圖像頁面。 選取完成後，按一下 [下一步。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > 之後您無法變更某些設定，例如資料儲存位置。 

   按 **[下一步]**。 

4. 按一下 **[繼續** ，它會針對端點租使用者提供您的 Microsoft Defender。

   ![頁面上of_the按一下 [繼續按鈕以建立雲端實例](../../media/mtp-eval-61.png)

5. 透過群組原則、Microsoft Endpoint Manager 或執行本地腳本到 Microsoft Defender for Endpoint，來設置端點。 為了簡化，本指南使用本地腳本。

6. 按一下 **[下載套件** ，然後複製設置腳本至 (端點) 。

   ![提示of_page下載套件按鈕以將上線腳本複製到端點或端點的圖像](../../media/mtp-eval-62.png)

7. 在端點上，以系統管理員的名次執行設置腳本，然後選擇 Y。 

   ![圖像of_the您執行設置腳本並選擇 Y 以繼續進行的命令列](../../media/mtp-eval-63.png)

8. 恭喜您，您的第一個端點已經上線。

   ![顯示of_the的影像，您可以在此取得已上線第一個端點的確認。 按任一按鍵以繼續](../../media/mtp-eval-64.png)

9. 從 Microsoft Defender for Endpoint 精靈複製貼上偵測測試。

   ![影像of_the偵測測試步驟，您應該按一下 [複製以複製偵測測試腳本，您應該貼到命令提示文字中](../../media/mtp-eval-65.png)

10. 將 PowerShell 腳本複製到提升許可權的命令提示文字，然後執行它。 

    ![影像of_command提示，您應該將 PowerShell 腳本複製到提升許可權的命令提示文字並加以執行](../../media/mtp-eval-66.png)

11. 從 **精靈選取** 開始使用 Microsoft Defender for Endpoint。

    ![影像of_the精靈中的確認提示，您應該按一下 [開始使用 Microsoft Defender for Endpoint](../../media/mtp-eval-67.png)
 
12. 請流覽 [Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)。 請前往設定 **，** 然後選取進 **一功能**。 

    ![圖像of_Microsoft Defender 資訊安全中心設定功能表，您應該選取進一功能](../../media/mtp-eval-68.png)

13. 開啟與 Microsoft **Defender 的身分識別整合**。  

    ![需要of_Microsoft的 Microsoft Defender 身分識別選項切換按鈕圖像](../../media/mtp-eval-69.png)

14. 開啟與 Office **365 威脅情報的整合**。

    ![需要of_Microsoft Defender 資訊安全中心進功能、Office 365 威脅情報選項切換開關的圖像](../../media/mtp-eval-70.png)

15. 開啟與 **Microsoft Cloud App 安全性的整合**。

    ![需要of_Microsoft Defender 資訊安全中心進功能、Microsoft 雲端 App 安全性選項切換開關的圖像](../../media/mtp-eval-71.png)

16. 向下卷軸並按一下 **[儲存偏好** 設定以確認新的整合。

    ![圖像of_Save您需要按一下的喜好設定按鈕](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>開始使用 Microsoft 365 Defender 服務

>[!NOTE]
>自 2020 年 6 月 1 日起，Microsoft 會自動針對所有合格租使用者啟用 Microsoft 365 Defender 功能。 請參閱此 [Microsoft 技術社群文章，瞭解授權資格的詳細資訊](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 。 


請前往 [Microsoft 365 資訊安全中心](https://security.microsoft.com/homepage)。 流覽至 **設定，** 然後選取 **Microsoft 365 Defender。**

![Microsoft 365 of_Microsoft設定頁面的影像顯示 365 Defender 選項螢幕擷取畫面 ](../../media/mtp-eval-72b.png) <br>

有關更全方位的指引，請參閱開啟[Microsoft 365 Defender。](mtp-enable.md) 

恭喜您！ 您剛建立 Microsoft 365 Defender 試用版實驗室或試驗環境！ 現在您可以熟悉 Microsoft 365 Defender 使用者介面了！ 查看您可從下列 Microsoft 365 Defender 互動式指南中學到什麼，並瞭解如何使用儀表板執行日常的安全性作業工作。


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

接下來，您可以模擬攻擊，並查看交叉產品功能偵測、建立警示，並自動回應端點上的無檔案攻擊。

## <a name="next-step"></a>下一步
|[攻擊模擬階段](mtp-pilot-simulate.md) | 針對您的 Microsoft 365 Defender 試驗環境執行攻擊模擬。
|:-------|:-----|
