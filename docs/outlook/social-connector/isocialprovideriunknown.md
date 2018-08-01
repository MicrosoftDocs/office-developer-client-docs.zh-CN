---
title: ISocialProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1c9f4dd4-65f6-446f-8b86-a375ce402658
description: 代表 Outlook Social Connector (OSC) 提供程序的实例。
ms.openlocfilehash: 912b2d92137febe80e0d97362e0a490f138b2e66
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779348"
---
# <a name="isocialprovider--iunknown"></a><span data-ttu-id="7a4cc-103">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7a4cc-103">ISocialProvider : IUnknown</span></span>

<span data-ttu-id="7a4cc-104">代表 Outlook Social Connector (OSC) 提供程序的实例。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-104">Represents an instance of an Outlook Social Connector (OSC) provider.</span></span>
  
## <a name="members"></a><span data-ttu-id="7a4cc-105">Members</span><span class="sxs-lookup"><span data-stu-id="7a4cc-105">Members</span></span>

<span data-ttu-id="7a4cc-106">下表显示了**ISocialProvider**接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-106">The following table shows the members that are available on the **ISocialProvider** interface.</span></span> 
  
|<span data-ttu-id="7a4cc-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="7a4cc-107">**Name**</span></span>|<span data-ttu-id="7a4cc-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="7a4cc-108">**Member type**</span></span>|<span data-ttu-id="7a4cc-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a4cc-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7a4cc-110">DefaultSiteUrls</span><span class="sxs-lookup"><span data-stu-id="7a4cc-110">DefaultSiteUrls</span></span>](isocialprovider-defaultsiteurls.md) <br/> |<span data-ttu-id="7a4cc-111">属性</span><span class="sxs-lookup"><span data-stu-id="7a4cc-111">Property</span></span>  <br/> |<span data-ttu-id="7a4cc-112">返回一个指定 OSC 提供程序网站 Url 的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-112">Returns an array of strings that specify site URLs for the OSC provider.</span></span>  <br/> |
|[<span data-ttu-id="7a4cc-113">GetAutoConfiguredSession</span><span class="sxs-lookup"><span data-stu-id="7a4cc-113">GetAutoConfiguredSession</span></span>](isocialprovider-getautoconfiguredsession.md) <br/> |<span data-ttu-id="7a4cc-114">方法</span><span class="sxs-lookup"><span data-stu-id="7a4cc-114">Method</span></span>  <br/> |<span data-ttu-id="7a4cc-115">获取自动配置的 [ISocialSession](isocialsessioniunknown.md) 界面。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-115">Gets an automatically configured [ISocialSession](isocialsessioniunknown.md) interface.</span></span>  <br/> |
|[<span data-ttu-id="7a4cc-116">GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="7a4cc-116">GetCapabilities</span></span>](isocialprovider-getcapabilities.md) <br/> |<span data-ttu-id="7a4cc-117">方法</span><span class="sxs-lookup"><span data-stu-id="7a4cc-117">Method</span></span>  <br/> |<span data-ttu-id="7a4cc-118">获取一个字符串，描述提供程序功能。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-118">Gets a string that describes provider capabilities.</span></span>  <br/> |
|[<span data-ttu-id="7a4cc-119">GetSession</span><span class="sxs-lookup"><span data-stu-id="7a4cc-119">GetSession</span></span>](isocialprovider-getsession.md) <br/> |<span data-ttu-id="7a4cc-120">方法</span><span class="sxs-lookup"><span data-stu-id="7a4cc-120">Method</span></span>  <br/> |<span data-ttu-id="7a4cc-121">获取[ISocialSession](isocialsessioniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-121">Gets an [ISocialSession](isocialsessioniunknown.md) interface.</span></span>  <br/> |
|[<span data-ttu-id="7a4cc-122">GetStatusSettings</span><span class="sxs-lookup"><span data-stu-id="7a4cc-122">GetStatusSettings</span></span>](isocialprovider-getstatussettings.md) <br/> |<span data-ttu-id="7a4cc-123">方法</span><span class="sxs-lookup"><span data-stu-id="7a4cc-123">Method</span></span>  <br/> |<span data-ttu-id="7a4cc-124">当前不支持此方法。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-124">This method is currently not supported.</span></span>  <br/> |
|[<span data-ttu-id="7a4cc-125">加载</span><span class="sxs-lookup"><span data-stu-id="7a4cc-125">Load</span></span>](isocialprovider-load.md) <br/> |<span data-ttu-id="7a4cc-126">方法</span><span class="sxs-lookup"><span data-stu-id="7a4cc-126">Method</span></span>  <br/> |<span data-ttu-id="7a4cc-127">初始化 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-127">Initializes the OSC provider.</span></span>  <br/> |
|[<span data-ttu-id="7a4cc-128">SocialNetworkGuid</span><span class="sxs-lookup"><span data-stu-id="7a4cc-128">SocialNetworkGuid</span></span>](isocialprovider-socialnetworkguid.md) <br/> |<span data-ttu-id="7a4cc-129">属性</span><span class="sxs-lookup"><span data-stu-id="7a4cc-129">Property</span></span>  <br/> |<span data-ttu-id="7a4cc-130">返回一个 GUID 值，该值代表社交网络的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-130">Returns a GUID that represents a unique identifier for the social network.</span></span>  <br/> |
|[<span data-ttu-id="7a4cc-131">SocialNetworkIcon</span><span class="sxs-lookup"><span data-stu-id="7a4cc-131">SocialNetworkIcon</span></span>](isocialprovider-socialnetworkicon.md) <br/> |<span data-ttu-id="7a4cc-132">属性</span><span class="sxs-lookup"><span data-stu-id="7a4cc-132">Property</span></span>  <br/> |<span data-ttu-id="7a4cc-133">返回表示图标的社交网络的字节数组。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-133">Returns an array of bytes that represents the icon for the social network.</span></span>  <br/> |
|[<span data-ttu-id="7a4cc-134">SocialNetworkName</span><span class="sxs-lookup"><span data-stu-id="7a4cc-134">SocialNetworkName</span></span>](isocialprovider-socialnetworkname.md) <br/> |<span data-ttu-id="7a4cc-135">属性</span><span class="sxs-lookup"><span data-stu-id="7a4cc-135">Property</span></span>  <br/> |<span data-ttu-id="7a4cc-136">返回 string 类型的值，该值代表社交网络名称。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-136">Returns a string that represents the social network name.</span></span>  <br/> |
|[<span data-ttu-id="7a4cc-137">版本</span><span class="sxs-lookup"><span data-stu-id="7a4cc-137">Version</span></span>](isocialprovider-version.md) <br/> |<span data-ttu-id="7a4cc-138">属性</span><span class="sxs-lookup"><span data-stu-id="7a4cc-138">Property</span></span>  <br/> |<span data-ttu-id="7a4cc-139">返回一个字符串，表示为此社交网络提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-139">Returns a string that represents the version number of the provider for this social network.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7a4cc-140">说明</span><span class="sxs-lookup"><span data-stu-id="7a4cc-140">Remarks</span></span>

<span data-ttu-id="7a4cc-141">OSC 提供程序必须实现此接口与 OSC 进行通信。</span><span class="sxs-lookup"><span data-stu-id="7a4cc-141">An OSC provider must implement this interface to communicate with the OSC.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a4cc-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a4cc-142">See also</span></span>

- [<span data-ttu-id="7a4cc-143">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="7a4cc-143">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

