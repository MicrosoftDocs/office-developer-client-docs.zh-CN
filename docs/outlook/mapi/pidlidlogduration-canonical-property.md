---
title: PidLidLogDuration 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLogDocumentSaved
api_type:
- COM
ms.assetid: 012a3f6e-fd16-4dc9-845d-2bf4cebeaa42
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: cc2d52ec183cc336bf126b1fda9a85d41f704f7d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776906"
---
# <a name="pidlidlogduration-canonical-property"></a><span data-ttu-id="97714-103">PidLidLogDuration 规范属性</span><span class="sxs-lookup"><span data-stu-id="97714-103">PidLidLogDuration Canonical Property</span></span>

  
  
<span data-ttu-id="97714-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="97714-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="97714-105">表示的工期，以分钟为单位的日记邮件。</span><span class="sxs-lookup"><span data-stu-id="97714-105">Represents the duration, in minutes, of a journal message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="97714-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="97714-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="97714-107">dispidLogDuration</span><span class="sxs-lookup"><span data-stu-id="97714-107">dispidLogDuration</span></span>  <br/> |
|<span data-ttu-id="97714-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="97714-108">Property set:</span></span>  <br/> |<span data-ttu-id="97714-109">PSETID_Log</span><span class="sxs-lookup"><span data-stu-id="97714-109">PSETID_Log</span></span>  <br/> |
|<span data-ttu-id="97714-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="97714-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="97714-111">0x00008707</span><span class="sxs-lookup"><span data-stu-id="97714-111">0x00008707</span></span>  <br/> |
|<span data-ttu-id="97714-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="97714-112">Data type:</span></span>  <br/> |<span data-ttu-id="97714-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="97714-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="97714-114">区域：</span><span class="sxs-lookup"><span data-stu-id="97714-114">Area:</span></span>  <br/> |<span data-ttu-id="97714-115">日记</span><span class="sxs-lookup"><span data-stu-id="97714-115">Journal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="97714-116">备注</span><span class="sxs-lookup"><span data-stu-id="97714-116">Remarks</span></span>

<span data-ttu-id="97714-117">持续时间，以分钟为单位的值必须为**dispidLogEnd** ([PidLidLogEnd](pidlidlogend-canonical-property.md)) 和**dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) 属性之间的差异的活动。</span><span class="sxs-lookup"><span data-stu-id="97714-117">The duration, in minutes, of the activity that must be the difference between the **dispidLogEnd** ([PidLidLogEnd](pidlidlogend-canonical-property.md)) and **dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="97714-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="97714-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="97714-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="97714-119">Protocol specifications</span></span>

<span data-ttu-id="97714-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="97714-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="97714-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="97714-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="97714-122">[[MS OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="97714-122">[[MS-OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="97714-123">指定的属性和操作所允许的日志。</span><span class="sxs-lookup"><span data-stu-id="97714-123">Specifies the properties and operations that are permissible for journals.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="97714-124">头文件</span><span class="sxs-lookup"><span data-stu-id="97714-124">Header files</span></span>

<span data-ttu-id="97714-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="97714-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="97714-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="97714-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="97714-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97714-127">See also</span></span>



[<span data-ttu-id="97714-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="97714-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="97714-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="97714-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="97714-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="97714-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="97714-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="97714-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

