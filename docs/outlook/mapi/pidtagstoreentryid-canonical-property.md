---
title: PidTagStoreEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreEntryId
api_type:
- COM
ms.assetid: 0d705667-19f4-4eda-a068-e65ea8f00d9b
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 075c5e894d4b039ce06ca0508b838a7094af8768
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778452"
---
# <a name="pidtagstoreentryid-canonical-property"></a><span data-ttu-id="fed39-103">PidTagStoreEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="fed39-103">PidTagStoreEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="fed39-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fed39-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fed39-105">包含消息存储对象所在的位置的唯一项标识符。</span><span class="sxs-lookup"><span data-stu-id="fed39-105">Contains the unique entry identifier of the message store where an object resides.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fed39-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="fed39-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fed39-107">PR_STORE_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="fed39-107">PR_STORE_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="fed39-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fed39-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fed39-109">0x0FFB</span><span class="sxs-lookup"><span data-stu-id="fed39-109">0x0FFB</span></span>  <br/> |
|<span data-ttu-id="fed39-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fed39-110">Data type:</span></span>  <br/> |<span data-ttu-id="fed39-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="fed39-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="fed39-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fed39-112">Area:</span></span>  <br/> |<span data-ttu-id="fed39-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="fed39-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fed39-114">备注</span><span class="sxs-lookup"><span data-stu-id="fed39-114">Remarks</span></span>

<span data-ttu-id="fed39-115">此属性用于与[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法打开的消息存储。</span><span class="sxs-lookup"><span data-stu-id="fed39-115">This property is used to open a message store with the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method.</span></span> <span data-ttu-id="fed39-116">它还用于打开拥有的任何对象的消息存储库。</span><span class="sxs-lookup"><span data-stu-id="fed39-116">It is also used to open any object that is owned by the message store.</span></span> 
  
<span data-ttu-id="fed39-117">消息存储区，该属性等同于存储自己**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="fed39-117">For a message store, this property is identical to the store's own **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="fed39-118">使用[IMAPISession::CompareEntryIDs](imapisession-compareentryids.md)方法的两个属性，可以将进行比较的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="fed39-118">A client application can compare the two properties using the [IMAPISession::CompareEntryIDs](imapisession-compareentryids.md) method.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="fed39-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="fed39-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fed39-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="fed39-120">Protocol specifications</span></span>

<span data-ttu-id="fed39-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed39-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed39-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="fed39-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fed39-123">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed39-123">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed39-124">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="fed39-124">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="fed39-125">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed39-125">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed39-126">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="fed39-126">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="fed39-127">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed39-127">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed39-128">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="fed39-128">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="fed39-129">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed39-129">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed39-130">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="fed39-130">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fed39-131">头文件</span><span class="sxs-lookup"><span data-stu-id="fed39-131">Header files</span></span>

<span data-ttu-id="fed39-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fed39-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="fed39-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fed39-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="fed39-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fed39-134">Mapitags.h</span></span>
  
> <span data-ttu-id="fed39-135">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fed39-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fed39-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fed39-136">See also</span></span>



[<span data-ttu-id="fed39-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fed39-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fed39-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fed39-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fed39-139">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fed39-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fed39-140">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fed39-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

