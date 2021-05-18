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
ms.openlocfilehash: ead7c9c33c92240ba5e458b68635b766caaa9760
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359561"
---
# <a name="pidtagroamingbinary-canonical-property"></a><span data-ttu-id="3dd1c-103">PidTagRoamingBinary 规范属性</span><span class="sxs-lookup"><span data-stu-id="3dd1c-103">PidTagRoamingBinary Canonical Property</span></span>

  
  
<span data-ttu-id="3dd1c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3dd1c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3dd1c-105">包含与 **uration** 类的子类IPM.Config流。</span><span class="sxs-lookup"><span data-stu-id="3dd1c-105">Contains a message stream associated with a subclass of the **IPM.Configuration** class.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3dd1c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3dd1c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3dd1c-107">PR_ROAMING_BINARYSTREAM</span><span class="sxs-lookup"><span data-stu-id="3dd1c-107">PR_ROAMING_BINARYSTREAM</span></span>  <br/> |
|<span data-ttu-id="3dd1c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3dd1c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3dd1c-109">0x7C09</span><span class="sxs-lookup"><span data-stu-id="3dd1c-109">0x7C09</span></span>  <br/> |
|<span data-ttu-id="3dd1c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3dd1c-110">Data type:</span></span>  <br/> |<span data-ttu-id="3dd1c-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="3dd1c-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="3dd1c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3dd1c-112">Area:</span></span>  <br/> |<span data-ttu-id="3dd1c-113">配置</span><span class="sxs-lookup"><span data-stu-id="3dd1c-113">Configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3dd1c-114">备注</span><span class="sxs-lookup"><span data-stu-id="3dd1c-114">Remarks</span></span>

<span data-ttu-id="3dd1c-115">此属性包含与邮件类消息 **IPM.Config关联的数据流** 。</span><span class="sxs-lookup"><span data-stu-id="3dd1c-115">This property contains the data stream associated with an **IPM.Configuration** message class message.</span></span> <span data-ttu-id="3dd1c-116">流的格式取决于邮件类。</span><span class="sxs-lookup"><span data-stu-id="3dd1c-116">The format of the stream depends on the message class.</span></span> <span data-ttu-id="3dd1c-117">例如，类类型为 **urationIPM.Config消息。自动完成将被** 格式化为自动 [完成流](autocomplete-stream.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd1c-117">For instance, a message of class type **IPM.Configuration.Autocomplete** would be formatted as an [Autocomplete Stream](autocomplete-stream.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3dd1c-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="3dd1c-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3dd1c-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="3dd1c-119">Protocol specifications</span></span>

<span data-ttu-id="3dd1c-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3dd1c-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3dd1c-121">提供对相关协议Microsoft Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="3dd1c-121">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3dd1c-122">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3dd1c-122">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3dd1c-123">指定客户端和服务器配置数据的位置和属性，例如共享类别列表和工作时间。</span><span class="sxs-lookup"><span data-stu-id="3dd1c-123">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3dd1c-124">头文件</span><span class="sxs-lookup"><span data-stu-id="3dd1c-124">Header files</span></span>

<span data-ttu-id="3dd1c-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3dd1c-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="3dd1c-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3dd1c-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="3dd1c-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3dd1c-127">Mapitags.h</span></span>
  
> <span data-ttu-id="3dd1c-128">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3dd1c-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3dd1c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dd1c-129">See also</span></span>



[<span data-ttu-id="3dd1c-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3dd1c-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3dd1c-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3dd1c-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3dd1c-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3dd1c-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3dd1c-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3dd1c-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

