---
title: PidTagRoamingDictionary 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRoamingDictionary
api_type:
- COM
ms.assetid: 40b50181-f88c-40ee-b3d0-a36dd36c158e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 263b7eb0de7fe724625d99c3f08ad12d5740dd52
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581634"
---
# <a name="pidtagroamingdictionary-canonical-property"></a><span data-ttu-id="81a19-103">PidTagRoamingDictionary 规范属性</span><span class="sxs-lookup"><span data-stu-id="81a19-103">PidTagRoamingDictionary Canonical Property</span></span>

<span data-ttu-id="81a19-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81a19-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="81a19-105">包含描述漫游字典 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="81a19-105">Contains an XML document that describes the roaming dictionary.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="81a19-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="81a19-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="81a19-107">PR_ROAMING_DICTIONARY</span><span class="sxs-lookup"><span data-stu-id="81a19-107">PR_ROAMING_DICTIONARY</span></span>  <br/> |
|<span data-ttu-id="81a19-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="81a19-108">Identifier:</span></span>  <br/> |<span data-ttu-id="81a19-109">0x7C07</span><span class="sxs-lookup"><span data-stu-id="81a19-109">0x7C07</span></span>  <br/> |
|<span data-ttu-id="81a19-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="81a19-110">Data type:</span></span>  <br/> |<span data-ttu-id="81a19-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="81a19-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="81a19-112">区域：</span><span class="sxs-lookup"><span data-stu-id="81a19-112">Area:</span></span>  <br/> |<span data-ttu-id="81a19-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="81a19-113">Configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="81a19-114">注解</span><span class="sxs-lookup"><span data-stu-id="81a19-114">Remarks</span></span>

<span data-ttu-id="81a19-115">此属性包含一个使用 UTF8 编码的 UNICODE XML 文档。</span><span class="sxs-lookup"><span data-stu-id="81a19-115">This property contains a UNICODE XML document that is using UTF8 encoding.</span></span> <span data-ttu-id="81a19-116">具有词典流一条消息必须设置此属性与下面的架构：</span><span class="sxs-lookup"><span data-stu-id="81a19-116">A message with a dictionary stream must set this property with the following schema:</span></span>
  
```xml
<?xml version="1.0" encoding="utf-8"?> 
<xs:schema targetNamespace="Dictionary.xsd" xmlns="Dictionary.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema"> 
   <xs:element name="UserConfiguration"> 
   <xs:complexType> 
   <xs:sequence> 
   <xs:element name="Info"> 
   <xs:complexType> 
   <xs:sequence /> 
   <xs:attribute name="version" type="VersionString"> 
   </xs:attribute> 
   </xs:complexType>
```

<span data-ttu-id="81a19-117">以下是存储在配置数据邮件此属性的示例 XML 文档：</span><span class="sxs-lookup"><span data-stu-id="81a19-117">The following is a sample XML document stored in this property on a Configuration Data message:</span></span> 
  
```xml
<?xml version="1.0"?> 
<UserConfiguration> 
<Info version="Outlook.12"/> 
<Data> <e k="18-piAutoProcess" v="3-True"/> 
<e k="18-piRemindDefault" v="9-15"/> 
<e k="18-piReminderUpgradeTime" v="9-212864507"/> 
<e k="18-OLPrefsVersion" v="9-1"/> 
</Data> 
</UserConfiguration>
```

## <a name="related-resources"></a><span data-ttu-id="81a19-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="81a19-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="81a19-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="81a19-119">Protocol specifications</span></span>

<span data-ttu-id="81a19-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="81a19-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="81a19-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="81a19-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="81a19-122">[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="81a19-122">[[MS-OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="81a19-123">指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。</span><span class="sxs-lookup"><span data-stu-id="81a19-123">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="81a19-124">头文件</span><span class="sxs-lookup"><span data-stu-id="81a19-124">Header files</span></span>

<span data-ttu-id="81a19-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="81a19-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="81a19-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="81a19-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="81a19-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="81a19-127">Mapitags.h</span></span>
  
> <span data-ttu-id="81a19-128">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="81a19-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="81a19-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81a19-129">See also</span></span>



[<span data-ttu-id="81a19-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="81a19-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="81a19-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="81a19-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="81a19-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="81a19-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="81a19-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="81a19-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

