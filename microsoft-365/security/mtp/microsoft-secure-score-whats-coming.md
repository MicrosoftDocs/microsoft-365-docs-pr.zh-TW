---
title: Microsoft 安全分數的情況為何？
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分、如何計算詳細資料，以及安全性管理員可以預期的情況。
keywords: 安全性、惡意程式碼、Microsoft 365、M365、安全分數、安全性中心、改進動作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 48ff6d6f5cac0991895c40cae90ca31657cfedff
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844879"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft 安全分數的情況為何？

若要讓[Microsoft 安全評分](microsoft-secure-score.md)為您安全性狀況的更佳代表並提高可用性，我們在近期進行一些變更。 您的分數和可能的最大分數會變更。 不過，這不是指安全性狀況的變更。

若要深入瞭解最近的變更，請參閱[Microsoft Secure 得分的新功能？](microsoft-secure-score.md#whats-new)

## <a name="june-2020"></a>2020 年 6 月

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>移除 Microsoft Defender 高級威脅防護的改進動作

* 開啟攻擊面減少規則

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>新增 Microsoft Defender 高級威脅防護的改進動作

* 封鎖 Adobe Reader，以建立子流程
* 使用勒索軟體的高級防護
* 封鎖所有 Office 應用程式以建立子流程
* 封鎖 Office 應用程式建立可執行檔內容
* 從啟動下載的可執行內容封鎖 JavaScript 或 VBScript
* 封鎖可能混淆的腳本執行
* 從電子郵件客戶程式和 web 郵件封鎖可執行檔內容
* 封鎖 Office communication application 建立子流程
* 封鎖從 USB 執行的不受信任和未簽署程式
* 透過 WMI 事件訂閱封鎖持久性
* 封鎖 Office 應用程式將程式碼注入其他程式
* 封鎖可執行檔，除非符合流行、age 或受信任的清單準則
* 封鎖來自 PSExec 和 WMI 命令的進程建立
* 從 Windows local security 機關子系統封鎖認證竊取（lsass.exe）
* 封鎖 Office 宏的 WIN32 API 呼叫
