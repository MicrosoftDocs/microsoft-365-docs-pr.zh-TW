---
title: 參照原則、 實務和指導方針
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft 開發各種原則、 程序，而且採用的許多業界最佳作法來協助保護我們的使用者沒有不當、 不想要或惡意電子郵件。
ms.openlocfilehash: 0957e34008f4e05693218970c458656d73d9c0fe
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031808"
---
# <a name="reference-policies-practices-and-guidelines"></a>參考：原則、實務與指導方針

Microsoft 致力於協助在 web 上提供的最受信任的使用者經驗。 因此，Microsoft 已開發各種原則、 程序，並採用的許多業界最佳作法來協助保護我們的使用者沒有不當、 不想要或惡意電子郵件。 寄件者嘗試傳送電子郵件給 Office 365 使用者應確保在完全了解並追蹤中用於協助進行這項工作，並可協助避免潛在傳遞問題這篇文章的指引。

如果您不符合這些原則和指導方針，它可能無法讓我們支援小組，以協助您。 如果您遵守指導方針、 實務，及本文所述的原則，仍遇到您傳送的 IP 位址為基礎的傳遞問題，請遵循的步驟來提交取消列出的要求。 如需相關指示，請參閱[使用取消列出入口網站將您自己從 Office 365 封鎖寄件者清單移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。

## <a name="general-microsoft-policies"></a>一般 Microsoft 原則

電子郵件傳送到 Office 365 使用者必須遵守所有 Microsoft 管理電子郵件傳輸，並使用 Office 365。

- 適用於 Office 365; 服務中的條款特別是針對垃圾郵件或散發惡意程式碼使用服務禁止

- [Microsoft 服務合約](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>政府法規

電子郵件傳送到 Office 365 使用者必須遵守所有適用的法律或法規控管自己適用管轄中的電子郵件通訊。

- [可以垃圾郵件法案： 合規性指南 for Business](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [ 移除我 」 回應及責任： 電子郵件上月必須受限於 「 取消訂閱 」 宣告](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>技術指導方針

電子郵件傳送到 Office 365 應遵守下列文件中所列 （某些連結會僅提供英文版） 的適用建議。

- [SMTP Mta RFC 2505： 反垃圾郵件建議](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP 服務延伸模組的管線命令](https://www.ietf.org/rfc/rfc2920.txt)

此外，連線至 Office 365 的電子郵件伺服器必須遵守下列需求：

- 寄件者預期會遵守所有技術的標準的網際網路電子郵件傳輸為發佈的網際網路協會的網際網路工程任務推動小組 (IETF)，包括 RFC 5321、 RFC 5322 和其他人。

- 指定 500 和 599 （也就是永久性的未傳遞回應或 NDR） 之間數值 SMTP 錯誤回應程式碼之後，寄件者必須不嘗試重新傳送郵件給該收件者。

- 多個未傳遞回應後，寄件者必須停止嘗試再次傳送電子郵件給該收件者。

- 郵件必須不是透過安全電子郵件轉送或 proxy 伺服器會傳輸。

- 清楚記載又簡單的收件者尋找和使用，必須取消訂閱，可以從個別清單] 或 [寄件者，所主控的所有清單的機制。

- 可能不會接受來自動態 IP 空間的連線。

- 電子郵件伺服器必須具有有效的反向 DNS 記錄。

## <a name="reputation-management"></a>信譽管理

寄件者、 ISP，以及其他服務提供者應積極管理您的輸出 IP 位址的信譽。

## <a name="office-365-limits"></a>Office 365 限制

寄件者必須遵守至[Exchange Online Protection 限制](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)中所列的 Office 365 限制。

## <a name="email-delivery-resources-and-organizations"></a>電子郵件傳遞資源和組織

Microsoft 主動產業主體與服務提供者運作，以改善網際網路和電子郵件生態系統。 這些組織已發佈的我們支援與建議寄件者都要遵循最佳作法是文件。 這樣可以改善您將多個電子郵件服務提供者之間的電子郵件傳送世界各地的能力。

- [郵件的惡意程式碼行動裝置反不當使用工作群組](https://www.m3aawg.org/)

- [線上信任的同盟關係](https://www.otalliance.org/resources)

- [寄件者的電子郵件&amp;提供者聯盟](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>濫用和垃圾郵件報告

報告非法、 粗俗、 不想要或惡意電子郵件，請[垃圾郵件和網路釣魚詐騙網頁型 Outlook 中的報表](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。 傳送這些類型的通訊是的 Microsoft 原則違規情形，並確認報表上會採取適當動作。

## <a name="law-enforcement"></a>執法機構

如果您是執法機構的成員，而且想要提供有關 Office 365 的法律文件與 Microsoft Corporation 或您如有疑問有關法律文件已提交給 Microsoft，請呼叫 (1) (425) 722-1299。
