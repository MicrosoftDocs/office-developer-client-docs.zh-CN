---
title: PidLidAutoFillLocation 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAutoFillLocation
api_type:
- COM
ms.assetid: e4db6cae-4730-45d0-8b8a-9bd484c8bd3f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2d1edf371486c5db0aa8b869726c8a9a7b62ab06
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344994"
---
# <a name="pidlidautofilllocation-canonical-property"></a><span data-ttu-id="bb8b0-103">PidLidAutoFillLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb8b0-103">PidLidAutoFillLocation Canonical Property</span></span>

  
  
<span data-ttu-id="bb8b0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb8b0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb8b0-105">指示 **dispidLocation** ([PidLidLocation](pidlidlocation-canonical-property.md)) 属性的值设置为表示资源的 RecipientRow 中的 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="bb8b0-105">Indicates that the value of the **dispidLocation** ([PidLidLocation](pidlidlocation-canonical-property.md)) property is set to the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property from the RecipientRow that represents a resource.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bb8b0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bb8b0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bb8b0-107">dispidAutoFillLocation</span><span class="sxs-lookup"><span data-stu-id="bb8b0-107">dispidAutoFillLocation</span></span>  <br/> |
|<span data-ttu-id="bb8b0-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="bb8b0-108">Property set:</span></span>  <br/> |<span data-ttu-id="bb8b0-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="bb8b0-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="bb8b0-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="bb8b0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="bb8b0-111">0x0000823A</span><span class="sxs-lookup"><span data-stu-id="bb8b0-111">0x0000823A</span></span>  <br/> |
|<span data-ttu-id="bb8b0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bb8b0-112">Data type:</span></span>  <br/> |<span data-ttu-id="bb8b0-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="bb8b0-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="bb8b0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="bb8b0-114">Area:</span></span>  <br/> |<span data-ttu-id="bb8b0-115">会议</span><span class="sxs-lookup"><span data-stu-id="bb8b0-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bb8b0-116">备注</span><span class="sxs-lookup"><span data-stu-id="bb8b0-116">Remarks</span></span>

<span data-ttu-id="bb8b0-117">有关 RecipientRow 的更多详细信息，请参阅 [[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)中指定的邮件和附件对象协议。</span><span class="sxs-lookup"><span data-stu-id="bb8b0-117">For more details on RecipientRow, see the Message and Attachment Object protocol as specified in [[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="bb8b0-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="bb8b0-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bb8b0-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="bb8b0-119">Protocol specifications</span></span>

<span data-ttu-id="bb8b0-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb8b0-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bb8b0-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="bb8b0-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="bb8b0-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb8b0-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bb8b0-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="bb8b0-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bb8b0-124">头文件</span><span class="sxs-lookup"><span data-stu-id="bb8b0-124">Header files</span></span>

<span data-ttu-id="bb8b0-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bb8b0-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="bb8b0-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bb8b0-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bb8b0-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb8b0-127">See also</span></span>



[<span data-ttu-id="bb8b0-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bb8b0-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bb8b0-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb8b0-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bb8b0-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bb8b0-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bb8b0-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bb8b0-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

