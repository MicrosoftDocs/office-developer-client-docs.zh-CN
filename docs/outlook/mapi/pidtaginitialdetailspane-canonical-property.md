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
ms.openlocfilehash: 884bbad509e459d4f329e6468dd99124cec6c7d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777713"
---
# <a name="pidtaginitialdetailspane-canonical-property"></a><span data-ttu-id="ecb6d-103">PidTagInitialDetailsPane 规范属性</span><span class="sxs-lookup"><span data-stu-id="ecb6d-103">PidTagInitialDetailsPane Canonical Property</span></span>

  
  
<span data-ttu-id="ecb6d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ecb6d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ecb6d-105">指示显示模板以显示第一页。</span><span class="sxs-lookup"><span data-stu-id="ecb6d-105">Indicates the page of a display template to display first.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ecb6d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ecb6d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ecb6d-107">PR_INITIAL_DETAILS_PANE</span><span class="sxs-lookup"><span data-stu-id="ecb6d-107">PR_INITIAL_DETAILS_PANE</span></span>  <br/> |
|<span data-ttu-id="ecb6d-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ecb6d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ecb6d-109">0x3F08</span><span class="sxs-lookup"><span data-stu-id="ecb6d-109">0x3F08</span></span>  <br/> |
|<span data-ttu-id="ecb6d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ecb6d-110">Data type:</span></span>  <br/> |<span data-ttu-id="ecb6d-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ecb6d-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ecb6d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ecb6d-112">Area:</span></span>  <br/> |<span data-ttu-id="ecb6d-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="ecb6d-113">MAPI Display Tables</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ecb6d-114">说明</span><span class="sxs-lookup"><span data-stu-id="ecb6d-114">Remarks</span></span>

<span data-ttu-id="ecb6d-115">它必须存在所有通讯簿对象的名称服务提供程序界面 (NSPI) 服务器上，并且必须具有的值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="ecb6d-115">It must be present on all address book objects on an Name Service Provider Interface (NSPI) server, and must have the value zero (0).</span></span> <span data-ttu-id="ecb6d-116">它必须未定义脱机通讯簿中的任何对象。</span><span class="sxs-lookup"><span data-stu-id="ecb6d-116">It must not be defined for any objects in an Offline Address Book.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ecb6d-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="ecb6d-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ecb6d-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="ecb6d-118">Protocol specifications</span></span>

<span data-ttu-id="ecb6d-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ecb6d-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ecb6d-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ecb6d-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ecb6d-121">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ecb6d-121">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ecb6d-122">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="ecb6d-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ecb6d-123">头文件</span><span class="sxs-lookup"><span data-stu-id="ecb6d-123">Header files</span></span>

<span data-ttu-id="ecb6d-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ecb6d-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="ecb6d-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ecb6d-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="ecb6d-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ecb6d-126">Mapitags.h</span></span>
  
> <span data-ttu-id="ecb6d-127">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ecb6d-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ecb6d-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecb6d-128">See also</span></span>



[<span data-ttu-id="ecb6d-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ecb6d-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ecb6d-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ecb6d-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ecb6d-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ecb6d-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ecb6d-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ecb6d-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

