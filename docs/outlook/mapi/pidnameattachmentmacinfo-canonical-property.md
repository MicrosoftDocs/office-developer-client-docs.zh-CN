---
title: PidNameAttachmentMacInfo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameAttachmentMacInfo
api_type:
- COM
ms.assetid: c46656d5-2cb1-45eb-9f66-9c2b6e3315cf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 375eac56253772b363ae320b3f7044ac600e71f6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777196"
---
# <a name="pidnameattachmentmacinfo-canonical-property"></a><span data-ttu-id="23553-103">PidNameAttachmentMacInfo 规范属性</span><span class="sxs-lookup"><span data-stu-id="23553-103">PidNameAttachmentMacInfo Canonical Property</span></span>

  
  
<span data-ttu-id="23553-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="23553-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="23553-105">包含组成基于 Macintosh 的电子邮件客户端使用的相应标头和资源的分叉数据 [RFC3282] 附件值。</span><span class="sxs-lookup"><span data-stu-id="23553-105">Contains an [RFC3282] attachment value that is comprised of appropriate header and resource fork data used by Macintosh-based email clients.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="23553-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="23553-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="23553-107">无</span><span class="sxs-lookup"><span data-stu-id="23553-107">None</span></span>  <br/> |
|<span data-ttu-id="23553-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="23553-108">Property set:</span></span>  <br/> |<span data-ttu-id="23553-109">PSETID_Attachment</span><span class="sxs-lookup"><span data-stu-id="23553-109">PSETID_Attachment</span></span>  <br/> |
|<span data-ttu-id="23553-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="23553-110">Property name:</span></span>  <br/> |<span data-ttu-id="23553-111">AttachmentMacInfo</span><span class="sxs-lookup"><span data-stu-id="23553-111">AttachmentMacInfo</span></span>  <br/> |
|<span data-ttu-id="23553-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="23553-112">Data type:</span></span>  <br/> |<span data-ttu-id="23553-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="23553-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="23553-114">区域：</span><span class="sxs-lookup"><span data-stu-id="23553-114">Area:</span></span>  <br/> |<span data-ttu-id="23553-115">邮件附件</span><span class="sxs-lookup"><span data-stu-id="23553-115">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="23553-116">说明</span><span class="sxs-lookup"><span data-stu-id="23553-116">Remarks</span></span>

<span data-ttu-id="23553-117">有关详细信息，请参阅 MS OXCMAIL 部分 2.2.4.2 Apple 文件格式。</span><span class="sxs-lookup"><span data-stu-id="23553-117">For more information, see MS-OXCMAIL section 2.2.4.2 Apple File Formats.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="23553-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="23553-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="23553-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="23553-119">Protocol specifications</span></span>

<span data-ttu-id="23553-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="23553-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="23553-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="23553-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="23553-122">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="23553-122">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="23553-123">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="23553-123">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="23553-124">头文件</span><span class="sxs-lookup"><span data-stu-id="23553-124">Header files</span></span>

<span data-ttu-id="23553-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="23553-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="23553-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="23553-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="23553-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23553-127">See also</span></span>



[<span data-ttu-id="23553-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="23553-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="23553-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="23553-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="23553-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="23553-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="23553-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="23553-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

