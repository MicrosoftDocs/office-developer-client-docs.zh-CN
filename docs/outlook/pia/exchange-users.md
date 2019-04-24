---
title: Exchange 用户
TOCTitle: Exchange users
ms:assetid: 01802032-fd60-400b-ad83-1f4eefe596bd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184585(v=office.15)
ms:contentKeyID: 55119835
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 667f8a07477c527d251c4e50f35baa2da2e417ed
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357832"
---
# <a name="exchange-users"></a><span data-ttu-id="933e3-102">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="933e3-102">Exchange users</span></span>

<span data-ttu-id="933e3-p101">本节提供涉及 Microsoft Exchange 邮箱用户的示例任务。Exchange 用户连接到 Exchange 服务器，并由派生自 [AddressEntry](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象的 [ExchangeUser](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象表示。</span><span class="sxs-lookup"><span data-stu-id="933e3-p101">This section provides sample tasks that involve Microsoft Exchange mailbox users. Exchange users are connected to an Exchange server, and are represented by [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) objects, which are derived from the [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) object.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="933e3-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="933e3-105">In this section</span></span>

|<span data-ttu-id="933e3-106">主题</span><span class="sxs-lookup"><span data-stu-id="933e3-106">Topic</span></span>|<span data-ttu-id="933e3-107">说明</span><span class="sxs-lookup"><span data-stu-id="933e3-107">Description</span></span>|
|:----|:----------|
|[<span data-ttu-id="933e3-108">获取当前用户的相关信息</span><span class="sxs-lookup"><span data-stu-id="933e3-108">Get information about the current user</span></span>](how-to-get-information-about-the-current-user.md)  |<span data-ttu-id="933e3-109">介绍了如何获取当前用户的相关信息（如姓名、职务和电话号码）。</span><span class="sxs-lookup"><span data-stu-id="933e3-109">Gets the current user’s information, such as name, job title, and telephone number.</span></span>|
|[<span data-ttu-id="933e3-110">获取当前用户所属全部通讯组列表的相关信息</span><span class="sxs-lookup"><span data-stu-id="933e3-110">Get information about all distribution lists of which the current user is a member</span></span>](how-to-get-information-about-all-distribution-lists-of-which-the-current-user-is-a-member.md)  |<span data-ttu-id="933e3-111">介绍了如何使用 [GetMemberOfList()](https://msdn.microsoft.com/library/bb623397\(v=office.15\)) 方法，获取当前用户所属全部通讯组列表的相关信息。</span><span class="sxs-lookup"><span data-stu-id="933e3-111">Uses the [GetMemberOfList()](https://msdn.microsoft.com/library/bb623397\(v=office.15\)) method to get information about all distribution lists of which the current user is a member.</span></span>|
|[<span data-ttu-id="933e3-112">创建通讯组列表</span><span class="sxs-lookup"><span data-stu-id="933e3-112">Create a distribution list</span></span>](how-to-create-a-distribution-list.md)  |<span data-ttu-id="933e3-113">介绍了如何创建通讯组列表，并将它显示给用户。</span><span class="sxs-lookup"><span data-stu-id="933e3-113">Creates a distribution list and displays it to the user.</span></span>|
[<span data-ttu-id="933e3-114">获取 Exchange 通讯组列表的成员</span><span class="sxs-lookup"><span data-stu-id="933e3-114">Get members of an Exchange distribution list</span></span>](how-to-get-members-of-an-exchange-distribution-list.md)  |<span data-ttu-id="933e3-115">提示用户从“选择姓名”\*\*\*\* 对话框中选择一个 Exchange 通讯组列表，然后展开该通讯组列表以显示其成员。</span><span class="sxs-lookup"><span data-stu-id="933e3-115">Prompts the user to select an Exchange distribution list from the **Select Names** dialog box and expands the distribution list to display its members.</span></span>|
[<span data-ttu-id="933e3-116">获取当前用户的经理信息</span><span class="sxs-lookup"><span data-stu-id="933e3-116">Get information about the current user's manager</span></span>](how-to-get-information-about-the-current-user-s-manager.md)  |<span data-ttu-id="933e3-117">介绍了如何获取当前用户的经理信息（如姓名、职务和电话号码）。</span><span class="sxs-lookup"><span data-stu-id="933e3-117">Gets information (such as name, job title, and phone numbers) about the current user’s manager.</span></span>|
[<span data-ttu-id="933e3-118">获取 Exchange 用户的经理闲/忙状态信息</span><span class="sxs-lookup"><span data-stu-id="933e3-118">Get availability information for an Exchange user's manager</span></span>](how-to-get-availability-information-for-an-exchange-user-s-manager.md) |  <span data-ttu-id="933e3-119">介绍了如何在日历中显示用户经理的下一个空闲 60 分钟时间段。</span><span class="sxs-lookup"><span data-stu-id="933e3-119">Displays the next free 60-minute time slot in the calendar for a user's manager.</span></span>|
|[<span data-ttu-id="933e3-120">检查经理对会议请求的响应</span><span class="sxs-lookup"><span data-stu-id="933e3-120">Check a manager's response to a meeting request</span></span>](how-to-check-a-manager-s-response-to-a-meeting-request.md) | <span data-ttu-id="933e3-121">介绍了如何通过使用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 和 [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法，检查当前用户的经理对会议请求的响应状态。</span><span class="sxs-lookup"><span data-stu-id="933e3-121">Uses the [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) and [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) methods to check the status of the response of the current user's manager to a meeting request.</span></span>|
|[<span data-ttu-id="933e3-122">获取当前用户的经理的直接下属的相关信息</span><span class="sxs-lookup"><span data-stu-id="933e3-122">Get information about direct reports of the current user's manager</span></span>](how-to-get-information-about-direct-reports-of-the-current-user-s-manager.md) | <span data-ttu-id="933e3-123">介绍了如何获取当前用户的经理的直接下属（若有），然后显示经理的每个直接下属的相关信息。</span><span class="sxs-lookup"><span data-stu-id="933e3-123">Gets the direct reports of the current user’s manager, if any, and then displays information about each of the manager’s direct reports.</span></span>|

## <a name="see-also"></a><span data-ttu-id="933e3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="933e3-124">See also</span></span>

- [<span data-ttu-id="933e3-125">帐户</span><span class="sxs-lookup"><span data-stu-id="933e3-125">Accounts</span></span>](accounts.md)
- [<span data-ttu-id="933e3-126">通讯簿</span><span class="sxs-lookup"><span data-stu-id="933e3-126">Address book</span></span>](address-book.md)
- [<span data-ttu-id="933e3-127">存储</span><span class="sxs-lookup"><span data-stu-id="933e3-127">Stores</span></span>](stores.md)
- [<span data-ttu-id="933e3-128">我如何...（Outlook 2013 PIA 参考）</span><span class="sxs-lookup"><span data-stu-id="933e3-128">How do I... (Outlook 2013 PIA reference)</span></span>](how-do-i-outlook-2013-pia-reference.md)

