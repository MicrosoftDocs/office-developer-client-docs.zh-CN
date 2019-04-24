---
title: PidTagContentReturnRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentReturnRequested
api_type:
- HeaderDef
ms.assetid: f86f7c59-42ab-4ac0-80fe-c985103e6bd6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c64288f393f15ee330065a43a92930f2e6f4e134
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331904"
---
# <a name="pidtagcontentreturnrequested-canonical-property"></a><span data-ttu-id="02b23-103">PidTagContentReturnRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="02b23-103">PidTagContentReturnRequested Canonical Property</span></span>

  
  
<span data-ttu-id="02b23-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="02b23-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="02b23-105">如果邮件应返回 nondelivery 报告, 则该参数包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="02b23-105">Contains TRUE if a message should be returned with a nondelivery report.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="02b23-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="02b23-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="02b23-107">PR_CONTENT_RETURN_REQUESTED</span><span class="sxs-lookup"><span data-stu-id="02b23-107">PR_CONTENT_RETURN_REQUESTED</span></span>  <br/> |
|<span data-ttu-id="02b23-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="02b23-108">Identifier:</span></span>  <br/> |<span data-ttu-id="02b23-109">0x000A</span><span class="sxs-lookup"><span data-stu-id="02b23-109">0x000A</span></span>  <br/> |
|<span data-ttu-id="02b23-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="02b23-110">Data type:</span></span>  <br/> |<span data-ttu-id="02b23-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="02b23-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="02b23-112">区域：</span><span class="sxs-lookup"><span data-stu-id="02b23-112">Area:</span></span>  <br/> |<span data-ttu-id="02b23-113">报表</span><span class="sxs-lookup"><span data-stu-id="02b23-113">Report</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="02b23-114">注解</span><span class="sxs-lookup"><span data-stu-id="02b23-114">Remarks</span></span>

<span data-ttu-id="02b23-115">如果未设置此属性, 则 MAPI 会将其视为具有真正的值。</span><span class="sxs-lookup"><span data-stu-id="02b23-115">If this property is not set, MAPI treats it as having a TRUE value.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="02b23-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="02b23-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="02b23-117">头文件</span><span class="sxs-lookup"><span data-stu-id="02b23-117">Header files</span></span>

<span data-ttu-id="02b23-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="02b23-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="02b23-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="02b23-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="02b23-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="02b23-120">Mapitags.h</span></span>
  
> <span data-ttu-id="02b23-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="02b23-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="02b23-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02b23-122">See also</span></span>



[<span data-ttu-id="02b23-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="02b23-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="02b23-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="02b23-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="02b23-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="02b23-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="02b23-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="02b23-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

