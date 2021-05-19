---
title: PidLidLogFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLogFlags
api_type:
- COM
ms.assetid: 3174d931-e045-44db-a203-a27c9c00f4fc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a407c065a51870ba9908fbd9b626d7f287a1df4e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336944"
---
# <a name="pidlidlogflags-canonical-property"></a><span data-ttu-id="20a2b-103">PidLidLogFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="20a2b-103">PidLidLogFlags Canonical Property</span></span>

  
  
<span data-ttu-id="20a2b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20a2b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20a2b-105">包含有关日记的元数据。</span><span class="sxs-lookup"><span data-stu-id="20a2b-105">Contains metadata about the journal.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="20a2b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="20a2b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="20a2b-107">dispidLogFlags</span><span class="sxs-lookup"><span data-stu-id="20a2b-107">dispidLogFlags</span></span>  <br/> |
|<span data-ttu-id="20a2b-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="20a2b-108">Property set:</span></span>  <br/> |<span data-ttu-id="20a2b-109">PSETID_Log</span><span class="sxs-lookup"><span data-stu-id="20a2b-109">PSETID_Log</span></span>  <br/> |
|<span data-ttu-id="20a2b-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="20a2b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="20a2b-111">0x0000870C</span><span class="sxs-lookup"><span data-stu-id="20a2b-111">0x0000870C</span></span>  <br/> |
|<span data-ttu-id="20a2b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="20a2b-112">Data type:</span></span>  <br/> |<span data-ttu-id="20a2b-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="20a2b-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="20a2b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="20a2b-114">Area:</span></span>  <br/> |<span data-ttu-id="20a2b-115">日志</span><span class="sxs-lookup"><span data-stu-id="20a2b-115">Journal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="20a2b-116">备注</span><span class="sxs-lookup"><span data-stu-id="20a2b-116">Remarks</span></span>

<span data-ttu-id="20a2b-117">包含有关日记的元数据的位字段必须为零或"0x40000000"。</span><span class="sxs-lookup"><span data-stu-id="20a2b-117">The bit field that contains metadata about the journal must be either zero or "0x40000000".</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="20a2b-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="20a2b-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="20a2b-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="20a2b-119">Protocol specifications</span></span>

<span data-ttu-id="20a2b-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="20a2b-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="20a2b-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="20a2b-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="20a2b-122">[[MS-OXOJRNL]](https://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="20a2b-122">[[MS-OXOJRNL]](https://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="20a2b-123">指定允许用于日记的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="20a2b-123">Specifies the properties and operations that are permissible for journals.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="20a2b-124">头文件</span><span class="sxs-lookup"><span data-stu-id="20a2b-124">Header files</span></span>

<span data-ttu-id="20a2b-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="20a2b-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="20a2b-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="20a2b-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="20a2b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20a2b-127">See also</span></span>



[<span data-ttu-id="20a2b-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="20a2b-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="20a2b-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="20a2b-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="20a2b-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="20a2b-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="20a2b-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="20a2b-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

