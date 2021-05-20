---
title: PidTagOriginalAuthorAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorAddressType
api_type:
- COM
ms.assetid: 7cdedb1a-e441-469b-be50-2f18203eb30d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 596e416624fb6f2bf1fdaef64c2179feb7787815
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431412"
---
# <a name="pidtagoriginalauthoraddresstype-canonical-property"></a><span data-ttu-id="e0b03-103">PidTagOriginalAuthorAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0b03-103">PidTagOriginalAuthorAddressType Canonical Property</span></span>

  
  
<span data-ttu-id="e0b03-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e0b03-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e0b03-105">包含邮件第一个版本的作者的地址类型，即转发或答复前的邮件。</span><span class="sxs-lookup"><span data-stu-id="e0b03-105">Contains the address type of the author of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e0b03-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e0b03-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e0b03-107">PR_ORIGINAL_AUTHOR_ADDRTYPE、PR_ORIGINAL_AUTHOR_ADDRTYPE_A、PR_ORIGINAL_AUTHOR_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="e0b03-107">PR_ORIGINAL_AUTHOR_ADDRTYPE, PR_ORIGINAL_AUTHOR_ADDRTYPE_A, PR_ORIGINAL_AUTHOR_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="e0b03-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e0b03-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e0b03-109">0x0079</span><span class="sxs-lookup"><span data-stu-id="e0b03-109">0x0079</span></span>  <br/> |
|<span data-ttu-id="e0b03-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e0b03-110">Data type:</span></span>  <br/> |<span data-ttu-id="e0b03-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e0b03-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e0b03-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e0b03-112">Area:</span></span>  <br/> |<span data-ttu-id="e0b03-113">服务器</span><span class="sxs-lookup"><span data-stu-id="e0b03-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e0b03-114">备注</span><span class="sxs-lookup"><span data-stu-id="e0b03-114">Remarks</span></span>

<span data-ttu-id="e0b03-115">这些属性是邮件作者的地址属性示例。</span><span class="sxs-lookup"><span data-stu-id="e0b03-115">These properties are examples of the address properties for the author of a message.</span></span> <span data-ttu-id="e0b03-116">首次提交邮件时，客户端应用程序应将此属性设置为 **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="e0b03-116">At first submission of the message, the client application should set this property to the value of the **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) property.</span></span> <span data-ttu-id="e0b03-117">转发或答复邮件时从不更改。</span><span class="sxs-lookup"><span data-stu-id="e0b03-117">It is never changed when the message is forwarded or replied to.</span></span>
  
<span data-ttu-id="e0b03-118">原始作者属性允许保留来自本地邮件域外部的信息。</span><span class="sxs-lookup"><span data-stu-id="e0b03-118">The original author properties allow for preservation of information from outside the local messaging domain.</span></span> <span data-ttu-id="e0b03-119">当邮件从另一个邮件域（如 Internet）到达时，这些属性提供了一种确保原始信息不会丢失的方法。</span><span class="sxs-lookup"><span data-stu-id="e0b03-119">When a message arrives from another messaging domain, such as from the Internet, these properties provide a way to ensure that original information is not lost.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e0b03-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="e0b03-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="e0b03-121">头文件</span><span class="sxs-lookup"><span data-stu-id="e0b03-121">Header files</span></span>

<span data-ttu-id="e0b03-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e0b03-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="e0b03-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e0b03-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="e0b03-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e0b03-124">Mapitags.h</span></span>
  
> <span data-ttu-id="e0b03-125">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e0b03-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e0b03-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0b03-126">See also</span></span>



[<span data-ttu-id="e0b03-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e0b03-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e0b03-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0b03-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e0b03-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e0b03-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e0b03-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e0b03-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

