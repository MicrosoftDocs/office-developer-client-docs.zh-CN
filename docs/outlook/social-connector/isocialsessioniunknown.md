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
# <a name="isocialsession--iunknown"></a><span data-ttu-id="df072-103">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="df072-103">ISocialSession : IUnknown</span></span>

<span data-ttu-id="df072-104">表示与社交网络网站的连接。</span><span class="sxs-lookup"><span data-stu-id="df072-104">Represents a connection to a social network site.</span></span>
  
## <a name="members"></a><span data-ttu-id="df072-105">Members</span><span class="sxs-lookup"><span data-stu-id="df072-105">Members</span></span>

<span data-ttu-id="df072-106">下表显示了**ISocialSession**接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="df072-106">The following table shows the members that are available on the **ISocialSession** interface.</span></span> 
  
|<span data-ttu-id="df072-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="df072-107">**Name**</span></span>|<span data-ttu-id="df072-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="df072-108">**Member type**</span></span>|<span data-ttu-id="df072-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="df072-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="df072-110">FindPerson</span><span class="sxs-lookup"><span data-stu-id="df072-110">FindPerson</span></span>](isocialsession-findperson.md) <br/> |<span data-ttu-id="df072-111">方法</span><span class="sxs-lookup"><span data-stu-id="df072-111">Method</span></span>  <br/> |<span data-ttu-id="df072-112">获取一个字符串, 表示与_userID_参数匹配的一个或多个人员。</span><span class="sxs-lookup"><span data-stu-id="df072-112">Gets a string that represents one or more persons who match the  _userID_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="df072-113">FollowPerson</span><span class="sxs-lookup"><span data-stu-id="df072-113">FollowPerson</span></span>](isocialsession-followperson.md) <br/> |<span data-ttu-id="df072-114">方法</span><span class="sxs-lookup"><span data-stu-id="df072-114">Method</span></span>  <br/> |<span data-ttu-id="df072-115">将_emailAddress_参数标识的人员添加为社交网络上已登录用户的友元。</span><span class="sxs-lookup"><span data-stu-id="df072-115">Adds the person identified by the  _emailAddress_ parameter as a friend for the logged-on user on the social network.</span></span>  <br/> |
|[<span data-ttu-id="df072-116">GetActivities</span><span class="sxs-lookup"><span data-stu-id="df072-116">GetActivities</span></span>](isocialsession-getactivities.md) <br/> |<span data-ttu-id="df072-117">方法</span><span class="sxs-lookup"><span data-stu-id="df072-117">Method</span></span>  <br/> |<span data-ttu-id="df072-118">在 Outlook Social Connector (.osc) 1.1 中已弃用此方法。</span><span class="sxs-lookup"><span data-stu-id="df072-118">This method has been deprecated in Outlook Social Connector (OSC) 1.1.</span></span>  <br/> |
|[<span data-ttu-id="df072-119">GetLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="df072-119">GetLoggedOnUser</span></span>](isocialsession-getloggedonuser.md) <br/> |<span data-ttu-id="df072-120">方法</span><span class="sxs-lookup"><span data-stu-id="df072-120">Method</span></span>  <br/> |<span data-ttu-id="df072-121">获取一个[ISocialProfile](isocialprofileisocialperson.md)接口, 该接口表示已登录的用户。</span><span class="sxs-lookup"><span data-stu-id="df072-121">Gets an [ISocialProfile](isocialprofileisocialperson.md) interface that represents the logged-on user.</span></span>  <br/> |
|[<span data-ttu-id="df072-122">GetLogonUrl</span><span class="sxs-lookup"><span data-stu-id="df072-122">GetLogonUrl</span></span>](isocialsession-getlogonurl.md) <br/> |<span data-ttu-id="df072-123">方法</span><span class="sxs-lookup"><span data-stu-id="df072-123">Method</span></span>  <br/> |<span data-ttu-id="df072-124">获取一个字符串, 表示用于在 web 身份验证期间向用户呈现基于浏览器的表单的 URL。</span><span class="sxs-lookup"><span data-stu-id="df072-124">Gets a string that represents a URL that is used for presenting a browser-based form to the user during web authentication.</span></span>  <br/> |
|[<span data-ttu-id="df072-125">GetNetworkIdentifier</span><span class="sxs-lookup"><span data-stu-id="df072-125">GetNetworkIdentifier</span></span>](isocialsession-getnetworkidentifier.md) <br/> |<span data-ttu-id="df072-126">方法</span><span class="sxs-lookup"><span data-stu-id="df072-126">Method</span></span>  <br/> |<span data-ttu-id="df072-127">获取一个字符串, 表示给定的社交网络连接的唯一社交网络标识符。</span><span class="sxs-lookup"><span data-stu-id="df072-127">Gets a string that represents a unique social network identifier for a given social network connection.</span></span>  <br/> |
|[<span data-ttu-id="df072-128">GetPerson</span><span class="sxs-lookup"><span data-stu-id="df072-128">GetPerson</span></span>](isocialsession-getperson.md) <br/> |<span data-ttu-id="df072-129">方法</span><span class="sxs-lookup"><span data-stu-id="df072-129">Method</span></span>  <br/> |<span data-ttu-id="df072-130">获取基于_userID_参数的[ISocialPerson](isocialpersoniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="df072-130">Gets an [ISocialPerson](isocialpersoniunknown.md) interface based on the  _userID_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="df072-131">LoggedOnUserID</span><span class="sxs-lookup"><span data-stu-id="df072-131">LoggedOnUserID</span></span>](isocialsession-loggedonuserid.md) <br/> |<span data-ttu-id="df072-132">属性</span><span class="sxs-lookup"><span data-stu-id="df072-132">Property</span></span>  <br/> |<span data-ttu-id="df072-133">返回一个字符串, 表示当前登录的用户的社交网络用户 ID。</span><span class="sxs-lookup"><span data-stu-id="df072-133">Returns a string that represents the social network user ID of the user who is currently logged on.</span></span>  <br/> |
|[<span data-ttu-id="df072-134">LoggedOnUserName</span><span class="sxs-lookup"><span data-stu-id="df072-134">LoggedOnUserName</span></span>](isocialsession-loggedonusername.md) <br/> |<span data-ttu-id="df072-135">属性</span><span class="sxs-lookup"><span data-stu-id="df072-135">Property</span></span>  <br/> |<span data-ttu-id="df072-136">返回一个字符串, 表示登录时使用的用户名。</span><span class="sxs-lookup"><span data-stu-id="df072-136">Returns a string that represents the user name that is used when logging on.</span></span>  <br/> |
|[<span data-ttu-id="df072-137">登录</span><span class="sxs-lookup"><span data-stu-id="df072-137">Logon</span></span>](isocialsession-logon.md) <br/> |<span data-ttu-id="df072-138">方法</span><span class="sxs-lookup"><span data-stu-id="df072-138">Method</span></span>  <br/> |<span data-ttu-id="df072-139">使用指定的用户名和密码登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="df072-139">Logs on to the social network site by using the specified user name and password.</span></span>  <br/> |
|[<span data-ttu-id="df072-140">LogonWeb</span><span class="sxs-lookup"><span data-stu-id="df072-140">LogonWeb</span></span>](isocialsession-logonweb.md) <br/> |<span data-ttu-id="df072-141">方法</span><span class="sxs-lookup"><span data-stu-id="df072-141">Method</span></span>  <br/> |<span data-ttu-id="df072-142">使用基于表单的身份验证登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="df072-142">Logs on to the social network site by using forms-based authentication.</span></span>  <br/> |
|[<span data-ttu-id="df072-143">SiteUrl</span><span class="sxs-lookup"><span data-stu-id="df072-143">SiteUrl</span></span>](isocialsession-siteurl.md) <br/> |<span data-ttu-id="df072-144">属性</span><span class="sxs-lookup"><span data-stu-id="df072-144">Property</span></span>  <br/> |<span data-ttu-id="df072-145">设置社交网络网站 URL。</span><span class="sxs-lookup"><span data-stu-id="df072-145">Sets the social network site URL.</span></span>  <br/> |
|[<span data-ttu-id="df072-146">UnFollowPerson</span><span class="sxs-lookup"><span data-stu-id="df072-146">UnFollowPerson</span></span>](isocialsession-unfollowperson.md) <br/> |<span data-ttu-id="df072-147">方法</span><span class="sxs-lookup"><span data-stu-id="df072-147">Method</span></span>  <br/> |<span data-ttu-id="df072-148">删除由_userID_参数标识为社交网络上的友元的人员。</span><span class="sxs-lookup"><span data-stu-id="df072-148">Removes the person identified by the  _userID_ parameter as a friend on the social network.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="df072-149">说明</span><span class="sxs-lookup"><span data-stu-id="df072-149">Remarks</span></span>

<span data-ttu-id="df072-150">一个 .osc 提供程序必须实现此接口才能与 .osc 进行通信。</span><span class="sxs-lookup"><span data-stu-id="df072-150">An OSC provider must implement this interface to communicate with the OSC.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="df072-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df072-151">See also</span></span>

- [<span data-ttu-id="df072-152">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="df072-152">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

