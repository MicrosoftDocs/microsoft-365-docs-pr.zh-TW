---
title: 參考原則、作法和指導方針
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft 已開發各種原則、程式，並採用數種行業最佳作法，協助保護我們的使用者免受濫用、有害或惡意的電子郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8ed78e4a0f233e8d04fbcfb7d7fa7b3859bc0e17
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925229"
---
# <a name="reference-policies-practices-and-guidelines"></a>參考：原則、實務與指導方針

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 致力於協助提供最受信任的使用者在網頁上的體驗。 因此，Microsoft 已開發各種原則、程式，並採用數種行業最佳作法，協助保護我們的使用者免受濫用、有害或惡意的電子郵件。 嘗試將電子郵件傳送給使用者的寄件者應確保他們完全瞭解並遵循本文中的指導方針，以協助您進行此工作，並協助避免潛在的傳遞問題。

如果您不遵循這些原則和指導方針，我們的支援小組可能無法協助您。 如果您遵循本文所述的指導方針、作法和原則，而且仍然會根據您傳送的 IP 位址，而遇到傳送問題，請依照下列步驟提交取消列出要求。 如需相關指示，請參閱 [使用取消列出入口網站將您自己從封鎖的寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。

## <a name="general-microsoft-policies"></a>一般 Microsoft 原則

傳送給 Microsoft 365 使用者的電子郵件必須遵守所有管理電子郵件傳輸和使用 Microsoft 365 的 Microsoft 原則。

- 適用于 Microsoft 365 的服務條款;特別是，禁止使用服務來垃圾郵件或散佈惡意程式碼。

- [Microsoft 服務合約](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>政府法規

傳送給 Microsoft 365 使用者的電子郵件，必須遵守所有適用司法轄區中的電子郵件通訊的法律和規定。

- [CAN-垃圾郵件法案：商務規範指南](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [「移除我的回應和責任：電子郵件行銷人員必須服從「取消訂閱」宣告](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>技術指導方針

傳送至 Microsoft 365 的電子郵件應該遵循下列檔中列出的適當建議 (某些連結只會以英文) 提供。

- [RFC 2505： SMTP Mta 的 Anti-Spam 建議](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920：命令流水線作業的 SMTP 服務擴充](https://www.ietf.org/rfc/rfc2920.txt)

此外，連接至 Microsoft 365 的電子郵件伺服器必須符合下列需求：

- 寄件者預計會遵守網際網路電子郵件傳輸的所有技術標準，如網際網路社會的網際網路工程工作力量 (IETF) （包括 RFC 5321、RFC 5322 及其他）所發佈。

- 在500和599之間的數位 SMTP 錯誤回應碼 (（也稱為永久未傳遞回應或 NDR) ）之後，寄件者不得嘗試將該郵件重新傳輸給該收件者。

- 在多個未傳遞回應後，寄件者必須停止進一步嘗試將電子郵件傳送給該收件者。

- 郵件不得透過不安全的電子郵件轉送或 proxy 伺服器來傳送。

- 從個別清單或寄件者所主控的所有清單中，退訂的機制，都必須清楚地加以記錄，且可讓收件者輕易找到及使用。

- 可能無法接受來自動態 IP 空間的連線。

- 電子郵件伺服器必須具有有效的反向 DNS 記錄。

## <a name="reputation-management"></a>信譽管理

寄件者、ISP 及其他服務提供者應該主動管理輸出 IP 位址的信譽。

## <a name="microsoft-365-limits"></a>Microsoft 365 限制

寄件者必須遵守 [Exchange Online Protection 限制](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)中所列的 Microsoft 365 限制。

## <a name="email-delivery-resources-and-organizations"></a>電子郵件傳遞資源和組織

Microsoft 主動與業界主體和服務提供者合作，以改善網際網路和電子郵件生態系統。 這些組織已發佈最佳作法檔，我們支援並建議寄件者遵循。 這會提升您在世界各地的幾個電子郵件服務提供者之間傳送電子郵件的能力。

- [郵件惡意程式碼動裝置的反濫用運作群組](https://www.m3aawg.org/)

- [線上信任同盟](https://www.internetsociety.org/ota/)

- [電子郵件寄件者 & 提供者聯盟](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>濫用和垃圾郵件報告

若要報告非法、濫用、有害或惡意的電子郵件，請參閱 [將郵件和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。 傳送這些類型的通訊會違反 Microsoft 原則，並對已確認的報告採取適當的動作。

## <a name="law-enforcement"></a>執法

如果您是法律強制執行的成員，且想要為 Microsoft Corporation 提供 Office 365 的法律檔，請致電 (1)  (425) 722-1299。