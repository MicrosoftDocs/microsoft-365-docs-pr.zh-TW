---
title: 上線非持續 Virtual Desktop Infrastructure (VDI) 裝置
description: 在虛擬桌面基礎結構 (VDI) 裝置上部署設定套件，使其架至 Microsoft Defender for Endpoint service。
keywords: 設定虛擬桌面基礎結構 (VDI) 裝置、VDI、裝置管理、設定 Microsoft Defender for 端點、端點
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 3872be343e51c4e28f946192256932b048a23791
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933898"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>上線非持續 Virtual Desktop Infrastructure (VDI) 裝置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- 虛擬桌面基礎結構 (VDI) 裝置
- Windows 10，Windows Server 2019，Windows Server Nm-winserver-2008r2-2nd/2012R2/2016

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>上線非持續 Virtual Desktop Infrastructure (VDI) 裝置

用於端點的 Defender 支援非持續性的 VDI 會話上架。 


上架 VDIs 時，可能會有相關的難題。 以下是此案例的常見挑戰：

- 立即上架短暫的會話，必須在實際布建之前，架至端點的 Defender。
- 裝置名稱通常會針對新的會話重複使用。

在端點入口網站中，VDI 裝置可以出現為下列其中一種：

- 每個裝置單一專案。

  > [!NOTE]
  > 在此情況下，您必須在建立會話時設定 *相同* 的裝置名稱，例如使用無人值守的回應檔案。

- 每個裝置的多個專案-每個會話一個。

下列步驟會引導您完成上架 VDI 裝置，並將會反白顯示單一和多個專案的步驟。

>[!WARNING]
> 在資源設定較低的環境中，VDI 引導程式可能會降低端點感應器上架的 Defender 速度。 


### <a name="for-windows-10-or-windows-server-2019"></a>適用于 Windows 10 或 Windows Server 2019

1.  從服務上架嚮導中，開啟 [VDI 設定套件 .zip 檔案] (*WindowsDefenderATPOnboardingPackage.zip* 所下載的) 。 您也可以從 [Microsoft Defender Security Center](https://securitycenter.windows.com/)取得套件：

    1.  在功能窗格中，選取 [**設定**] [上  >  **架**]。

    1. 選取 [Windows 10] 做為作業系統。

    1.  在 [ **部署方法** ] 欄位中，選取 **非持續端點的 VDI 上架腳本**。

    1. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。

2. 將檔案從 .zip 檔案解壓縮至路徑底下的 WindowsDefenderATPOnboardingPackage 資料夾中 `golden/master` `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。 

    1. 如果您未針對每個裝置實施單一專案，請複製 WindowsDefenderATPOnboardingScript。

    1. 若要針對每個裝置實施單一專案，請同時複製 Onboard-NonPersistentMachine.ps1 和 WindowsDefenderATPOnboardingScript。
    
    > [!NOTE]
    > 如果您看不到 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 資料夾，它可能是隱藏的。 您必須選擇 [從檔案瀏覽器 **顯示隱藏的檔案和資料夾** ] 選項。

3. 開啟 [本機群組原則編輯器] 視窗，並流覽至 [**電腦** 設定] [  >  **Windows 設定**  >  **腳本**  >  **啟動**]。

   > [!NOTE]
   > 網域群組原則也可用於上架非持續性的 VDI 裝置。

4. 請根據您想要執行的方法，遵循適當的步驟：

   - 針對每個裝置的單一專案：
   
     選取 [ **PowerShell 腳本** ] 索引標籤，然後按一下 [ **新增** (Windows Explorer 會直接開啟您在先前複製上架腳本的路徑中) 。 流覽至上架 PowerShell script `Onboard-NonPersistentMachine.ps1` 。 不需要指定另一個檔案，因為會自動觸發該檔案。
   
   - 針對每個裝置的多個專案：
   
     選取 [ **腳本** ] 索引標籤，然後按一下 [ **新增** ] (Windows Explorer 會直接在您先前複製上架腳本的路徑中開啟) 。 流覽至上架 bash 腳本 `WindowsDefenderATPOnboardingScript.cmd` 。

5. 測試您的解決方案：

   1. 建立具有一個裝置的集區。
      
   1. 登入裝置。
      
   1. 從裝置登出。

   1. 使用另一位使用者登入裝置。
      
   1. 請根據您想要執行的方法，遵循適當的步驟：
   
      - 針對每個裝置的單一專案： 
    
        檢查 Microsoft Defender Security Center 中的一個專案。

      - 針對每個裝置的多個專案： 
       
        檢查 Microsoft Defender Security Center 中的多個專案。

6. 按一下功能窗格上的 [ **裝置] 清單** 。

7. 輸入裝置名稱並選取 [ **裝置** ] 作為搜尋類型，即可使用搜尋功能。


## <a name="for-downlevel-skus"></a>對於下層 SKUs

> [!NOTE]
> 只有當瞄準是針對每個裝置建立單一專案時，才會與下列登錄相關。

1. 將登錄值設定為：

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    或者使用命令列：

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. 遵循 [伺服器上架](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)程式。 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>更新非持久性虛擬桌面基礎結構 (VDI) 影像
建議的最佳作法是使用離線服務工具來修補黃金/主映射。<br>
例如，您可以使用下列命令來安裝更新，讓影像保持離線狀態：

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

如需 DISM 命令和離線服務的詳細資訊，請參閱下列文章：
- [使用 DISM 修改 Windows 映像](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM 影像管理 Command-Line 選項](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [縮小離線 Windows 映像中元件存放區的大小](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

如果離線服務不是非持續性的 VDI 環境可行的選項，應採取下列步驟，以確保一致性及感應器的健全狀況：

1. 在啟動線上服務或修補的主映射後，請執行脫離腳本，以關閉端點感應器的 Defender。 如需詳細資訊，請參閱 [使用本機腳本的下架裝置](configure-endpoints-script.md#offboard-devices-using-a-local-script)。

2. 在 CMD 視窗中執行下列命令，以確定感應器已停止：

   ```console
   sc query sense
   ```

3. 視需要為影像服務。

4. 使用下列 PsExec.exe (執行下列命令 https://download.sysinternals.com/files/PSTools.zip) ，以清理自啟動後，感應器可能已積累的網路資料夾內容：

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 照常重新密封黃金/主映射。

## <a name="related-topics"></a>相關主題
- [使用群組原則的板載 Windows 10 裝置](configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置](configure-endpoints-sccm.md)
- [使用行動裝置管理工具上線 Windows 10 電腦](configure-endpoints-mdm.md)
- [使用本機指令碼上線 Windows 10 裝置](configure-endpoints-script.md)
- [疑難排解 Microsoft Defender 的端點上架問題](troubleshoot-onboarding.md)
