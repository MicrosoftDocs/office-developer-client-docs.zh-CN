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
ms.openlocfilehash: ab906d83ae4ad46747fd9037728620db1d656d25
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394767"
---
# <a name="pidtagviewdescriptorname-canonical-property"></a><span data-ttu-id="bb2e9-103">PidTagViewDescriptorName 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb2e9-103">PidTagViewDescriptorName Canonical Property</span></span>

  
  
<span data-ttu-id="bb2e9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb2e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb2e9-105">包含视图描述符的名称。</span><span class="sxs-lookup"><span data-stu-id="bb2e9-105">Contains the name of a view descriptor.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bb2e9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bb2e9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bb2e9-107">PR_VD_NAME，PR_VD_NAME_A，PR_VD_NAME_W</span><span class="sxs-lookup"><span data-stu-id="bb2e9-107">PR_VD_NAME, PR_VD_NAME_A, PR_VD_NAME_W</span></span>  <br/> |
|<span data-ttu-id="bb2e9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="bb2e9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bb2e9-109">0x7006</span><span class="sxs-lookup"><span data-stu-id="bb2e9-109">0x7006</span></span>  <br/> |
|<span data-ttu-id="bb2e9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bb2e9-110">Data type:</span></span>  <br/> |<span data-ttu-id="bb2e9-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="bb2e9-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="bb2e9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bb2e9-112">Area:</span></span>  <br/> |<span data-ttu-id="bb2e9-113">类定义消息可传送</span><span class="sxs-lookup"><span data-stu-id="bb2e9-113">Message class-defined transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bb2e9-114">说明</span><span class="sxs-lookup"><span data-stu-id="bb2e9-114">Remarks</span></span>

<span data-ttu-id="bb2e9-115">这些属性必须设置为包含视图定义的文件夹关联的信息 （从故障） 消息的非空字符串。</span><span class="sxs-lookup"><span data-stu-id="bb2e9-115">These properties must be set to a non-empty string for a Folder Associate Information (FAI) message that contains view definitions.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="bb2e9-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="bb2e9-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bb2e9-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="bb2e9-117">Protocol specifications</span></span>

<span data-ttu-id="bb2e9-118">[[MS OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb2e9-118">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bb2e9-119">指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。</span><span class="sxs-lookup"><span data-stu-id="bb2e9-119">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bb2e9-120">头文件</span><span class="sxs-lookup"><span data-stu-id="bb2e9-120">Header files</span></span>

<span data-ttu-id="bb2e9-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bb2e9-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="bb2e9-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bb2e9-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="bb2e9-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="bb2e9-123">Mapitags.h</span></span>
  
> <span data-ttu-id="bb2e9-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bb2e9-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bb2e9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb2e9-125">See also</span></span>



[<span data-ttu-id="bb2e9-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bb2e9-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bb2e9-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb2e9-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bb2e9-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bb2e9-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bb2e9-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bb2e9-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

