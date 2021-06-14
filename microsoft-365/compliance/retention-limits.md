---
title: 保留原則和保留標籤原則的限制
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: 瞭解針對保留原則及保留標籤原則，每個原則的原則和專案數量上限。
ms.openlocfilehash: 92647911cfc3435c2d88ce5caa0624a34467a60f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908098"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>保留原則和保留標籤原則的限制

>*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

當您使用 [保留原則及保留標籤原則](retention.md#retention-policies-and-retention-labels) 以自動保留或刪除貴組織的資料時，有一些您需要注意的最大值。

## <a name="maximum-number-of-policies-per-tenant"></a>每個租用戶的原則數量上限

單一租用戶最多可以有10,000個原則 (任何設定)。 這個最大值包括保留的不同原則和其他合規性原則，例如 DLP 原則、資訊屏障、eDiscovery 保留和敏感度標籤。

在此 10，000 個原則限制內，每個工作負載的保留原則數量上限也有一些限制：

- Exchange (任何設定)：1,800
- SharePoint 或 OneDrive：(自動包含所有網站)：13
- SharePoint 或 OneDrive (包含或排除的特定位置)：2,600

雖然 Microsoft Teams 和 Yammer 的保留原則會使用信箱來儲存資料以用於保留目的，但 Exchange Online 的保留原則數目上限會排除 Teams 和 Yammer 的保留原則。

## <a name="maximum-number-of-items-per-policy"></a>每個原則的專案數量上限

當您使用選用設定將保留設定限定為特定使用者、特定 Microsoft 365 群組或特定網站時，需要注意根據原則而異的限制： 

每個原則保留的專案數量上限：

- Exchange 信箱：1,000
- Microsoft 365 群組：1,000
- Teams 通道訊息：1,000
- Teams 聊天：1,000
- Yammer 社群訊息：1,000
- Yammer 使用者訊息：1,000
- SharePoint 網站：100
- OneDrive 帳戶：100

商務用 Skype 的範圍必須針對特定使用者，且每個原則支援的最大數目為 1,000。

因為這些限制根據原則而異，因此如果您需要使用會導致超出這些數字的特定包含或排除，您可以建立具有相同保留設定的額外原則。 請參閱下一節中因此項緣由而使用多個保留原則的部分 [案例和解決方案](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers)。

然而，多個原則會造成更高的系統管理費用，因此請隨時確認是否確實需要包含與排除。 請記住，套用到整個位置的預設設定並沒有任何限制，且此設定選項可能是比建立及維護多個原則更好的解決方案。

> [!TIP]
> 如果您需要針對此情況，建立並維護多個原則，請考慮使用 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) ，以進行更有效率的設定。

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>使用多個原則來避免超過數量上限的範例

下列範例提供一些設計解決方案，適用於當您無法只指定保留原則的位置，且必須考慮上一節中所述的專案數量上限的情況。

Exchange 範例：

- **需求**：在具有超過 40,000 個使用者信箱的組織中，大部分的使用者都必須將其電子郵件保留 7 年，但是子集的已識別使用者 (425) 的電子郵件只能保留 5 年。

- **解決方案**：為 Exchange 電子郵件建立一份保留原則，保留期間為 7 年，並排除使用者子集。 然後，為 Exchange 電子郵件建立第二份保留原則，保留期間為 5 年，並包含使用者子集。 
    
    在這兩種情況下，包含和排除的數字皆低於單一原則指定信箱的上限，且使用者的子集必須明確排除于第一個原則之外，因為其 [保留期間](retention.md#the-principles-of-retention-or-what-takes-precedence) 較第二個原則要長。 如果使用者的子集需要較長的保留原則，則不需要將之從第一個原則中排除。
     
    使用這個解決方案，如果有其他人加入該組織，則其信箱會自動包含在第一個原則中 7 年限制，且不會影響支援的上限。 不過，要求 5 年保留期間的新使用者會被納入包含和排除的限制數目，則此限制將超出 1,000。

SharePoint 範例：

- **需求**：一個組織擁有數千個 SharePoint 網站，但只有 2,000 個網站需要 10 年的保留期間，和 8,000 個需要 4 年保留期間的網站。

- **解決方案**：建立 20 個 SharePoint 保留原則，保留期間為 10 年，其中包括 100 個特定網站，並建立 80個 SharePoint 保留原則，保留期間為 4 年，其中包含 100 個特定網站。
    
    因為您不需要保留所有的 SharePoint 網站，您必須建立指定特定網站的保留原則。 由於保留原則不支援超過 100 個指定的網站，因此您必須針對兩個保留期間建立多個原則。 這些保留原則所包含的網站數量為上限，因此需要保留的下一個新網站不論保留期間都會需要新的保留原則。

## <a name="maximum-number-of-items-for-disposition"></a>要處置的項目數目上限

對於[內容處置](disposition.md)，有一些限制需要注意：

- 每個保留標籤的每個階段有 1，000，000 個項目擱置處置

- 處置項目後最多七年的處置證明，該期間每個保留標籤的限制為 1，000，000 個項目。 
    
如果您需要標示為記錄之項目的處置證明高於此 1，000，000 上限，請連繫 [Microsoft 支援服務](../business-video/get-help-support.md)。
