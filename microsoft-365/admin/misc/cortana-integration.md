---
title: 與 Office 365 進行 Cortana 整合
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: '了解如何使用 Cortana，它與 Office 365 整合時。 您可以關閉 Cortana 在系統管理中心來限制其存取貴組織的資料。 '
ms.openlocfilehash: 21de80d127498dd40db932923a8d650b87b8a24c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254341"
---
# <a name="cortana-in-office-365"></a><span data-ttu-id="00048-104">Office 365 中的 Cortana</span><span class="sxs-lookup"><span data-stu-id="00048-104">Cortana in Office 365</span></span>

<span data-ttu-id="00048-105">Cortana 是雲端式數位小幫手] 和 [適用於您裝置上的 Microsoft 365 和 Office 365 服務和 Microsoft 服務。</span><span class="sxs-lookup"><span data-stu-id="00048-105">Cortana is a cloud-based digital assistant and Microsoft 365 and Office 365 service that works across your devices and Microsoft services.</span></span> <span data-ttu-id="00048-106">Cortana 可以使用 Microsoft 365 和 Office 365 中儲存的資訊可協助您組織中的人員以保持最新取得深入資訊、 建議的工作，並協助他們的會議、 文件，與連絡人。</span><span class="sxs-lookup"><span data-stu-id="00048-106">Cortana can use information stored in Microsoft 365 and Office 365 to help people in your organization stay up to date and get insights, suggested tasks, and help with their meetings, documents, and contacts.</span></span>
  
## <a name="info-for-admins"></a><span data-ttu-id="00048-107">管理員適用資訊</span><span class="sxs-lookup"><span data-stu-id="00048-107">Info for admins</span></span>

<span data-ttu-id="00048-108">合規性是 Microsoft 對企業客戶的承諾。</span><span class="sxs-lookup"><span data-stu-id="00048-108">Compliance is a commitment that Microsoft makes to enterprise customers.</span></span> [<span data-ttu-id="00048-109">深入了解 Microsoft 合規性架構。</span><span class="sxs-lookup"><span data-stu-id="00048-109">Learn more about the Microsoft compliance framework.</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=2109173)

<span data-ttu-id="00048-110">與其他 Microsoft 365 和 Office 365 相容 Cortana 功能是受保護，並包含一組 promise 涉及意外遺失、 被變更，對使用者資料的保護線上服務條款受到保護服務、 一致未經授權的外洩的存取或非法毀損。</span><span class="sxs-lookup"><span data-stu-id="00048-110">Consistent with other Microsoft 365 and Office 365 services, compliant Cortana features are protected and secured subject to the Online Service Terms that includes a set of promises involving protection of user data against accidental loss, alteration, unauthorized disclosure or access, or unlawful destruction.</span></span> <span data-ttu-id="00048-111">所有其他 Cortana 功能 （亦即，Cortana 選用連線服務） 會受到[Microsoft 服務合約](https://go.microsoft.com/fwlink/p/?LinkId=2109174)和[Microsoft 隱私權聲明。](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span><span class="sxs-lookup"><span data-stu-id="00048-111">All other Cortana features (i.e., Cortana optional connected services) are subject to the [Microsoft Services Agreement](https://go.microsoft.com/fwlink/p/?LinkId=2109174) and  [Microsoft Privacy Statement.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span></span>

<span data-ttu-id="00048-112">Cortana 服務可分為兩個資料分類**相容**和**選擇性的連線的服務**，而您可以控制。</span><span class="sxs-lookup"><span data-stu-id="00048-112">Cortana services are broken into two data categories, **compliant** and **optional connected services**, which you can control.</span></span>

## <a name="turn-off-cortana-optional-connected-services"></a><span data-ttu-id="00048-113">關閉 Cortana 選用連線服務</span><span class="sxs-lookup"><span data-stu-id="00048-113">Turn off Cortana optional connected services</span></span>

<span data-ttu-id="00048-114">Cortana 選用連線的服務可以關閉在貴組織的員工。</span><span class="sxs-lookup"><span data-stu-id="00048-114">Cortana optional connected services can be turned off for employees at your organization.</span></span> <span data-ttu-id="00048-115">這將會停用 Cortana 選用連線的服務在 Windows 和 Cortana 行動應用程式上的 Cortana。</span><span class="sxs-lookup"><span data-stu-id="00048-115">This will disable Cortana optional connected services in Cortana on Windows and the Cortana mobile app.</span></span> <span data-ttu-id="00048-116">這包括 Cortana 提醒、 清單、 工作及其他功能。</span><span class="sxs-lookup"><span data-stu-id="00048-116">This includes Cortana reminders, lists, tasks, and other features.</span></span> <span data-ttu-id="00048-117">在 [相容] 類別 （亦即，Cortana OST 體驗），例如 Cortana 的簡報的電子郵件與行動裝置，在 Outlook 中播放我電子郵件服務仍可使用。</span><span class="sxs-lookup"><span data-stu-id="00048-117">Services in the compliant category (i.e., Cortana OST experiences), such as Cortana’s Briefing email, and Play My Emails in Outlook mobile, will remain active.</span></span>

1. <span data-ttu-id="00048-118">在 Microsoft 365 系統管理中心中，選取 [**設定** > **設定**並選取 [ **Cortana**。</span><span class="sxs-lookup"><span data-stu-id="00048-118">In the Microsoft 365 admin center, select **Settings** > **Settings** and select **Cortana**.</span></span>

4. <span data-ttu-id="00048-119">選取 [**允許 Cortana 選用連線的經驗來使用貴組織的 Microsoft 主控的資料**來啟用或停用連線的 Cortana 體驗的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="00048-119">Select the checkbox for **Allow Cortana optional connected experiences to use your organizations's Microsoft hosted data** to enable or disable Cortana connected experiences.</span></span>

5. <span data-ttu-id="00048-120">選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="00048-120">Select **Save changes**.</span></span>

## <a name="turn-off-cortana-ost-experiences"></a><span data-ttu-id="00048-121">關閉 Cortana OST 體驗</span><span class="sxs-lookup"><span data-stu-id="00048-121">Turn off Cortana OST experiences</span></span>

<span data-ttu-id="00048-122">貴組織的員工可以選擇退出 Cortana OST 體驗個別遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="00048-122">Your organization's employees can opt out of Cortana OST experiences individually by following the steps below.</span></span>

1. <span data-ttu-id="00048-123">開啟 Outlook mobile。</span><span class="sxs-lookup"><span data-stu-id="00048-123">Open Outlook mobile.</span></span>

2. <span data-ttu-id="00048-124">移至 [**設定**。</span><span class="sxs-lookup"><span data-stu-id="00048-124">Go to **Settings**.</span></span>
  
3. <span data-ttu-id="00048-125">選取 [**播放我的電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="00048-125">Select **Play My Emails**.</span></span>

4. <span data-ttu-id="00048-126">移動將開關切換為 [關閉您想要停用帳戶。</span><span class="sxs-lookup"><span data-stu-id="00048-126">Move the toggle to off on the accounts you want to disable.</span></span>

### <a name="briefing-email"></a><span data-ttu-id="00048-127">簡報電子郵件</span><span class="sxs-lookup"><span data-stu-id="00048-127">Briefing email</span></span>

<span data-ttu-id="00048-128">在工作列上停用 Cortana 不會停用 Cortana 的簡報電子郵件。</span><span class="sxs-lookup"><span data-stu-id="00048-128">Disabling Cortana on the taskbar won't disable Cortana’s Briefing email.</span></span> <span data-ttu-id="00048-129">員工必須個別取消訂閱。</span><span class="sxs-lookup"><span data-stu-id="00048-129">Employees must unsubscribe individually.</span></span> <span data-ttu-id="00048-130">從您的組織的個人可以藉由選取 [頁尾的郵件中的 [**取消訂閱**選擇退出 Cortana 的簡報電子郵件。</span><span class="sxs-lookup"><span data-stu-id="00048-130">Individuals from your organization can opt out of Cortana’s Briefing email by selecting **Unsubscribe** in the footer of the message.</span></span>