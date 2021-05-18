---
title: PidTagHasAttachments 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagHasAttachments
api_type:
- HeaderDef
ms.assetid: fd236d74-2868-46a8-bb3d-17f8365931b6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aca9c9f9c22fc4057f1650d1342492d2ed34653c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316126"
---
# <a name="pidtaghasattachments-canonical-property"></a><span data-ttu-id="cdc29-103">PidTagHasAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="cdc29-103">PidTagHasAttachments Canonical Property</span></span>

  
  
<span data-ttu-id="cdc29-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cdc29-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cdc29-105">如果邮件包含至少一个附件，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="cdc29-105">Contains TRUE if a message contains at least one attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cdc29-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cdc29-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cdc29-107">PR_HASATTACH</span><span class="sxs-lookup"><span data-stu-id="cdc29-107">PR_HASATTACH</span></span>  <br/> |
|<span data-ttu-id="cdc29-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="cdc29-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cdc29-109">0x0E1B</span><span class="sxs-lookup"><span data-stu-id="cdc29-109">0x0E1B</span></span>  <br/> |
|<span data-ttu-id="cdc29-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cdc29-110">Data type:</span></span>  <br/> |<span data-ttu-id="cdc29-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="cdc29-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="cdc29-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cdc29-112">Area:</span></span>  <br/> |<span data-ttu-id="cdc29-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="cdc29-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cdc29-114">备注</span><span class="sxs-lookup"><span data-stu-id="cdc29-114">Remarks</span></span>

<span data-ttu-id="cdc29-115">邮件存储从[PidTagMessageFlags PR_MESSAGE_FLAGS (PidTagMessageFlags](pidtagmessageflags-canonical-property.md) MSGFLAG_HASATTACH的) 标记中复制此属性。  </span><span class="sxs-lookup"><span data-stu-id="cdc29-115">The message store copies this property from the **MSGFLAG_HASATTACH** flag of the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="cdc29-116">然后，客户端 **应用程序可以使用PR_HASATTACH** 对邮件查看器中的邮件附件进行排序。</span><span class="sxs-lookup"><span data-stu-id="cdc29-116">A client application can then use **PR_HASATTACH** to sort on message attachments in a message viewer.</span></span> 
  
<span data-ttu-id="cdc29-117">使用 [IMAPIProp：：SaveChanges 方法更新此](imapiprop-savechanges.md) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="cdc29-117">The value this property is updated with the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="cdc29-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="cdc29-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cdc29-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="cdc29-119">Protocol specifications</span></span>

<span data-ttu-id="cdc29-120">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cdc29-120">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cdc29-121">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="cdc29-121">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cdc29-122">头文件</span><span class="sxs-lookup"><span data-stu-id="cdc29-122">Header files</span></span>

<span data-ttu-id="cdc29-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cdc29-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="cdc29-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cdc29-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="cdc29-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cdc29-125">Mapitags.h</span></span>
  
> <span data-ttu-id="cdc29-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cdc29-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cdc29-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdc29-127">See also</span></span>



[<span data-ttu-id="cdc29-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cdc29-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cdc29-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cdc29-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cdc29-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cdc29-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cdc29-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cdc29-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

