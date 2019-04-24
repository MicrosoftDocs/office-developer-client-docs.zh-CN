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
ms.openlocfilehash: 57b65f8423cbbc48e3eac066c45cab0fcc90fe18
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316196"
---
# <a name="pidtagfreebusyentryids-canonical-property"></a><span data-ttu-id="67134-103">PidTagFreeBusyEntryIds 规范属性</span><span class="sxs-lookup"><span data-stu-id="67134-103">PidTagFreeBusyEntryIds Canonical Property</span></span>

  
  
<span data-ttu-id="67134-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="67134-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="67134-105">包含代理信息消息的**entryid** 、登录用户的忙/闲消息以及其**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 等于 "FreeBusy Data" 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="67134-105">Contains the **EntryIDs** for the delegate information message, the free/busy message of the logged in user, and the folder whose **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) is equal to "FreeBusy Data."</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="67134-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="67134-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="67134-107">PR_FREEBUSY_ENTRYIDS</span><span class="sxs-lookup"><span data-stu-id="67134-107">PR_FREEBUSY_ENTRYIDS</span></span>  <br/> |
|<span data-ttu-id="67134-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="67134-108">Identifier:</span></span>  <br/> |<span data-ttu-id="67134-109">0x36E4</span><span class="sxs-lookup"><span data-stu-id="67134-109">0x36E4</span></span>  <br/> |
|<span data-ttu-id="67134-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="67134-110">Data type:</span></span>  <br/> |<span data-ttu-id="67134-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="67134-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="67134-112">区域：</span><span class="sxs-lookup"><span data-stu-id="67134-112">Area:</span></span>  <br/> |<span data-ttu-id="67134-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="67134-113">MAPI container</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="67134-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="67134-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="67134-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="67134-115">Protocol specifications</span></span>

<span data-ttu-id="67134-116">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67134-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67134-117">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="67134-117">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="67134-118">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67134-118">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67134-119">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="67134-119">Publishes the availability of a user or resource.</span></span>
    
<span data-ttu-id="67134-120">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67134-120">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67134-121">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历项目代表另一个用户操作时与之进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="67134-121">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar items when they act on behalf of another user.</span></span>
    
<span data-ttu-id="67134-122">[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67134-122">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67134-123">指定用于创建和定位邮箱中的特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="67134-123">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="67134-124">头文件</span><span class="sxs-lookup"><span data-stu-id="67134-124">Header files</span></span>

<span data-ttu-id="67134-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="67134-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="67134-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="67134-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="67134-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="67134-127">Mapitags.h</span></span>
  
> <span data-ttu-id="67134-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="67134-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="67134-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67134-129">See also</span></span>



[<span data-ttu-id="67134-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="67134-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="67134-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="67134-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="67134-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="67134-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="67134-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="67134-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

