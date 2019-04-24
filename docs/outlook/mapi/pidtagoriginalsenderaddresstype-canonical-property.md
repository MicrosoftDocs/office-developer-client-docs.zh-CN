---
title: PidTagOriginalSenderAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSenderAddressType
api_type:
- COM
ms.assetid: bd777f19-cbb1-4497-8a0b-e05b491c6957
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d593b5ae1c2341ae0972ba68bcf42dde64e9a2f1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342677"
---
# <a name="pidtagoriginalsenderaddresstype-canonical-property"></a><span data-ttu-id="5d895-103">PidTagOriginalSenderAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d895-103">PidTagOriginalSenderAddressType Canonical Property</span></span>

  
  
<span data-ttu-id="5d895-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d895-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d895-105">包含邮件的第一种版本的发件人地址类型, 即邮件转发或答复前的邮件。</span><span class="sxs-lookup"><span data-stu-id="5d895-105">Contains the address type of the sender of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5d895-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5d895-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5d895-107">PR_ORIGINAL_SENDER_ADDRTYPE、PR_ORIGINAL_SENDER_ADDRTYPE_A、PR_ORIGINAL_SENDER_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="5d895-107">PR_ORIGINAL_SENDER_ADDRTYPE, PR_ORIGINAL_SENDER_ADDRTYPE_A, PR_ORIGINAL_SENDER_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="5d895-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5d895-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5d895-109">0x0066</span><span class="sxs-lookup"><span data-stu-id="5d895-109">0x0066</span></span>  <br/> |
|<span data-ttu-id="5d895-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5d895-110">Data type:</span></span>  <br/> |<span data-ttu-id="5d895-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5d895-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="5d895-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5d895-112">Area:</span></span>  <br/> |<span data-ttu-id="5d895-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="5d895-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5d895-114">注解</span><span class="sxs-lookup"><span data-stu-id="5d895-114">Remarks</span></span>

<span data-ttu-id="5d895-115">这些属性是邮件原始发件人的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="5d895-115">These properties are examples of the address properties for the original sender of a message.</span></span> <span data-ttu-id="5d895-116">首次提交邮件时, 客户端应用程序应将这些属性设置为**PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) 的值。</span><span class="sxs-lookup"><span data-stu-id="5d895-116">At first submission of the message, the client application should set these properties to the value of **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)).</span></span> <span data-ttu-id="5d895-117">转发或答复邮件时, 它永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="5d895-117">It is never changed when the message is forwarded or replied to.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5d895-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="5d895-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5d895-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="5d895-119">Protocol specifications</span></span>

<span data-ttu-id="5d895-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d895-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5d895-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="5d895-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5d895-122">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d895-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5d895-123">指定在电子邮件对象上允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5d895-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5d895-124">头文件</span><span class="sxs-lookup"><span data-stu-id="5d895-124">Header files</span></span>

<span data-ttu-id="5d895-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="5d895-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="5d895-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5d895-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="5d895-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="5d895-127">Mapitags.h</span></span>
  
> <span data-ttu-id="5d895-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5d895-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5d895-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d895-129">See also</span></span>



[<span data-ttu-id="5d895-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5d895-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5d895-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d895-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5d895-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5d895-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5d895-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5d895-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

