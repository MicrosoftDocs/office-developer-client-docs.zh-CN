---
title: PidTagStoreRecordKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreRecordKey
api_type:
- COM
ms.assetid: 27347302-bd52-4f62-98f1-6c37f9a66463
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4598ca5e654308f7701b1dd66adb227599773b7d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778478"
---
# <a name="pidtagstorerecordkey-canonical-property"></a><span data-ttu-id="e34f3-103">PidTagStoreRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="e34f3-103">PidTagStoreRecordKey Canonical Property</span></span>

  
  
<span data-ttu-id="e34f3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e34f3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e34f3-105">包含消息存储对象所在唯一的二进制相当的标识符 （记录密钥）。</span><span class="sxs-lookup"><span data-stu-id="e34f3-105">Contains the unique binary-comparable identifier (record key) of the message store in which an object resides.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e34f3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e34f3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e34f3-107">PR_STORE_RECORD_KEY</span><span class="sxs-lookup"><span data-stu-id="e34f3-107">PR_STORE_RECORD_KEY</span></span>  <br/> |
|<span data-ttu-id="e34f3-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e34f3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e34f3-109">0x0FFA</span><span class="sxs-lookup"><span data-stu-id="e34f3-109">0x0FFA</span></span>  <br/> |
|<span data-ttu-id="e34f3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e34f3-110">Data type:</span></span>  <br/> |<span data-ttu-id="e34f3-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e34f3-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e34f3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e34f3-112">Area:</span></span>  <br/> |<span data-ttu-id="e34f3-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="e34f3-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e34f3-114">说明</span><span class="sxs-lookup"><span data-stu-id="e34f3-114">Remarks</span></span>

<span data-ttu-id="e34f3-115">消息存储区，该属性等同于存储自己**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e34f3-115">For a message store, this property is identical to the store's own **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="e34f3-116">该属性与**PR_RECORD_KEY**之间的关系是**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 和**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 之间的关系相同。</span><span class="sxs-lookup"><span data-stu-id="e34f3-116">The relationship between this property and **PR_RECORD_KEY** is the same as the relationship between **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) and **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e34f3-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="e34f3-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e34f3-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="e34f3-118">Protocol specifications</span></span>

<span data-ttu-id="e34f3-119">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e34f3-119">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e34f3-120">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="e34f3-120">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="e34f3-121">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e34f3-121">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e34f3-122">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="e34f3-122">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e34f3-123">头文件</span><span class="sxs-lookup"><span data-stu-id="e34f3-123">Header files</span></span>

<span data-ttu-id="e34f3-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e34f3-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="e34f3-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e34f3-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="e34f3-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e34f3-126">Mapitags.h</span></span>
  
> <span data-ttu-id="e34f3-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e34f3-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e34f3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e34f3-128">See also</span></span>



[<span data-ttu-id="e34f3-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e34f3-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e34f3-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e34f3-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e34f3-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e34f3-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e34f3-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e34f3-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

