---
title: PidTagFreeBusyEntryIds 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFreeBusyEntryIds
api_type:
- HeaderDef
ms.assetid: 8bc40ebf-76f2-49dd-af4b-4095bc07c639
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 603adf8df0c00efc592572fd9a46434f42845011
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564736"
---
# <a name="pidtagfreebusyentryids-canonical-property"></a><span data-ttu-id="66b5b-103">PidTagFreeBusyEntryIds 规范属性</span><span class="sxs-lookup"><span data-stu-id="66b5b-103">PidTagFreeBusyEntryIds Canonical Property</span></span>

  
  
<span data-ttu-id="66b5b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66b5b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="66b5b-105">包含**Entryid**委托信息消息、 登录的用户，以及其**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 等于"FreeBusy 数据。"文件夹的忙/闲消息</span><span class="sxs-lookup"><span data-stu-id="66b5b-105">Contains the **EntryIDs** for the delegate information message, the free/busy message of the logged in user, and the folder whose **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) is equal to "FreeBusy Data."</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="66b5b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="66b5b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="66b5b-107">PR_FREEBUSY_ENTRYIDS</span><span class="sxs-lookup"><span data-stu-id="66b5b-107">PR_FREEBUSY_ENTRYIDS</span></span>  <br/> |
|<span data-ttu-id="66b5b-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="66b5b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="66b5b-109">0x36E4</span><span class="sxs-lookup"><span data-stu-id="66b5b-109">0x36E4</span></span>  <br/> |
|<span data-ttu-id="66b5b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="66b5b-110">Data type:</span></span>  <br/> |<span data-ttu-id="66b5b-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="66b5b-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="66b5b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="66b5b-112">Area:</span></span>  <br/> |<span data-ttu-id="66b5b-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="66b5b-113">MAPI container</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="66b5b-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="66b5b-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="66b5b-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="66b5b-115">Protocol specifications</span></span>

<span data-ttu-id="66b5b-116">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66b5b-116">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66b5b-117">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="66b5b-117">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="66b5b-118">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66b5b-118">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66b5b-119">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="66b5b-119">Publishes the availability of a user or resource.</span></span>
    
<span data-ttu-id="66b5b-120">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66b5b-120">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66b5b-121">指定连接到和配置为代理人，以及与邮件和日历项目交互的邮箱，当这些代表其他用户操作的方法。</span><span class="sxs-lookup"><span data-stu-id="66b5b-121">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar items when they act on behalf of another user.</span></span>
    
<span data-ttu-id="66b5b-122">[[MS OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66b5b-122">[[MS-OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66b5b-123">指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="66b5b-123">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="66b5b-124">头文件</span><span class="sxs-lookup"><span data-stu-id="66b5b-124">Header files</span></span>

<span data-ttu-id="66b5b-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="66b5b-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="66b5b-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="66b5b-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="66b5b-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="66b5b-127">Mapitags.h</span></span>
  
> <span data-ttu-id="66b5b-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="66b5b-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="66b5b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66b5b-129">See also</span></span>



[<span data-ttu-id="66b5b-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="66b5b-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="66b5b-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="66b5b-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="66b5b-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="66b5b-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="66b5b-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="66b5b-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

