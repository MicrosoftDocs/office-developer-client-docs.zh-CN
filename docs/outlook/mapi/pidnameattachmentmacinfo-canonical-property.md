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
ms.openlocfilehash: d2a7fcf06c4e09f46c0d50f9e5f8897874c5f9a2
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387431"
---
# <a name="pidnameattachmentmacinfo-canonical-property"></a><span data-ttu-id="ac001-103">PidNameAttachmentMacInfo 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac001-103">PidNameAttachmentMacInfo Canonical Property</span></span>

  
  
<span data-ttu-id="ac001-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ac001-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ac001-105">包含组成基于 Macintosh 的电子邮件客户端使用的相应标头和资源的分叉数据 [RFC3282] 附件值。</span><span class="sxs-lookup"><span data-stu-id="ac001-105">Contains an [RFC3282] attachment value that is comprised of appropriate header and resource fork data used by Macintosh-based email clients.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ac001-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="ac001-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="ac001-107">无</span><span class="sxs-lookup"><span data-stu-id="ac001-107">None</span></span>  <br/> |
|<span data-ttu-id="ac001-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ac001-108">Property set:</span></span>  <br/> |<span data-ttu-id="ac001-109">PSETID_Attachment</span><span class="sxs-lookup"><span data-stu-id="ac001-109">PSETID_Attachment</span></span>  <br/> |
|<span data-ttu-id="ac001-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="ac001-110">Property name:</span></span>  <br/> |<span data-ttu-id="ac001-111">AttachmentMacInfo</span><span class="sxs-lookup"><span data-stu-id="ac001-111">AttachmentMacInfo</span></span>  <br/> |
|<span data-ttu-id="ac001-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ac001-112">Data type:</span></span>  <br/> |<span data-ttu-id="ac001-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ac001-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ac001-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ac001-114">Area:</span></span>  <br/> |<span data-ttu-id="ac001-115">邮件附件</span><span class="sxs-lookup"><span data-stu-id="ac001-115">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ac001-116">说明</span><span class="sxs-lookup"><span data-stu-id="ac001-116">Remarks</span></span>

<span data-ttu-id="ac001-117">有关详细信息，请参阅 MS OXCMAIL 部分 2.2.4.2 Apple 文件格式。</span><span class="sxs-lookup"><span data-stu-id="ac001-117">For more information, see MS-OXCMAIL section 2.2.4.2 Apple File Formats.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ac001-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="ac001-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ac001-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="ac001-119">Protocol specifications</span></span>

<span data-ttu-id="ac001-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac001-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ac001-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ac001-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ac001-122">[[MS OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac001-122">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ac001-123">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="ac001-123">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ac001-124">头文件</span><span class="sxs-lookup"><span data-stu-id="ac001-124">Header files</span></span>

<span data-ttu-id="ac001-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ac001-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="ac001-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ac001-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ac001-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac001-127">See also</span></span>



[<span data-ttu-id="ac001-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ac001-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ac001-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac001-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ac001-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ac001-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ac001-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ac001-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

