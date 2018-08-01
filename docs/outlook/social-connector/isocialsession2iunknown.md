---
title: ISocialSession2 IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f516e86e-0158-472b-9711-fe7491b24404
description: 支持使用缓存的凭据添加朋友、 按需或混合同步朋友、 活动或登录到社交网络的按需同步。
ms.openlocfilehash: b14804d35e54ebe9fe2a529fb2664f0a661653bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779245"
---
# <a name="isocialsession2--iunknown"></a><span data-ttu-id="00033-103">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="00033-103">ISocialSession2 : IUnknown</span></span>

<span data-ttu-id="00033-104">支持使用缓存的凭据添加朋友、 按需或混合同步朋友、 活动或登录到社交网络的按需同步。</span><span class="sxs-lookup"><span data-stu-id="00033-104">Supports adding friends, on-demand or hybrid synchronization of friends, on-demand synchronization of activities, or logging on to the social network by using cached credentials.</span></span>
  
## <a name="members"></a><span data-ttu-id="00033-105">Members</span><span class="sxs-lookup"><span data-stu-id="00033-105">Members</span></span>

<span data-ttu-id="00033-106">下表显示了**ISocialSession2**接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="00033-106">The following table shows the members that are available on the **ISocialSession2** interface.</span></span> 
  
|<span data-ttu-id="00033-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="00033-107">**Name**</span></span>|<span data-ttu-id="00033-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="00033-108">**Member type**</span></span>|<span data-ttu-id="00033-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="00033-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="00033-110">FollowPersonEx</span><span class="sxs-lookup"><span data-stu-id="00033-110">FollowPersonEx</span></span>](isocialsession2-followpersonex.md) <br/> |<span data-ttu-id="00033-111">方法</span><span class="sxs-lookup"><span data-stu-id="00033-111">Method</span></span>  <br/> |<span data-ttu-id="00033-112">添加为社交网络登录用户的朋友由_emailAddresses_和_displayName_参数标识的人员。</span><span class="sxs-lookup"><span data-stu-id="00033-112">Adds the person identified by the  _emailAddresses_ and  _displayName_ parameters as a friend for the logged-on user on the social network.</span></span>  <br/> |
|[<span data-ttu-id="00033-113">GetActivitiesEx</span><span class="sxs-lookup"><span data-stu-id="00033-113">GetActivitiesEx</span></span>](isocialsession2-getactivitiesex.md) <br/> |<span data-ttu-id="00033-114">方法</span><span class="sxs-lookup"><span data-stu-id="00033-114">Method</span></span>  <br/> |<span data-ttu-id="00033-115">获取一个字符串，表示活动_hashedAddresses_参数指定的用户的集合。</span><span class="sxs-lookup"><span data-stu-id="00033-115">Gets a string that represents a collection of activities of the users specified by the  _hashedAddresses_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="00033-116">GetPeopleDetails</span><span class="sxs-lookup"><span data-stu-id="00033-116">GetPeopleDetails</span></span>](isocialsession2-getpeopledetails.md) <br/> |<span data-ttu-id="00033-117">方法</span><span class="sxs-lookup"><span data-stu-id="00033-117">Method</span></span>  <br/> |<span data-ttu-id="00033-118">返回一个字符串，包含一人和图片_personsAddresses_参数指定用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="00033-118">Returns a string that contains a collection of person and picture details for the users specified by the  _personsAddresses_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="00033-119">LogonCached</span><span class="sxs-lookup"><span data-stu-id="00033-119">LogonCached</span></span>](isocialsession2-logoncached.md) <br/> |<span data-ttu-id="00033-120">方法</span><span class="sxs-lookup"><span data-stu-id="00033-120">Method</span></span>  <br/> |<span data-ttu-id="00033-121">登录到使用缓存的凭据的社交网络站点。</span><span class="sxs-lookup"><span data-stu-id="00033-121">Logs on to the social network site using cached credentials.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="00033-122">说明</span><span class="sxs-lookup"><span data-stu-id="00033-122">Remarks</span></span>

<span data-ttu-id="00033-123">Outlook Social Connector (OSC) 提供程序可以选择实现此接口，如果提供程序支持的点播或混合同步朋友、 活动或登录到社交网络的按需同步使用缓存的凭据。</span><span class="sxs-lookup"><span data-stu-id="00033-123">An Outlook Social Connector (OSC) provider can choose to implement this interface if the provider supports on-demand or hybrid synchronization of friends, on-demand synchronization of activities, or logging on to the social network by using cached credentials.</span></span> <span data-ttu-id="00033-124">如果 OSC 提供程序实现**ISocialSession2**和支持以下社交网络上的人员，OSC 调用[ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md)而不是[ISocialSession::FollowPerson](isocialsession-followperson.md)，并提供程序必须实现**ISocialSession2::FollowPersonEx**，以及。</span><span class="sxs-lookup"><span data-stu-id="00033-124">If the OSC provider implements **ISocialSession2** and supports following persons on the social network, the OSC would call [ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md) instead of [ISocialSession::FollowPerson](isocialsession-followperson.md), and the provider must implement **ISocialSession2::FollowPersonEx**, as well.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00033-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00033-125">See also</span></span>

- [<span data-ttu-id="00033-126">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="00033-126">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

