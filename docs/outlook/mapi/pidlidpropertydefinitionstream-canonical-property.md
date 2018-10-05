---
title: PidLidPropertyDefinitionStream 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidPropertyDefinitionStream
api_type:
- COM
ms.assetid: ead35049-e60e-4b46-bf12-f73d77cd36b2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b5ddb87111cfb0039cb1150338945615bbd5afc5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393269"
---
# <a name="pidlidpropertydefinitionstream-canonical-property"></a><span data-ttu-id="cc4c1-103">PidLidPropertyDefinitionStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="cc4c1-103">PidLidPropertyDefinitionStream Canonical Property</span></span>

  
  
<span data-ttu-id="cc4c1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc4c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc4c1-105">代表用户定义的字段的定义和消息的内置字段的数据绑定设置。</span><span class="sxs-lookup"><span data-stu-id="cc4c1-105">Represents definitions of user-defined fields and data-binding settings of built-in fields of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cc4c1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cc4c1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cc4c1-107">dispidPropDefStream</span><span class="sxs-lookup"><span data-stu-id="cc4c1-107">dispidPropDefStream</span></span>  <br/> |
|<span data-ttu-id="cc4c1-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="cc4c1-108">Property set:</span></span>  <br/> |<span data-ttu-id="cc4c1-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="cc4c1-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="cc4c1-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="cc4c1-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cc4c1-111">0x00008540</span><span class="sxs-lookup"><span data-stu-id="cc4c1-111">0x00008540</span></span>  <br/> |
|<span data-ttu-id="cc4c1-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cc4c1-112">Data type:</span></span>  <br/> |<span data-ttu-id="cc4c1-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="cc4c1-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="cc4c1-114">区域：</span><span class="sxs-lookup"><span data-stu-id="cc4c1-114">Area:</span></span>  <br/> |<span data-ttu-id="cc4c1-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="cc4c1-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cc4c1-116">说明</span><span class="sxs-lookup"><span data-stu-id="cc4c1-116">Remarks</span></span>

<span data-ttu-id="cc4c1-117">邮件的自定义窗体定义的一部分保存**PidLidPropertyDefinitionStream**属性的值。</span><span class="sxs-lookup"><span data-stu-id="cc4c1-117">The value of the **PidLidPropertyDefinitionStream** property is saved as part of the custom form definition for the message.</span></span> 
  
<span data-ttu-id="cc4c1-118">此属性的值是二进制流。</span><span class="sxs-lookup"><span data-stu-id="cc4c1-118">The value of this property is a binary stream.</span></span> <span data-ttu-id="cc4c1-119">有关此流的结构的信息，请参阅[属性定义流结构](propertydefinition-stream-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="cc4c1-119">For information on the structure of this stream, see [PropertyDefinition Stream Structure](propertydefinition-stream-structure.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="cc4c1-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="cc4c1-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cc4c1-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="cc4c1-121">Protocol specifications</span></span>

<span data-ttu-id="cc4c1-122">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc4c1-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cc4c1-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cc4c1-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cc4c1-124">头文件</span><span class="sxs-lookup"><span data-stu-id="cc4c1-124">Header files</span></span>

<span data-ttu-id="cc4c1-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cc4c1-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="cc4c1-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cc4c1-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cc4c1-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc4c1-127">See also</span></span>



[<span data-ttu-id="cc4c1-128">Outlook 项和字段</span><span class="sxs-lookup"><span data-stu-id="cc4c1-128">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="cc4c1-129">为新的用户定义字段添加定义</span><span class="sxs-lookup"><span data-stu-id="cc4c1-129">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[<span data-ttu-id="cc4c1-130">PropertyDefinition 流示例</span><span class="sxs-lookup"><span data-stu-id="cc4c1-130">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)
  
[<span data-ttu-id="cc4c1-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cc4c1-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cc4c1-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cc4c1-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cc4c1-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cc4c1-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cc4c1-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cc4c1-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

