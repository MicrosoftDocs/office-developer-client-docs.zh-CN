---
title: PidTagAccess 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAccess
api_type:
- HeaderDef
ms.assetid: 8c8a882e-62c1-4c57-8c63-ee5849f656b0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b453a7b0cfa04dd94da01089573427a931fb4d4f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316511"
---
# <a name="pidtagaccess-canonical-property"></a><span data-ttu-id="f3577-103">PidTagAccess 规范属性</span><span class="sxs-lookup"><span data-stu-id="f3577-103">PidTagAccess Canonical Property</span></span>

  
  
<span data-ttu-id="f3577-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3577-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3577-105">包含标志的位掩码, 这些标志指示可用于对象的客户端的操作。</span><span class="sxs-lookup"><span data-stu-id="f3577-105">Contains a bitmask of flags indicating the operations that are available to the client for the object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f3577-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f3577-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f3577-107">PR_ACCESS</span><span class="sxs-lookup"><span data-stu-id="f3577-107">PR_ACCESS</span></span>  <br/> |
|<span data-ttu-id="f3577-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f3577-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f3577-109">0x0FF4</span><span class="sxs-lookup"><span data-stu-id="f3577-109">0x0FF4</span></span>  <br/> |
|<span data-ttu-id="f3577-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f3577-110">Data type:</span></span>  <br/> |<span data-ttu-id="f3577-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f3577-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f3577-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f3577-112">Area:</span></span>  <br/> |<span data-ttu-id="f3577-113">访问控制属性</span><span class="sxs-lookup"><span data-stu-id="f3577-113">Access Control Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f3577-114">注解</span><span class="sxs-lookup"><span data-stu-id="f3577-114">Remarks</span></span>

<span data-ttu-id="f3577-115">对于客户端, 此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="f3577-115">This property is read-only for the client.</span></span> <span data-ttu-id="f3577-116">它必须是下表中的一个或多个值的按位 "**或**"。</span><span class="sxs-lookup"><span data-stu-id="f3577-116">It must be a bitwise **OR** of zero or more values from the following table.</span></span> 
  
|<span data-ttu-id="f3577-117">**Name**</span><span class="sxs-lookup"><span data-stu-id="f3577-117">**Name**</span></span>|<span data-ttu-id="f3577-118">**Value**</span><span class="sxs-lookup"><span data-stu-id="f3577-118">**Value**</span></span>|<span data-ttu-id="f3577-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3577-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3577-120">MAPI_ACCESS_MODIFY</span><span class="sxs-lookup"><span data-stu-id="f3577-120">MAPI_ACCESS_MODIFY</span></span>  <br/> |<span data-ttu-id="f3577-121">0x00000001</span><span class="sxs-lookup"><span data-stu-id="f3577-121">0x00000001</span></span>  <br/> |<span data-ttu-id="f3577-122">写入</span><span class="sxs-lookup"><span data-stu-id="f3577-122">Write</span></span>  <br/> |
|<span data-ttu-id="f3577-123">MAPI_ACCESS_READ</span><span class="sxs-lookup"><span data-stu-id="f3577-123">MAPI_ACCESS_READ</span></span>  <br/> |<span data-ttu-id="f3577-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="f3577-124">0x00000002</span></span>  <br/> |<span data-ttu-id="f3577-125">读取</span><span class="sxs-lookup"><span data-stu-id="f3577-125">Read</span></span>  <br/> |
|<span data-ttu-id="f3577-126">MAPI_ACCESS_DELETE</span><span class="sxs-lookup"><span data-stu-id="f3577-126">MAPI_ACCESS_DELETE</span></span>  <br/> |<span data-ttu-id="f3577-127">0x00000004</span><span class="sxs-lookup"><span data-stu-id="f3577-127">0x00000004</span></span>  <br/> |<span data-ttu-id="f3577-128">删除</span><span class="sxs-lookup"><span data-stu-id="f3577-128">Delete</span></span>  <br/> |
|<span data-ttu-id="f3577-129">MAPI_ACCESS_CREATE_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="f3577-129">MAPI_ACCESS_CREATE_HIERARCHY</span></span>  <br/> |<span data-ttu-id="f3577-130">0x00000008</span><span class="sxs-lookup"><span data-stu-id="f3577-130">0x00000008</span></span>  <br/> |<span data-ttu-id="f3577-131">在文件夹层次结构中创建子文件夹</span><span class="sxs-lookup"><span data-stu-id="f3577-131">Create subfolders in the folder hierarchy</span></span>  <br/> |
|<span data-ttu-id="f3577-132">MAPI_ACCESS_CREATE_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="f3577-132">MAPI_ACCESS_CREATE_CONTENTS</span></span>  <br/> |<span data-ttu-id="f3577-133">0x00000010</span><span class="sxs-lookup"><span data-stu-id="f3577-133">0x00000010</span></span>  <br/> |<span data-ttu-id="f3577-134">创建内容邮件</span><span class="sxs-lookup"><span data-stu-id="f3577-134">Create content messages</span></span>  <br/> |
|<span data-ttu-id="f3577-135">MAPI_ACCESS_CREATE_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="f3577-135">MAPI_ACCESS_CREATE_ASSOCIATED</span></span>  <br/> |<span data-ttu-id="f3577-136">0x00000020</span><span class="sxs-lookup"><span data-stu-id="f3577-136">0x00000020</span></span>  <br/> |<span data-ttu-id="f3577-137">创建关联的内容邮件</span><span class="sxs-lookup"><span data-stu-id="f3577-137">Create associated content messages</span></span>  <br/> |
   
<span data-ttu-id="f3577-138">MAPI_ACCESS_DELETE、MAPI_ACCESS_MODIFY 和 MAPI_ACCESS_READ 标志位于 folder 和 message 对象以及内容表和关联的内容表中的**PR_ACCESS**列中。</span><span class="sxs-lookup"><span data-stu-id="f3577-138">The MAPI_ACCESS_DELETE, MAPI_ACCESS_MODIFY, and MAPI_ACCESS_READ flags are found on folder and message objects and in the **PR_ACCESS** column in contents tables and associated contents tables.</span></span> <span data-ttu-id="f3577-139">MAPI_ACCESS_CREATE_ASSOCIATED、MAPI_ACCESS_CREATE_CONTENTS 和 MAPI_ACCESS_CREATE_HIERARCHY 标志仅在 folder 对象上找到。</span><span class="sxs-lookup"><span data-stu-id="f3577-139">The MAPI_ACCESS_CREATE_ASSOCIATED, MAPI_ACCESS_CREATE_CONTENTS, and MAPI_ACCESS_CREATE_HIERARCHY flags are found on folder objects only.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f3577-140">相关资源</span><span class="sxs-lookup"><span data-stu-id="f3577-140">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f3577-141">协议规范</span><span class="sxs-lookup"><span data-stu-id="f3577-141">Protocol specifications</span></span>

<span data-ttu-id="f3577-142">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3577-142">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3577-143">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f3577-143">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f3577-144">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3577-144">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3577-145">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="f3577-145">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f3577-146">头文件</span><span class="sxs-lookup"><span data-stu-id="f3577-146">Header files</span></span>

<span data-ttu-id="f3577-147">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f3577-147">Mapidefs.h</span></span>
  
> <span data-ttu-id="f3577-148">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f3577-148">Provides data type definitions.</span></span>
    
<span data-ttu-id="f3577-149">Mapitags</span><span class="sxs-lookup"><span data-stu-id="f3577-149">Mapitags.h</span></span>
  
> <span data-ttu-id="f3577-150">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f3577-150">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f3577-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3577-151">See also</span></span>



[<span data-ttu-id="f3577-152">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f3577-152">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f3577-153">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f3577-153">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f3577-154">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f3577-154">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f3577-155">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f3577-155">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

