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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c3845c745dcd2c18525f147308233b94fbce70d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327840"
---
# <a name="pidtagipmtaskentryid-canonical-property"></a><span data-ttu-id="6a108-103">PidTagIpmTaskEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a108-103">PidTagIpmTaskEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="6a108-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6a108-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6a108-105">包含任务 **文件夹** Outlook条目 ID。</span><span class="sxs-lookup"><span data-stu-id="6a108-105">Contains the **EntryID** of the Outlook Tasks folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6a108-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6a108-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6a108-107">PR_IPM_TASK_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="6a108-107">PR_IPM_TASK_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="6a108-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6a108-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6a108-109">0x36D4</span><span class="sxs-lookup"><span data-stu-id="6a108-109">0x36D4</span></span>  <br/> |
|<span data-ttu-id="6a108-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6a108-110">Data type:</span></span>  <br/> |<span data-ttu-id="6a108-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6a108-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6a108-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6a108-112">Area:</span></span>  <br/> |<span data-ttu-id="6a108-113">文件夹</span><span class="sxs-lookup"><span data-stu-id="6a108-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6a108-114">备注</span><span class="sxs-lookup"><span data-stu-id="6a108-114">Remarks</span></span>

<span data-ttu-id="6a108-115">使用 Property 和 Stream 对象协议读取或写入此属性。</span><span class="sxs-lookup"><span data-stu-id="6a108-115">This property is read or written by using the Property and Stream Object protocol.</span></span> <span data-ttu-id="6a108-116">从"收件箱"或"根"文件夹读取和写入邮件。</span><span class="sxs-lookup"><span data-stu-id="6a108-116">It is read from and written to the Inbox or Root folder.</span></span> <span data-ttu-id="6a108-117">当存储是主要邮件用户的"收件箱"文件夹时，实现必须使用"收件箱"文件夹，并且当存储是委派用户的存储区时，它必须使用根文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a108-117">The implementation must use the Inbox folder when the store is that of the primary messaging user, and it must use the Root folder when the store is that of a delegate user.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6a108-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="6a108-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6a108-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="6a108-119">Protocol specifications</span></span>

<span data-ttu-id="6a108-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a108-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a108-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="6a108-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6a108-122">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a108-122">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a108-123">指定用于创建和定位邮箱中特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="6a108-123">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="6a108-124">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a108-124">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a108-125">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="6a108-125">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6a108-126">头文件</span><span class="sxs-lookup"><span data-stu-id="6a108-126">Header files</span></span>

<span data-ttu-id="6a108-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6a108-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="6a108-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6a108-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="6a108-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6a108-129">Mapitags.h</span></span>
  
> <span data-ttu-id="6a108-130">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6a108-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6a108-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a108-131">See also</span></span>



[<span data-ttu-id="6a108-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6a108-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6a108-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a108-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6a108-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6a108-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6a108-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6a108-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

