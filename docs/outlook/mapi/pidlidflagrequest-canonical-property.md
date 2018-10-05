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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397364"
---
# <a name="pidlidflagrequest-canonical-property"></a><span data-ttu-id="af021-103">PidLidFlagRequest 规范属性</span><span class="sxs-lookup"><span data-stu-id="af021-103">PidLidFlagRequest Canonical Property</span></span>

  
  
<span data-ttu-id="af021-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="af021-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="af021-105">表示会议请求的状态。</span><span class="sxs-lookup"><span data-stu-id="af021-105">Represents the status of a meeting request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="af021-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="af021-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="af021-107">dispidRequest</span><span class="sxs-lookup"><span data-stu-id="af021-107">dispidRequest</span></span>  <br/> |
|<span data-ttu-id="af021-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="af021-108">Property set:</span></span>  <br/> |<span data-ttu-id="af021-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="af021-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="af021-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="af021-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="af021-111">0x00008530</span><span class="sxs-lookup"><span data-stu-id="af021-111">0x00008530</span></span>  <br/> |
|<span data-ttu-id="af021-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="af021-112">Data type:</span></span>  <br/> |<span data-ttu-id="af021-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="af021-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="af021-114">区域：</span><span class="sxs-lookup"><span data-stu-id="af021-114">Area:</span></span>  <br/> |<span data-ttu-id="af021-115">标记</span><span class="sxs-lookup"><span data-stu-id="af021-115">Flagging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="af021-116">说明</span><span class="sxs-lookup"><span data-stu-id="af021-116">Remarks</span></span>

<span data-ttu-id="af021-117">在 Microsoft Office Outlook 会议请求是约会项目。</span><span class="sxs-lookup"><span data-stu-id="af021-117">In Microsoft Office Outlook, a meeting request is an appointment item.</span></span>
  
<span data-ttu-id="af021-118">此属性包含用户并以此来与标志相关联的文本和应为设置消息对象是标记或完成，但不是应存在会议相关对象。</span><span class="sxs-lookup"><span data-stu-id="af021-118">This property contains user-specifiable text to be associated with the flag and should be set if the message object is flagged or completed, but should not exist for a meeting-related object.</span></span> <span data-ttu-id="af021-119">客户端可以选择不支持此属性，并始终编写"后续标志"（如果适用的用户的语言翻译） 作为字符串时应设置此属性的值。</span><span class="sxs-lookup"><span data-stu-id="af021-119">Clients may choose not to support this property, and always write "Follow up" (translated to the user's language if appropriate) as the value of the string when this property should be set.</span></span> <span data-ttu-id="af021-120">应基于**dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) 和**dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md)) 属性的值有条件地忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="af021-120">This property should be conditionally ignored based on the values of the **dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) and **dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md)) properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="af021-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="af021-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="af021-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="af021-122">Protocol specifications</span></span>

<span data-ttu-id="af021-123">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="af021-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="af021-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="af021-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="af021-125">[[MS OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="af021-125">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="af021-126">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="af021-126">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="af021-127">头文件</span><span class="sxs-lookup"><span data-stu-id="af021-127">Header files</span></span>

<span data-ttu-id="af021-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="af021-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="af021-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="af021-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="af021-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af021-130">See also</span></span>



[<span data-ttu-id="af021-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="af021-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="af021-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="af021-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="af021-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="af021-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="af021-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="af021-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

