---
title: PidTagOriginalSentRepresentingAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSentRepresentingAddressType
api_type:
- COM
ms.assetid: 93f40161-d4e5-4ef9-a55f-cee62529fc04
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7fcd358b2ada5137ed28f4439dcc9d4ebdc50305
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777945"
---
# <a name="pidtagoriginalsentrepresentingaddresstype-canonical-property"></a><span data-ttu-id="0ecd8-103">PidTagOriginalSentRepresentingAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="0ecd8-103">PidTagOriginalSentRepresentingAddressType Canonical Property</span></span>

  
  
<span data-ttu-id="0ecd8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0ecd8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0ecd8-105">包含的名义原始邮件已发送的邮件用户的地址类型。</span><span class="sxs-lookup"><span data-stu-id="0ecd8-105">Contains the address type of the messaging user on whose behalf the original message was sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0ecd8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0ecd8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0ecd8-107">PR_ORIGINAL_SENT_REPRESENTING_ADDRTYPE，PR_ORIGINAL_SENT_REPRESENTING_ADDRTYPE_A，PR_ORIGINAL_SENT_REPRESENTING_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="0ecd8-107">PR_ORIGINAL_SENT_REPRESENTING_ADDRTYPE, PR_ORIGINAL_SENT_REPRESENTING_ADDRTYPE_A, PR_ORIGINAL_SENT_REPRESENTING_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="0ecd8-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="0ecd8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0ecd8-109">0x0068</span><span class="sxs-lookup"><span data-stu-id="0ecd8-109">0x0068</span></span>  <br/> |
|<span data-ttu-id="0ecd8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0ecd8-110">Data type:</span></span>  <br/> |<span data-ttu-id="0ecd8-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0ecd8-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0ecd8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0ecd8-112">Area:</span></span>  <br/> |<span data-ttu-id="0ecd8-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="0ecd8-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0ecd8-114">说明</span><span class="sxs-lookup"><span data-stu-id="0ecd8-114">Remarks</span></span>

<span data-ttu-id="0ecd8-115">这些属性是表示原始发件人的邮件的类型。</span><span class="sxs-lookup"><span data-stu-id="0ecd8-115">These properties are the type for the original represented sender of a message.</span></span> <span data-ttu-id="0ecd8-116">在对话的线程中使用它们。</span><span class="sxs-lookup"><span data-stu-id="0ecd8-116">They are used in a conversation thread.</span></span>
  
<span data-ttu-id="0ecd8-117">发送一条消息，代表另一个客户端的客户端应用程序应将这些属性设置为在首次提交邮件**PR_SENT_REPRESENTING_ADDRTYPE** ([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="0ecd8-117">A client application sending a message on behalf of another client should set these properties to the value of the **PR_SENT_REPRESENTING_ADDRTYPE** ([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md)) property at the first submission of the message.</span></span> <span data-ttu-id="0ecd8-118">设置后，它应永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="0ecd8-118">Once set, it should never be changed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0ecd8-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="0ecd8-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0ecd8-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="0ecd8-120">Protocol specifications</span></span>

<span data-ttu-id="0ecd8-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0ecd8-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0ecd8-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="0ecd8-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0ecd8-123">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0ecd8-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0ecd8-124">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="0ecd8-124">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0ecd8-125">头文件</span><span class="sxs-lookup"><span data-stu-id="0ecd8-125">Header files</span></span>

<span data-ttu-id="0ecd8-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0ecd8-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="0ecd8-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0ecd8-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="0ecd8-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0ecd8-128">Mapitags.h</span></span>
  
> <span data-ttu-id="0ecd8-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0ecd8-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0ecd8-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ecd8-130">See also</span></span>



[<span data-ttu-id="0ecd8-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0ecd8-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0ecd8-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0ecd8-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0ecd8-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0ecd8-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0ecd8-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0ecd8-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

