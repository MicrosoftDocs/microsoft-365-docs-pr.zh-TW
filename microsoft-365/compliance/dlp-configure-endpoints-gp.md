---
title: 透過群組原則上線 Windows 10 裝置
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用群組原則在 Windows 10 裝置上部署設定套件，使其可架至服務。
ms.openlocfilehash: b786d011a46f69e7bcac846e726e2aeb3031ae08
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918019"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>使用群組原則的板載 Windows 10 裝置 

適用於：

- [Microsoft 365 端點資料遺失防護 (DLP) ](./endpoint-dlp-learn-about.md)
- 群組原則

> [!NOTE]
> 若要使用群組原則 (GP) 更新若要部署套件，您必須在 Windows Server 2008 R2 或更新版本上。

> 若為 Windows Server 2019，您可能需要使用「群組原則」偏好建立之 XML 檔案的 NT AUTHORITY\SYSTEM 取代 NT AUTHORITY\Well-Known-System-Account。

## <a name="onboard-devices-using-group-policy"></a>使用群組原則的板載裝置

1. 從 [服務上架] 嚮導中，開啟已下載的 GP configuration 套件 .zip 檔案 (*DeviceComplianceOnboardingPackage.zip*) 。 您也可以從[Microsoft 規範中心](https://compliance.microsoft.com/compliancesettings/deviceonboarding)取得套件

2. 在功能窗格中，選取 [**設定**  >  **裝置上架**]。

3. 在 [ **部署方法** ] 欄位中，選取 [ **群組原則**]。

4. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。

5. 將 .zip 檔案的內容解壓縮到可供裝置存取的共用唯讀位置。 您應該會有一個稱為 *OptionalParamsPolicy* 的資料夾，以及檔案 *DeviceComplianceLocalOnboardingScript .cmd*。

6. 開啟「 [群組原則管理主控台](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。

7. 在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]、[ **喜好** 設定] 及 [控制台 **設定**]。

8. 以滑鼠右鍵按一下 [ **排程任務**]，指向 [ **新增**]，然後按一下 [ **立即工作 (至少為 Windows 7)**。

9. 在開啟的 **任務** 視窗中，移至 [**一般**] 索引標籤。在 [**安全性選項**] 底下，按一下 [**變更使用者或群組** 和類型系統]，然後按一下 [**檢查名稱** 然後按一下 **[確定]** NT AUTHORITY\SYSTEM 會顯示為執行工作時所用的使用者帳戶。

10. 選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。

11. 移至 [**動作**] 索引標籤，然後按一下 [**新增 ...** ]確定 [**動作**] 欄位中已選取 [**啟動程式**]。 輸入共用 *WindowsDefenderATPOnboardingScript .cmd* 檔案的檔案名和位置。

12. 按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。


## <a name="offboard-devices-using-group-policy"></a>使用群組原則的下架裝置
基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。 傳送給裝置的已到期的脫離套件會遭到拒絕。 下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。

> [!NOTE]
> 上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。

1. 從 [Microsoft 規範中心](https://compliance.microsoft.com/compliancesettings/deviceonboarding)取得脫離套件。

2. 在功能窗格中，選取 [**設定**  >  **//Device 上架**  >  **脫離**]。

3. 在 [ **部署方法** ] 欄位中，選取 [ **群組原則**]。

4. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。

5. 將 .zip 檔案的內容解壓縮到可供裝置存取的共用唯讀位置。 您應該有一個名為 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的檔案。

6. 開啟「 [群組原則管理主控台](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。

7. 在 [ **群組原則管理編輯器**] 中，移至 [電腦設定] **、** [ **喜好** 設定] 及 [控制台 **設定**]。

8. 以滑鼠右鍵按一下 [ **排程任務**]，指向 [ **新增**]，然後按一下 [ **立即** 工作]。

9. 在開啟的 **任務** 視窗中，移至 [ **一般** ] 索引標籤。在 [ **安全性選項**] 底下，選擇 [ (BUILTIN\SYSTEM]) 的 [本機系統] 使用者帳戶。

10. 選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。

11. 移至 [**動作**] 索引標籤，然後按一下 [**新增 ...**]。確定 [**動作**] 欄位中已選取 [**啟動程式**]。 輸入共用  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 檔案的檔案名和位置。

12. 按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。

> [!IMPORTANT]
> 脫離會導致裝置停止將感應器資料傳送至入口網站，但從裝置資料。


## <a name="monitor-device-configuration"></a>監視裝置設定
使用群組原則時，沒有任何選項可監視裝置上的原則部署。 監控可以直接在入口網站上進行，也可以使用不同的部署工具進行。

## <a name="monitor-devices-using-the-portal"></a>使用入口網站監視裝置
1. 移至 [Microsoft 規範中心](https://compliance.microsoft.com/)。
2. 按一下 [ **裝置** 清單]。
3. 驗證裝置是否出現。

> [!NOTE]
> 在 [ **裝置] 清單** 上，裝置開始顯示可能需要幾天。 這包括將原則發佈至裝置所需的時間、使用者登入前所需的時間，以及結束報告端點所需的時間。


## <a name="related-topics"></a>相關主題
- [使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置](dlp-configure-endpoints-sccm.md)
- [使用行動裝置管理工具上線 Windows 10 電腦](dlp-configure-endpoints-mdm.md)
- [使用本機指令碼上線 Windows 10 裝置](dlp-configure-endpoints-script.md)
- [上線非持續 Virtual Desktop Infrastructure (VDI) 裝置](dlp-configure-endpoints-vdi.md)
- [在新架的 Microsoft Defender ATP 裝置上執行偵測測試](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [疑難排解 Microsoft Defender 高級威脅防護上架問題](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)