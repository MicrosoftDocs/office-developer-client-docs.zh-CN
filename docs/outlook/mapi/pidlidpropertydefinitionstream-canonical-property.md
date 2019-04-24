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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315937"
---
# <a name="pidlidpropertydefinitionstream-canonical-property"></a><span data-ttu-id="47824-103">PidLidPropertyDefinitionStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="47824-103">PidLidPropertyDefinitionStream Canonical Property</span></span>

  
  
<span data-ttu-id="47824-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="47824-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="47824-105">表示邮件的内置字段的用户定义字段和数据绑定设置的定义。</span><span class="sxs-lookup"><span data-stu-id="47824-105">Represents definitions of user-defined fields and data-binding settings of built-in fields of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="47824-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="47824-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="47824-107">dispidPropDefStream</span><span class="sxs-lookup"><span data-stu-id="47824-107">dispidPropDefStream</span></span>  <br/> |
|<span data-ttu-id="47824-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="47824-108">Property set:</span></span>  <br/> |<span data-ttu-id="47824-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="47824-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="47824-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="47824-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="47824-111">0x00008540</span><span class="sxs-lookup"><span data-stu-id="47824-111">0x00008540</span></span>  <br/> |
|<span data-ttu-id="47824-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="47824-112">Data type:</span></span>  <br/> |<span data-ttu-id="47824-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="47824-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="47824-114">区域：</span><span class="sxs-lookup"><span data-stu-id="47824-114">Area:</span></span>  <br/> |<span data-ttu-id="47824-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="47824-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="47824-116">注解</span><span class="sxs-lookup"><span data-stu-id="47824-116">Remarks</span></span>

<span data-ttu-id="47824-117">**PidLidPropertyDefinitionStream**属性的值保存为邮件的自定义表单定义的一部分。</span><span class="sxs-lookup"><span data-stu-id="47824-117">The value of the **PidLidPropertyDefinitionStream** property is saved as part of the custom form definition for the message.</span></span> 
  
<span data-ttu-id="47824-118">此属性的值为二进制流。</span><span class="sxs-lookup"><span data-stu-id="47824-118">The value of this property is a binary stream.</span></span> <span data-ttu-id="47824-119">有关此流的结构的信息, 请参阅[PropertyDefinition stream structure](propertydefinition-stream-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="47824-119">For information on the structure of this stream, see [PropertyDefinition Stream Structure](propertydefinition-stream-structure.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="47824-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="47824-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="47824-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="47824-121">Protocol specifications</span></span>

<span data-ttu-id="47824-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="47824-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="47824-123">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="47824-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="47824-124">头文件</span><span class="sxs-lookup"><span data-stu-id="47824-124">Header files</span></span>

<span data-ttu-id="47824-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="47824-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="47824-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="47824-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="47824-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47824-127">See also</span></span>



[<span data-ttu-id="47824-128">Outlook 项目和字段</span><span class="sxs-lookup"><span data-stu-id="47824-128">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="47824-129">为新的用户定义的字段添加定义</span><span class="sxs-lookup"><span data-stu-id="47824-129">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[<span data-ttu-id="47824-130">PropertyDefinition 流示例</span><span class="sxs-lookup"><span data-stu-id="47824-130">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)
  
[<span data-ttu-id="47824-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="47824-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="47824-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="47824-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="47824-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="47824-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="47824-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="47824-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

