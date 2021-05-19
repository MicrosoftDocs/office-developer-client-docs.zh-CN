---
title: PidTagOriginalSenderEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSenderEntryId
api_type:
- COM
ms.assetid: bd182589-afea-4967-92f5-ba1914e4db3f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bd32ef6540e0deec1b793bd49bab651d864754c6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342614"
---
# <a name="pidtagoriginalsenderentryid-canonical-property"></a><span data-ttu-id="cba69-103">PidTagOriginalSenderEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="cba69-103">PidTagOriginalSenderEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="cba69-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cba69-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cba69-105">包含邮件第一个版本的发件人的条目标识符，即转发或答复前的邮件。</span><span class="sxs-lookup"><span data-stu-id="cba69-105">Contains the entry identifier of the sender of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cba69-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cba69-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cba69-107">PR_ORIGINAL_SENDER_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="cba69-107">PR_ORIGINAL_SENDER_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="cba69-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="cba69-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cba69-109">0x005B</span><span class="sxs-lookup"><span data-stu-id="cba69-109">0x005B</span></span>  <br/> |
|<span data-ttu-id="cba69-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cba69-110">Data type:</span></span>  <br/> |<span data-ttu-id="cba69-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="cba69-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="cba69-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cba69-112">Area:</span></span>  <br/> |<span data-ttu-id="cba69-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="cba69-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cba69-114">备注</span><span class="sxs-lookup"><span data-stu-id="cba69-114">Remarks</span></span>

<span data-ttu-id="cba69-115">此属性是邮件的原始发件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="cba69-115">This property is one of the address properties for the original sender of a message.</span></span> <span data-ttu-id="cba69-116">首次提交邮件时，客户端应用程序应该将此属性设置为 PR_SENDER_ENTRYID ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 属性的值。 </span><span class="sxs-lookup"><span data-stu-id="cba69-116">At first submission of the message, a client application should set this property to the value of the **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="cba69-117">转发或答复邮件时从不更改。</span><span class="sxs-lookup"><span data-stu-id="cba69-117">It is never changed when the message is forwarded or replied to.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cba69-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="cba69-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cba69-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="cba69-119">Protocol specifications</span></span>

<span data-ttu-id="cba69-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cba69-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cba69-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="cba69-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cba69-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cba69-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cba69-123">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="cba69-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cba69-124">头文件</span><span class="sxs-lookup"><span data-stu-id="cba69-124">Header files</span></span>

<span data-ttu-id="cba69-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cba69-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="cba69-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cba69-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="cba69-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cba69-127">Mapitags.h</span></span>
  
> <span data-ttu-id="cba69-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cba69-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cba69-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cba69-129">See also</span></span>



[<span data-ttu-id="cba69-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cba69-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cba69-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cba69-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cba69-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cba69-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cba69-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cba69-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

