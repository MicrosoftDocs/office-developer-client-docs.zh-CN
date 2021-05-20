---
title: ISocialSession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0fe423d7-b044-479b-89ad-c39620eedd65
description: 表示与社交网络网站的连接。
ms.openlocfilehash: c60fab1c27d2f761db28ed06bb45080857630e8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437824"
---
# <a name="isocialsession--iunknown"></a><span data-ttu-id="82d37-103">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="82d37-103">ISocialSession : IUnknown</span></span>

<span data-ttu-id="82d37-104">表示与社交网络网站的连接。</span><span class="sxs-lookup"><span data-stu-id="82d37-104">Represents a connection to a social network site.</span></span>
  
## <a name="members"></a><span data-ttu-id="82d37-105">Members</span><span class="sxs-lookup"><span data-stu-id="82d37-105">Members</span></span>

<span data-ttu-id="82d37-106">下表显示了 **ISocialSession** 接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="82d37-106">The following table shows the members that are available on the **ISocialSession** interface.</span></span> 
  
|<span data-ttu-id="82d37-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="82d37-107">**Name**</span></span>|<span data-ttu-id="82d37-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="82d37-108">**Member type**</span></span>|<span data-ttu-id="82d37-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="82d37-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="82d37-110">FindPerson</span><span class="sxs-lookup"><span data-stu-id="82d37-110">FindPerson</span></span>](isocialsession-findperson.md) <br/> |<span data-ttu-id="82d37-111">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-111">Method</span></span>  <br/> |<span data-ttu-id="82d37-112">获取一个字符串，代表与 userID 参数匹配的  _一个或多个_ 人员。</span><span class="sxs-lookup"><span data-stu-id="82d37-112">Gets a string that represents one or more persons who match the  _userID_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="82d37-113">FollowPerson</span><span class="sxs-lookup"><span data-stu-id="82d37-113">FollowPerson</span></span>](isocialsession-followperson.md) <br/> |<span data-ttu-id="82d37-114">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-114">Method</span></span>  <br/> |<span data-ttu-id="82d37-115">将  _emailAddress_ 参数标识的人添加为社交网络上已登录用户的好友。</span><span class="sxs-lookup"><span data-stu-id="82d37-115">Adds the person identified by the  _emailAddress_ parameter as a friend for the logged-on user on the social network.</span></span>  <br/> |
|[<span data-ttu-id="82d37-116">GetActivities</span><span class="sxs-lookup"><span data-stu-id="82d37-116">GetActivities</span></span>](isocialsession-getactivities.md) <br/> |<span data-ttu-id="82d37-117">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-117">Method</span></span>  <br/> |<span data-ttu-id="82d37-118">在 OSC 1.1 Outlook Social Connector (中) 此方法。</span><span class="sxs-lookup"><span data-stu-id="82d37-118">This method has been deprecated in Outlook Social Connector (OSC) 1.1.</span></span>  <br/> |
|[<span data-ttu-id="82d37-119">GetLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="82d37-119">GetLoggedOnUser</span></span>](isocialsession-getloggedonuser.md) <br/> |<span data-ttu-id="82d37-120">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-120">Method</span></span>  <br/> |<span data-ttu-id="82d37-121">获取一个代表已登录用户的 [ISocialProfile](isocialprofileisocialperson.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="82d37-121">Gets an [ISocialProfile](isocialprofileisocialperson.md) interface that represents the logged-on user.</span></span>  <br/> |
|[<span data-ttu-id="82d37-122">GetLogonUrl</span><span class="sxs-lookup"><span data-stu-id="82d37-122">GetLogonUrl</span></span>](isocialsession-getlogonurl.md) <br/> |<span data-ttu-id="82d37-123">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-123">Method</span></span>  <br/> |<span data-ttu-id="82d37-124">获取一个字符串，代表在 Web 身份验证期间用于向用户显示基于浏览器的表单的 URL。</span><span class="sxs-lookup"><span data-stu-id="82d37-124">Gets a string that represents a URL that is used for presenting a browser-based form to the user during web authentication.</span></span>  <br/> |
|[<span data-ttu-id="82d37-125">GetNetworkIdentifier</span><span class="sxs-lookup"><span data-stu-id="82d37-125">GetNetworkIdentifier</span></span>](isocialsession-getnetworkidentifier.md) <br/> |<span data-ttu-id="82d37-126">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-126">Method</span></span>  <br/> |<span data-ttu-id="82d37-127">获取一个字符串，该字符串代表给定社交网络连接的唯一社交网络标识符。</span><span class="sxs-lookup"><span data-stu-id="82d37-127">Gets a string that represents a unique social network identifier for a given social network connection.</span></span>  <br/> |
|[<span data-ttu-id="82d37-128">GetPerson</span><span class="sxs-lookup"><span data-stu-id="82d37-128">GetPerson</span></span>](isocialsession-getperson.md) <br/> |<span data-ttu-id="82d37-129">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-129">Method</span></span>  <br/> |<span data-ttu-id="82d37-130">获取基于 _userID_ 参数的 [ISocialPerson](isocialpersoniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="82d37-130">Gets an [ISocialPerson](isocialpersoniunknown.md) interface based on the  _userID_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="82d37-131">LoggedOnUserID</span><span class="sxs-lookup"><span data-stu-id="82d37-131">LoggedOnUserID</span></span>](isocialsession-loggedonuserid.md) <br/> |<span data-ttu-id="82d37-132">属性</span><span class="sxs-lookup"><span data-stu-id="82d37-132">Property</span></span>  <br/> |<span data-ttu-id="82d37-133">返回一个字符串，表示当前登录的用户的社交网络用户 ID。</span><span class="sxs-lookup"><span data-stu-id="82d37-133">Returns a string that represents the social network user ID of the user who is currently logged on.</span></span>  <br/> |
|[<span data-ttu-id="82d37-134">LoggedOnUserName</span><span class="sxs-lookup"><span data-stu-id="82d37-134">LoggedOnUserName</span></span>](isocialsession-loggedonusername.md) <br/> |<span data-ttu-id="82d37-135">属性</span><span class="sxs-lookup"><span data-stu-id="82d37-135">Property</span></span>  <br/> |<span data-ttu-id="82d37-136">返回一个字符串，该字符串表示登录时所使用的用户名。</span><span class="sxs-lookup"><span data-stu-id="82d37-136">Returns a string that represents the user name that is used when logging on.</span></span>  <br/> |
|[<span data-ttu-id="82d37-137">登录</span><span class="sxs-lookup"><span data-stu-id="82d37-137">Logon</span></span>](isocialsession-logon.md) <br/> |<span data-ttu-id="82d37-138">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-138">Method</span></span>  <br/> |<span data-ttu-id="82d37-139">使用指定的用户名和密码登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="82d37-139">Logs on to the social network site by using the specified user name and password.</span></span>  <br/> |
|[<span data-ttu-id="82d37-140">LogonWeb</span><span class="sxs-lookup"><span data-stu-id="82d37-140">LogonWeb</span></span>](isocialsession-logonweb.md) <br/> |<span data-ttu-id="82d37-141">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-141">Method</span></span>  <br/> |<span data-ttu-id="82d37-142">使用基于表单的身份验证登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="82d37-142">Logs on to the social network site by using forms-based authentication.</span></span>  <br/> |
|[<span data-ttu-id="82d37-143">SiteUrl</span><span class="sxs-lookup"><span data-stu-id="82d37-143">SiteUrl</span></span>](isocialsession-siteurl.md) <br/> |<span data-ttu-id="82d37-144">属性</span><span class="sxs-lookup"><span data-stu-id="82d37-144">Property</span></span>  <br/> |<span data-ttu-id="82d37-145">设置社交网络网站 URL。</span><span class="sxs-lookup"><span data-stu-id="82d37-145">Sets the social network site URL.</span></span>  <br/> |
|[<span data-ttu-id="82d37-146">UnFollowPerson</span><span class="sxs-lookup"><span data-stu-id="82d37-146">UnFollowPerson</span></span>](isocialsession-unfollowperson.md) <br/> |<span data-ttu-id="82d37-147">方法</span><span class="sxs-lookup"><span data-stu-id="82d37-147">Method</span></span>  <br/> |<span data-ttu-id="82d37-148">删除  _userID_ 参数标识为社交网络上好友的人。</span><span class="sxs-lookup"><span data-stu-id="82d37-148">Removes the person identified by the  _userID_ parameter as a friend on the social network.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="82d37-149">备注</span><span class="sxs-lookup"><span data-stu-id="82d37-149">Remarks</span></span>

<span data-ttu-id="82d37-150">OSC 提供程序必须实现此接口以与 OSC 通信。</span><span class="sxs-lookup"><span data-stu-id="82d37-150">An OSC provider must implement this interface to communicate with the OSC.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="82d37-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82d37-151">See also</span></span>

- [<span data-ttu-id="82d37-152">OutlookSocial Connector Provider Interfaces</span><span class="sxs-lookup"><span data-stu-id="82d37-152">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

