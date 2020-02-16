---
title: Office 365 ATP 安全連結警告頁面
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
description: 概略警告頁面，您可能會看到 Office 365 進階威脅防護位於工時。
ms.openlocfilehash: ef2f0fd59c7d5f8e62b0f562097fafd01d669459
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086672"
---
# <a name="office-365-atp-safe-links-warning-pages"></a>Office 365 ATP 安全連結警告頁面

> [!IMPORTANT]
> 本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。 如果您使用 Outlook.com、Office 365 家用版或 Office 365 個人版，並且在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)。

[Office 365 進階威脅防護](office-365-atp.md)(ATP) 可協助保護組織免於網路釣魚企圖和惡意程式碼透過功能，例如[ATP 安全連結](atp-safe-links.md)、 [ATP 安全附件](atp-safe-attachments.md)，以及[防網路釣魚保護](anti-phishing-protection.md)。 就地保護時，就會檢查電子郵件和 Office 文件中的連結 (Url)。 如果 URL 便會被視為可疑或惡意，您可能會封鎖從開啟 URL，當您按一下。 而不是直接前往網站，您可能會看到警告] 頁面。 
  
閱讀本篇文章以查看，以及最新的更新至警告頁面可能出現的警告頁面的範例。
  
## <a name="examples-of-warning-pages"></a>警告頁面範例

### <a name="atp-is-scanning-the-link"></a>ATP 會掃描的連結

URL 是由 ATP 安全連結掃描。 您可能必須等待幾分鐘再試一次連結的時間。

![ATP 會掃描的連結](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="a-url-is-in-a-suspicious-email-message"></a>URL 是中的可疑的電子郵件

URL 是看起來類似會被視為可疑的其他電子郵件的電子郵件中。 我們建議您仔細檢查繼續進行站台的電子郵件。

![此 URL 是中的可疑的電子郵件](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="a-url-is-in-a-message-identified-as-a-phishing-attempt"></a>URL 是在郵件被識別為網路釣魚嘗試

URL 是已被識別為網路釣魚攻擊的電子郵件中。 因此，會封鎖電子郵件訊息中的所有 Url。 我們建議您不要不繼續進行站台。

![此 URL 會被識別為網路釣魚嘗試在郵件中](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="a-site-has-been-identified-as-malicious"></a>已識別為惡意的網站

URL 會指向已識別為惡意的網站。  <br/> 我們建議您不要不繼續進行站台。

![此網站已識別為惡意](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="a-site-is-blocked"></a>封鎖網站

URL 會封鎖您的組織。 有幾個理由為什麼 URL 可能被封鎖。 我們建議您連絡貴組織的 Office 365 系統管理員。

![網站已遭封鎖](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="an-error-has-occurred"></a>發生的錯誤

發生某種錯誤，且無法開啟 URL。

![發生的錯誤](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

## <a name="recent-updates-to-warning-pages"></a>新版更新至警告頁面

數個警告頁面最近已更新的 Office 365 ATP。 如果您還沒看到 [更新] 頁面，您將會推出。 更新加入新的色彩配置、 詳細資訊，並繼續進行至網站，而不管給定的警告和建議的能力。

### <a name="url-scan-in-progress"></a>進行中的 URL 掃描

原始的警告] 頁面上：

![原始的警告] 頁面上有關進行中的 URL 掃描](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

更新的警告] 頁面上：

![ATP 會掃描的連結](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="malicious-site-warning"></a>惡意網站警告

原始的警告] 頁面上：

![原始的警告] 頁面上關於惡意的網站](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

更新的警告] 頁面上：

![此網站已識別為惡意](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="blocked-url-warning"></a>封鎖 URL 警告

原始的警告] 頁面上：

![封鎖 URL 相關的原始警告頁面](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

更新的警告] 頁面上：

![網站已遭封鎖](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="error-occurred-warning-page"></a>「 發生錯誤 」 警告頁面

原始的警告] 頁面上：

![原始 「 發生錯誤 」 警告頁面](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)

更新的警告] 頁面上：

![發生的錯誤](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)
   
