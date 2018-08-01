---
title: PidTagReadReceiptRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReadReceiptRequested
api_type:
- COM
ms.assetid: 7db0645b-f3ab-4fc4-b865-68c952aeb359
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1d4d4404d175458d5b708948b11c93b734a8bd1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778111"
---
# <a name="pidtagreadreceiptrequested-canonical-property"></a><span data-ttu-id="e9dcd-103">PidTagReadReceiptRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="e9dcd-103">PidTagReadReceiptRequested Canonical Property</span></span>

  
  
<span data-ttu-id="e9dcd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e9dcd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e9dcd-105">如果邮件发件人消息系统收件人已阅读邮件时生成读取的报表，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="e9dcd-105">Contains TRUE if a message sender wants the messaging system to generate a read report when the recipient has read a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e9dcd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e9dcd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e9dcd-107">PR_READ_RECEIPT_REQUESTED</span><span class="sxs-lookup"><span data-stu-id="e9dcd-107">PR_READ_RECEIPT_REQUESTED</span></span>  <br/> |
|<span data-ttu-id="e9dcd-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e9dcd-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e9dcd-109">0x0029</span><span class="sxs-lookup"><span data-stu-id="e9dcd-109">0x0029</span></span>  <br/> |
|<span data-ttu-id="e9dcd-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e9dcd-110">Data type:</span></span>  <br/> |<span data-ttu-id="e9dcd-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="e9dcd-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="e9dcd-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e9dcd-112">Area:</span></span>  <br/> |<span data-ttu-id="e9dcd-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="e9dcd-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e9dcd-114">说明</span><span class="sxs-lookup"><span data-stu-id="e9dcd-114">Remarks</span></span>

<span data-ttu-id="e9dcd-115">此属性必须设置为 TRUE，以验证**PR_READ_RECEIPT_ENTRYID** ([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md)) 和**PR_READ_RECEIPT_SEARCH_KEY** ([PidTagReadReceiptSearchKey](pidtagreadreceiptsearchkey-canonical-property.md)) 属性中的值。</span><span class="sxs-lookup"><span data-stu-id="e9dcd-115">This property must be set to TRUE to validate the values in the **PR_READ_RECEIPT_ENTRYID** ([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md)) and **PR_READ_RECEIPT_SEARCH_KEY** ([PidTagReadReceiptSearchKey](pidtagreadreceiptsearchkey-canonical-property.md)) properties.</span></span>
  
<span data-ttu-id="e9dcd-116">如果**PR_READ_RECEIPT_REQUESTED**设置了一条消息被删除或过期之前在邮件系统可以生成阅读的报告，则生成 nonread 的报表。</span><span class="sxs-lookup"><span data-stu-id="e9dcd-116">If a message with **PR_READ_RECEIPT_REQUESTED** set is deleted or expires before the messaging system can generate a read report, a nonread report is generated.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e9dcd-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="e9dcd-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e9dcd-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="e9dcd-118">Protocol specifications</span></span>

<span data-ttu-id="e9dcd-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9dcd-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e9dcd-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e9dcd-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e9dcd-121">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9dcd-121">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e9dcd-122">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="e9dcd-122">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e9dcd-123">头文件</span><span class="sxs-lookup"><span data-stu-id="e9dcd-123">Header files</span></span>

<span data-ttu-id="e9dcd-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e9dcd-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="e9dcd-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e9dcd-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="e9dcd-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e9dcd-126">Mapitags.h</span></span>
  
> <span data-ttu-id="e9dcd-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e9dcd-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e9dcd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9dcd-128">See also</span></span>



[<span data-ttu-id="e9dcd-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e9dcd-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e9dcd-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e9dcd-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e9dcd-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e9dcd-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e9dcd-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e9dcd-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

