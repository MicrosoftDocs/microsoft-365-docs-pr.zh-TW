---
title: 在 Outlook 中報告 iOS 和 Android 的垃圾郵件和網路釣魚電子郵件
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 系統管理員可以深入瞭解 Outlook 中內建的垃圾郵件、非垃圾郵件和網路釣魚電子郵件報告選項，以供 iOS 和 Android。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6e63f534a9f9516c6e1a87ff82d5b0916d25778
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509323"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>在適用于 Exchange Online 的 iOS 和 Android 的 Outlook 中報告垃圾郵件和網路釣魚電子郵件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在使用 [混合式新式驗證](../../enterprise/hybrid-modern-auth-overview.md)的 Exchange online 或內部部署信箱中具有信箱的 Microsoft 365 組織中，您可以提交誤報 (已標示為垃圾郵件的適當電子郵件) 、false 不利 (允許的電子郵件) ，以及網路釣魚郵件至 Exchange Online PROTECTION (EOP) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前，您必須瞭解哪些事項

- 為了獲得最佳的使用者提交經驗，我們建議使用報告訊息和報告網路釣魚增益集。請參閱 [enable The Report Message 增益集](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) 及 [啟用報告網路釣魚增益集](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) 以取得詳細資訊。

- 如果您是 Exchange Online 信箱組織中的系統管理員，建議您在安全性 & 規範中心內使用提交入口網站。 如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。

- 您可以設定報告的郵件以複製或重新導向至您指定的信箱。 如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。

- 如需將郵件報告給 Microsoft 的詳細資訊，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。

  > [!NOTE]
  > 如果在使用者提交原則中停用 Outlook 的垃圾郵件報告，則垃圾郵件或網路釣魚郵件會移至 [垃圾郵件] 資料夾，而不會向您的系統管理員或 Microsoft 報告。
