---
title: 封存第三方資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何將「社交媒體平臺」、「立即訊息平臺」及「檔共同作業平臺」的協力廠商資料匯入至 Microsoft 365 信箱。
ms.openlocfilehash: 0db7019b607388b7c62fe19210b85b8410083f32
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035481"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="69ac3-103">封存第三方資料</span><span class="sxs-lookup"><span data-stu-id="69ac3-103">Archive third-party data</span></span>

<span data-ttu-id="69ac3-104">Microsoft 365 可讓系統管理員從社交媒體平臺、立即訊息平臺及檔共同作業平臺，將協力廠商資料匯入並封存至您的 Microsoft 365 組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="69ac3-104">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="69ac3-105">您可以匯入 Microsoft 365 的協力廠商資料來源範例包含下列服務：</span><span class="sxs-lookup"><span data-stu-id="69ac3-105">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="69ac3-106">**社交：** Facebook、LinkedIn、Twitter 和 Yammer</span><span class="sxs-lookup"><span data-stu-id="69ac3-106">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="69ac3-107">**立即訊息：** Yahoo Messenger 和 GoogleTalk</span><span class="sxs-lookup"><span data-stu-id="69ac3-107">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="69ac3-108">**檔**共同作業：Box 及 DropBox</span><span class="sxs-lookup"><span data-stu-id="69ac3-108">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="69ac3-109">**垂直行業：** 客戶關係管理（例如 Salesforce 交談）和金融服務（例如 Bloomberg 和 Thomson Reuters）</span><span class="sxs-lookup"><span data-stu-id="69ac3-109">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="69ac3-110">**短信/文字訊息：** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="69ac3-110">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="69ac3-111">匯入協力廠商資料後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、eDiscovery、In-Place 封存、審核、通訊法規遵從性及保留原則）套用至此資料。</span><span class="sxs-lookup"><span data-stu-id="69ac3-111">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="69ac3-112">例如，當信箱處於訴訟暫止狀態時，會保留協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="69ac3-112">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="69ac3-113">您可以使用 Microsoft eDiscovery 工具來搜尋協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="69ac3-113">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="69ac3-114">或者，您可以將封存和保留原則套用至協力廠商資料，就像您可以使用 Microsoft 資料一樣。</span><span class="sxs-lookup"><span data-stu-id="69ac3-114">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="69ac3-115">簡而言之，封存 Microsoft 365 中的協力廠商資料可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="69ac3-115">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="69ac3-116">有兩種方法可匯入及封存 Microsoft 365 中的協力廠商資料：</span><span class="sxs-lookup"><span data-stu-id="69ac3-116">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="69ac3-117">**在安全性 & 規範中心使用協力廠商資料連線器：** 使用 Microsoft 365 規範中心提供的自訂資料連線器。</span><span class="sxs-lookup"><span data-stu-id="69ac3-117">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="69ac3-118">在您設定及設定連接器之後，它會連線至協力廠商資料來源、將專案內容轉換為電子郵件訊息格式，然後將該專案匯入 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="69ac3-118">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="69ac3-119">目前，您可以從 Facebook 商務頁面、公司 Twitter 帳戶、LinkedIn、立即 Bloomberg 及組織的人力資源（HR）資料中，執行連接器以匯入及封存資料。</span><span class="sxs-lookup"><span data-stu-id="69ac3-119">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="69ac3-120">如需設定這些連接器之一的逐步指示，請參閱：</span><span class="sxs-lookup"><span data-stu-id="69ac3-120">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="69ac3-121">**Facebook：** [使用連接器封存 Facebook 資料](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="69ac3-121">**Facebook:** [Use a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="69ac3-122">**Twitter：** [使用連接器封存 Twitter 資料](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="69ac3-122">**Twitter:** [Use a connector to archive Twitter data](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="69ac3-123">**LinkedIn：** [設定連接器以封存 LinkedIn 資料](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="69ac3-123">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="69ac3-124">**立即 Bloomberg：** [設定連接器以封存立即 Bloomberg 資料](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="69ac3-124">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="69ac3-125">**人力資源資料：** [設定連接器以匯入 HR 資料](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="69ac3-125">**HR data:** [Set up a connector to import HR data](import-hr-data.md)</span></span>

- <span data-ttu-id="69ac3-126">**與 Microsoft Partner 搭配使用：** 您的組織與 Microsoft 合作夥伴合作，其提供自訂連接器，該連接器會設定為定期解壓縮協力廠商資料來源中的專案，然後以協力廠商 API 連線至 Microsoft 雲端，並將這些專案匯入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="69ac3-126">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="69ac3-127">夥伴連接器也會將專案的內容從協力廠商資料來源轉換成電子郵件，然後將其匯入 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="69ac3-127">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="69ac3-128">如需您可以使用的合作夥伴清單及此方法的逐步程式，請參閱在[Microsoft 365 中封存協力廠商資料](work-with-partner-to-archive-third-party-data.md)的合作。</span><span class="sxs-lookup"><span data-stu-id="69ac3-128">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
