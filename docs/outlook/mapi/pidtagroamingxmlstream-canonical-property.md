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
ms.openlocfilehash: 3e7ce1f810a1dd37cd4370ceb423b664d75878a2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359540"
---
# <a name="pidtagroamingxmlstream-canonical-property"></a><span data-ttu-id="71a09-103">PidTagRoamingXmlStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="71a09-103">PidTagRoamingXmlStream Canonical Property</span></span>

  
  
<span data-ttu-id="71a09-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="71a09-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="71a09-105">包含任意 XML 流。</span><span class="sxs-lookup"><span data-stu-id="71a09-105">Contains an arbitrary XML stream.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="71a09-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="71a09-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="71a09-107">PR_ROAMING_XMLSTREAM</span><span class="sxs-lookup"><span data-stu-id="71a09-107">PR_ROAMING_XMLSTREAM</span></span>  <br/> |
|<span data-ttu-id="71a09-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="71a09-108">Identifier:</span></span>  <br/> |<span data-ttu-id="71a09-109">0x7C08</span><span class="sxs-lookup"><span data-stu-id="71a09-109">0x7C08</span></span>  <br/> |
|<span data-ttu-id="71a09-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="71a09-110">Data type:</span></span>  <br/> |<span data-ttu-id="71a09-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="71a09-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="71a09-112">区域：</span><span class="sxs-lookup"><span data-stu-id="71a09-112">Area:</span></span>  <br/> |<span data-ttu-id="71a09-113">配置</span><span class="sxs-lookup"><span data-stu-id="71a09-113">Configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="71a09-114">注解</span><span class="sxs-lookup"><span data-stu-id="71a09-114">Remarks</span></span>

<span data-ttu-id="71a09-115">此属性包含 XML 数据的任意流。</span><span class="sxs-lookup"><span data-stu-id="71a09-115">This property contains an arbitrary stream of XML data.</span></span> <span data-ttu-id="71a09-116">邮件中的其他属性可能暗示了要在此属性中使用的特定架构。</span><span class="sxs-lookup"><span data-stu-id="71a09-116">Other properties in the message may imply specific schemas to use in this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="71a09-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="71a09-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="71a09-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="71a09-118">Protocol specifications</span></span>

<span data-ttu-id="71a09-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="71a09-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="71a09-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="71a09-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="71a09-121">[[毫秒-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="71a09-121">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="71a09-122">指定客户端和服务器配置数据的位置和属性, 如共享类别列表和工作时间。</span><span class="sxs-lookup"><span data-stu-id="71a09-122">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="71a09-123">头文件</span><span class="sxs-lookup"><span data-stu-id="71a09-123">Header files</span></span>

<span data-ttu-id="71a09-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="71a09-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="71a09-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="71a09-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="71a09-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="71a09-126">Mapitags.h</span></span>
  
> <span data-ttu-id="71a09-127">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="71a09-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="71a09-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71a09-128">See also</span></span>



[<span data-ttu-id="71a09-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="71a09-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="71a09-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="71a09-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="71a09-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="71a09-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="71a09-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="71a09-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

