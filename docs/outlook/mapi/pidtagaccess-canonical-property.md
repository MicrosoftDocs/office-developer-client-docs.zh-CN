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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bb00d4e0e1437f9b3c13ac5e7d0a9dc4f3610d32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777285"
---
# <a name="pidtagaccess-canonical-property"></a><span data-ttu-id="b9fc6-103">PidTagAccess 规范属性</span><span class="sxs-lookup"><span data-stu-id="b9fc6-103">PidTagAccess Canonical Property</span></span>

  
  
<span data-ttu-id="b9fc6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b9fc6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b9fc6-105">包含标志指示对象的客户端可用的操作的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-105">Contains a bitmask of flags indicating the operations that are available to the client for the object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b9fc6-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="b9fc6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b9fc6-107">PR_ACCESS</span><span class="sxs-lookup"><span data-stu-id="b9fc6-107">PR_ACCESS</span></span>  <br/> |
|<span data-ttu-id="b9fc6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b9fc6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b9fc6-109">0x0FF4</span><span class="sxs-lookup"><span data-stu-id="b9fc6-109">0x0FF4</span></span>  <br/> |
|<span data-ttu-id="b9fc6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b9fc6-110">Data type:</span></span>  <br/> |<span data-ttu-id="b9fc6-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b9fc6-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b9fc6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b9fc6-112">Area:</span></span>  <br/> |<span data-ttu-id="b9fc6-113">访问控件属性</span><span class="sxs-lookup"><span data-stu-id="b9fc6-113">Access Control Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b9fc6-114">备注</span><span class="sxs-lookup"><span data-stu-id="b9fc6-114">Remarks</span></span>

<span data-ttu-id="b9fc6-115">此属性是只读的客户端。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-115">This property is read-only for the client.</span></span> <span data-ttu-id="b9fc6-116">它必须是按位**或**下表中的零个或多个值。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-116">It must be a bitwise **OR** of zero or more values from the following table.</span></span> 
  
|<span data-ttu-id="b9fc6-117">**名称**</span><span class="sxs-lookup"><span data-stu-id="b9fc6-117">**Name**</span></span>|<span data-ttu-id="b9fc6-118">**值**</span><span class="sxs-lookup"><span data-stu-id="b9fc6-118">**Value**</span></span>|<span data-ttu-id="b9fc6-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b9fc6-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9fc6-120">MAPI_ACCESS_MODIFY</span><span class="sxs-lookup"><span data-stu-id="b9fc6-120">MAPI_ACCESS_MODIFY</span></span>  <br/> |<span data-ttu-id="b9fc6-121">0x00000001</span><span class="sxs-lookup"><span data-stu-id="b9fc6-121">0x00000001</span></span>  <br/> |<span data-ttu-id="b9fc6-122">写入</span><span class="sxs-lookup"><span data-stu-id="b9fc6-122">Write</span></span>  <br/> |
|<span data-ttu-id="b9fc6-123">MAPI_ACCESS_READ</span><span class="sxs-lookup"><span data-stu-id="b9fc6-123">MAPI_ACCESS_READ</span></span>  <br/> |<span data-ttu-id="b9fc6-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="b9fc6-124">0x00000002</span></span>  <br/> |<span data-ttu-id="b9fc6-125">已阅读</span><span class="sxs-lookup"><span data-stu-id="b9fc6-125">Read</span></span>  <br/> |
|<span data-ttu-id="b9fc6-126">MAPI_ACCESS_DELETE</span><span class="sxs-lookup"><span data-stu-id="b9fc6-126">MAPI_ACCESS_DELETE</span></span>  <br/> |<span data-ttu-id="b9fc6-127">0x00000004</span><span class="sxs-lookup"><span data-stu-id="b9fc6-127">0x00000004</span></span>  <br/> |<span data-ttu-id="b9fc6-128">Delete</span><span class="sxs-lookup"><span data-stu-id="b9fc6-128">Delete</span></span>  <br/> |
|<span data-ttu-id="b9fc6-129">MAPI_ACCESS_CREATE_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="b9fc6-129">MAPI_ACCESS_CREATE_HIERARCHY</span></span>  <br/> |<span data-ttu-id="b9fc6-130">0x00000008</span><span class="sxs-lookup"><span data-stu-id="b9fc6-130">0x00000008</span></span>  <br/> |<span data-ttu-id="b9fc6-131">在文件夹层次结构中创建子文件夹</span><span class="sxs-lookup"><span data-stu-id="b9fc6-131">Create subfolders in the folder hierarchy</span></span>  <br/> |
|<span data-ttu-id="b9fc6-132">MAPI_ACCESS_CREATE_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="b9fc6-132">MAPI_ACCESS_CREATE_CONTENTS</span></span>  <br/> |<span data-ttu-id="b9fc6-133">0x00000010</span><span class="sxs-lookup"><span data-stu-id="b9fc6-133">0x00000010</span></span>  <br/> |<span data-ttu-id="b9fc6-134">创建内容的消息</span><span class="sxs-lookup"><span data-stu-id="b9fc6-134">Create content messages</span></span>  <br/> |
|<span data-ttu-id="b9fc6-135">MAPI_ACCESS_CREATE_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="b9fc6-135">MAPI_ACCESS_CREATE_ASSOCIATED</span></span>  <br/> |<span data-ttu-id="b9fc6-136">0x00000020</span><span class="sxs-lookup"><span data-stu-id="b9fc6-136">0x00000020</span></span>  <br/> |<span data-ttu-id="b9fc6-137">创建关联的内容消息</span><span class="sxs-lookup"><span data-stu-id="b9fc6-137">Create associated content messages</span></span>  <br/> |
   
<span data-ttu-id="b9fc6-138">MAPI_ACCESS_DELETE、 MAPI_ACCESS_MODIFY 和 MAPI_ACCESS_READ 标志中内容表和关联的内容表文件夹和消息对象上和**PR_ACCESS**列中找到。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-138">The MAPI_ACCESS_DELETE, MAPI_ACCESS_MODIFY, and MAPI_ACCESS_READ flags are found on folder and message objects and in the **PR_ACCESS** column in contents tables and associated contents tables.</span></span> <span data-ttu-id="b9fc6-139">仅文件夹对象上找到 MAPI_ACCESS_CREATE_ASSOCIATED、 MAPI_ACCESS_CREATE_CONTENTS 和 MAPI_ACCESS_CREATE_HIERARCHY 标志。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-139">The MAPI_ACCESS_CREATE_ASSOCIATED, MAPI_ACCESS_CREATE_CONTENTS, and MAPI_ACCESS_CREATE_HIERARCHY flags are found on folder objects only.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b9fc6-140">相关资源</span><span class="sxs-lookup"><span data-stu-id="b9fc6-140">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b9fc6-141">协议规范</span><span class="sxs-lookup"><span data-stu-id="b9fc6-141">Protocol specifications</span></span>

<span data-ttu-id="b9fc6-142">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b9fc6-142">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b9fc6-143">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-143">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b9fc6-144">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b9fc6-144">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b9fc6-145">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-145">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b9fc6-146">头文件</span><span class="sxs-lookup"><span data-stu-id="b9fc6-146">Header files</span></span>

<span data-ttu-id="b9fc6-147">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b9fc6-147">Mapidefs.h</span></span>
  
> <span data-ttu-id="b9fc6-148">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-148">Provides data type definitions.</span></span>
    
<span data-ttu-id="b9fc6-149">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b9fc6-149">Mapitags.h</span></span>
  
> <span data-ttu-id="b9fc6-150">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-150">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b9fc6-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9fc6-151">See also</span></span>



[<span data-ttu-id="b9fc6-152">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b9fc6-152">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b9fc6-153">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b9fc6-153">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b9fc6-154">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b9fc6-154">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b9fc6-155">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b9fc6-155">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

