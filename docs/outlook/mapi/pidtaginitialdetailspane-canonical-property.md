---
title: PidTagInitialDetailsPane 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInitialDetailsPane
api_type:
- HeaderDef
ms.assetid: c4712133-6fbd-4c50-a258-5f4317120476
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3bf0f52dbeda37ac35024ae3bf38df8919e37b60
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346576"
---
# <a name="pidtaginitialdetailspane-canonical-property"></a><span data-ttu-id="cb413-103">PidTagInitialDetailsPane 规范属性</span><span class="sxs-lookup"><span data-stu-id="cb413-103">PidTagInitialDetailsPane Canonical Property</span></span>

  
  
<span data-ttu-id="cb413-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cb413-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cb413-105">指示要首先显示的显示模板的页面。</span><span class="sxs-lookup"><span data-stu-id="cb413-105">Indicates the page of a display template to display first.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cb413-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cb413-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cb413-107">PR_INITIAL_DETAILS_PANE</span><span class="sxs-lookup"><span data-stu-id="cb413-107">PR_INITIAL_DETAILS_PANE</span></span>  <br/> |
|<span data-ttu-id="cb413-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="cb413-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cb413-109">0x3F08</span><span class="sxs-lookup"><span data-stu-id="cb413-109">0x3F08</span></span>  <br/> |
|<span data-ttu-id="cb413-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cb413-110">Data type:</span></span>  <br/> |<span data-ttu-id="cb413-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cb413-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="cb413-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cb413-112">Area:</span></span>  <br/> |<span data-ttu-id="cb413-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="cb413-113">MAPI Display Tables</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cb413-114">注解</span><span class="sxs-lookup"><span data-stu-id="cb413-114">Remarks</span></span>

<span data-ttu-id="cb413-115">它必须存在于名称服务提供程序接口 (NSPI) 服务器上的所有通讯簿对象中, 并且必须具有值零 (0)。</span><span class="sxs-lookup"><span data-stu-id="cb413-115">It must be present on all address book objects on an Name Service Provider Interface (NSPI) server, and must have the value zero (0).</span></span> <span data-ttu-id="cb413-116">不得为脱机通讯簿中的任何对象定义它。</span><span class="sxs-lookup"><span data-stu-id="cb413-116">It must not be defined for any objects in an Offline Address Book.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cb413-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="cb413-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cb413-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="cb413-118">Protocol specifications</span></span>

<span data-ttu-id="cb413-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cb413-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cb413-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cb413-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cb413-121">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cb413-121">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cb413-122">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="cb413-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cb413-123">头文件</span><span class="sxs-lookup"><span data-stu-id="cb413-123">Header files</span></span>

<span data-ttu-id="cb413-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="cb413-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="cb413-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cb413-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="cb413-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="cb413-126">Mapitags.h</span></span>
  
> <span data-ttu-id="cb413-127">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cb413-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cb413-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb413-128">See also</span></span>



[<span data-ttu-id="cb413-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cb413-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cb413-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cb413-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cb413-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cb413-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cb413-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cb413-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

