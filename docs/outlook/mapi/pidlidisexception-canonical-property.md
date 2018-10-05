---
title: PidLidIsException 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidIsException
api_type:
- COM
ms.assetid: 802321fb-4261-4c3e-9de3-8b4f490dae13
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 18dfa8a5936902afe0272274f7a48d01b28f94f3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386248"
---
# <a name="pidlidisexception-canonical-property"></a><span data-ttu-id="ee411-103">PidLidIsException 规范属性</span><span class="sxs-lookup"><span data-stu-id="ee411-103">PidLidIsException Canonical Property</span></span>

  
  
<span data-ttu-id="ee411-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ee411-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ee411-105">指示代表异常 （包括孤立实例） 的对象。</span><span class="sxs-lookup"><span data-stu-id="ee411-105">Indicates that the object that represents an exception (including an orphan instance).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ee411-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ee411-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ee411-107">LID_IS_EXCEPTION</span><span class="sxs-lookup"><span data-stu-id="ee411-107">LID_IS_EXCEPTION</span></span>  <br/> |
|<span data-ttu-id="ee411-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ee411-108">Property set:</span></span>  <br/> |<span data-ttu-id="ee411-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="ee411-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="ee411-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ee411-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ee411-111">0x0000000A</span><span class="sxs-lookup"><span data-stu-id="ee411-111">0x0000000A</span></span>  <br/> |
|<span data-ttu-id="ee411-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ee411-112">Data type:</span></span>  <br/> |<span data-ttu-id="ee411-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="ee411-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="ee411-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ee411-114">Area:</span></span>  <br/> |<span data-ttu-id="ee411-115">会议</span><span class="sxs-lookup"><span data-stu-id="ee411-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ee411-116">说明</span><span class="sxs-lookup"><span data-stu-id="ee411-116">Remarks</span></span>

<span data-ttu-id="ee411-117">值为 FALSE 指示该对象表示定期系列或单个实例。</span><span class="sxs-lookup"><span data-stu-id="ee411-117">A value of FALSE indicates that the object that represents a recurring series or a single instance.</span></span> <span data-ttu-id="ee411-118">此属性对于任何对象不存在指示值为 false，表示除异常嵌入消息，其中假定值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="ee411-118">The absence of this property for any object indicates a value of FALSE except for the exception embedded message, which assumes a value of TRUE.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ee411-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="ee411-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ee411-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="ee411-120">Protocol specifications</span></span>

<span data-ttu-id="ee411-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ee411-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ee411-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ee411-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ee411-123">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ee411-123">[[MS-OXOCAL] ](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ee411-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="ee411-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ee411-125">头文件</span><span class="sxs-lookup"><span data-stu-id="ee411-125">Header files</span></span>

<span data-ttu-id="ee411-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ee411-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="ee411-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ee411-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ee411-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee411-128">See also</span></span>



[<span data-ttu-id="ee411-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ee411-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ee411-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ee411-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ee411-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ee411-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ee411-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ee411-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

