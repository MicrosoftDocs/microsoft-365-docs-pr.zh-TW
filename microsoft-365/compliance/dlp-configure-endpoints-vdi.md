---
title: 板載非持久性虛擬桌面基礎結構 (VDI) 裝置
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 在虛擬桌面基礎結構 (VDI) 裝置上部署設定套件，使其架至 Microsoft 365 端點資料遺失防護服務。
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769400"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>板載非持久性虛擬桌面基礎結構 (VDI) 裝置

適用於： 
- [Microsoft 365 端點資料遺失防護 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)

- 虛擬桌面基礎結構 (VDI) 裝置

>[!WARNING]
> Windows 虛擬桌面的 Microsoft 365 端點資料遺失防護支援可支援單一會話案例。 目前不支援 Windows 虛擬桌面上的多重會話案例。

## <a name="onboard-vdi-devices"></a>板載 VDI 裝置

Microsoft 365 端點資料遺失防護功能支援非持續性的 VDI 會話上架。 

>[!Note]
>若要進行板載非持續的 VDI 會話，VDI 裝置必須在 Windows 10 1809 或更新版本上。

上架 VDIs 時，可能會有相關的難題。 以下是此案例的常見挑戰：

- 立即上架短暫的會話，在實際布建之前，必須架至 Microsoft 365 端點資料遺失防護。
- 裝置名稱通常會針對新的會話重複使用。

VDI 裝置可以出現在 Microsoft 365 規範中心，您可以：

- 每個裝置單一專案。  
請注意，在此情況下，建立會話時必須設定 *相同* 的裝置名稱，例如使用自動回應檔案。
- 每個裝置的多個專案-每個會話一個。

下列步驟會引導您完成上架 VDI 裝置，並將會反白顯示單一和多個專案的步驟。

>[!WARNING]
> 對於資源設定低的環境，VDI 引導程式可能會降低 Microsoft 365 端點資料遺失防護上架的速度。 

1.  從服務上架嚮導中，開啟 [VDI 設定套件 .zip 檔案] ( *DeviceCompliancePackage.zip* 所下載的) 。

2.  在功能窗格中，選取 [ **設定** 裝置上架] 上  >  **Device onboarding**  >  **架** 。

3. 在 [ **部署方法** ] 欄位中，選取 **非持續端點的 VDI 上架腳本** 。

5. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。

6. 將檔案從 .zip 檔案解壓縮至路徑底下的 DeviceCompliancePackage 資料夾中 `golden/master` `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。 

7. 如果您未針對每個裝置實施單一專案，請複製 DeviceComplianceOnboardingScript。

8. 若要針對每個裝置實施單一專案，請同時複製 Onboard-NonPersistentMachine.ps1 和 DeviceComplianceOnboardingScript。
    
    > [!NOTE]
    > 如果您看不到 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 資料夾，它可能是隱藏的。 您必須選擇 [從檔案瀏覽器 **顯示隱藏的檔案和資料夾** ] 選項。

9. 開啟 [本機群組原則編輯器] 視窗，並流覽至 [ **電腦** 設定] [  >  **Windows 設定**  >  **腳本**  >  **啟動** ]。

   > [!NOTE]
   > 網域群組原則也可用於上架非持續性的 VDI 裝置。

4. 請根據您想要執行的方法，遵循適當的步驟：

   **每個裝置的單一專案**
   
   選取 [ **PowerShell 腳本** ] 索引標籤，然後按一下 [ **新增** (Windows Explorer 會直接開啟您在先前複製上架腳本的路徑中) 。 流覽至上架 PowerShell script `Onboard-NonPersistentMachine.ps1` 。
   
   **針對每個裝置的多個專案** ：
   
   選取 [ **腳本** ] 索引標籤，然後按一下 [ **新增** ] (Windows Explorer 會直接在您先前複製上架腳本的路徑中開啟) 。 流覽至上架 bash 腳本 `DeviceComplianceOnboardingScript.cmd` 。

5. 測試您的解決方案：

   1. 建立具有一個裝置的集區。
      
   1. 登入裝置。
      
   1. 從裝置登出。

   1. 使用另一位使用者登入裝置。
      
   1. **針對每個裝置的單一專案** ：請檢查 Microsoft Defender Security Center 中只有一個專案。<br>
      **針對每個裝置的多個專案** ：檢查 Microsoft Defender Security Center 中的多個專案。

6. 按一下功能窗格上的 [ **裝置] 清單** 。

7. 輸入裝置名稱並選取 [ **裝置** ] 作為搜尋類型，即可使用搜尋功能。

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

1. 在啟動線上服務或修補的主映射後，請執行脫離腳本，關閉 Microsoft 365 端點資料遺失防護感應器。 如需詳細資訊，請參閱 [使用本機腳本的下架裝置](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)。

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
- [使用群組原則的板載 Windows 10 裝置](dlp-configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置](dlp-configure-endpoints-sccm.md)
- [使用行動裝置管理工具的板載 Windows 10 裝置](dlp-configure-endpoints-mdm.md)
- [使用本機腳本的板載 Windows 10 裝置](dlp-configure-endpoints-script.md)
- [疑難排解 Microsoft Defender 高級威脅防護上架問題](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
