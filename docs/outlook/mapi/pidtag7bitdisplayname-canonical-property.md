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
ms.openlocfilehash: 4ae7645e45efb461ac53b6718569d909cec76504
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777273"
---
# <a name="pidtag7bitdisplayname-canonical-property"></a><span data-ttu-id="444b1-103">PidTag7BitDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="444b1-103">PidTag7BitDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="444b1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="444b1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="444b1-105">包含邮件用户的名称的 7 位 ASCII 表示形式。</span><span class="sxs-lookup"><span data-stu-id="444b1-105">Contains a 7-bit ASCII representation of a messaging user's name.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="444b1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="444b1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="444b1-107">PR_7BIT_DISPLAY_NAME，PR_7BIT_DISPLAY_NAME_A，PR_7BIT_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="444b1-107">PR_7BIT_DISPLAY_NAME, PR_7BIT_DISPLAY_NAME_A, PR_7BIT_DISPLAY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="444b1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="444b1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="444b1-109">0x39FF</span><span class="sxs-lookup"><span data-stu-id="444b1-109">0x39FF</span></span>  <br/> |
|<span data-ttu-id="444b1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="444b1-110">Data type:</span></span>  <br/> |<span data-ttu-id="444b1-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="444b1-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="444b1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="444b1-112">Area:</span></span>  <br/> |<span data-ttu-id="444b1-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="444b1-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="444b1-114">说明</span><span class="sxs-lookup"><span data-stu-id="444b1-114">Remarks</span></span>

<span data-ttu-id="444b1-115">这些属性映射到 7 位字符集**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="444b1-115">These properties map the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property into a 7-bit character set.</span></span> <span data-ttu-id="444b1-116">某些消息系统，如 Internet 和某些 X.400 链接被限制为 128 个字符 7 位 ASCII 代码集。</span><span class="sxs-lookup"><span data-stu-id="444b1-116">Some messaging systems, such as Internet and certain X.400 links, are limited to the 128-character 7-bit ASCII code set.</span></span> <span data-ttu-id="444b1-117">与此类邮件系统的网关可提高性能，通过调用[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)方法直接检索此属性，从而避免额外处理代码转换。</span><span class="sxs-lookup"><span data-stu-id="444b1-117">Gateways to such messaging systems can improve their performance by calling the [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) method directly to retrieve the this property, thereby avoiding extra processing for code conversion.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="444b1-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="444b1-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="444b1-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="444b1-119">Protocol specifications</span></span>

<span data-ttu-id="444b1-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="444b1-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="444b1-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="444b1-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="444b1-122">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="444b1-122">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="444b1-123">指定的属性和操作对列表的用户、 联系人、 组和资源。</span><span class="sxs-lookup"><span data-stu-id="444b1-123">Specifies the properties and operations on lists of users, contacts, groups and resources.</span></span>
    
<span data-ttu-id="444b1-124">[[MS NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="444b1-124">[[MS-NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="444b1-125">处理与 NSPI 服务器的客户端的通信。</span><span class="sxs-lookup"><span data-stu-id="444b1-125">Handles a client's communications with an NSPI server.</span></span>
    
<span data-ttu-id="444b1-126">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="444b1-126">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="444b1-127">处理用于客户端和服务器之间传输数据顺序和数据流。</span><span class="sxs-lookup"><span data-stu-id="444b1-127">Handles the order and data flow that is used to transfers data between client and server.</span></span>
    
<span data-ttu-id="444b1-128">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="444b1-128">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="444b1-129">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="444b1-129">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="444b1-130">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="444b1-130">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="444b1-131">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="444b1-131">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="444b1-132">头文件</span><span class="sxs-lookup"><span data-stu-id="444b1-132">Header files</span></span>

<span data-ttu-id="444b1-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="444b1-133">Mapitags.h</span></span>
  
> <span data-ttu-id="444b1-134">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="444b1-134">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="444b1-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="444b1-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="444b1-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="444b1-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="444b1-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="444b1-137">See also</span></span>



[<span data-ttu-id="444b1-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="444b1-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="444b1-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="444b1-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="444b1-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="444b1-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="444b1-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="444b1-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

