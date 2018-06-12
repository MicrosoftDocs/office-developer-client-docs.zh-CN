---
title: PidLidLogEnd 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLogEnd
api_type:
- COM
ms.assetid: 621459ea-adf5-4420-9f0f-6f31b9b95508
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ef1c9814aa6d1f81a44883d09ac635a5eed76517
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776904"
---
# <a name="pidlidlogend-canonical-property"></a><span data-ttu-id="50d75-103">PidLidLogEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="50d75-103">PidLidLogEnd Canonical Property</span></span>

  
  
<span data-ttu-id="50d75-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="50d75-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="50d75-105">表示的结束日期和时间的日记邮件。</span><span class="sxs-lookup"><span data-stu-id="50d75-105">Represents the end date and time for the journal message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="50d75-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="50d75-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="50d75-107">dispidLogEnd</span><span class="sxs-lookup"><span data-stu-id="50d75-107">dispidLogEnd</span></span>  <br/> |
|<span data-ttu-id="50d75-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="50d75-108">Property set:</span></span>  <br/> |<span data-ttu-id="50d75-109">PSETID_Log</span><span class="sxs-lookup"><span data-stu-id="50d75-109">PSETID_Log</span></span>  <br/> |
|<span data-ttu-id="50d75-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="50d75-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="50d75-111">0x00008708</span><span class="sxs-lookup"><span data-stu-id="50d75-111">0x00008708</span></span>  <br/> |
|<span data-ttu-id="50d75-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="50d75-112">Data type:</span></span>  <br/> |<span data-ttu-id="50d75-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="50d75-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="50d75-114">区域：</span><span class="sxs-lookup"><span data-stu-id="50d75-114">Area:</span></span>  <br/> |<span data-ttu-id="50d75-115">日记</span><span class="sxs-lookup"><span data-stu-id="50d75-115">Journal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="50d75-116">备注</span><span class="sxs-lookup"><span data-stu-id="50d75-116">Remarks</span></span>

<span data-ttu-id="50d75-117">活动的结束时间以协调世界时 (UTC)，必须等于**dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) 属性和大于或等于**dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="50d75-117">The time when the activity ended in Coordinated Universal Time The (UTC), which must be equal to the **dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) property and greater than or equal to **dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="50d75-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="50d75-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="50d75-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="50d75-119">Protocol specifications</span></span>

<span data-ttu-id="50d75-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="50d75-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="50d75-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="50d75-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="50d75-122">[[MS OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="50d75-122">[[MS-OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="50d75-123">指定的属性和操作所允许的日志。</span><span class="sxs-lookup"><span data-stu-id="50d75-123">Specifies the properties and operations that are permissible for journals.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="50d75-124">头文件</span><span class="sxs-lookup"><span data-stu-id="50d75-124">Header files</span></span>

<span data-ttu-id="50d75-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="50d75-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="50d75-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="50d75-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="50d75-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50d75-127">See also</span></span>



[<span data-ttu-id="50d75-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="50d75-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="50d75-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="50d75-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="50d75-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="50d75-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="50d75-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="50d75-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

