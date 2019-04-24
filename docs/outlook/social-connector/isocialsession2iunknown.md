---
title: ISocialSession2 IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f516e86e-0158-472b-9711-fe7491b24404
description: 支持添加朋友的好友、按需或混合同步、活动的按需同步或使用缓存凭据登录到社交网络。
ms.openlocfilehash: 6dc581bb812408d7e01f94c375671783445616a1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345295"
---
# <a name="isocialsession2--iunknown"></a><span data-ttu-id="8bcff-103">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8bcff-103">ISocialSession2 : IUnknown</span></span>

<span data-ttu-id="8bcff-104">支持添加朋友的好友、按需或混合同步、活动的按需同步或使用缓存凭据登录到社交网络。</span><span class="sxs-lookup"><span data-stu-id="8bcff-104">Supports adding friends, on-demand or hybrid synchronization of friends, on-demand synchronization of activities, or logging on to the social network by using cached credentials.</span></span>
  
## <a name="members"></a><span data-ttu-id="8bcff-105">Members</span><span class="sxs-lookup"><span data-stu-id="8bcff-105">Members</span></span>

<span data-ttu-id="8bcff-106">下表显示了**ISocialSession2**接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="8bcff-106">The following table shows the members that are available on the **ISocialSession2** interface.</span></span> 
  
|<span data-ttu-id="8bcff-107">**Name**</span><span class="sxs-lookup"><span data-stu-id="8bcff-107">**Name**</span></span>|<span data-ttu-id="8bcff-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="8bcff-108">**Member type**</span></span>|<span data-ttu-id="8bcff-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="8bcff-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8bcff-110">FollowPersonEx</span><span class="sxs-lookup"><span data-stu-id="8bcff-110">FollowPersonEx</span></span>](isocialsession2-followpersonex.md) <br/> |<span data-ttu-id="8bcff-111">方法</span><span class="sxs-lookup"><span data-stu-id="8bcff-111">Method</span></span>  <br/> |<span data-ttu-id="8bcff-112">将由_emailAddresses_和_displayName_参数标识的人员添加为社交网络上登录用户的友元。</span><span class="sxs-lookup"><span data-stu-id="8bcff-112">Adds the person identified by the  _emailAddresses_ and  _displayName_ parameters as a friend for the logged-on user on the social network.</span></span>  <br/> |
|[<span data-ttu-id="8bcff-113">GetActivitiesEx</span><span class="sxs-lookup"><span data-stu-id="8bcff-113">GetActivitiesEx</span></span>](isocialsession2-getactivitiesex.md) <br/> |<span data-ttu-id="8bcff-114">方法</span><span class="sxs-lookup"><span data-stu-id="8bcff-114">Method</span></span>  <br/> |<span data-ttu-id="8bcff-115">获取一个字符串, 表示由_hashedAddresses_参数指定的用户的活动的集合。</span><span class="sxs-lookup"><span data-stu-id="8bcff-115">Gets a string that represents a collection of activities of the users specified by the  _hashedAddresses_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="8bcff-116">GetPeopleDetails</span><span class="sxs-lookup"><span data-stu-id="8bcff-116">GetPeopleDetails</span></span>](isocialsession2-getpeopledetails.md) <br/> |<span data-ttu-id="8bcff-117">方法</span><span class="sxs-lookup"><span data-stu-id="8bcff-117">Method</span></span>  <br/> |<span data-ttu-id="8bcff-118">返回一个字符串, 其中包含_personsAddresses_参数所指定用户的人员和图片详细信息的集合。</span><span class="sxs-lookup"><span data-stu-id="8bcff-118">Returns a string that contains a collection of person and picture details for the users specified by the  _personsAddresses_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="8bcff-119">LogonCached</span><span class="sxs-lookup"><span data-stu-id="8bcff-119">LogonCached</span></span>](isocialsession2-logoncached.md) <br/> |<span data-ttu-id="8bcff-120">方法</span><span class="sxs-lookup"><span data-stu-id="8bcff-120">Method</span></span>  <br/> |<span data-ttu-id="8bcff-121">使用缓存凭据登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="8bcff-121">Logs on to the social network site using cached credentials.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8bcff-122">注解</span><span class="sxs-lookup"><span data-stu-id="8bcff-122">Remarks</span></span>

<span data-ttu-id="8bcff-123">如果提供程序支持对朋友的按需或混合同步、按需同步活动或使用缓存凭据登录到社交网络, Outlook Social Connector (.osc) 提供程序可以选择实现此接口。</span><span class="sxs-lookup"><span data-stu-id="8bcff-123">An Outlook Social Connector (OSC) provider can choose to implement this interface if the provider supports on-demand or hybrid synchronization of friends, on-demand synchronization of activities, or logging on to the social network by using cached credentials.</span></span> <span data-ttu-id="8bcff-124">如果 .osc 提供程序实现**ISocialSession2**并支持社交网络中的以下人员, 则 .osc 将调用[ISocialSession2:: FollowPersonEx](isocialsession2-followpersonex.md)而不是[ISocialSession:: FollowPerson](isocialsession-followperson.md), 并且提供程序必须实现**ISocialSession2:: FollowPersonEx**。</span><span class="sxs-lookup"><span data-stu-id="8bcff-124">If the OSC provider implements **ISocialSession2** and supports following persons on the social network, the OSC would call [ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md) instead of [ISocialSession::FollowPerson](isocialsession-followperson.md), and the provider must implement **ISocialSession2::FollowPersonEx**, as well.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8bcff-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bcff-125">See also</span></span>

- [<span data-ttu-id="8bcff-126">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="8bcff-126">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

