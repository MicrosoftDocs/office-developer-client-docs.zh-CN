---
title: ISocialSession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0fe423d7-b044-479b-89ad-c39620eedd65
description: 代表与社交网络站点的连接。
ms.openlocfilehash: ee3a8aa72ea187b4c211bc7a49e8a2dbe170adad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779250"
---
# <a name="isocialsession--iunknown"></a><span data-ttu-id="42e84-103">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="42e84-103">ISocialSession : IUnknown</span></span>

<span data-ttu-id="42e84-104">代表与社交网络站点的连接。</span><span class="sxs-lookup"><span data-stu-id="42e84-104">Represents a connection to a social network site.</span></span>
  
## <a name="members"></a><span data-ttu-id="42e84-105">Members</span><span class="sxs-lookup"><span data-stu-id="42e84-105">Members</span></span>

<span data-ttu-id="42e84-106">下表显示了**ISocialSession**接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="42e84-106">The following table shows the members that are available on the **ISocialSession** interface.</span></span> 
  
|<span data-ttu-id="42e84-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="42e84-107">**Name**</span></span>|<span data-ttu-id="42e84-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="42e84-108">**Member type**</span></span>|<span data-ttu-id="42e84-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="42e84-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="42e84-110">FindPerson</span><span class="sxs-lookup"><span data-stu-id="42e84-110">FindPerson</span></span>](isocialsession-findperson.md) <br/> |<span data-ttu-id="42e84-111">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-111">Method</span></span>  <br/> |<span data-ttu-id="42e84-112">获取一个值，该值代表一个或多个人员_userID_参数匹配的字符串。</span><span class="sxs-lookup"><span data-stu-id="42e84-112">Gets a string that represents one or more persons who match the  _userID_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="42e84-113">FollowPerson</span><span class="sxs-lookup"><span data-stu-id="42e84-113">FollowPerson</span></span>](isocialsession-followperson.md) <br/> |<span data-ttu-id="42e84-114">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-114">Method</span></span>  <br/> |<span data-ttu-id="42e84-115">添加为朋友社交网络登录用户的_电子邮件地址_参数标识的人员。</span><span class="sxs-lookup"><span data-stu-id="42e84-115">Adds the person identified by the  _emailAddress_ parameter as a friend for the logged-on user on the social network.</span></span>  <br/> |
|[<span data-ttu-id="42e84-116">GetActivities</span><span class="sxs-lookup"><span data-stu-id="42e84-116">GetActivities</span></span>](isocialsession-getactivities.md) <br/> |<span data-ttu-id="42e84-117">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-117">Method</span></span>  <br/> |<span data-ttu-id="42e84-118">此方法已被弃用在 Outlook Social Connector (OSC) 1.1。</span><span class="sxs-lookup"><span data-stu-id="42e84-118">This method has been deprecated in Outlook Social Connector (OSC) 1.1.</span></span>  <br/> |
|[<span data-ttu-id="42e84-119">GetLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="42e84-119">GetLoggedOnUser</span></span>](isocialsession-getloggedonuser.md) <br/> |<span data-ttu-id="42e84-120">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-120">Method</span></span>  <br/> |<span data-ttu-id="42e84-121">获取一个值，该值代表登录用户的[ISocialProfile](isocialprofileisocialperson.md)接口。</span><span class="sxs-lookup"><span data-stu-id="42e84-121">Gets an [ISocialProfile](isocialprofileisocialperson.md) interface that represents the logged-on user.</span></span>  <br/> |
|[<span data-ttu-id="42e84-122">GetLogonUrl</span><span class="sxs-lookup"><span data-stu-id="42e84-122">GetLogonUrl</span></span>](isocialsession-getlogonurl.md) <br/> |<span data-ttu-id="42e84-123">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-123">Method</span></span>  <br/> |<span data-ttu-id="42e84-124">获取一个字符串，表示用于 web 身份验证过程中显示给用户的基于浏览器的表单的 URL。</span><span class="sxs-lookup"><span data-stu-id="42e84-124">Gets a string that represents a URL that is used for presenting a browser-based form to the user during web authentication.</span></span>  <br/> |
|[<span data-ttu-id="42e84-125">GetNetworkIdentifier</span><span class="sxs-lookup"><span data-stu-id="42e84-125">GetNetworkIdentifier</span></span>](isocialsession-getnetworkidentifier.md) <br/> |<span data-ttu-id="42e84-126">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-126">Method</span></span>  <br/> |<span data-ttu-id="42e84-127">获取一个字符串，表示对于给定的社交网络连接的唯一的社交网络标识符。</span><span class="sxs-lookup"><span data-stu-id="42e84-127">Gets a string that represents a unique social network identifier for a given social network connection.</span></span>  <br/> |
|[<span data-ttu-id="42e84-128">GetPerson</span><span class="sxs-lookup"><span data-stu-id="42e84-128">GetPerson</span></span>](isocialsession-getperson.md) <br/> |<span data-ttu-id="42e84-129">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-129">Method</span></span>  <br/> |<span data-ttu-id="42e84-130">获取基于_用户 Id_参数[ISocialPerson](isocialpersoniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="42e84-130">Gets an [ISocialPerson](isocialpersoniunknown.md) interface based on the  _userID_ parameter.</span></span>  <br/> |
|[<span data-ttu-id="42e84-131">LoggedOnUserID</span><span class="sxs-lookup"><span data-stu-id="42e84-131">LoggedOnUserID</span></span>](isocialsession-loggedonuserid.md) <br/> |<span data-ttu-id="42e84-132">属性</span><span class="sxs-lookup"><span data-stu-id="42e84-132">Property</span></span>  <br/> |<span data-ttu-id="42e84-133">返回一个字符串，表示当前已登录的用户的社交网络用户 ID。</span><span class="sxs-lookup"><span data-stu-id="42e84-133">Returns a string that represents the social network user ID of the user who is currently logged on.</span></span>  <br/> |
|[<span data-ttu-id="42e84-134">LoggedOnUserName</span><span class="sxs-lookup"><span data-stu-id="42e84-134">LoggedOnUserName</span></span>](isocialsession-loggedonusername.md) <br/> |<span data-ttu-id="42e84-135">属性</span><span class="sxs-lookup"><span data-stu-id="42e84-135">Property</span></span>  <br/> |<span data-ttu-id="42e84-136">返回一个字符串，表示在登录时使用的用户名。</span><span class="sxs-lookup"><span data-stu-id="42e84-136">Returns a string that represents the user name that is used when logging on.</span></span>  <br/> |
|[<span data-ttu-id="42e84-137">登录</span><span class="sxs-lookup"><span data-stu-id="42e84-137">Logon</span></span>](isocialsession-logon.md) <br/> |<span data-ttu-id="42e84-138">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-138">Method</span></span>  <br/> |<span data-ttu-id="42e84-139">登录到社交网络站点使用指定的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="42e84-139">Logs on to the social network site by using the specified user name and password.</span></span>  <br/> |
|[<span data-ttu-id="42e84-140">LogonWeb</span><span class="sxs-lookup"><span data-stu-id="42e84-140">LogonWeb</span></span>](isocialsession-logonweb.md) <br/> |<span data-ttu-id="42e84-141">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-141">Method</span></span>  <br/> |<span data-ttu-id="42e84-142">登录到使用基于表单的身份验证的社交网络站点。</span><span class="sxs-lookup"><span data-stu-id="42e84-142">Logs on to the social network site by using forms-based authentication.</span></span>  <br/> |
|[<span data-ttu-id="42e84-143">SiteUrl</span><span class="sxs-lookup"><span data-stu-id="42e84-143">SiteUrl</span></span>](isocialsession-siteurl.md) <br/> |<span data-ttu-id="42e84-144">属性</span><span class="sxs-lookup"><span data-stu-id="42e84-144">Property</span></span>  <br/> |<span data-ttu-id="42e84-145">设置的社交网络站点的 URL。</span><span class="sxs-lookup"><span data-stu-id="42e84-145">Sets the social network site URL.</span></span>  <br/> |
|[<span data-ttu-id="42e84-146">UnFollowPerson</span><span class="sxs-lookup"><span data-stu-id="42e84-146">UnFollowPerson</span></span>](isocialsession-unfollowperson.md) <br/> |<span data-ttu-id="42e84-147">方法</span><span class="sxs-lookup"><span data-stu-id="42e84-147">Method</span></span>  <br/> |<span data-ttu-id="42e84-148">删除为社交网络上朋友_userID_参数标识的人员。</span><span class="sxs-lookup"><span data-stu-id="42e84-148">Removes the person identified by the  _userID_ parameter as a friend on the social network.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="42e84-149">说明</span><span class="sxs-lookup"><span data-stu-id="42e84-149">Remarks</span></span>

<span data-ttu-id="42e84-150">OSC 提供程序必须实现此接口与 OSC 进行通信。</span><span class="sxs-lookup"><span data-stu-id="42e84-150">An OSC provider must implement this interface to communicate with the OSC.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="42e84-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42e84-151">See also</span></span>

- [<span data-ttu-id="42e84-152">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="42e84-152">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

