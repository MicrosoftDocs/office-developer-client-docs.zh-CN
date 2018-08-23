---
title: PidLidClassificationKeep 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidClassificationKeep
api_type:
- COM
ms.assetid: 83a4d458-9982-4857-8d4a-7ce4a0d97668
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e2a1aa45bfd718fa8ae1d4cd827023a80463a47
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580444"
---
# <a name="pidlidclassificationkeep-canonical-property"></a><span data-ttu-id="23094-103">PidLidClassificationKeep 规范属性</span><span class="sxs-lookup"><span data-stu-id="23094-103">PidLidClassificationKeep Canonical Property</span></span>

  
  
<span data-ttu-id="23094-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="23094-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="23094-105">指示是否保留邮件分类应为邮件转发或答复邮件时。</span><span class="sxs-lookup"><span data-stu-id="23094-105">Indicates whether the message classification should persist with the message if the message is forwarded or replied.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="23094-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="23094-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="23094-107">dispidClassKeep</span><span class="sxs-lookup"><span data-stu-id="23094-107">dispidClassKeep</span></span>  <br/> |
|<span data-ttu-id="23094-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="23094-108">Property set:</span></span>  <br/> |<span data-ttu-id="23094-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="23094-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="23094-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="23094-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="23094-111">0x000085BA</span><span class="sxs-lookup"><span data-stu-id="23094-111">0x000085BA</span></span>  <br/> |
|<span data-ttu-id="23094-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="23094-112">Data type:</span></span>  <br/> |<span data-ttu-id="23094-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="23094-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="23094-114">区域：</span><span class="sxs-lookup"><span data-stu-id="23094-114">Area:</span></span>  <br/> |<span data-ttu-id="23094-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="23094-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="23094-116">注解</span><span class="sxs-lookup"><span data-stu-id="23094-116">Remarks</span></span>

<span data-ttu-id="23094-117">有关其他信息，请参阅[如何为 Outlook 2007 部署邮件分类](http://msdn.microsoft.com/library/5a220424-edd5-4a21-b7fd-8106c23c3b39.aspx)。</span><span class="sxs-lookup"><span data-stu-id="23094-117">For additional information, see [How to Deploy Message Classification for Outlook 2007](http://msdn.microsoft.com/library/5a220424-edd5-4a21-b7fd-8106c23c3b39.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="23094-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="23094-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="23094-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="23094-119">Protocol specifications</span></span>

<span data-ttu-id="23094-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="23094-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="23094-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="23094-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="23094-122">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="23094-122">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="23094-123">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="23094-123">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="23094-124">头文件</span><span class="sxs-lookup"><span data-stu-id="23094-124">Header files</span></span>

<span data-ttu-id="23094-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="23094-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="23094-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="23094-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="23094-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23094-127">See also</span></span>



[<span data-ttu-id="23094-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="23094-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="23094-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="23094-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="23094-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="23094-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="23094-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="23094-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

