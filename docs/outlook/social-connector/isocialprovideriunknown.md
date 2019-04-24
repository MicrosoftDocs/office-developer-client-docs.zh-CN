---
title: ISocialProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1c9f4dd4-65f6-446f-8b86-a375ce402658
description: 表示 Outlook Social Connector (.osc) 提供程序的实例。
ms.openlocfilehash: f28b8343d92b09455b6049f421b839efbda21c1a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285482"
---
# <a name="isocialprovider--iunknown"></a><span data-ttu-id="6b2d7-103">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6b2d7-103">ISocialProvider : IUnknown</span></span>

<span data-ttu-id="6b2d7-104">表示 Outlook Social Connector (.osc) 提供程序的实例。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-104">Represents an instance of an Outlook Social Connector (OSC) provider.</span></span>
  
## <a name="members"></a><span data-ttu-id="6b2d7-105">Members</span><span class="sxs-lookup"><span data-stu-id="6b2d7-105">Members</span></span>

<span data-ttu-id="6b2d7-106">下表显示了**ISocialProvider**接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-106">The following table shows the members that are available on the **ISocialProvider** interface.</span></span> 
  
|<span data-ttu-id="6b2d7-107">**Name**</span><span class="sxs-lookup"><span data-stu-id="6b2d7-107">**Name**</span></span>|<span data-ttu-id="6b2d7-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="6b2d7-108">**Member type**</span></span>|<span data-ttu-id="6b2d7-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="6b2d7-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6b2d7-110">DefaultSiteUrls</span><span class="sxs-lookup"><span data-stu-id="6b2d7-110">DefaultSiteUrls</span></span>](isocialprovider-defaultsiteurls.md) <br/> |<span data-ttu-id="6b2d7-111">属性</span><span class="sxs-lookup"><span data-stu-id="6b2d7-111">Property</span></span>  <br/> |<span data-ttu-id="6b2d7-112">返回一个字符串数组, 这些字符串指定 .osc 提供程序的网站 url。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-112">Returns an array of strings that specify site URLs for the OSC provider.</span></span>  <br/> |
|[<span data-ttu-id="6b2d7-113">GetAutoConfiguredSession</span><span class="sxs-lookup"><span data-stu-id="6b2d7-113">GetAutoConfiguredSession</span></span>](isocialprovider-getautoconfiguredsession.md) <br/> |<span data-ttu-id="6b2d7-114">方法</span><span class="sxs-lookup"><span data-stu-id="6b2d7-114">Method</span></span>  <br/> |<span data-ttu-id="6b2d7-115">获取自动配置的 [ISocialSession](isocialsessioniunknown.md) 界面。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-115">Gets an automatically configured [ISocialSession](isocialsessioniunknown.md) interface.</span></span>  <br/> |
|[<span data-ttu-id="6b2d7-116">GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="6b2d7-116">GetCapabilities</span></span>](isocialprovider-getcapabilities.md) <br/> |<span data-ttu-id="6b2d7-117">方法</span><span class="sxs-lookup"><span data-stu-id="6b2d7-117">Method</span></span>  <br/> |<span data-ttu-id="6b2d7-118">获取描述提供程序功能的字符串。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-118">Gets a string that describes provider capabilities.</span></span>  <br/> |
|[<span data-ttu-id="6b2d7-119">GetSession</span><span class="sxs-lookup"><span data-stu-id="6b2d7-119">GetSession</span></span>](isocialprovider-getsession.md) <br/> |<span data-ttu-id="6b2d7-120">方法</span><span class="sxs-lookup"><span data-stu-id="6b2d7-120">Method</span></span>  <br/> |<span data-ttu-id="6b2d7-121">获取[ISocialSession](isocialsessioniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-121">Gets an [ISocialSession](isocialsessioniunknown.md) interface.</span></span>  <br/> |
|[<span data-ttu-id="6b2d7-122">GetStatusSettings</span><span class="sxs-lookup"><span data-stu-id="6b2d7-122">GetStatusSettings</span></span>](isocialprovider-getstatussettings.md) <br/> |<span data-ttu-id="6b2d7-123">方法</span><span class="sxs-lookup"><span data-stu-id="6b2d7-123">Method</span></span>  <br/> |<span data-ttu-id="6b2d7-124">目前不支持此方法。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-124">This method is currently not supported.</span></span>  <br/> |
|[<span data-ttu-id="6b2d7-125">Load</span><span class="sxs-lookup"><span data-stu-id="6b2d7-125">Load</span></span>](isocialprovider-load.md) <br/> |<span data-ttu-id="6b2d7-126">方法</span><span class="sxs-lookup"><span data-stu-id="6b2d7-126">Method</span></span>  <br/> |<span data-ttu-id="6b2d7-127">初始化 .osc 提供程序。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-127">Initializes the OSC provider.</span></span>  <br/> |
|[<span data-ttu-id="6b2d7-128">SocialNetworkGuid</span><span class="sxs-lookup"><span data-stu-id="6b2d7-128">SocialNetworkGuid</span></span>](isocialprovider-socialnetworkguid.md) <br/> |<span data-ttu-id="6b2d7-129">属性</span><span class="sxs-lookup"><span data-stu-id="6b2d7-129">Property</span></span>  <br/> |<span data-ttu-id="6b2d7-130">返回表示社交网络的唯一标识符的 GUID。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-130">Returns a GUID that represents a unique identifier for the social network.</span></span>  <br/> |
|[<span data-ttu-id="6b2d7-131">SocialNetworkIcon</span><span class="sxs-lookup"><span data-stu-id="6b2d7-131">SocialNetworkIcon</span></span>](isocialprovider-socialnetworkicon.md) <br/> |<span data-ttu-id="6b2d7-132">属性</span><span class="sxs-lookup"><span data-stu-id="6b2d7-132">Property</span></span>  <br/> |<span data-ttu-id="6b2d7-133">返回表示社交网络图标的字节数组。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-133">Returns an array of bytes that represents the icon for the social network.</span></span>  <br/> |
|[<span data-ttu-id="6b2d7-134">SocialNetworkName</span><span class="sxs-lookup"><span data-stu-id="6b2d7-134">SocialNetworkName</span></span>](isocialprovider-socialnetworkname.md) <br/> |<span data-ttu-id="6b2d7-135">属性</span><span class="sxs-lookup"><span data-stu-id="6b2d7-135">Property</span></span>  <br/> |<span data-ttu-id="6b2d7-136">返回一个字符串, 表示社交网络名称。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-136">Returns a string that represents the social network name.</span></span>  <br/> |
|[<span data-ttu-id="6b2d7-137">Version</span><span class="sxs-lookup"><span data-stu-id="6b2d7-137">Version</span></span>](isocialprovider-version.md) <br/> |<span data-ttu-id="6b2d7-138">属性</span><span class="sxs-lookup"><span data-stu-id="6b2d7-138">Property</span></span>  <br/> |<span data-ttu-id="6b2d7-139">返回一个 string 类型的值, 该值代表此社交网络提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-139">Returns a string that represents the version number of the provider for this social network.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6b2d7-140">注解</span><span class="sxs-lookup"><span data-stu-id="6b2d7-140">Remarks</span></span>

<span data-ttu-id="6b2d7-141">一个 .osc 提供程序必须实现此接口才能与 .osc 进行通信。</span><span class="sxs-lookup"><span data-stu-id="6b2d7-141">An OSC provider must implement this interface to communicate with the OSC.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6b2d7-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b2d7-142">See also</span></span>

- [<span data-ttu-id="6b2d7-143">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="6b2d7-143">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

