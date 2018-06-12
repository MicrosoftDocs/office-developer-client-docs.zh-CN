---
title: PidTagIpmTaskEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmTaskEntryId
api_type:
- HeaderDef
ms.assetid: ec8b7486-b547-4a4e-96e5-1fc825b23f3d
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: aa1c4979ce66a0e32aea7b04ef4412679545b3de
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777781"
---
# <a name="pidtagipmtaskentryid-canonical-property"></a><span data-ttu-id="09754-103">PidTagIpmTaskEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="09754-103">PidTagIpmTaskEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="09754-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="09754-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="09754-105">包含 Outlook 任务文件夹的**EntryID** 。</span><span class="sxs-lookup"><span data-stu-id="09754-105">Contains the **EntryID** of the Outlook Tasks folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="09754-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="09754-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="09754-107">PR_IPM_TASK_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="09754-107">PR_IPM_TASK_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="09754-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="09754-108">Identifier:</span></span>  <br/> |<span data-ttu-id="09754-109">0x36D4</span><span class="sxs-lookup"><span data-stu-id="09754-109">0x36D4</span></span>  <br/> |
|<span data-ttu-id="09754-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="09754-110">Data type:</span></span>  <br/> |<span data-ttu-id="09754-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="09754-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="09754-112">区域：</span><span class="sxs-lookup"><span data-stu-id="09754-112">Area:</span></span>  <br/> |<span data-ttu-id="09754-113">Folder</span><span class="sxs-lookup"><span data-stu-id="09754-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="09754-114">备注</span><span class="sxs-lookup"><span data-stu-id="09754-114">Remarks</span></span>

<span data-ttu-id="09754-115">此属性是读取或写入使用的属性和 Stream 对象的协议。</span><span class="sxs-lookup"><span data-stu-id="09754-115">This property is read or written by using the Property and Stream Object protocol.</span></span> <span data-ttu-id="09754-116">它是读取和写入收件箱或根文件夹。</span><span class="sxs-lookup"><span data-stu-id="09754-116">It is read from and written to the Inbox or Root folder.</span></span> <span data-ttu-id="09754-117">存储的主邮件用户，并且它必须使用的根文件夹存储区时，代理用户时，实现必须使用收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="09754-117">The implementation must use the Inbox folder when the store is that of the primary messaging user, and it must use the Root folder when the store is that of a delegate user.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="09754-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="09754-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="09754-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="09754-119">Protocol specifications</span></span>

<span data-ttu-id="09754-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="09754-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="09754-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="09754-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="09754-122">[[MS OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="09754-122">[[MS-OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="09754-123">指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="09754-123">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="09754-124">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="09754-124">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="09754-125">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="09754-125">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="09754-126">头文件</span><span class="sxs-lookup"><span data-stu-id="09754-126">Header files</span></span>

<span data-ttu-id="09754-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="09754-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="09754-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="09754-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="09754-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="09754-129">Mapitags.h</span></span>
  
> <span data-ttu-id="09754-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="09754-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="09754-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09754-131">See also</span></span>



[<span data-ttu-id="09754-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="09754-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="09754-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="09754-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="09754-134">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="09754-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="09754-135">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="09754-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

