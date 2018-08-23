---
title: PidTagRoamingXmlStream 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRoamingXmlStream
api_type:
- COM
ms.assetid: ce55b50e-3dbf-4690-9102-c08f35ada82e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e1d9a8bce2207529d1062f50a86547379c6255e4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569400"
---
# <a name="pidtagroamingxmlstream-canonical-property"></a><span data-ttu-id="d1952-103">PidTagRoamingXmlStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1952-103">PidTagRoamingXmlStream Canonical Property</span></span>

  
  
<span data-ttu-id="d1952-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1952-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1952-105">包含任意 XML 流。</span><span class="sxs-lookup"><span data-stu-id="d1952-105">Contains an arbitrary XML stream.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d1952-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d1952-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d1952-107">PR_ROAMING_XMLSTREAM</span><span class="sxs-lookup"><span data-stu-id="d1952-107">PR_ROAMING_XMLSTREAM</span></span>  <br/> |
|<span data-ttu-id="d1952-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d1952-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d1952-109">0x7C08</span><span class="sxs-lookup"><span data-stu-id="d1952-109">0x7C08</span></span>  <br/> |
|<span data-ttu-id="d1952-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d1952-110">Data type:</span></span>  <br/> |<span data-ttu-id="d1952-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d1952-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d1952-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d1952-112">Area:</span></span>  <br/> |<span data-ttu-id="d1952-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="d1952-113">Configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d1952-114">注解</span><span class="sxs-lookup"><span data-stu-id="d1952-114">Remarks</span></span>

<span data-ttu-id="d1952-115">此属性包含任意 XML 数据的流。</span><span class="sxs-lookup"><span data-stu-id="d1952-115">This property contains an arbitrary stream of XML data.</span></span> <span data-ttu-id="d1952-116">在邮件中的其他属性可能意味着要使用此属性中的特定架构。</span><span class="sxs-lookup"><span data-stu-id="d1952-116">Other properties in the message may imply specific schemas to use in this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d1952-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d1952-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d1952-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="d1952-118">Protocol specifications</span></span>

<span data-ttu-id="d1952-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1952-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1952-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="d1952-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d1952-121">[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1952-121">[[MS-OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1952-122">指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。</span><span class="sxs-lookup"><span data-stu-id="d1952-122">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d1952-123">头文件</span><span class="sxs-lookup"><span data-stu-id="d1952-123">Header files</span></span>

<span data-ttu-id="d1952-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d1952-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="d1952-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d1952-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="d1952-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d1952-126">Mapitags.h</span></span>
  
> <span data-ttu-id="d1952-127">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d1952-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d1952-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1952-128">See also</span></span>



[<span data-ttu-id="d1952-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d1952-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d1952-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1952-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d1952-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d1952-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d1952-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d1952-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

