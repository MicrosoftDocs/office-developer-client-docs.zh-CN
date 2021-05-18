---
title: ISocialSession2 IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f516e86e-0158-472b-9711-fe7491b24404
description: 支持添加好友、按需或好友混合同步、按需同步活动，或者使用缓存凭据登录社交网络。
ms.openlocfilehash: 6dc581bb812408d7e01f94c375671783445616a1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408829"
---
# <a name="isocialsession2--iunknown"></a><span data-ttu-id="d5fdb-103">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d5fdb-103">ISocialSession2 : IUnknown</span></span>

<span data-ttu-id="d5fdb-104">支持添加好友、按需或好友混合同步、按需同步活动，或者使用缓存凭据登录社交网络。</span><span class="sxs-lookup"><span data-stu-id="d5fdb-104">Supports adding friends, on-demand or hybrid synchronization of friends, on-demand synchronization of activities, or logging on to the social network by using cached credentials.</span></span>
  
## <a name="members"></a><span data-ttu-id="d5fdb-105">Members</span><span class="sxs-lookup"><span data-stu-id="d5fdb-105">Members</span></span>

<span data-ttu-id="d5fdb-106">下表显示了 **ISocialSession2** 接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="d5fdb-106">The following table shows the members that are available on the **ISocialSession2** interface.</span></span> 
  
|<span data-ttu-id="d5fdb-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="d5fdb-107">**Name**</span></span>|<span data-ttu-id="d5fdb-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="d5fdb-108">**Member type**</span></span>|<span data-ttu-id="d5fdb-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="d5fdb-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d5fdb-110">FollowPersonEx</span><span class="sxs-lookup"><span data-stu-id="d5fdb-110">FollowPersonEx</span></span>](isocialsession2-followpersonex.md) <br/> |<span data-ttu-id="d5fdb-111">方法</span><span class="sxs-lookup"><span data-stu-id="d5fdb-111">Method</span></span>  <br/> |<span data-ttu-id="d5fdb-112">将  _emailAddresses_ 和  _displayName_ 参数标识的人添加为社交网络上登录的用户的好友。</span><span class="sxs-lookup"><span data-stu-id="d5fdb-112">Adds the person identified by the  _emailAddresses_ and  _displayName_ parameters as a friend for the logged-on user on the social network.</span></span>  <br/> |
|[<span data-ttu-id="d5fdb-113">GetActivitiesEx</span><span class="sxs-lookup"><span data-stu-id="d5fdb-113">GetActivitiesEx</span></span>](isocialsession2-getactivitiesex.md) <br/> |<span data-ttu-id="d5fdb-114">方法</span><span class="sxs-lookup"><span data-stu-id="d5fdb-114">Method</span></span>  <br/> |<span data-ttu-id="d5fdb-115">获取一个字符串，该字符串代表  _hashedAddresses_ 参数指定的用户的活动集合。</span><span class="sxs-lookup"><span data-stu-id="d5fdb-115">Gets a string that represents a collection of activities of the users specified by the  _hashedAddresses_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="d5fdb-116">GetPeopleDetails</span><span class="sxs-lookup"><span data-stu-id="d5fdb-116">GetPeopleDetails</span></span>](isocialsession2-getpeopledetails.md) <br/> |<span data-ttu-id="d5fdb-117">方法</span><span class="sxs-lookup"><span data-stu-id="d5fdb-117">Method</span></span>  <br/> |<span data-ttu-id="d5fdb-118">返回一个字符串，其中包含  _personAddresses_ 参数指定的用户的人员和图片详细信息的集合。</span><span class="sxs-lookup"><span data-stu-id="d5fdb-118">Returns a string that contains a collection of person and picture details for the users specified by the  _personsAddresses_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="d5fdb-119">LogonCached</span><span class="sxs-lookup"><span data-stu-id="d5fdb-119">LogonCached</span></span>](isocialsession2-logoncached.md) <br/> |<span data-ttu-id="d5fdb-120">方法</span><span class="sxs-lookup"><span data-stu-id="d5fdb-120">Method</span></span>  <br/> |<span data-ttu-id="d5fdb-121">使用缓存的凭据登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="d5fdb-121">Logs on to the social network site using cached credentials.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d5fdb-122">备注</span><span class="sxs-lookup"><span data-stu-id="d5fdb-122">Remarks</span></span>

<span data-ttu-id="d5fdb-123">如果 Outlook Social Connector (OSC) 提供程序支持好友的按需或混合同步、活动的按需同步，或者使用缓存的凭据登录到社交网络，则提供商可以选择实现此接口。</span><span class="sxs-lookup"><span data-stu-id="d5fdb-123">An Outlook Social Connector (OSC) provider can choose to implement this interface if the provider supports on-demand or hybrid synchronization of friends, on-demand synchronization of activities, or logging on to the social network by using cached credentials.</span></span> <span data-ttu-id="d5fdb-124">如果 OSC 提供程序实现 **ISocialSession2** 并支持在社交网络上关注人员，则 OSC 将调用 [ISocialSession2：：FollowPersonEx](isocialsession2-followpersonex.md)而不是 [ISocialSession：：FollowPerson，](isocialsession-followperson.md)并且该提供程序也必须实现 **ISocialSession2：：FollowPersonEx。**</span><span class="sxs-lookup"><span data-stu-id="d5fdb-124">If the OSC provider implements **ISocialSession2** and supports following persons on the social network, the OSC would call [ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md) instead of [ISocialSession::FollowPerson](isocialsession-followperson.md), and the provider must implement **ISocialSession2::FollowPersonEx**, as well.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d5fdb-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5fdb-125">See also</span></span>

- [<span data-ttu-id="d5fdb-126">OutlookSocial Connector Provider Interfaces</span><span class="sxs-lookup"><span data-stu-id="d5fdb-126">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

