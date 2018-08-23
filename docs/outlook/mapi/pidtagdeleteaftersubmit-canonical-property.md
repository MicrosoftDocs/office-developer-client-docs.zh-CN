---
title: PidTagDeleteAfterSubmit 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeleteAfterSubmit
api_type:
- HeaderDef
ms.assetid: ba69a557-120c-4b1e-bbb7-0e901e7d1ebf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21bbb498eb4d53704c7a1a1a5bc84e9c72a75258
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566424"
---
# <a name="pidtagdeleteaftersubmit-canonical-property"></a><span data-ttu-id="108f9-103">PidTagDeleteAfterSubmit 规范属性</span><span class="sxs-lookup"><span data-stu-id="108f9-103">PidTagDeleteAfterSubmit Canonical Property</span></span>

  
  
<span data-ttu-id="108f9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="108f9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="108f9-105">如果客户端应用程序提交后删除关联的邮件的 MAPI，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="108f9-105">Contains TRUE if a client application wants MAPI to delete the associated message after submission.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="108f9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="108f9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="108f9-107">PR_DELETE_AFTER_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="108f9-107">PR_DELETE_AFTER_SUBMIT</span></span>  <br/> |
|<span data-ttu-id="108f9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="108f9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="108f9-109">0x0E01</span><span class="sxs-lookup"><span data-stu-id="108f9-109">0x0E01</span></span>  <br/> |
|<span data-ttu-id="108f9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="108f9-110">Data type:</span></span>  <br/> |<span data-ttu-id="108f9-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="108f9-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="108f9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="108f9-112">Area:</span></span>  <br/> |<span data-ttu-id="108f9-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="108f9-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="108f9-114">注解</span><span class="sxs-lookup"><span data-stu-id="108f9-114">Remarks</span></span>

<span data-ttu-id="108f9-115">客户端应用程序使用此属性与**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性控制提交后，一条消息，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="108f9-115">A client application uses this property with the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property to control what happens to a message after it is submitted.</span></span> <span data-ttu-id="108f9-116">设置，但不是能同时，应为一个或多。</span><span class="sxs-lookup"><span data-stu-id="108f9-116">Either one or the other should be set, but not both.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="108f9-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="108f9-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="108f9-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="108f9-118">Protocol specifications</span></span>

<span data-ttu-id="108f9-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="108f9-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="108f9-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="108f9-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="108f9-121">[[MS OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="108f9-121">[[MS-OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="108f9-122">指定允许的操作的核心消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="108f9-122">Specifies permissible operations for the core message store objects.</span></span>
    
<span data-ttu-id="108f9-123">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="108f9-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="108f9-124">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="108f9-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="108f9-125">头文件</span><span class="sxs-lookup"><span data-stu-id="108f9-125">Header files</span></span>

<span data-ttu-id="108f9-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="108f9-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="108f9-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="108f9-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="108f9-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="108f9-128">Mapitags.h</span></span>
  
> <span data-ttu-id="108f9-129">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="108f9-129">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="108f9-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="108f9-130">See also</span></span>



[<span data-ttu-id="108f9-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="108f9-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="108f9-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="108f9-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="108f9-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="108f9-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="108f9-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="108f9-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

