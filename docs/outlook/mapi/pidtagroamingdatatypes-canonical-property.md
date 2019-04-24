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
ms.openlocfilehash: fe5528f7605412d0cfd4b4b914e9b221c715e1b1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359554"
---
# <a name="pidtagroamingdatatypes-canonical-property"></a><span data-ttu-id="cd557-103">PidTagRoamingDatatypes 规范属性</span><span class="sxs-lookup"><span data-stu-id="cd557-103">PidTagRoamingDatatypes Canonical Property</span></span>

  
  
<span data-ttu-id="cd557-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cd557-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cd557-105">包含表示邮件中存在哪些流属性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="cd557-105">Contains a bitmask that indicates which stream properties exist on the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cd557-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cd557-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cd557-107">PR_ROAMING_DATATYPES</span><span class="sxs-lookup"><span data-stu-id="cd557-107">PR_ROAMING_DATATYPES</span></span>  <br/> |
|<span data-ttu-id="cd557-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="cd557-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cd557-109">0x7C06</span><span class="sxs-lookup"><span data-stu-id="cd557-109">0x7C06</span></span>  <br/> |
|<span data-ttu-id="cd557-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cd557-110">Data type:</span></span>  <br/> |<span data-ttu-id="cd557-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cd557-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="cd557-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cd557-112">Area:</span></span>  <br/> |<span data-ttu-id="cd557-113">配置</span><span class="sxs-lookup"><span data-stu-id="cd557-113">Configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cd557-114">注解</span><span class="sxs-lookup"><span data-stu-id="cd557-114">Remarks</span></span>

<span data-ttu-id="cd557-115">此属性必须设置为以下一个或多个值:</span><span class="sxs-lookup"><span data-stu-id="cd557-115">This property must be set to one or more of the following values:</span></span>
  
|<span data-ttu-id="cd557-116">**Value**</span><span class="sxs-lookup"><span data-stu-id="cd557-116">**Value**</span></span>|<span data-ttu-id="cd557-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="cd557-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cd557-118">0x00000002</span><span class="sxs-lookup"><span data-stu-id="cd557-118">0x00000002</span></span>  <br/> |<span data-ttu-id="cd557-119">指示文件夹关联的信息 (FAI) 邮件应包含字典流, 并序列化为固定 XML 架构并存储在**PR_ROAMING_DICTIONARY** ([PidTagRoamingDictionary](pidtagroamingdictionary-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="cd557-119">Indicates that the Folder Associated Information (FAI) message should contain a Dictionary stream, serialized into a fixed XML schema and stored in the **PR_ROAMING_DICTIONARY** ([PidTagRoamingDictionary](pidtagroamingdictionary-canonical-property.md)) property.</span></span> <span data-ttu-id="cd557-120">如果 FAI 消息不包含字典流, 则应用程序必须将字典视为无条目。</span><span class="sxs-lookup"><span data-stu-id="cd557-120">If the FAI message does not contain a Dictionary stream, the application must treat the Dictionary as having no entries.</span></span>  <br/> |
|<span data-ttu-id="cd557-121">0x00000004</span><span class="sxs-lookup"><span data-stu-id="cd557-121">0x00000004</span></span>  <br/> |<span data-ttu-id="cd557-122">指示 FAI 消息必须包含使用任意 XML 架构的**PR_ROAMING_XMLSTREAM** ([PidTagRoamingXmlStream](pidtagroamingxmlstream-canonical-property.md)) 属性中存储的 XML 流。</span><span class="sxs-lookup"><span data-stu-id="cd557-122">Indicates that the FAI message must contain an XML stream stored in the **PR_ROAMING_XMLSTREAM** ([PidTagRoamingXmlStream](pidtagroamingxmlstream-canonical-property.md)) property that uses an arbitrary XML schema.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="cd557-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="cd557-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cd557-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="cd557-124">Protocol specifications</span></span>

<span data-ttu-id="cd557-125">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cd557-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cd557-126">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cd557-126">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cd557-127">[[毫秒-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cd557-127">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cd557-128">指定客户端和服务器配置数据的位置和属性, 如共享类别列表和工作时间。</span><span class="sxs-lookup"><span data-stu-id="cd557-128">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cd557-129">头文件</span><span class="sxs-lookup"><span data-stu-id="cd557-129">Header files</span></span>

<span data-ttu-id="cd557-130">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="cd557-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="cd557-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cd557-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="cd557-132">Mapitags</span><span class="sxs-lookup"><span data-stu-id="cd557-132">Mapitags.h</span></span>
  
> <span data-ttu-id="cd557-133">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cd557-133">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cd557-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd557-134">See also</span></span>



[<span data-ttu-id="cd557-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cd557-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cd557-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cd557-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cd557-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cd557-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cd557-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cd557-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

