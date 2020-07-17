---
title: ATP 安全附件的運作方式
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何使用 Office 365 的 ATP 安全附件，讓組織安全地抵禦惡意檔。
ms.openlocfilehash: f4f355d4def1f108a72854c3796e0e9373cb5ef1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819397"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="0cc90-103">ATP 安全附件的運作方式</span><span class="sxs-lookup"><span data-stu-id="0cc90-103">How ATP Safe Attachments works</span></span>

<span data-ttu-id="0cc90-104">ATP 安全附件功能會檢查電子郵件附件中組織的人員。</span><span class="sxs-lookup"><span data-stu-id="0cc90-104">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="0cc90-105">當 ATP 安全附件原則已到位，且該原則所涵蓋的人員會在 Office 365 中查看其電子郵件時，會根據您的 ATP 安全附件原則，檢查其電子郵件附件並採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="0cc90-105">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="0cc90-106">根據您的原則定義方式，使用者可以繼續運作，而不會知道他們已傳送惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="0cc90-106">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="0cc90-107">以下是工作中 ATP 安全附件的兩個範例。</span><span class="sxs-lookup"><span data-stu-id="0cc90-107">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="0cc90-108">**範例1：電子郵件附件**假設您收到一封具有附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0cc90-108">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="0cc90-109">不管附件是安全還是實際包含惡意程式碼，以竊取使用者的認證，並不容易。</span><span class="sxs-lookup"><span data-stu-id="0cc90-109">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="0cc90-110">在「公司管理員」中，安全性管理員會在幾天前定義 ATP 安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="0cc90-110">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="0cc90-111">透過 ATP 安全附件功能，電子郵件附件會在虛擬環境中開啟並測試，然後才會收到該附件。</span><span class="sxs-lookup"><span data-stu-id="0cc90-111">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="0cc90-112">如果附件決定為惡意的，將會自動移除它。</span><span class="sxs-lookup"><span data-stu-id="0cc90-112">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="0cc90-113">如果附件是安全的，當您按一下該附件時，它會如預期的方式開啟。</span><span class="sxs-lookup"><span data-stu-id="0cc90-113">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="0cc90-114">**範例2：線上 SharePoint 中的**檔案假設 Jean-francois 收到檔案，並將其上傳至 SharePoint Online 中的文件庫。</span><span class="sxs-lookup"><span data-stu-id="0cc90-114">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="0cc90-115">Jean-francois 與小組的其餘部分共用檔案的連結，而不知道該檔案實際上是惡意的。</span><span class="sxs-lookup"><span data-stu-id="0cc90-115">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="0cc90-116">幸運的是， [SharePoint、OneDrive 和 Microsoft 團隊的 ATP](atp-for-spo-odb-and-teams.md)會偵測惡意檔，並加以封鎖。</span><span class="sxs-lookup"><span data-stu-id="0cc90-116">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="0cc90-117">幾天後，Chris 會開啟檔。</span><span class="sxs-lookup"><span data-stu-id="0cc90-117">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="0cc90-118">雖然 Chris 可以看見該檔案，Chris 卻無法開啟或分享它，可保護 Chris 的電腦和其他惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="0cc90-118">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="0cc90-119">ATP 安全附件原則可以套用到組織中的特定人員或群組，或套用至整個網域。</span><span class="sxs-lookup"><span data-stu-id="0cc90-119">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="0cc90-120">此外，ATP 安全附件原則可以設定為在掃描實際附件時使用預留位置附件。</span><span class="sxs-lookup"><span data-stu-id="0cc90-120">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="0cc90-121">若要深入瞭解，請參閱**[在 Office 365 中設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)**。</span><span class="sxs-lookup"><span data-stu-id="0cc90-121">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="0cc90-122">ATP 安全附件掃描會在您的資料所在的相同區域中進行。</span><span class="sxs-lookup"><span data-stu-id="0cc90-122">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="0cc90-123">如需資料中心地理位置的詳細資訊，請參閱[您的資料位於何處？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="0cc90-123">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

