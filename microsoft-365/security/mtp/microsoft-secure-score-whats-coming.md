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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583712"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft 安全分數的情況為何？

若要讓[Microsoft 安全評分](microsoft-secure-score.md)為您安全性狀況的更佳代表並提高可用性，我們在近期進行一些變更。 您的分數和可能的最大分數會變更。 不過，這不是指安全性狀況的變更。

若要深入瞭解最近的變更，請參閱[Microsoft Secure 得分的新功能？](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>2020年4月21日

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>移除不符合可靠度量期望的改進動作，或不提供安全狀況的有用標記法

為了確保 Microsoft 安全分數有意義，且每個改進動作都有意義且可靠，我們正在移除下列改進動作。

- 將 IRM 保護套用至檔
- 套用資料遺失防護原則

### <a name="adding-azure-ad-improvement-action-to-preview"></a>將 Azure AD 改進動作新增至預覽

將下列 Azure Active Directory 改進動作新增至[Microsoft Secure 得分的預覽版本](microsoft-secure-score-preview.md)：

- 不允許使用者將同意授與未受管理的應用程式（目前已發行版本本中提供）

### <a name="adding-azure-atp-improvement-actions-to-preview"></a>新增 Azure ATP 改進動作以供預覽

將下列 Azure 高級威脅防護改進動作新增至[Microsoft Secure 得分的預覽版本](microsoft-secure-score-preview.md)：

- 停用網域控制站上的幕後列印程式服務
- 修改不安全的 Kerberos 委派以防止模仿
- 使用 Microsoft LAPS 保護和管理本機系統管理員密碼
- 降低橫向移動路徑對機密實體的風險
- 移除敏感群組中的睡眠帳戶
- 從實體中移除不安全的 SID 歷程記錄屬性
- 解決不安全的帳戶屬性
- 停止清除文字認證曝光
- 停止舊版通訊協定通訊
- 停止弱密碼使用

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a>支援 Microsoft Defender ATP 威脅 & 漏洞管理（TVM）預覽中的安全性建議

TVM 所提供的所有發行的安全性建議現在也可用於[預覽版本的 Microsoft 安全分數](microsoft-secure-score-preview.md)。
