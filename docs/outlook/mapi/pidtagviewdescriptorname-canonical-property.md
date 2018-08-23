---
title: PidTagViewDescriptorName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagViewDescriptorName
api_type:
- COM
ms.assetid: 1e689ee4-9e89-4328-beb9-05c80a6544a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 55d838661dcbe0efb604e6a623a434f9ae87512e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567781"
---
# <a name="pidtagviewdescriptorname-canonical-property"></a><span data-ttu-id="472c4-103">PidTagViewDescriptorName 规范属性</span><span class="sxs-lookup"><span data-stu-id="472c4-103">PidTagViewDescriptorName Canonical Property</span></span>

  
  
<span data-ttu-id="472c4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="472c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="472c4-105">包含视图描述符的名称。</span><span class="sxs-lookup"><span data-stu-id="472c4-105">Contains the name of a view descriptor.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="472c4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="472c4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="472c4-107">PR_VD_NAME，PR_VD_NAME_A，PR_VD_NAME_W</span><span class="sxs-lookup"><span data-stu-id="472c4-107">PR_VD_NAME, PR_VD_NAME_A, PR_VD_NAME_W</span></span>  <br/> |
|<span data-ttu-id="472c4-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="472c4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="472c4-109">0x7006</span><span class="sxs-lookup"><span data-stu-id="472c4-109">0x7006</span></span>  <br/> |
|<span data-ttu-id="472c4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="472c4-110">Data type:</span></span>  <br/> |<span data-ttu-id="472c4-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="472c4-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="472c4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="472c4-112">Area:</span></span>  <br/> |<span data-ttu-id="472c4-113">类定义消息可传送</span><span class="sxs-lookup"><span data-stu-id="472c4-113">Message class-defined transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="472c4-114">注解</span><span class="sxs-lookup"><span data-stu-id="472c4-114">Remarks</span></span>

<span data-ttu-id="472c4-115">这些属性必须设置为包含视图定义的文件夹关联的信息 （从故障） 消息的非空字符串。</span><span class="sxs-lookup"><span data-stu-id="472c4-115">These properties must be set to a non-empty string for a Folder Associate Information (FAI) message that contains view definitions.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="472c4-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="472c4-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="472c4-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="472c4-117">Protocol specifications</span></span>

<span data-ttu-id="472c4-118">[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="472c4-118">[[MS-OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="472c4-119">指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。</span><span class="sxs-lookup"><span data-stu-id="472c4-119">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="472c4-120">头文件</span><span class="sxs-lookup"><span data-stu-id="472c4-120">Header files</span></span>

<span data-ttu-id="472c4-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="472c4-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="472c4-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="472c4-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="472c4-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="472c4-123">Mapitags.h</span></span>
  
> <span data-ttu-id="472c4-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="472c4-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="472c4-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="472c4-125">See also</span></span>



[<span data-ttu-id="472c4-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="472c4-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="472c4-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="472c4-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="472c4-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="472c4-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="472c4-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="472c4-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

