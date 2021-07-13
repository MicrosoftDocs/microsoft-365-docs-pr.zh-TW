---
title: 啟用企業狀態漫遊
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 709a231f1c3f401ceeee2b3aaf99ff275f107e30
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409113"
---
# <a name="enable-enterprise-state-roaming"></a><span data-ttu-id="34308-103">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="34308-103">Enable Enterprise State Roaming</span></span>

<span data-ttu-id="34308-104">[Enterprise 狀態漫遊](/azure/active-directory/devices/enterprise-state-roaming-overview)可讓使用者安全地將使用者和應用程式設定資料同步處理至雲端。</span><span class="sxs-lookup"><span data-stu-id="34308-104">[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) lets users securely synchronize user and application settings data to the cloud.</span></span> <span data-ttu-id="34308-105">這表示不管使用者登入哪 Windows 裝置，都有相同的經驗。</span><span class="sxs-lookup"><span data-stu-id="34308-105">This means they'll have the same experience no matter which Windows device they sign into.</span></span> <span data-ttu-id="34308-106">例如，如果您將其中一個 Microsoft 受管理的電腦裝置更換為新裝置，它的外觀和行為會與最後一個裝置完全相同。</span><span class="sxs-lookup"><span data-stu-id="34308-106">For example, if you replace one of their Microsoft Managed Desktop devices with a new one, it will look and behave exactly the same as the last one.</span></span> <span data-ttu-id="34308-107">Enterprise狀態漫遊是可為使用者設定的 Microsoft 受管理的電腦服務選用的功能，且不會包含或管理 Microsoft 受管理的電腦的一部分。</span><span class="sxs-lookup"><span data-stu-id="34308-107">Enterprise State Roaming is an optional feature for the Microsoft Managed Desktop service that you can configure for your users and isn't included or managed as part of Microsoft Managed Desktop.</span></span>

<span data-ttu-id="34308-108">若要啟用 Enterprise 狀態漫遊，請依照 Azure Active Directory 中的[啟用 Enterprise 狀態漫遊](/azure/active-directory/devices/enterprise-state-roaming-enable)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="34308-108">To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

>[!NOTE]
><span data-ttu-id="34308-109">如果您啟用 Enterprise 狀態漫遊，您的慣用語言清單將會覆寫裝置安裝期間選取的語言。</span><span class="sxs-lookup"><span data-stu-id="34308-109">If you enable Enterprise State Roaming, your preferred language list will overwrite the language selected during device setup.</span></span> <span data-ttu-id="34308-110">雖然使用者可以輕鬆地修正這種情況，但最初可能會造成不一致的當地語系化體驗。</span><span class="sxs-lookup"><span data-stu-id="34308-110">Although users can fix this easily, it could cause an inconsistent localization experience initially.</span></span> <span data-ttu-id="34308-111">在設定裝置之前，判斷 Enterprise 狀態漫遊是否適合您的使用者。</span><span class="sxs-lookup"><span data-stu-id="34308-111">Determine if Enterprise State Roaming is right for your users before setting up devices.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="34308-112">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="34308-112">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="34308-113">在系統管理入口網站中新增和驗證系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="34308-113">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="34308-114">調整條件式存取</span><span class="sxs-lookup"><span data-stu-id="34308-114">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="34308-115">指派授權</span><span class="sxs-lookup"><span data-stu-id="34308-115">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="34308-116">部署 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="34308-116">Deploy Intune Company Portal</span></span>](company-portal.md)
5. <span data-ttu-id="34308-117">啟用 Enterprise 狀態漫遊 (本主題) </span><span class="sxs-lookup"><span data-stu-id="34308-117">Enable Enterprise State Roaming (this topic)</span></span>
6. [<span data-ttu-id="34308-118">設定裝置</span><span class="sxs-lookup"><span data-stu-id="34308-118">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="34308-119">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="34308-119">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="34308-120">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="34308-120">Deploy apps</span></span>](deploy-apps.md)
