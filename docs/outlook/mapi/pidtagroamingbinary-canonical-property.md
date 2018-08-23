---
title: PidTagRoamingBinary 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f06bf063-fc95-46f9-b5fa-3f127a59ebda
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 717c456024dd98495550f1377edc6a53f82ee042
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572408"
---
# <a name="pidtagroamingbinary-canonical-property"></a><span data-ttu-id="aafde-103">PidTagRoamingBinary 规范属性</span><span class="sxs-lookup"><span data-stu-id="aafde-103">PidTagRoamingBinary Canonical Property</span></span>

  
  
<span data-ttu-id="aafde-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aafde-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aafde-105">包含与**IPM 的一个子类关联邮件流。配置**类。</span><span class="sxs-lookup"><span data-stu-id="aafde-105">Contains a message stream associated with a subclass of the **IPM.Configuration** class.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aafde-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="aafde-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="aafde-107">PR_ROAMING_BINARYSTREAM</span><span class="sxs-lookup"><span data-stu-id="aafde-107">PR_ROAMING_BINARYSTREAM</span></span>  <br/> |
|<span data-ttu-id="aafde-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="aafde-108">Identifier:</span></span>  <br/> |<span data-ttu-id="aafde-109">0x7C09</span><span class="sxs-lookup"><span data-stu-id="aafde-109">0x7C09</span></span>  <br/> |
|<span data-ttu-id="aafde-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="aafde-110">Data type:</span></span>  <br/> |<span data-ttu-id="aafde-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="aafde-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="aafde-112">区域：</span><span class="sxs-lookup"><span data-stu-id="aafde-112">Area:</span></span>  <br/> |<span data-ttu-id="aafde-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="aafde-113">Configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="aafde-114">注解</span><span class="sxs-lookup"><span data-stu-id="aafde-114">Remarks</span></span>

<span data-ttu-id="aafde-115">此属性包含与**IPM 关联的数据流。配置**消息类消息。</span><span class="sxs-lookup"><span data-stu-id="aafde-115">This property contains the data stream associated with an **IPM.Configuration** message class message.</span></span> <span data-ttu-id="aafde-116">Stream 的格式取决于邮件类。</span><span class="sxs-lookup"><span data-stu-id="aafde-116">The format of the stream depends on the message class.</span></span> <span data-ttu-id="aafde-117">例如，类类型**IPM 的消息。Configuration.Autocomplete**作为[记忆式键入流](autocomplete-stream.md)进行格式设置。</span><span class="sxs-lookup"><span data-stu-id="aafde-117">For instance, a message of class type **IPM.Configuration.Autocomplete** would be formatted as an [Autocomplete Stream](autocomplete-stream.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="aafde-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="aafde-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="aafde-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="aafde-119">Protocol specifications</span></span>

<span data-ttu-id="aafde-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aafde-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="aafde-121">提供了相关的 Microsoft Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="aafde-121">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="aafde-122">[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aafde-122">[[MS-OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="aafde-123">指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。</span><span class="sxs-lookup"><span data-stu-id="aafde-123">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="aafde-124">头文件</span><span class="sxs-lookup"><span data-stu-id="aafde-124">Header files</span></span>

<span data-ttu-id="aafde-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="aafde-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="aafde-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="aafde-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="aafde-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="aafde-127">Mapitags.h</span></span>
  
> <span data-ttu-id="aafde-128">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="aafde-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="aafde-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aafde-129">See also</span></span>



[<span data-ttu-id="aafde-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="aafde-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="aafde-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="aafde-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="aafde-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="aafde-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="aafde-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="aafde-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

