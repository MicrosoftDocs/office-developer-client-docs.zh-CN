---
title: PidLidFShouldTNEF 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFShouldTNEF
api_type:
- COM
ms.assetid: 3cab23b6-f0e3-4703-a83b-12a617537651
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8f88e4b41ab455c55bfd1cb36b73ce7ef0383b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438965"
---
# <a name="pidlidfshouldtnef-canonical-property"></a><span data-ttu-id="b8f0f-103">PidLidFShouldTNEF 规范属性</span><span class="sxs-lookup"><span data-stu-id="b8f0f-103">PidLidFShouldTNEF Canonical Property</span></span>

  
  
<span data-ttu-id="b8f0f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b8f0f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b8f0f-105">指示是否使用 TNEF 传输中性封装格式 (项) 。</span><span class="sxs-lookup"><span data-stu-id="b8f0f-105">Indicates whether to encode an item with Transport Neutral Encapsulation Format (TNEF).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b8f0f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b8f0f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b8f0f-107">dispidFShouldTNEF</span><span class="sxs-lookup"><span data-stu-id="b8f0f-107">dispidFShouldTNEF</span></span>  <br/> |
|<span data-ttu-id="b8f0f-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="b8f0f-108">Property set:</span></span>  <br/> |<span data-ttu-id="b8f0f-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="b8f0f-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="b8f0f-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="b8f0f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b8f0f-111">0x000085A5</span><span class="sxs-lookup"><span data-stu-id="b8f0f-111">0x000085A5</span></span>  <br/> |
|<span data-ttu-id="b8f0f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b8f0f-112">Data type:</span></span>  <br/> |<span data-ttu-id="b8f0f-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="b8f0f-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="b8f0f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b8f0f-114">Area:</span></span>  <br/> |<span data-ttu-id="b8f0f-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="b8f0f-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b8f0f-116">备注</span><span class="sxs-lookup"><span data-stu-id="b8f0f-116">Remarks</span></span>

<span data-ttu-id="b8f0f-117">此属性在将 Microsoft Word 设置为电子邮件编辑器时设置，并且它将发送嵌入 RTF rtF 格式格式的 OLE 对象 (RTF) 流。</span><span class="sxs-lookup"><span data-stu-id="b8f0f-117">This property is set when Microsoft Word is set as the email editor, and it sends an OLE object that is embedded in a Rich Text Format (RTF) stream.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b8f0f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="b8f0f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b8f0f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="b8f0f-119">Protocol specifications</span></span>

<span data-ttu-id="b8f0f-120">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="b8f0f-120">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="b8f0f-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="b8f0f-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b8f0f-122">头文件</span><span class="sxs-lookup"><span data-stu-id="b8f0f-122">Header files</span></span>

<span data-ttu-id="b8f0f-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b8f0f-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="b8f0f-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b8f0f-124">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b8f0f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8f0f-125">See also</span></span>



[<span data-ttu-id="b8f0f-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b8f0f-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b8f0f-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b8f0f-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b8f0f-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b8f0f-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b8f0f-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b8f0f-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

