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
ms.openlocfilehash: 2708d89e2572e8820de0b525b4f53ccd309ae2a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359911"
---
# <a name="pidtagdeleteaftersubmit-canonical-property"></a><span data-ttu-id="e89a4-103">PidTagDeleteAfterSubmit 规范属性</span><span class="sxs-lookup"><span data-stu-id="e89a4-103">PidTagDeleteAfterSubmit Canonical Property</span></span>

  
  
<span data-ttu-id="e89a4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e89a4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e89a4-105">如果客户端应用程序希望 MAPI 在提交后删除关联的邮件，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="e89a4-105">Contains TRUE if a client application wants MAPI to delete the associated message after submission.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e89a4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e89a4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e89a4-107">PR_DELETE_AFTER_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="e89a4-107">PR_DELETE_AFTER_SUBMIT</span></span>  <br/> |
|<span data-ttu-id="e89a4-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e89a4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e89a4-109">0x0E01</span><span class="sxs-lookup"><span data-stu-id="e89a4-109">0x0E01</span></span>  <br/> |
|<span data-ttu-id="e89a4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e89a4-110">Data type:</span></span>  <br/> |<span data-ttu-id="e89a4-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="e89a4-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="e89a4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e89a4-112">Area:</span></span>  <br/> |<span data-ttu-id="e89a4-113">MAPI 不可传输</span><span class="sxs-lookup"><span data-stu-id="e89a4-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e89a4-114">备注</span><span class="sxs-lookup"><span data-stu-id="e89a4-114">Remarks</span></span>

<span data-ttu-id="e89a4-115">客户端应用程序使用此属性和 PR_SENTMAIL_ENTRYID  ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性来控制邮件提交后会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e89a4-115">A client application uses this property with the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property to control what happens to a message after it is submitted.</span></span> <span data-ttu-id="e89a4-116">应设置其中一个，但不能同时设置两者。</span><span class="sxs-lookup"><span data-stu-id="e89a4-116">Either one or the other should be set, but not both.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e89a4-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="e89a4-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e89a4-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="e89a4-118">Protocol specifications</span></span>

<span data-ttu-id="e89a4-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e89a4-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e89a4-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="e89a4-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e89a4-121">[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e89a4-121">[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e89a4-122">指定核心邮件存储对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="e89a4-122">Specifies permissible operations for the core message store objects.</span></span>
    
<span data-ttu-id="e89a4-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e89a4-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e89a4-124">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e89a4-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e89a4-125">头文件</span><span class="sxs-lookup"><span data-stu-id="e89a4-125">Header files</span></span>

<span data-ttu-id="e89a4-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e89a4-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="e89a4-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e89a4-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="e89a4-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e89a4-128">Mapitags.h</span></span>
  
> <span data-ttu-id="e89a4-129">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e89a4-129">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e89a4-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e89a4-130">See also</span></span>



[<span data-ttu-id="e89a4-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e89a4-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e89a4-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e89a4-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e89a4-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e89a4-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e89a4-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e89a4-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

