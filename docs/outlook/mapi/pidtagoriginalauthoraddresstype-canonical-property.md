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
# <a name="pidtagoriginalauthoraddresstype-canonical-property"></a><span data-ttu-id="8cf61-103">PidTagOriginalAuthorAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="8cf61-103">PidTagOriginalAuthorAddressType Canonical Property</span></span>

  
  
<span data-ttu-id="8cf61-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8cf61-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8cf61-105">包含邮件的首个版本的作者地址类型, 即邮件在转发或答复之前的地址类型。</span><span class="sxs-lookup"><span data-stu-id="8cf61-105">Contains the address type of the author of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8cf61-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8cf61-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8cf61-107">PR_ORIGINAL_AUTHOR_ADDRTYPE、PR_ORIGINAL_AUTHOR_ADDRTYPE_A、PR_ORIGINAL_AUTHOR_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="8cf61-107">PR_ORIGINAL_AUTHOR_ADDRTYPE, PR_ORIGINAL_AUTHOR_ADDRTYPE_A, PR_ORIGINAL_AUTHOR_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="8cf61-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8cf61-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8cf61-109">0x0079</span><span class="sxs-lookup"><span data-stu-id="8cf61-109">0x0079</span></span>  <br/> |
|<span data-ttu-id="8cf61-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8cf61-110">Data type:</span></span>  <br/> |<span data-ttu-id="8cf61-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8cf61-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="8cf61-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8cf61-112">Area:</span></span>  <br/> |<span data-ttu-id="8cf61-113">服务器</span><span class="sxs-lookup"><span data-stu-id="8cf61-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8cf61-114">说明</span><span class="sxs-lookup"><span data-stu-id="8cf61-114">Remarks</span></span>

<span data-ttu-id="8cf61-115">这些属性是邮件作者地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="8cf61-115">These properties are examples of the address properties for the author of a message.</span></span> <span data-ttu-id="8cf61-116">首次提交邮件时, 客户端应用程序应将此属性设置为**PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="8cf61-116">At first submission of the message, the client application should set this property to the value of the **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) property.</span></span> <span data-ttu-id="8cf61-117">转发或答复邮件时, 它永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="8cf61-117">It is never changed when the message is forwarded or replied to.</span></span>
  
<span data-ttu-id="8cf61-118">原始作者属性允许保留本地邮件域外部的信息。</span><span class="sxs-lookup"><span data-stu-id="8cf61-118">The original author properties allow for preservation of information from outside the local messaging domain.</span></span> <span data-ttu-id="8cf61-119">当邮件到达其他邮件域 (例如从 Internet) 时, 这些属性提供了一种确保原始信息不会丢失的方法。</span><span class="sxs-lookup"><span data-stu-id="8cf61-119">When a message arrives from another messaging domain, such as from the Internet, these properties provide a way to ensure that original information is not lost.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8cf61-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="8cf61-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8cf61-121">头文件</span><span class="sxs-lookup"><span data-stu-id="8cf61-121">Header files</span></span>

<span data-ttu-id="8cf61-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8cf61-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="8cf61-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8cf61-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="8cf61-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8cf61-124">Mapitags.h</span></span>
  
> <span data-ttu-id="8cf61-125">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8cf61-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8cf61-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf61-126">See also</span></span>



[<span data-ttu-id="8cf61-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8cf61-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8cf61-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8cf61-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8cf61-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8cf61-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8cf61-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8cf61-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

