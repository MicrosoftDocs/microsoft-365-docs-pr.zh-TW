---
title: Microsoft 365 信箱遷移
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文包含有關 Microsoft 365 信箱遷移的簡短摘要，以及用於遷移的 Cmdlet 清單。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a31eda9c33aa12e4f7c1fe3da4580eba9e1698a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688582"
---
# <a name="microsoft-365-mailbox-migrations"></a><span data-ttu-id="96b38-103">Microsoft 365 信箱遷移</span><span class="sxs-lookup"><span data-stu-id="96b38-103">Microsoft 365 mailbox migrations</span></span>

<span data-ttu-id="96b38-104">透過以 Exchange 為基礎的混合式部署，客戶可以選擇將內部部署 Exchange 信箱移至 [Exchange online](https://docs.microsoft.com/Exchange/exchange-online) 組織，或將 exchange Online 信箱移至 [exchange 內部部署](https://docs.microsoft.com/Exchange/exchange-server) 組織。</span><span class="sxs-lookup"><span data-stu-id="96b38-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="96b38-105">在內部部署和 Exchange Online 組織之間移動信箱時，會使用遷移批次。</span><span class="sxs-lookup"><span data-stu-id="96b38-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span>

<span data-ttu-id="96b38-106">客戶可以使用下列 Cmdlet 來查看信箱遷移的統計資料和其他資訊：</span><span class="sxs-lookup"><span data-stu-id="96b38-106">Customers can review statistics and other information about mailbox migrations with the following cmdlets:</span></span>

- <span data-ttu-id="96b38-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps)：提供使用者信箱的預設統計資料，其中包括狀態、信箱大小、封存信箱大小，以及完成百分比。</span><span class="sxs-lookup"><span data-stu-id="96b38-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps): Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size, and percentage complete.</span></span>
- <span data-ttu-id="96b38-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
)：提供組織中信箱物件及屬性的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="96b38-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
): Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="96b38-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)：提供現有擁有郵件功能的物件清單，例如信箱、郵件使用者、連絡人及通訊群組。</span><span class="sxs-lookup"><span data-stu-id="96b38-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps): Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts, and distribution groups.</span></span>
- <span data-ttu-id="96b38-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps)：提供進行中信箱遷移的詳細狀態。</span><span class="sxs-lookup"><span data-stu-id="96b38-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps): Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="96b38-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps)：提供信箱移動和遷移使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="96b38-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps): Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="96b38-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps)：提供目前遷移批次狀態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="96b38-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps): Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="96b38-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps)：提供特定使用者之遷移狀態的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="96b38-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps): Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="96b38-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps)：提供信箱的相關資訊，例如大小、郵件數目及最後存取時間。</span><span class="sxs-lookup"><span data-stu-id="96b38-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps): Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="96b38-115">如需 Cmdlet 的詳細資訊，請參閱 [Exchange Online 中的移動和遷移 Cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="96b38-115">For more information about cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
