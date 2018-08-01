---
title: PidTagRoamingDatatypes 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRoamingDatatypes
api_type:
- COM
ms.assetid: a3336b61-01b6-47a7-9498-0a03878e91cb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d8b4df2dbb0d7fd2edeb82222f333c11c5f71987
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778236"
---
# <a name="pidtagroamingdatatypes-canonical-property"></a><span data-ttu-id="e1c2c-103">PidTagRoamingDatatypes 规范属性</span><span class="sxs-lookup"><span data-stu-id="e1c2c-103">PidTagRoamingDatatypes Canonical Property</span></span>

  
  
<span data-ttu-id="e1c2c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e1c2c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e1c2c-105">包含一个位掩码，指示属性存在邮件的流。</span><span class="sxs-lookup"><span data-stu-id="e1c2c-105">Contains a bitmask that indicates which stream properties exist on the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e1c2c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e1c2c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e1c2c-107">PR_ROAMING_DATATYPES</span><span class="sxs-lookup"><span data-stu-id="e1c2c-107">PR_ROAMING_DATATYPES</span></span>  <br/> |
|<span data-ttu-id="e1c2c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e1c2c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e1c2c-109">0x7C06</span><span class="sxs-lookup"><span data-stu-id="e1c2c-109">0x7C06</span></span>  <br/> |
|<span data-ttu-id="e1c2c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e1c2c-110">Data type:</span></span>  <br/> |<span data-ttu-id="e1c2c-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e1c2c-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e1c2c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e1c2c-112">Area:</span></span>  <br/> |<span data-ttu-id="e1c2c-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="e1c2c-113">Configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e1c2c-114">说明</span><span class="sxs-lookup"><span data-stu-id="e1c2c-114">Remarks</span></span>

<span data-ttu-id="e1c2c-115">此属性必须设置为一个或多个下列值：</span><span class="sxs-lookup"><span data-stu-id="e1c2c-115">This property must be set to one or more of the following values:</span></span>
  
|<span data-ttu-id="e1c2c-116">**值**</span><span class="sxs-lookup"><span data-stu-id="e1c2c-116">**Value**</span></span>|<span data-ttu-id="e1c2c-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1c2c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1c2c-118">0x00000002</span><span class="sxs-lookup"><span data-stu-id="e1c2c-118">0x00000002</span></span>  <br/> |<span data-ttu-id="e1c2c-119">指示文件夹关联的信息 （从故障） 邮件应包含词典流，序列化为固定的 XML 架构，并存储在**PR_ROAMING_DICTIONARY** ([PidTagRoamingDictionary](pidtagroamingdictionary-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e1c2c-119">Indicates that the Folder Associated Information (FAI) message should contain a Dictionary stream, serialized into a fixed XML schema and stored in the **PR_ROAMING_DICTIONARY** ([PidTagRoamingDictionary](pidtagroamingdictionary-canonical-property.md)) property.</span></span> <span data-ttu-id="e1c2c-120">如果从故障消息不包含词典流，应用程序必须视为字典无任何条目。</span><span class="sxs-lookup"><span data-stu-id="e1c2c-120">If the FAI message does not contain a Dictionary stream, the application must treat the Dictionary as having no entries.</span></span>  <br/> |
|<span data-ttu-id="e1c2c-121">0x00000004</span><span class="sxs-lookup"><span data-stu-id="e1c2c-121">0x00000004</span></span>  <br/> |<span data-ttu-id="e1c2c-122">指示从故障消息必须包含存储在**PR_ROAMING_XMLSTREAM** ([PidTagRoamingXmlStream](pidtagroamingxmlstream-canonical-property.md)) 属性使用任意 XML 架构的 XML 流。</span><span class="sxs-lookup"><span data-stu-id="e1c2c-122">Indicates that the FAI message must contain an XML stream stored in the **PR_ROAMING_XMLSTREAM** ([PidTagRoamingXmlStream](pidtagroamingxmlstream-canonical-property.md)) property that uses an arbitrary XML schema.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="e1c2c-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="e1c2c-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e1c2c-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="e1c2c-124">Protocol specifications</span></span>

<span data-ttu-id="e1c2c-125">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1c2c-125">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e1c2c-126">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e1c2c-126">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e1c2c-127">[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1c2c-127">[[MS-OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e1c2c-128">指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。</span><span class="sxs-lookup"><span data-stu-id="e1c2c-128">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e1c2c-129">头文件</span><span class="sxs-lookup"><span data-stu-id="e1c2c-129">Header files</span></span>

<span data-ttu-id="e1c2c-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e1c2c-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="e1c2c-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e1c2c-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="e1c2c-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e1c2c-132">Mapitags.h</span></span>
  
> <span data-ttu-id="e1c2c-133">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e1c2c-133">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e1c2c-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1c2c-134">See also</span></span>



[<span data-ttu-id="e1c2c-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e1c2c-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e1c2c-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e1c2c-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e1c2c-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e1c2c-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e1c2c-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e1c2c-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

