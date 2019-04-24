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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dea709b457e28efef62718fc388621e01c4eb5bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279707"
---
# <a name="pidtaglastmodificationtime-canonical-property"></a><span data-ttu-id="be282-103">PidTagLastModificationTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="be282-103">PidTagLastModificationTime Canonical Property</span></span>

  
  
<span data-ttu-id="be282-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="be282-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="be282-105">包含上次修改对象或子对象时的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="be282-105">Contains the date and time when the object or subobject was last modified.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="be282-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="be282-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="be282-107">操作</span><span class="sxs-lookup"><span data-stu-id="be282-107">PR_LAST_MODIFICATION_TIME</span></span>  <br/> |
|<span data-ttu-id="be282-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="be282-108">Identifier:</span></span>  <br/> |<span data-ttu-id="be282-109">0x3008</span><span class="sxs-lookup"><span data-stu-id="be282-109">0x3008</span></span>  <br/> |
|<span data-ttu-id="be282-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="be282-110">Data type:</span></span>  <br/> |<span data-ttu-id="be282-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="be282-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="be282-112">区域：</span><span class="sxs-lookup"><span data-stu-id="be282-112">Area:</span></span>  <br/> |<span data-ttu-id="be282-113">邮件时间</span><span class="sxs-lookup"><span data-stu-id="be282-113">Message time</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="be282-114">注解</span><span class="sxs-lookup"><span data-stu-id="be282-114">Remarks</span></span>

<span data-ttu-id="be282-115">此属性最初设置为与**PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md)) 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="be282-115">This property is initially set to the same value as the **PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md)) property.</span></span> <span data-ttu-id="be282-116">通过复制由本机文件系统维护的上次修改时间, 附件子文件可根据需要进行更新。</span><span class="sxs-lookup"><span data-stu-id="be282-116">Attachment subobjects can update it as necessary by copying the last modification time maintained by the native file system.</span></span> <span data-ttu-id="be282-117">在第一次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法之前, 客户端应用程序可以设置此属性。</span><span class="sxs-lookup"><span data-stu-id="be282-117">A client application can set this property until the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="be282-118">从随后, 提供程序应在每个**IMAPIProp:: SaveChanges**调用中更新**操作**。</span><span class="sxs-lookup"><span data-stu-id="be282-118">From then on the provider should update **PR_LAST_MODIFICATION_TIME** during every **IMAPIProp::SaveChanges** call.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="be282-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="be282-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="be282-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="be282-120">Protocol specifications</span></span>

<span data-ttu-id="be282-121">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="be282-121">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="be282-122">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="be282-122">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="be282-123">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="be282-123">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="be282-124">处理服务器和客户端之间的同步邮件对象数据。</span><span class="sxs-lookup"><span data-stu-id="be282-124">Handles synchronizing messaging object data between a server and a client.</span></span>
    
<span data-ttu-id="be282-125">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="be282-125">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="be282-126">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="be282-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="be282-127">头文件</span><span class="sxs-lookup"><span data-stu-id="be282-127">Header files</span></span>

<span data-ttu-id="be282-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="be282-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="be282-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="be282-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="be282-130">Mapitags</span><span class="sxs-lookup"><span data-stu-id="be282-130">Mapitags.h</span></span>
  
> <span data-ttu-id="be282-131">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="be282-131">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="be282-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be282-132">See also</span></span>



[<span data-ttu-id="be282-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="be282-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="be282-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="be282-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="be282-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="be282-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="be282-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="be282-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

