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
ms.openlocfilehash: 0e49b73c777988ad3559a442af920af3d8f4bdbb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356467"
---
# <a name="pidtagreadreceiptrequested-canonical-property"></a><span data-ttu-id="42dc8-103">PidTagReadReceiptRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="42dc8-103">PidTagReadReceiptRequested Canonical Property</span></span>

  
  
<span data-ttu-id="42dc8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="42dc8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="42dc8-105">如果邮件发件人希望邮件系统在收件人阅读邮件时生成阅读报告, 则该参数为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="42dc8-105">Contains TRUE if a message sender wants the messaging system to generate a read report when the recipient has read a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="42dc8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="42dc8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="42dc8-107">PR_READ_RECEIPT_REQUESTED</span><span class="sxs-lookup"><span data-stu-id="42dc8-107">PR_READ_RECEIPT_REQUESTED</span></span>  <br/> |
|<span data-ttu-id="42dc8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="42dc8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="42dc8-109">0x0029</span><span class="sxs-lookup"><span data-stu-id="42dc8-109">0x0029</span></span>  <br/> |
|<span data-ttu-id="42dc8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="42dc8-110">Data type:</span></span>  <br/> |<span data-ttu-id="42dc8-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="42dc8-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="42dc8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="42dc8-112">Area:</span></span>  <br/> |<span data-ttu-id="42dc8-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="42dc8-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="42dc8-114">注解</span><span class="sxs-lookup"><span data-stu-id="42dc8-114">Remarks</span></span>

<span data-ttu-id="42dc8-115">此属性必须设置为 TRUE, 以验证**PR_READ_RECEIPT_ENTRYID** ([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md)) 和**PR_READ_RECEIPT_SEARCH_KEY** ([PidTagReadReceiptSearchKey](pidtagreadreceiptsearchkey-canonical-property.md)) 属性中的值。</span><span class="sxs-lookup"><span data-stu-id="42dc8-115">This property must be set to TRUE to validate the values in the **PR_READ_RECEIPT_ENTRYID** ([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md)) and **PR_READ_RECEIPT_SEARCH_KEY** ([PidTagReadReceiptSearchKey](pidtagreadreceiptsearchkey-canonical-property.md)) properties.</span></span>
  
<span data-ttu-id="42dc8-116">如果在邮件系统可以生成已读报告之前, **PR_READ_RECEIPT_REQUESTED**设置的邮件已被删除或过期, 则会生成未读报告。</span><span class="sxs-lookup"><span data-stu-id="42dc8-116">If a message with **PR_READ_RECEIPT_REQUESTED** set is deleted or expires before the messaging system can generate a read report, a nonread report is generated.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="42dc8-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="42dc8-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="42dc8-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="42dc8-118">Protocol specifications</span></span>

<span data-ttu-id="42dc8-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="42dc8-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="42dc8-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="42dc8-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="42dc8-121">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="42dc8-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="42dc8-122">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="42dc8-122">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="42dc8-123">头文件</span><span class="sxs-lookup"><span data-stu-id="42dc8-123">Header files</span></span>

<span data-ttu-id="42dc8-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="42dc8-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="42dc8-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="42dc8-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="42dc8-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="42dc8-126">Mapitags.h</span></span>
  
> <span data-ttu-id="42dc8-127">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="42dc8-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="42dc8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42dc8-128">See also</span></span>



[<span data-ttu-id="42dc8-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="42dc8-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="42dc8-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="42dc8-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="42dc8-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="42dc8-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="42dc8-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="42dc8-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

