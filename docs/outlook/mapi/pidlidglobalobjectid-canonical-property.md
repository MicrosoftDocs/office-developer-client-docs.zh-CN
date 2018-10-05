---
title: PidLidGlobalObjectId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidGlobalObjectId
api_type:
- COM
ms.assetid: a4e3f9ab-b7ee-4dff-b7bd-2462c561735c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c7a77e6e295d1433bd617a55656ee15d172f1f06
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390665"
---
# <a name="pidlidglobalobjectid-canonical-property"></a><span data-ttu-id="2ddbd-103">PidLidGlobalObjectId 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ddbd-103">PidLidGlobalObjectId Canonical Property</span></span>

  
  
<span data-ttu-id="2ddbd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ddbd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ddbd-105">指定的 calendar 对象的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="2ddbd-105">Specifies the unique identifier of the calendar object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ddbd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2ddbd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2ddbd-107">LID_GLOBAL_OBJID</span><span class="sxs-lookup"><span data-stu-id="2ddbd-107">LID_GLOBAL_OBJID</span></span>  <br/> |
|<span data-ttu-id="2ddbd-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="2ddbd-108">Property set:</span></span>  <br/> |<span data-ttu-id="2ddbd-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="2ddbd-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="2ddbd-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="2ddbd-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2ddbd-111">0x00000003</span><span class="sxs-lookup"><span data-stu-id="2ddbd-111">0x00000003</span></span>  <br/> |
|<span data-ttu-id="2ddbd-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2ddbd-112">Data type:</span></span>  <br/> |<span data-ttu-id="2ddbd-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2ddbd-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2ddbd-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2ddbd-114">Area:</span></span>  <br/> |<span data-ttu-id="2ddbd-115">会议</span><span class="sxs-lookup"><span data-stu-id="2ddbd-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ddbd-116">说明</span><span class="sxs-lookup"><span data-stu-id="2ddbd-116">Remarks</span></span>

<span data-ttu-id="2ddbd-117">一次设置 calendar 对象，此属性的值必须不会更改。</span><span class="sxs-lookup"><span data-stu-id="2ddbd-117">Once set for a calendar object, the value of this property must not change.</span></span> <span data-ttu-id="2ddbd-118">[[MS OXOCAL]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中找不到格式的详细的说明。</span><span class="sxs-lookup"><span data-stu-id="2ddbd-118">A detailed description of the format can be found in [[MS-OXOCAL]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2ddbd-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="2ddbd-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2ddbd-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="2ddbd-120">Protocol specifications</span></span>

<span data-ttu-id="2ddbd-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ddbd-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2ddbd-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2ddbd-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2ddbd-123">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ddbd-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2ddbd-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="2ddbd-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2ddbd-125">头文件</span><span class="sxs-lookup"><span data-stu-id="2ddbd-125">Header files</span></span>

<span data-ttu-id="2ddbd-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2ddbd-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="2ddbd-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2ddbd-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2ddbd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ddbd-128">See also</span></span>



[<span data-ttu-id="2ddbd-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2ddbd-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2ddbd-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ddbd-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2ddbd-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2ddbd-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2ddbd-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ddbd-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

