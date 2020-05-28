---
title: 開啟或關閉整合式應用程式
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 深入瞭解整合式應用程式，以及如何將其開啟以允許協力廠商應用程式存取使用者的 Microsoft 365 資訊。
ms.openlocfilehash: 070150662daeefb2a4d02c7e0940dfd242bd4b5f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399335"
---
# <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="17867-103">開啟或關閉整合式應用程式</span><span class="sxs-lookup"><span data-stu-id="17867-103">Turning Integrated Apps on or off</span></span>

<span data-ttu-id="17867-104">啟用整合式應用程式時，您組織中的使用者可以允許協力廠商應用程式存取其 Microsoft 365 資訊。</span><span class="sxs-lookup"><span data-stu-id="17867-104">When Integrated Apps is turned on, users in your organization can allow third-party apps to access their Microsoft 365 information.</span></span> <span data-ttu-id="17867-105">例如，當有人使用協力廠商應用程式時，該應用程式可能會要求行事曆的存取權限，以編輯 OneDrive 資料夾中的檔案。</span><span class="sxs-lookup"><span data-stu-id="17867-105">For example, when someone uses a third-party app, that app might ask for permission to access their calendar and to edit files that are in a OneDrive folder.</span></span>

## <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="17867-106">開啟或關閉整合式應用程式</span><span class="sxs-lookup"><span data-stu-id="17867-106">Turning Integrated Apps on or off</span></span>
<span data-ttu-id="17867-107"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="17867-107"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="17867-108">以下說明如何開啟或關閉整合式應用程式。</span><span class="sxs-lookup"><span data-stu-id="17867-108">Here's how to turn Integrated Apps on or off.</span></span>

1. <span data-ttu-id="17867-109">在 Microsoft 365 系統管理中心中，移至 [**設定**] [設定] 頁面的 [服務] 索引標籤 \> **Settings** \> **Services** ，然後選取 [**整合式應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="17867-109">In the Microsoft 365 admin center, go to the **Settings** \> **Settings** page, \> **Services** tab, and then select **Integrated apps**.</span></span>

2. <span data-ttu-id="17867-110">在 [**整合式應用程式**] 頁面上，選取要開啟或關閉整合式應用程式的選項。</span><span class="sxs-lookup"><span data-stu-id="17867-110">On the **Integrated Apps** page, select the option to turn Integrated Apps on or off.</span></span>

## <a name="more-info-on-integrated-apps"></a><span data-ttu-id="17867-111">更多整合式應用程式的資訊</span><span class="sxs-lookup"><span data-stu-id="17867-111">More info on Integrated Apps</span></span>
<span data-ttu-id="17867-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="17867-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="17867-113">整合式應用程式可以從您自己的組織內部建立，也可以來自其他組織或協力廠商。</span><span class="sxs-lookup"><span data-stu-id="17867-113">An integrated app can be created from within your own organization, or it can come from another organization or a third-party.</span></span>

<span data-ttu-id="17867-114">開啟整合式應用程式並使用應用程式時，應用程式會在其存取使用者的資訊時，要求設定其需要的存取層級的權限。</span><span class="sxs-lookup"><span data-stu-id="17867-114">When Integrated Apps is turned on and an app is used, the app asks for permission to set the level of access it needs when it accesses the user's information.</span></span> <span data-ttu-id="17867-115">使用者只能將存取其 Microsoft 365 資訊的應用程式授與存取權。</span><span class="sxs-lookup"><span data-stu-id="17867-115">A user can give access only to apps they own that access their Microsoft 365 information.</span></span> <span data-ttu-id="17867-116">他們無法讓應用程式存取任何其他使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="17867-116">They can't give an app access to any other user's information.</span></span>

<span data-ttu-id="17867-117">在 Microsoft 365 中使用整合式應用程式時，有兩種許可權會使用：使用者許可權和系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="17867-117">There are two kinds of permissions that are used when using Integrated Apps in Microsoft 365: user permissions and admin permissions.</span></span> <span data-ttu-id="17867-118">例如，當您的組織已啟用整合式應用程式，而使用者使用的是協力廠商應用程式，應用程式可能會要求使用者權限以讀取其使用者的設定檔詳細資料、編輯或刪除使用者檔案、讀取網站集合中包含的項目，並為使用者傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="17867-118">For example, when your organization is enabled for Integrated Apps and a user uses a third-party app, the app might ask for the user's permission to read their user profile details, edit or delete their files, read items contained in site collections, and send email as that user.</span></span>

![整合式應用程式使用者權限](../../media/bb9a6cf8-da39-4ac0-9e40-cde03a81c121.gif)

<span data-ttu-id="17867-120">若管理員為組織中的所有使用者註冊應用程式，則系統會要求使用者提供許可權，讓應用程式存取組織中的資訊和資源。</span><span class="sxs-lookup"><span data-stu-id="17867-120">If an admin registers an app for all users in an organization, he or she is asked for permission to let that app access information and resources in the organization.</span></span> <span data-ttu-id="17867-121">之後，當組織中的其他使用者使用該應用程式時，應用程式就不會向他們要求權限。</span><span class="sxs-lookup"><span data-stu-id="17867-121">After this, when other users in the organization use that app, they won't be asked for permission.</span></span> <span data-ttu-id="17867-122">當管理員註冊應用程式時，管理員必須確定他們能信任該應用程式的發行者。</span><span class="sxs-lookup"><span data-stu-id="17867-122">When an admin registers an app, that admin must make sure that they trust that app's publisher.</span></span> <span data-ttu-id="17867-123">如需註冊應用程式的詳細資訊，請參閱[新增、更新與移除應用程式](https://go.microsoft.com/fwlink/p/?LinkID=518600)。</span><span class="sxs-lookup"><span data-stu-id="17867-123">For details on registering an app, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/p/?LinkID=518600).</span></span>

![整合式應用程式管理員權限](../../media/e24aa504-bf10-446c-a9d5-45a6f2655187.gif)

<span data-ttu-id="17867-p105">如果關閉整合式應用程式，已安裝並有存取資訊權限的應用程式不會解除安裝，權限也不會移除。 即使已關閉整合式應用程式，管理員仍然可以註冊應用程式，讓使用者使用它們，並允許這些應用程式存取使用者的相關資訊。 如需移除已註冊的應用程式與其權限的詳細資訊，請參閱 [新增、更新與移除應用程式](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="17867-p105">If Integrated Apps is turned off, apps that have already been installed and have permission to access information won't be uninstalled, and the permissions won't be removed. Even though Integrated Apps is turned off, admins can still register apps to make them available to their users and allow those apps access to the users' information. For details on removing a registered application and it's permissions, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409).</span></span>


