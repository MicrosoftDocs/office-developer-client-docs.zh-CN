---
title: PidLidFlagRequest 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFlagRequest
api_type:
- COM
ms.assetid: 38981f07-14b8-47c2-93df-e6aed91896e4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ddcf32df716fe2b0a02655278ff0cd8d821de1f4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357804"
---
# <a name="pidlidflagrequest-canonical-property"></a><span data-ttu-id="5a31c-103">PidLidFlagRequest 规范属性</span><span class="sxs-lookup"><span data-stu-id="5a31c-103">PidLidFlagRequest Canonical Property</span></span>

  
  
<span data-ttu-id="5a31c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5a31c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5a31c-105">表示会议请求的状态。</span><span class="sxs-lookup"><span data-stu-id="5a31c-105">Represents the status of a meeting request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5a31c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5a31c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5a31c-107">dispidRequest</span><span class="sxs-lookup"><span data-stu-id="5a31c-107">dispidRequest</span></span>  <br/> |
|<span data-ttu-id="5a31c-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="5a31c-108">Property set:</span></span>  <br/> |<span data-ttu-id="5a31c-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="5a31c-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="5a31c-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="5a31c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="5a31c-111">0x00008530</span><span class="sxs-lookup"><span data-stu-id="5a31c-111">0x00008530</span></span>  <br/> |
|<span data-ttu-id="5a31c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5a31c-112">Data type:</span></span>  <br/> |<span data-ttu-id="5a31c-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5a31c-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="5a31c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="5a31c-114">Area:</span></span>  <br/> |<span data-ttu-id="5a31c-115">标记</span><span class="sxs-lookup"><span data-stu-id="5a31c-115">Flagging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5a31c-116">备注</span><span class="sxs-lookup"><span data-stu-id="5a31c-116">Remarks</span></span>

<span data-ttu-id="5a31c-117">在Microsoft Office Outlook中，会议请求是约会项目。</span><span class="sxs-lookup"><span data-stu-id="5a31c-117">In Microsoft Office Outlook, a meeting request is an appointment item.</span></span>
  
<span data-ttu-id="5a31c-118">此属性包含要与标志关联的用户可指定文本，如果邮件对象已标记或已完成，但与会议相关的对象不应存在，则应该设置该属性。</span><span class="sxs-lookup"><span data-stu-id="5a31c-118">This property contains user-specifiable text to be associated with the flag and should be set if the message object is flagged or completed, but should not exist for a meeting-related object.</span></span> <span data-ttu-id="5a31c-119">客户端可以选择不支持此属性，并始终编写"跟进" (翻译为用户语言（如果适用) ）作为应设置此属性的字符串值。</span><span class="sxs-lookup"><span data-stu-id="5a31c-119">Clients may choose not to support this property, and always write "Follow up" (translated to the user's language if appropriate) as the value of the string when this property should be set.</span></span> <span data-ttu-id="5a31c-120">应基于 **dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) 和 **dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md)) 属性的值有条件地忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="5a31c-120">This property should be conditionally ignored based on the values of the **dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) and **dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md)) properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5a31c-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="5a31c-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5a31c-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="5a31c-122">Protocol specifications</span></span>

<span data-ttu-id="5a31c-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5a31c-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5a31c-124">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="5a31c-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5a31c-125">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5a31c-125">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5a31c-126">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5a31c-126">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5a31c-127">头文件</span><span class="sxs-lookup"><span data-stu-id="5a31c-127">Header files</span></span>

<span data-ttu-id="5a31c-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5a31c-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="5a31c-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5a31c-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5a31c-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a31c-130">See also</span></span>



[<span data-ttu-id="5a31c-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5a31c-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5a31c-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5a31c-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5a31c-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5a31c-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5a31c-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5a31c-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

