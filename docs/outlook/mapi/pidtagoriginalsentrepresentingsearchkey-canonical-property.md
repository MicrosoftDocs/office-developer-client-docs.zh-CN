---
title: PidTagOriginalSentRepresentingSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSentRepresentingSearchKey
api_type:
- COM
ms.assetid: 0fb1b803-f8b4-4d6d-8e2a-836daa98ac63
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ee23e2f25370a253b914779b3bfd0ab82fd08c7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340976"
---
# <a name="pidtagoriginalsentrepresentingsearchkey-canonical-property"></a><span data-ttu-id="b6fcc-103">PidTagOriginalSentRepresentingSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="b6fcc-103">PidTagOriginalSentRepresentingSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="b6fcc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6fcc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6fcc-105">包含代表其发送原始邮件的邮件用户的搜索密钥。</span><span class="sxs-lookup"><span data-stu-id="b6fcc-105">Contains the search key of the messaging user on whose behalf the original message was sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b6fcc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b6fcc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b6fcc-107">PR_ORIGINAL_SENT_REPRESENTING_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="b6fcc-107">PR_ORIGINAL_SENT_REPRESENTING_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="b6fcc-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b6fcc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b6fcc-109">0x005F</span><span class="sxs-lookup"><span data-stu-id="b6fcc-109">0x005F</span></span>  <br/> |
|<span data-ttu-id="b6fcc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b6fcc-110">Data type:</span></span>  <br/> |<span data-ttu-id="b6fcc-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b6fcc-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b6fcc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b6fcc-112">Area:</span></span>  <br/> |<span data-ttu-id="b6fcc-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="b6fcc-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b6fcc-114">备注</span><span class="sxs-lookup"><span data-stu-id="b6fcc-114">Remarks</span></span>

<span data-ttu-id="b6fcc-115">此属性是邮件的原始表示发件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="b6fcc-115">This property is one of the address properties for the original represented sender of a message.</span></span> <span data-ttu-id="b6fcc-116">它在对话线程中使用。</span><span class="sxs-lookup"><span data-stu-id="b6fcc-116">It is used in a conversation thread.</span></span>
  
<span data-ttu-id="b6fcc-117">代表其他客户端发送邮件的客户端应用程序应在第一次提交邮件时将此属性设置为 **PR_SENT_REPRESENTING_SEARCH_KEY** ([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b6fcc-117">A client application sending a message on behalf of another client should set this property to the value of the **PR_SENT_REPRESENTING_SEARCH_KEY** ([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md)) property at the first submission of the message.</span></span> <span data-ttu-id="b6fcc-118">设置后，不应更改它。</span><span class="sxs-lookup"><span data-stu-id="b6fcc-118">Once set, it should never be changed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b6fcc-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="b6fcc-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b6fcc-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="b6fcc-120">Protocol specifications</span></span>

<span data-ttu-id="b6fcc-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b6fcc-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b6fcc-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="b6fcc-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b6fcc-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b6fcc-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b6fcc-124">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b6fcc-124">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b6fcc-125">头文件</span><span class="sxs-lookup"><span data-stu-id="b6fcc-125">Header files</span></span>

<span data-ttu-id="b6fcc-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b6fcc-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="b6fcc-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b6fcc-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="b6fcc-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b6fcc-128">Mapitags.h</span></span>
  
> <span data-ttu-id="b6fcc-129">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b6fcc-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b6fcc-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6fcc-130">See also</span></span>



[<span data-ttu-id="b6fcc-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b6fcc-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b6fcc-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b6fcc-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b6fcc-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b6fcc-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b6fcc-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b6fcc-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

