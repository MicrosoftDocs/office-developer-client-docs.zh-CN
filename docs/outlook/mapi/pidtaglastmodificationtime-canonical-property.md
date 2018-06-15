---
title: PidTagLastModificationTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLastModificationTime
api_type:
- HeaderDef
ms.assetid: a64e5300-6865-4588-8e1b-158cfd9c60c2
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bf58e0598af6eb833b003b824be95f8fb82bd8bf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19777808"
---
# <a name="pidtaglastmodificationtime-canonical-property"></a><span data-ttu-id="2ab7a-103">PidTagLastModificationTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ab7a-103">PidTagLastModificationTime Canonical Property</span></span>

  
  
<span data-ttu-id="2ab7a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2ab7a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2ab7a-105">包含的日期和时间上次修改的对象或子对象。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-105">Contains the date and time when the object or subobject was last modified.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2ab7a-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="2ab7a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2ab7a-107">操作</span><span class="sxs-lookup"><span data-stu-id="2ab7a-107">PR_LAST_MODIFICATION_TIME</span></span>  <br/> |
|<span data-ttu-id="2ab7a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2ab7a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2ab7a-109">0x3008</span><span class="sxs-lookup"><span data-stu-id="2ab7a-109">0x3008</span></span>  <br/> |
|<span data-ttu-id="2ab7a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2ab7a-110">Data type:</span></span>  <br/> |<span data-ttu-id="2ab7a-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="2ab7a-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="2ab7a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2ab7a-112">Area:</span></span>  <br/> |<span data-ttu-id="2ab7a-113">消息时间</span><span class="sxs-lookup"><span data-stu-id="2ab7a-113">Message time</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ab7a-114">备注</span><span class="sxs-lookup"><span data-stu-id="2ab7a-114">Remarks</span></span>

<span data-ttu-id="2ab7a-115">此属性最初设置为相同的值的**PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-115">This property is initially set to the same value as the **PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md)) property.</span></span> <span data-ttu-id="2ab7a-116">附件子对象可将其更新根据需要通过复制由本地文件系统维护的上次修改时间。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-116">Attachment subobjects can update it as necessary by copying the last modification time maintained by the native file system.</span></span> <span data-ttu-id="2ab7a-117">客户端应用程序直到第一个呼叫[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法可以设置该属性。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-117">A client application can set this property until the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="2ab7a-118">此后提供程序应在每个**IMAPIProp::SaveChanges**呼叫期间更新**操作**。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-118">From then on the provider should update **PR_LAST_MODIFICATION_TIME** during every **IMAPIProp::SaveChanges** call.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2ab7a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="2ab7a-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2ab7a-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="2ab7a-120">Protocol specifications</span></span>

<span data-ttu-id="2ab7a-121">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ab7a-121">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2ab7a-122">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-122">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="2ab7a-123">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ab7a-123">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2ab7a-124">同步服务器和客户端之间的消息对象数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-124">Handles synchronizing messaging object data between a server and a client.</span></span>
    
<span data-ttu-id="2ab7a-125">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ab7a-125">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2ab7a-126">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2ab7a-127">头文件</span><span class="sxs-lookup"><span data-stu-id="2ab7a-127">Header files</span></span>

<span data-ttu-id="2ab7a-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2ab7a-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="2ab7a-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="2ab7a-130">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2ab7a-130">Mapitags.h</span></span>
  
> <span data-ttu-id="2ab7a-131">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-131">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2ab7a-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ab7a-132">See also</span></span>



[<span data-ttu-id="2ab7a-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2ab7a-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2ab7a-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ab7a-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2ab7a-135">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ab7a-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2ab7a-136">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ab7a-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

