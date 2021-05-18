---
title: PidTagViewDescriptorVersion 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagViewDescriptorVersion
api_type:
- COM
ms.assetid: aaf48f2b-8c57-473c-8be4-f93619255eb8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eefed3fc54285b238e9a8acde1d63f6f591c08d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360730"
---
# <a name="pidtagviewdescriptorversion-canonical-property"></a><span data-ttu-id="0e630-103">PidTagViewDescriptorVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="0e630-103">PidTagViewDescriptorVersion Canonical Property</span></span>

  
  
<span data-ttu-id="0e630-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0e630-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0e630-105">指示视图描述符的版本。</span><span class="sxs-lookup"><span data-stu-id="0e630-105">Indicates the version of a view descriptor.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0e630-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0e630-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0e630-107">PR_VD_VERSION</span><span class="sxs-lookup"><span data-stu-id="0e630-107">PR_VD_VERSION</span></span>  <br/> |
|<span data-ttu-id="0e630-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0e630-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0e630-109">0x7007</span><span class="sxs-lookup"><span data-stu-id="0e630-109">0x7007</span></span>  <br/> |
|<span data-ttu-id="0e630-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0e630-110">Data type:</span></span>  <br/> |<span data-ttu-id="0e630-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0e630-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0e630-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0e630-112">Area:</span></span>  <br/> |<span data-ttu-id="0e630-113">其他</span><span class="sxs-lookup"><span data-stu-id="0e630-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0e630-114">备注</span><span class="sxs-lookup"><span data-stu-id="0e630-114">Remarks</span></span>

<span data-ttu-id="0e630-115">此属性的值必须为 8。</span><span class="sxs-lookup"><span data-stu-id="0e630-115">This property's value must be 8.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0e630-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="0e630-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0e630-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="0e630-117">Protocol specifications</span></span>

<span data-ttu-id="0e630-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0e630-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0e630-119">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="0e630-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0e630-120">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0e630-120">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0e630-121">指定客户端和服务器配置数据的位置和属性，例如共享类别列表和工作时间。</span><span class="sxs-lookup"><span data-stu-id="0e630-121">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0e630-122">头文件</span><span class="sxs-lookup"><span data-stu-id="0e630-122">Header files</span></span>

<span data-ttu-id="0e630-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0e630-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="0e630-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0e630-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="0e630-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0e630-125">Mapitags.h</span></span>
  
> <span data-ttu-id="0e630-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0e630-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0e630-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e630-127">See also</span></span>



[<span data-ttu-id="0e630-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0e630-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0e630-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0e630-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0e630-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0e630-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0e630-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0e630-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

