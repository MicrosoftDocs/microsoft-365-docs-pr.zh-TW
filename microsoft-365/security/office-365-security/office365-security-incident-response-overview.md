---
title: 安全性事件回應
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 此解決方案會告訴您，在 Microsoft 365 中最常見的 cybersecurity 攻擊可能如您所述，以及如何回應它們
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65ff75253f45ae2d0f051dafe73c6e665f89827a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203637"
---
# <a name="security-incident-response"></a><span data-ttu-id="f8e0f-103">安全性事件回應</span><span class="sxs-lookup"><span data-stu-id="f8e0f-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f8e0f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="f8e0f-104">**Applies to**</span></span>
- [<span data-ttu-id="f8e0f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f8e0f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f8e0f-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="f8e0f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f8e0f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8e0f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="f8e0f-108">**摘要：** 此解決方案會告訴您 Office 365 中最常見的 cybersecurity 攻擊的指示器為何，如何正確確認任何指定的攻擊，以及如何對其作出回應。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="f8e0f-109">瞭解如何回應 cyberattacks</span><span class="sxs-lookup"><span data-stu-id="f8e0f-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="f8e0f-110">並非所有 cyberattacks 都可以 thwarted。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="f8e0f-111">攻擊者不斷尋找防禦策略中的新弱點，或利用舊弱點。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="f8e0f-112">瞭解如何辨識攻擊可讓您更快速地回應，進而縮短安全性事件的持續時間。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="f8e0f-113">這一系列的文章可協助您瞭解哪些特定類型的攻擊在 Microsoft 365 中看起來可能如您所示，並提供您可以採取回應的步驟。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="f8e0f-114">它們是瞭解的快速入門知識：</span><span class="sxs-lookup"><span data-stu-id="f8e0f-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="f8e0f-115">攻擊的含義及其運作方式。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="f8e0f-116"> (IOC) 中的標誌（稱為「損損」），以尋找及如何尋找這些標記。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="f8e0f-117">如何正確確認攻擊。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="f8e0f-118">要採取的步驟來剪下攻擊，並更好地保護您的組織今後的組織。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="f8e0f-119">每個攻擊類型的深入資訊連結。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="f8e0f-120">每月查看一次，隨著時間的增加將新增文章。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="f8e0f-121">偵測和修正文章</span><span class="sxs-lookup"><span data-stu-id="f8e0f-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="f8e0f-122">偵測並修復 Office 365 中的非法同意授權</span><span class="sxs-lookup"><span data-stu-id="f8e0f-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="f8e0f-123">偵測並修復 Office 365 中 Outlook 規則與自訂表單資料隱碼攻擊</span><span class="sxs-lookup"><span data-stu-id="f8e0f-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="f8e0f-124">事件回應文章</span><span class="sxs-lookup"><span data-stu-id="f8e0f-124">Incident response articles</span></span>

- [<span data-ttu-id="f8e0f-125">對於 Office 365 遭入侵電子郵件帳戶的回覆</span><span class="sxs-lookup"><span data-stu-id="f8e0f-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="f8e0f-126">像網路安全專業人員一般保護 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8e0f-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="f8e0f-127">您的 Microsoft 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="f8e0f-128">使用 [microsoft 365 安全性藍圖-前30天、90天和之後的最高優先順序](security-roadmap.md) ，以執行 microsoft 建議的最佳作法，以保護您的 microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="f8e0f-129">要在前 30 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="f8e0f-130">這些工作會有立即的影響，而且對您的使用者影響較低。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="f8e0f-131">要在 90 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="f8e0f-132">需要更多時間來規劃及實施，但能大幅改善您的安全性狀況</span><span class="sxs-lookup"><span data-stu-id="f8e0f-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="f8e0f-133">90 天之後。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-133">Beyond 90 days.</span></span> <span data-ttu-id="f8e0f-134">這些增強功能會在您的前 90 天工作內建置。</span><span class="sxs-lookup"><span data-stu-id="f8e0f-134">These enhancements build in your first 90 days work.</span></span>
