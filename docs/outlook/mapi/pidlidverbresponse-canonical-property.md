---
title: PidLidVerbResponse 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidVerbResponse
api_type:
- COM
ms.assetid: 6f3db5ac-f1cb-4c55-ab88-c126dd5f48ee
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 474df017954618e6411494454c1405445563b862
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386990"
---
# <a name="pidlidverbresponse-canonical-property"></a><span data-ttu-id="b0ef3-103">PidLidVerbResponse 规范属性</span><span class="sxs-lookup"><span data-stu-id="b0ef3-103">PidLidVerbResponse Canonical Property</span></span>

  
  
<span data-ttu-id="b0ef3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b0ef3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b0ef3-105">指定回应者选择的投票选项。</span><span class="sxs-lookup"><span data-stu-id="b0ef3-105">Specifies the voting option that a respondent selected.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b0ef3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b0ef3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b0ef3-107">dispidVerbResponse</span><span class="sxs-lookup"><span data-stu-id="b0ef3-107">dispidVerbResponse</span></span>  <br/> |
|<span data-ttu-id="b0ef3-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b0ef3-108">Property set:</span></span>  <br/> |<span data-ttu-id="b0ef3-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="b0ef3-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="b0ef3-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b0ef3-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b0ef3-111">0x00008524</span><span class="sxs-lookup"><span data-stu-id="b0ef3-111">0x00008524</span></span>  <br/> |
|<span data-ttu-id="b0ef3-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b0ef3-112">Data type:</span></span>  <br/> |<span data-ttu-id="b0ef3-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b0ef3-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b0ef3-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b0ef3-114">Area:</span></span>  <br/> |<span data-ttu-id="b0ef3-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="b0ef3-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b0ef3-116">说明</span><span class="sxs-lookup"><span data-stu-id="b0ef3-116">Remarks</span></span>

<span data-ttu-id="b0ef3-117">此属性通常设置为在其回应投票**dispidVerbStream** ([PidLidVerbStream](pidlidverbstream-canonical-property.md)) 属性中包含的分隔值之一。</span><span class="sxs-lookup"><span data-stu-id="b0ef3-117">This property is usually set to one of the delimited values that are contained in the **dispidVerbStream** ([PidLidVerbStream](pidlidverbstream-canonical-property.md)) property on which the respondent votes.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b0ef3-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="b0ef3-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b0ef3-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="b0ef3-119">Protocol specifications</span></span>

<span data-ttu-id="b0ef3-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b0ef3-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b0ef3-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b0ef3-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b0ef3-122">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b0ef3-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b0ef3-123">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="b0ef3-123">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b0ef3-124">头文件</span><span class="sxs-lookup"><span data-stu-id="b0ef3-124">Header files</span></span>

<span data-ttu-id="b0ef3-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b0ef3-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="b0ef3-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b0ef3-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b0ef3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0ef3-127">See also</span></span>



[<span data-ttu-id="b0ef3-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b0ef3-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b0ef3-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b0ef3-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b0ef3-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b0ef3-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b0ef3-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b0ef3-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

