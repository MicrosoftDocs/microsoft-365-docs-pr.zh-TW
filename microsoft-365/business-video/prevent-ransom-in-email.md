---
title: 針對勒索軟體建立電子郵件規則
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何建立電子郵件規則，以防止勒索軟體。
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580495"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="a5076-103">建立電子郵件規則以防止勒索軟體</span><span class="sxs-lookup"><span data-stu-id="a5076-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="a5076-104">Microsoft 365 會防止在 Outlook 中開啟可能有害的檔案（如 JavaScript、批次及可執行檔），以協助保護您的企業抵禦勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="a5076-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="a5076-105">若要增加這種保護層級，您可以新增封鎖或警告您其他檔案類型的規則，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="a5076-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="a5076-106">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="a5076-106">Try it!</span></span>

1. <span data-ttu-id="a5076-107">在系統管理中心，選擇 [系統管理中心] 底下的 [ [https://admin.microsoft.com](https://admin.microsoft.com) **Exchange** ]。 </span><span class="sxs-lookup"><span data-stu-id="a5076-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="a5076-108">從左側的功能表中，選擇 [ **郵件流程**]。</span><span class="sxs-lookup"><span data-stu-id="a5076-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="a5076-109">在 [規則] 索引標籤上，選擇加號 (+) 符號旁的箭號，然後選擇 [ **建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="a5076-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="a5076-110">在 [ **新增規則** ] 頁面上，輸入規則的名稱，然後滾動至底部，然後選擇 [ **更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="a5076-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="a5076-111">在 [套用 **此規則條件**] 底下，選取 [ **任何附件**]，然後選取 [ **副檔名] 包含這些文字**。</span><span class="sxs-lookup"><span data-stu-id="a5076-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="a5076-112">在 [ **指定文字或片語**] 底下的方塊中，輸入您要套用規則的副檔名，例如可以包含宏的副檔名。</span><span class="sxs-lookup"><span data-stu-id="a5076-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="a5076-113">使用 plus (+) 符號，一次新增一個。</span><span class="sxs-lookup"><span data-stu-id="a5076-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="a5076-114">閱讀 [針對勒索軟體的保護](../admin/security-and-compliance/secure-your-business-data.md#ransomware)，深入瞭解檔案類型。</span><span class="sxs-lookup"><span data-stu-id="a5076-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="a5076-115">向下滾動以查看清單，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a5076-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="a5076-116">在 [ **新增規則** ] 頁面上，選擇 [新增 **條件**]，然後選擇 [ **執行下列** 動作] 下的條件。</span><span class="sxs-lookup"><span data-stu-id="a5076-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="a5076-117">您有許多規則選項可供選擇，但在此範例中，我們會選擇以 **郵件通知收件** 者。</span><span class="sxs-lookup"><span data-stu-id="a5076-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="a5076-118">輸入通知的訊息文字，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a5076-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="a5076-119">選用：在 [ **新增規則** ] 頁面上，選擇 [新增 **例外** 狀況]，然後輸入規則例外狀況的任何詳細資料，例如來自信任寄件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="a5076-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="a5076-120">在 [新增規則] 頁面上，選擇 [ **儲存**]，並複查所提供的規則摘要資訊。</span><span class="sxs-lookup"><span data-stu-id="a5076-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>