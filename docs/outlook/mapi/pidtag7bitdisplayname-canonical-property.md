---
title: PidTag7BitDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTag7BitDisplayName
api_type:
- HeaderDef
ms.assetid: 803d7c4e-ed80-4d5b-988f-27068a8ccd63
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e5177d47749c2f60a883bd12fbba27045114c601
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315811"
---
# <a name="pidtag7bitdisplayname-canonical-property"></a><span data-ttu-id="8be3a-103">PidTag7BitDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="8be3a-103">PidTag7BitDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="8be3a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8be3a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8be3a-105">包含消息用户名称的 7 位 ASCII 表示形式。</span><span class="sxs-lookup"><span data-stu-id="8be3a-105">Contains a 7-bit ASCII representation of a messaging user's name.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8be3a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8be3a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8be3a-107">PR_7BIT_DISPLAY_NAME、PR_7BIT_DISPLAY_NAME_A、PR_7BIT_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="8be3a-107">PR_7BIT_DISPLAY_NAME, PR_7BIT_DISPLAY_NAME_A, PR_7BIT_DISPLAY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="8be3a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8be3a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8be3a-109">0x39FF</span><span class="sxs-lookup"><span data-stu-id="8be3a-109">0x39FF</span></span>  <br/> |
|<span data-ttu-id="8be3a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8be3a-110">Data type:</span></span>  <br/> |<span data-ttu-id="8be3a-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8be3a-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="8be3a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8be3a-112">Area:</span></span>  <br/> |<span data-ttu-id="8be3a-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="8be3a-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8be3a-114">备注</span><span class="sxs-lookup"><span data-stu-id="8be3a-114">Remarks</span></span>

<span data-ttu-id="8be3a-115">这些属性将 [PidTagDisplayName](pidtagdisplayname-canonical-property.md) **PR_DISPLAY_NAME (** 属性) 7 位字符集。</span><span class="sxs-lookup"><span data-stu-id="8be3a-115">These properties map the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property into a 7-bit character set.</span></span> <span data-ttu-id="8be3a-116">某些邮件系统（如 Internet 和某些 X.400 链接）限制为 128 个字符的 7 位 ASCII 代码集。</span><span class="sxs-lookup"><span data-stu-id="8be3a-116">Some messaging systems, such as Internet and certain X.400 links, are limited to the 128-character 7-bit ASCII code set.</span></span> <span data-ttu-id="8be3a-117">通过直接调用 [IAddrBook：:P repareRecips](iaddrbook-preparerecips.md) 方法检索此属性，此类邮件系统的网关可以提高性能，从而避免代码转换的额外处理。</span><span class="sxs-lookup"><span data-stu-id="8be3a-117">Gateways to such messaging systems can improve their performance by calling the [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) method directly to retrieve the this property, thereby avoiding extra processing for code conversion.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8be3a-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="8be3a-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8be3a-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="8be3a-119">Protocol specifications</span></span>

<span data-ttu-id="8be3a-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8be3a-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8be3a-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="8be3a-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8be3a-122">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8be3a-122">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8be3a-123">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8be3a-123">Specifies the properties and operations on lists of users, contacts, groups and resources.</span></span>
    
<span data-ttu-id="8be3a-124">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8be3a-124">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8be3a-125">处理客户端与 NSPI 服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="8be3a-125">Handles a client's communications with an NSPI server.</span></span>
    
<span data-ttu-id="8be3a-126">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8be3a-126">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8be3a-127">处理用于在客户端和服务器之间传输数据的顺序和数据流。</span><span class="sxs-lookup"><span data-stu-id="8be3a-127">Handles the order and data flow that is used to transfers data between client and server.</span></span>
    
<span data-ttu-id="8be3a-128">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8be3a-128">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8be3a-129">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="8be3a-129">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="8be3a-130">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8be3a-130">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8be3a-131">指定允许对电子邮件执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8be3a-131">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8be3a-132">头文件</span><span class="sxs-lookup"><span data-stu-id="8be3a-132">Header files</span></span>

<span data-ttu-id="8be3a-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8be3a-133">Mapitags.h</span></span>
  
> <span data-ttu-id="8be3a-134">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8be3a-134">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="8be3a-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8be3a-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="8be3a-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8be3a-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8be3a-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8be3a-137">See also</span></span>



[<span data-ttu-id="8be3a-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8be3a-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8be3a-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8be3a-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8be3a-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8be3a-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8be3a-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8be3a-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

