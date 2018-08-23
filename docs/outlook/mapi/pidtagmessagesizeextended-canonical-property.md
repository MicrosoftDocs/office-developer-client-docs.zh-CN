---
title: PidTagMessageSizeExtended 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageSizeExtended
api_type:
- HeaderDef
ms.assetid: e6413cb9-2633-44a0-b408-b5688c47433e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5090ec35885ada98e1e9c0e35c97d51ba98b1b77
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595256"
---
# <a name="pidtagmessagesizeextended-canonical-property"></a><span data-ttu-id="8d980-103">PidTagMessageSizeExtended 规范属性</span><span class="sxs-lookup"><span data-stu-id="8d980-103">PidTagMessageSizeExtended Canonical Property</span></span>

  
  
<span data-ttu-id="8d980-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8d980-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8d980-105">包含 64 位整数版本的**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="8d980-105">Contains a 64 bit integer version of the **PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8d980-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8d980-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8d980-107">PR_MESSAGE_SIZE_EXTENDED</span><span class="sxs-lookup"><span data-stu-id="8d980-107">PR_MESSAGE_SIZE_EXTENDED</span></span>  <br/> |
|<span data-ttu-id="8d980-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8d980-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8d980-109">0x0E08</span><span class="sxs-lookup"><span data-stu-id="8d980-109">0x0E08</span></span>  <br/> |
|<span data-ttu-id="8d980-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8d980-110">Data type:</span></span>  <br/> |<span data-ttu-id="8d980-111">PT_I8</span><span class="sxs-lookup"><span data-stu-id="8d980-111">PT_I8</span></span>  <br/> |
|<span data-ttu-id="8d980-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8d980-112">Area:</span></span>  <br/> |<span data-ttu-id="8d980-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="8d980-113">General messaging</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="8d980-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="8d980-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8d980-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="8d980-115">Protocol specifications</span></span>

<span data-ttu-id="8d980-116">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8d980-116">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8d980-117">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="8d980-117">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8d980-118">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8d980-118">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8d980-119">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="8d980-119">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="8d980-120">[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8d980-120">[[MS-OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8d980-121">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="8d980-121">Handles folder operations.</span></span>
    
<span data-ttu-id="8d980-122">[[MS OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8d980-122">[[MS-OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8d980-123">指定允许的操作的核心消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="8d980-123">Specifies permissible operations for the core message store objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8d980-124">头文件</span><span class="sxs-lookup"><span data-stu-id="8d980-124">Header files</span></span>

<span data-ttu-id="8d980-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8d980-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="8d980-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8d980-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="8d980-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8d980-127">Mapitags.h</span></span>
  
> <span data-ttu-id="8d980-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8d980-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8d980-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d980-129">See also</span></span>



[<span data-ttu-id="8d980-130">PidTagMessageSize 规范属性</span><span class="sxs-lookup"><span data-stu-id="8d980-130">PidTagMessageSize Canonical Property</span></span>](pidtagmessagesize-canonical-property.md)


[<span data-ttu-id="8d980-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8d980-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8d980-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8d980-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8d980-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8d980-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8d980-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8d980-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

