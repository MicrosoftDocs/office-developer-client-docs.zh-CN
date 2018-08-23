---
title: PidLidNoteHeight 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidNoteHeight
api_type:
- COM
ms.assetid: 2d8ca0e1-6849-4e27-a26f-e77d0df608fd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f5f2d95a2968420bc26a78f2a05e718070f95b37
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580892"
---
# <a name="pidlidnoteheight-canonical-property"></a><span data-ttu-id="41b9b-103">PidLidNoteHeight 规范属性</span><span class="sxs-lookup"><span data-stu-id="41b9b-103">PidLidNoteHeight Canonical Property</span></span>

  
  
<span data-ttu-id="41b9b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="41b9b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="41b9b-105">以像素为单位指定显示一条消息窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="41b9b-105">Specifies the height of the visible message window in pixels.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="41b9b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="41b9b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="41b9b-107">dispidNoteHeight</span><span class="sxs-lookup"><span data-stu-id="41b9b-107">dispidNoteHeight</span></span>  <br/> |
|<span data-ttu-id="41b9b-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="41b9b-108">Property set:</span></span>  <br/> |<span data-ttu-id="41b9b-109">PSETID_Note</span><span class="sxs-lookup"><span data-stu-id="41b9b-109">PSETID_Note</span></span>  <br/> |
|<span data-ttu-id="41b9b-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="41b9b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="41b9b-111">0x00008B03</span><span class="sxs-lookup"><span data-stu-id="41b9b-111">0x00008B03</span></span>  <br/> |
|<span data-ttu-id="41b9b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="41b9b-112">Data type:</span></span>  <br/> |<span data-ttu-id="41b9b-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="41b9b-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="41b9b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="41b9b-114">Area:</span></span>  <br/> |<span data-ttu-id="41b9b-115">粘滞便笺</span><span class="sxs-lookup"><span data-stu-id="41b9b-115">Sticky Note</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="41b9b-116">注解</span><span class="sxs-lookup"><span data-stu-id="41b9b-116">Remarks</span></span>

<span data-ttu-id="41b9b-117">此值必须大于零。</span><span class="sxs-lookup"><span data-stu-id="41b9b-117">This value must be greater than zero.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="41b9b-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="41b9b-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="41b9b-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="41b9b-119">Protocol specifications</span></span>

<span data-ttu-id="41b9b-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="41b9b-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="41b9b-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="41b9b-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="41b9b-122">[[MS OXONOTE]](http://msdn.microsoft.com/library/6bf4ed7e-316c-4a3c-be27-5ec93e7ab39f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="41b9b-122">[[MS-OXONOTE]](http://msdn.microsoft.com/library/6bf4ed7e-316c-4a3c-be27-5ec93e7ab39f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="41b9b-123">指定的属性和说明在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="41b9b-123">Specifies the properties and operations that are permissible on notes.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="41b9b-124">头文件</span><span class="sxs-lookup"><span data-stu-id="41b9b-124">Header files</span></span>

<span data-ttu-id="41b9b-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="41b9b-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="41b9b-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="41b9b-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="41b9b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41b9b-127">See also</span></span>



[<span data-ttu-id="41b9b-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="41b9b-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="41b9b-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="41b9b-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="41b9b-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="41b9b-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="41b9b-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="41b9b-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

