---
title: 將郵件傳送至 Microsoft 365 的非客戶服務
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 為了協助維護使用者對電子郵件使用的信任，Microsoft 將各種原則和技術放在一起，以協助保護我們的使用者。
ms.openlocfilehash: 3a3dc26d757de84f5abd46c85f3596db67d676ae
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208231"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>將郵件傳送至 Microsoft 365 的非客戶服務

電子郵件濫用、垃圾郵件和欺詐電子郵件（網路釣魚）都會繼續負擔整個電子郵件生態系統。 為了協助維護使用者對電子郵件使用的信任，Microsoft 將各種原則和技術放在適當位置，以協助保護我們的使用者。 不過，Microsoft 知道合法的電子郵件不會受到不良影響。 因此，我們已建立一套服務，以協助寄件者透過主動管理其傳送信譽，以提升電子郵件傳送至 Microsoft 365 使用者的能力。

此概述提供我們為您的組織提供的效益資訊，即使您不是客戶也是如此。

## <a name="sender-solutions"></a>寄件者方案

|**Service** (服務)|**效益**|
|:-----|:-----|
|這個線上說明內容|提供： <br/> 與提供與 EOP 使用者通訊相關之任何問題的起點。 <br/><br/> 包含與我們的原則及需求有關的簡易線上指南。 <br/><br/> Microsoft 所採用的垃圾郵件篩選器和驗證技術的概述。|
|[Microsoft 支援](#microsoft-support)|提供傳送問題的自我協助和上報支援。|
|[Anti-Spam IP 取消列出入口網站](#anti-spam-ip-delist-portal)|用於提交 IP 取消列出要求的工具。 在提交此要求之前，寄件者的責任是確保任何來自于問題的 IP 的後續郵件都不會遭到濫用或惡意。|
|[來自 Exchange Online 的垃圾郵件的濫用和垃圾郵件報告](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|讓垃圾郵件和其他有害的郵件無法從 Exchange Online 傳送，並打亂網際網路和您的郵件系統。|

## <a name="microsoft-support"></a>Microsoft 支援

Microsoft 提供數種支援選項，讓使用者在傳送郵件給 Microsoft 365 收件者時遇到問題。 我們建議您：

- 遵循您收到的任何未傳遞回報中的指示進行。

- 查看[對傳送至 Office 365 的郵件進行疑難排解](troubleshooting-mail-sent-to-office-365.md)時，最常遇到的問題。

- 使用[Microsoft 365 取消列出入口網站](https://sender.office.com)提交要求從封鎖的寄件者清單中移除您的 IP 的要求。

- 閱讀[Microsoft 社區論壇](https://community.office365.com/f/)。

- 請聯繫您嘗試使用另一種方法傳送電子郵件的客戶，並要求他們聯繫 Microsoft 支援服務，並代表您開啟支援票證。 在某些情況下，由於法律原因，Microsoft 支援必須直接與擁有被封鎖之 IP 空間的寄件者直接通訊。 不過，非客戶通常無法開啟支援票證。

  如需 Microsoft 技術支援 Office 365 的詳細資訊，請參閱[support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)。

## <a name="anti-spam-ip-delist-portal"></a>Anti-Spam IP 取消列出入口網站

這是自助服務入口網站，您可以用來將自己從 Microsoft 365 封鎖的寄件者清單中移除。 如果您在嘗試將電子郵件傳送給其電子郵件地址是 Microsoft 365 的收件者時收到錯誤訊息，且您不想要，請使用此入口網站。 如需詳細資訊，請參閱[使用取消列出入口網站將您自己從封鎖的寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>來自 Exchange Online 的垃圾郵件的濫用和垃圾郵件報告

Microsoft365 是協力廠商使用，以傳送垃圾郵件，違反我們的使用條款和原則。 如果您收到來自 Office 365 的任何垃圾郵件，您可以將這些郵件報告給 Microsoft。 如需相關指示，請參閱[將訊息和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。
