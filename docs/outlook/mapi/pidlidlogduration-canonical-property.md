---
title: PidLidLogDuration 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLogDocumentSaved
api_type:
- COM
ms.assetid: 012a3f6e-fd16-4dc9-845d-2bf4cebeaa42
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f25c1a72882f9236d56532b7259f51512734945
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336916"
---
# <a name="pidlidlogduration-canonical-property"></a><span data-ttu-id="0cd8f-103">PidLidLogDuration 规范属性</span><span class="sxs-lookup"><span data-stu-id="0cd8f-103">PidLidLogDuration Canonical Property</span></span>

  
  
<span data-ttu-id="0cd8f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0cd8f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0cd8f-105">表示日记邮件的持续时间（分钟）。</span><span class="sxs-lookup"><span data-stu-id="0cd8f-105">Represents the duration, in minutes, of a journal message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0cd8f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0cd8f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0cd8f-107">dispidLogDuration</span><span class="sxs-lookup"><span data-stu-id="0cd8f-107">dispidLogDuration</span></span>  <br/> |
|<span data-ttu-id="0cd8f-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="0cd8f-108">Property set:</span></span>  <br/> |<span data-ttu-id="0cd8f-109">PSETID_Log</span><span class="sxs-lookup"><span data-stu-id="0cd8f-109">PSETID_Log</span></span>  <br/> |
|<span data-ttu-id="0cd8f-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="0cd8f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="0cd8f-111">0x00008707</span><span class="sxs-lookup"><span data-stu-id="0cd8f-111">0x00008707</span></span>  <br/> |
|<span data-ttu-id="0cd8f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0cd8f-112">Data type:</span></span>  <br/> |<span data-ttu-id="0cd8f-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0cd8f-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0cd8f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="0cd8f-114">Area:</span></span>  <br/> |<span data-ttu-id="0cd8f-115">日志</span><span class="sxs-lookup"><span data-stu-id="0cd8f-115">Journal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0cd8f-116">备注</span><span class="sxs-lookup"><span data-stu-id="0cd8f-116">Remarks</span></span>

<span data-ttu-id="0cd8f-117">活动持续时间（以分钟表示）必须是 **dispidLogEnd** ([PidLidLogEnd](pidlidlogend-canonical-property.md)) 和 **dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) 属性之间的差。</span><span class="sxs-lookup"><span data-stu-id="0cd8f-117">The duration, in minutes, of the activity that must be the difference between the **dispidLogEnd** ([PidLidLogEnd](pidlidlogend-canonical-property.md)) and **dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0cd8f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="0cd8f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0cd8f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="0cd8f-119">Protocol specifications</span></span>

<span data-ttu-id="0cd8f-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0cd8f-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0cd8f-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="0cd8f-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0cd8f-122">[[MS-OXOJRNL]](https://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0cd8f-122">[[MS-OXOJRNL]](https://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0cd8f-123">指定允许用于日记的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="0cd8f-123">Specifies the properties and operations that are permissible for journals.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0cd8f-124">头文件</span><span class="sxs-lookup"><span data-stu-id="0cd8f-124">Header files</span></span>

<span data-ttu-id="0cd8f-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0cd8f-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="0cd8f-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0cd8f-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0cd8f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cd8f-127">See also</span></span>



[<span data-ttu-id="0cd8f-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0cd8f-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0cd8f-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0cd8f-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0cd8f-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0cd8f-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0cd8f-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0cd8f-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

