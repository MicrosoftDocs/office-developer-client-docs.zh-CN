---
title: PidTagExceptionStartTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExceptionStartTime
api_type:
- HeaderDef
ms.assetid: 3aa4f9d7-8105-435d-af68-424a079e1a84
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2ed498295de6748dfa50f1f4a8ba2710c8be64f7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316378"
---
# <a name="pidtagexceptionstarttime-canonical-property"></a><span data-ttu-id="27e83-103">PidTagExceptionStartTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="27e83-103">PidTagExceptionStartTime Canonical Property</span></span>

  
  
<span data-ttu-id="27e83-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27e83-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27e83-105">指示创建异常时计算机本地时区的异常的开始日期和时间。</span><span class="sxs-lookup"><span data-stu-id="27e83-105">Indicates the start date and time of the exception in the local time zone of the machine when the exception is created.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="27e83-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="27e83-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="27e83-107">PR_EXCEPTION_STARTTIME</span><span class="sxs-lookup"><span data-stu-id="27e83-107">PR_EXCEPTION_STARTTIME</span></span>  <br/> |
|<span data-ttu-id="27e83-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="27e83-108">Identifier:</span></span>  <br/> |<span data-ttu-id="27e83-109">0x7FFB</span><span class="sxs-lookup"><span data-stu-id="27e83-109">0x7FFB</span></span>  <br/> |
|<span data-ttu-id="27e83-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="27e83-110">Data type:</span></span>  <br/> |<span data-ttu-id="27e83-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="27e83-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="27e83-112">区域：</span><span class="sxs-lookup"><span data-stu-id="27e83-112">Area:</span></span>  <br/> |<span data-ttu-id="27e83-113">邮件类定义的不可传输</span><span class="sxs-lookup"><span data-stu-id="27e83-113">Message class-defined non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="27e83-114">备注</span><span class="sxs-lookup"><span data-stu-id="27e83-114">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="27e83-115">此属性是信息性的，不得依赖它获取关键信息。</span><span class="sxs-lookup"><span data-stu-id="27e83-115">This property is informational and must not be relied on for critical information.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="27e83-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="27e83-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="27e83-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="27e83-117">Protocol specifications</span></span>

<span data-ttu-id="27e83-118">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="27e83-118">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="27e83-119">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="27e83-119">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="27e83-120">头文件</span><span class="sxs-lookup"><span data-stu-id="27e83-120">Header files</span></span>

<span data-ttu-id="27e83-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="27e83-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="27e83-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="27e83-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="27e83-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="27e83-123">Mapitags.h</span></span>
  
> <span data-ttu-id="27e83-124">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="27e83-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="27e83-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27e83-125">See also</span></span>



[<span data-ttu-id="27e83-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="27e83-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="27e83-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="27e83-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="27e83-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="27e83-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="27e83-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="27e83-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

