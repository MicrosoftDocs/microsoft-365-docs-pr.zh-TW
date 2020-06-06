---
title: ATP 安全連結警告頁面
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fc4e6ebb-5acc-4bc5-bad8-4f3407d1d3f4
ms.collection:
- M365-security-compliance
description: 取得您在 Office 365 高級威脅防護工作時可能看到的警告頁面的概覽。
ms.openlocfilehash: 00052c7212f9f469ca94d83ed53851b65904fd8e
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588285"
---
# <a name="atp-safe-links-warning-pages"></a>ATP 安全連結警告頁面

> [!IMPORTANT]
> 本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。 如果您使用的是 Outlook.com、Microsoft 365 系列或 Microsoft 365 個人，而且您正在尋找 Outlook 中安全連結的相關資訊，請參閱[Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

[Office 365 Advanced 威脅防護](office-365-atp.md)（ATP）可協助您的組織防禦透過功能（例如[atp 安全連結](atp-safe-links.md)、 [atp 安全附件](atp-safe-attachments.md)和[反網路釣魚防護](anti-phishing-protection.md)）等功能的網路釣魚企圖和惡意程式碼。 保護功能到位時，會檢查電子郵件和 Office 檔中的連結（URLs）。 如果 URL 被識別為可疑或惡意的，當您按一下 url 時，可能會遭到封鎖，無法將其開啟。 您也可能會看到警告頁面，而不是直接前往網站。

請閱讀本文，以查看可能出現之警告頁面的範例，以及警告頁面的最近更新。

## <a name="examples-of-warning-pages"></a>警告頁面範例

### <a name="atp-is-scanning-the-link"></a>ATP 正在掃描連結

ATP 安全連結正在掃描 URL。 您可能需要等待幾分鐘再重新嘗試連結。

![ATP 正在掃描連結](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="a-url-is-in-a-suspicious-email-message"></a>URL 位於可疑的電子郵件中

URL 的電子郵件與其他視為可疑的電子郵件訊息類似。 建議您先檢查電子郵件訊息，再繼續進行網站。

![此 URL 位於可疑的電子郵件中](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="a-url-is-in-a-message-identified-as-a-phishing-attempt"></a>URL 位於識別為網路釣魚嘗試的郵件中

URL 位於識別為網路釣魚攻擊的電子郵件中。 因此，電子郵件中的所有 URLs 都會遭到封鎖。 建議您不要繼續進行網站。

![此 URL 位於識別為網路釣魚嘗試的郵件中](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="a-site-has-been-identified-as-malicious"></a>網站已識別為惡意

URL 指向已識別為惡意的網站。  <br/> 建議您不要繼續進行網站。

![此網站已辨識為惡意](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="a-site-is-blocked"></a>封鎖網站

您的組織已封鎖此 URL。 有幾個原因可能會封鎖 URL。 建議您與組織的 Microsoft 365 for business 管理員聯繫。

![網站已遭封鎖](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="an-error-has-occurred"></a>發生錯誤

發生某種類型的錯誤，無法開啟此 URL。

![發生錯誤](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

## <a name="recent-updates-to-warning-pages"></a>最新的警告頁面更新

最近針對 Office 365 ATP 更新數個警告頁面。 如果您還沒有看到更新的頁面，您會很快。 這類更新包括新的色彩配置、更多詳細資料，以及在使用指定的警告和建議時，可繼續前往網站的功能。

### <a name="url-scan-in-progress"></a>進行 URL 掃描

原始警告頁面：

![有關正在掃描之 URL 掃描的原始警告頁面](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

更新的警告頁面：

![ATP 正在掃描連結](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="malicious-site-warning"></a>惡意網站警告

原始警告頁面：

![關於惡意網站的原始警告頁面](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

更新的警告頁面：

![此網站已辨識為惡意](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="blocked-url-warning"></a>封鎖的 URL 警告

原始警告頁面：

![有關封鎖 URL 的原始警告頁面](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

更新的警告頁面：

![網站已遭封鎖](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="error-occurred-warning-page"></a>「發生錯誤」警告頁面

原始警告頁面：

![原始的「發生錯誤」警告頁面](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)

更新的警告頁面：

![發生錯誤](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)
