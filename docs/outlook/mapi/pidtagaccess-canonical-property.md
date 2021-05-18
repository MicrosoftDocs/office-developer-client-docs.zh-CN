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
# <a name="pidtagaccess-canonical-property"></a><span data-ttu-id="3dbef-103">PidTagAccess 规范属性</span><span class="sxs-lookup"><span data-stu-id="3dbef-103">PidTagAccess Canonical Property</span></span>

  
  
<span data-ttu-id="3dbef-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3dbef-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3dbef-105">包含指示对象的客户端可用的操作的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="3dbef-105">Contains a bitmask of flags indicating the operations that are available to the client for the object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3dbef-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3dbef-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3dbef-107">PR_ACCESS</span><span class="sxs-lookup"><span data-stu-id="3dbef-107">PR_ACCESS</span></span>  <br/> |
|<span data-ttu-id="3dbef-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3dbef-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3dbef-109">0x0FF4</span><span class="sxs-lookup"><span data-stu-id="3dbef-109">0x0FF4</span></span>  <br/> |
|<span data-ttu-id="3dbef-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3dbef-110">Data type:</span></span>  <br/> |<span data-ttu-id="3dbef-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="3dbef-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="3dbef-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3dbef-112">Area:</span></span>  <br/> |<span data-ttu-id="3dbef-113">访问控制属性</span><span class="sxs-lookup"><span data-stu-id="3dbef-113">Access Control Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3dbef-114">备注</span><span class="sxs-lookup"><span data-stu-id="3dbef-114">Remarks</span></span>

<span data-ttu-id="3dbef-115">对于客户端，此属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="3dbef-115">This property is read-only for the client.</span></span> <span data-ttu-id="3dbef-116">它必须是下表中的零个或多个值的位 **OR。**</span><span class="sxs-lookup"><span data-stu-id="3dbef-116">It must be a bitwise **OR** of zero or more values from the following table.</span></span> 
  
|<span data-ttu-id="3dbef-117">**名称**</span><span class="sxs-lookup"><span data-stu-id="3dbef-117">**Name**</span></span>|<span data-ttu-id="3dbef-118">**值**</span><span class="sxs-lookup"><span data-stu-id="3dbef-118">**Value**</span></span>|<span data-ttu-id="3dbef-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="3dbef-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3dbef-120">MAPI_ACCESS_MODIFY</span><span class="sxs-lookup"><span data-stu-id="3dbef-120">MAPI_ACCESS_MODIFY</span></span>  <br/> |<span data-ttu-id="3dbef-121">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3dbef-121">0x00000001</span></span>  <br/> |<span data-ttu-id="3dbef-122">写入</span><span class="sxs-lookup"><span data-stu-id="3dbef-122">Write</span></span>  <br/> |
|<span data-ttu-id="3dbef-123">MAPI_ACCESS_READ</span><span class="sxs-lookup"><span data-stu-id="3dbef-123">MAPI_ACCESS_READ</span></span>  <br/> |<span data-ttu-id="3dbef-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="3dbef-124">0x00000002</span></span>  <br/> |<span data-ttu-id="3dbef-125">阅读</span><span class="sxs-lookup"><span data-stu-id="3dbef-125">Read</span></span>  <br/> |
|<span data-ttu-id="3dbef-126">MAPI_ACCESS_DELETE</span><span class="sxs-lookup"><span data-stu-id="3dbef-126">MAPI_ACCESS_DELETE</span></span>  <br/> |<span data-ttu-id="3dbef-127">0x00000004</span><span class="sxs-lookup"><span data-stu-id="3dbef-127">0x00000004</span></span>  <br/> |<span data-ttu-id="3dbef-128">删除</span><span class="sxs-lookup"><span data-stu-id="3dbef-128">Delete</span></span>  <br/> |
|<span data-ttu-id="3dbef-129">MAPI_ACCESS_CREATE_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="3dbef-129">MAPI_ACCESS_CREATE_HIERARCHY</span></span>  <br/> |<span data-ttu-id="3dbef-130">0x00000008</span><span class="sxs-lookup"><span data-stu-id="3dbef-130">0x00000008</span></span>  <br/> |<span data-ttu-id="3dbef-131">在文件夹层次结构中创建子文件夹</span><span class="sxs-lookup"><span data-stu-id="3dbef-131">Create subfolders in the folder hierarchy</span></span>  <br/> |
|<span data-ttu-id="3dbef-132">MAPI_ACCESS_CREATE_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="3dbef-132">MAPI_ACCESS_CREATE_CONTENTS</span></span>  <br/> |<span data-ttu-id="3dbef-133">0x00000010</span><span class="sxs-lookup"><span data-stu-id="3dbef-133">0x00000010</span></span>  <br/> |<span data-ttu-id="3dbef-134">创建内容消息</span><span class="sxs-lookup"><span data-stu-id="3dbef-134">Create content messages</span></span>  <br/> |
|<span data-ttu-id="3dbef-135">MAPI_ACCESS_CREATE_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="3dbef-135">MAPI_ACCESS_CREATE_ASSOCIATED</span></span>  <br/> |<span data-ttu-id="3dbef-136">0x00000020</span><span class="sxs-lookup"><span data-stu-id="3dbef-136">0x00000020</span></span>  <br/> |<span data-ttu-id="3dbef-137">创建关联的内容消息</span><span class="sxs-lookup"><span data-stu-id="3dbef-137">Create associated content messages</span></span>  <br/> |
   
<span data-ttu-id="3dbef-138">文件夹MAPI_ACCESS_DELETE、MAPI_ACCESS_MODIFY 和 MAPI_ACCESS_READ 标记位于文件夹和邮件对象上，在内容表和关联内容表的 **PR_ACCESS** 列中。</span><span class="sxs-lookup"><span data-stu-id="3dbef-138">The MAPI_ACCESS_DELETE, MAPI_ACCESS_MODIFY, and MAPI_ACCESS_READ flags are found on folder and message objects and in the **PR_ACCESS** column in contents tables and associated contents tables.</span></span> <span data-ttu-id="3dbef-139">仅MAPI_ACCESS_CREATE_ASSOCIATED文件夹MAPI_ACCESS_CREATE_CONTENTS、MAPI_ACCESS_CREATE_HIERARCHY 和 MAPI_ACCESS_CREATE_HIERARCHY 标记。</span><span class="sxs-lookup"><span data-stu-id="3dbef-139">The MAPI_ACCESS_CREATE_ASSOCIATED, MAPI_ACCESS_CREATE_CONTENTS, and MAPI_ACCESS_CREATE_HIERARCHY flags are found on folder objects only.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="3dbef-140">相关资源</span><span class="sxs-lookup"><span data-stu-id="3dbef-140">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3dbef-141">协议规范</span><span class="sxs-lookup"><span data-stu-id="3dbef-141">Protocol specifications</span></span>

<span data-ttu-id="3dbef-142">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3dbef-142">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3dbef-143">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="3dbef-143">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3dbef-144">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3dbef-144">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3dbef-145">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="3dbef-145">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3dbef-146">头文件</span><span class="sxs-lookup"><span data-stu-id="3dbef-146">Header files</span></span>

<span data-ttu-id="3dbef-147">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3dbef-147">Mapidefs.h</span></span>
  
> <span data-ttu-id="3dbef-148">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3dbef-148">Provides data type definitions.</span></span>
    
<span data-ttu-id="3dbef-149">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3dbef-149">Mapitags.h</span></span>
  
> <span data-ttu-id="3dbef-150">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3dbef-150">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3dbef-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dbef-151">See also</span></span>



[<span data-ttu-id="3dbef-152">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3dbef-152">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3dbef-153">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3dbef-153">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3dbef-154">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3dbef-154">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3dbef-155">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3dbef-155">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

