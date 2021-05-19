---
title: ISocialProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1c9f4dd4-65f6-446f-8b86-a375ce402658
description: 表示 OSC 提供程序中的 Outlook Social Connector () 实例。
ms.openlocfilehash: f28b8343d92b09455b6049f421b839efbda21c1a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409956"
---
# <a name="isocialprovider--iunknown"></a><span data-ttu-id="11be9-103">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="11be9-103">ISocialProvider : IUnknown</span></span>

<span data-ttu-id="11be9-104">表示 OSC 提供程序中的 Outlook Social Connector () 实例。</span><span class="sxs-lookup"><span data-stu-id="11be9-104">Represents an instance of an Outlook Social Connector (OSC) provider.</span></span>
  
## <a name="members"></a><span data-ttu-id="11be9-105">Members</span><span class="sxs-lookup"><span data-stu-id="11be9-105">Members</span></span>

<span data-ttu-id="11be9-106">下表显示了 **ISocialProvider** 接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="11be9-106">The following table shows the members that are available on the **ISocialProvider** interface.</span></span> 
  
|<span data-ttu-id="11be9-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="11be9-107">**Name**</span></span>|<span data-ttu-id="11be9-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="11be9-108">**Member type**</span></span>|<span data-ttu-id="11be9-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="11be9-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="11be9-110">DefaultSiteUrls</span><span class="sxs-lookup"><span data-stu-id="11be9-110">DefaultSiteUrls</span></span>](isocialprovider-defaultsiteurls.md) <br/> |<span data-ttu-id="11be9-111">属性</span><span class="sxs-lookup"><span data-stu-id="11be9-111">Property</span></span>  <br/> |<span data-ttu-id="11be9-112">返回一个字符串数组，该数组指定 OSC 提供程序的网站 URL。</span><span class="sxs-lookup"><span data-stu-id="11be9-112">Returns an array of strings that specify site URLs for the OSC provider.</span></span>  <br/> |
|[<span data-ttu-id="11be9-113">GetAutoConfiguredSession</span><span class="sxs-lookup"><span data-stu-id="11be9-113">GetAutoConfiguredSession</span></span>](isocialprovider-getautoconfiguredsession.md) <br/> |<span data-ttu-id="11be9-114">方法</span><span class="sxs-lookup"><span data-stu-id="11be9-114">Method</span></span>  <br/> |<span data-ttu-id="11be9-115">获取自动配置的 [ISocialSession](isocialsessioniunknown.md) 界面。</span><span class="sxs-lookup"><span data-stu-id="11be9-115">Gets an automatically configured [ISocialSession](isocialsessioniunknown.md) interface.</span></span>  <br/> |
|[<span data-ttu-id="11be9-116">GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="11be9-116">GetCapabilities</span></span>](isocialprovider-getcapabilities.md) <br/> |<span data-ttu-id="11be9-117">方法</span><span class="sxs-lookup"><span data-stu-id="11be9-117">Method</span></span>  <br/> |<span data-ttu-id="11be9-118">获取一个描述提供程序功能的字符串。</span><span class="sxs-lookup"><span data-stu-id="11be9-118">Gets a string that describes provider capabilities.</span></span>  <br/> |
|[<span data-ttu-id="11be9-119">GetSession</span><span class="sxs-lookup"><span data-stu-id="11be9-119">GetSession</span></span>](isocialprovider-getsession.md) <br/> |<span data-ttu-id="11be9-120">方法</span><span class="sxs-lookup"><span data-stu-id="11be9-120">Method</span></span>  <br/> |<span data-ttu-id="11be9-121">获取 [ISocialSession](isocialsessioniunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="11be9-121">Gets an [ISocialSession](isocialsessioniunknown.md) interface.</span></span>  <br/> |
|[<span data-ttu-id="11be9-122">GetStatusSettings</span><span class="sxs-lookup"><span data-stu-id="11be9-122">GetStatusSettings</span></span>](isocialprovider-getstatussettings.md) <br/> |<span data-ttu-id="11be9-123">方法</span><span class="sxs-lookup"><span data-stu-id="11be9-123">Method</span></span>  <br/> |<span data-ttu-id="11be9-124">此方法当前不受支持。</span><span class="sxs-lookup"><span data-stu-id="11be9-124">This method is currently not supported.</span></span>  <br/> |
|[<span data-ttu-id="11be9-125">Load</span><span class="sxs-lookup"><span data-stu-id="11be9-125">Load</span></span>](isocialprovider-load.md) <br/> |<span data-ttu-id="11be9-126">方法</span><span class="sxs-lookup"><span data-stu-id="11be9-126">Method</span></span>  <br/> |<span data-ttu-id="11be9-127">初始化 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="11be9-127">Initializes the OSC provider.</span></span>  <br/> |
|[<span data-ttu-id="11be9-128">SocialNetworkGuid</span><span class="sxs-lookup"><span data-stu-id="11be9-128">SocialNetworkGuid</span></span>](isocialprovider-socialnetworkguid.md) <br/> |<span data-ttu-id="11be9-129">属性</span><span class="sxs-lookup"><span data-stu-id="11be9-129">Property</span></span>  <br/> |<span data-ttu-id="11be9-130">返回表示社交网络的唯一标识符的 GUID。</span><span class="sxs-lookup"><span data-stu-id="11be9-130">Returns a GUID that represents a unique identifier for the social network.</span></span>  <br/> |
|[<span data-ttu-id="11be9-131">SocialNetworkIcon</span><span class="sxs-lookup"><span data-stu-id="11be9-131">SocialNetworkIcon</span></span>](isocialprovider-socialnetworkicon.md) <br/> |<span data-ttu-id="11be9-132">属性</span><span class="sxs-lookup"><span data-stu-id="11be9-132">Property</span></span>  <br/> |<span data-ttu-id="11be9-133">返回一个字节数组，该数组代表社交网络的图标。</span><span class="sxs-lookup"><span data-stu-id="11be9-133">Returns an array of bytes that represents the icon for the social network.</span></span>  <br/> |
|[<span data-ttu-id="11be9-134">SocialNetworkName</span><span class="sxs-lookup"><span data-stu-id="11be9-134">SocialNetworkName</span></span>](isocialprovider-socialnetworkname.md) <br/> |<span data-ttu-id="11be9-135">属性</span><span class="sxs-lookup"><span data-stu-id="11be9-135">Property</span></span>  <br/> |<span data-ttu-id="11be9-136">返回一个代表社交网络名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="11be9-136">Returns a string that represents the social network name.</span></span>  <br/> |
|[<span data-ttu-id="11be9-137">版本</span><span class="sxs-lookup"><span data-stu-id="11be9-137">Version</span></span>](isocialprovider-version.md) <br/> |<span data-ttu-id="11be9-138">属性</span><span class="sxs-lookup"><span data-stu-id="11be9-138">Property</span></span>  <br/> |<span data-ttu-id="11be9-139">返回一个字符串，该字符串表示此社交网络的提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="11be9-139">Returns a string that represents the version number of the provider for this social network.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="11be9-140">备注</span><span class="sxs-lookup"><span data-stu-id="11be9-140">Remarks</span></span>

<span data-ttu-id="11be9-141">OSC 提供程序必须实现此接口以与 OSC 通信。</span><span class="sxs-lookup"><span data-stu-id="11be9-141">An OSC provider must implement this interface to communicate with the OSC.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="11be9-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11be9-142">See also</span></span>

- [<span data-ttu-id="11be9-143">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="11be9-143">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

