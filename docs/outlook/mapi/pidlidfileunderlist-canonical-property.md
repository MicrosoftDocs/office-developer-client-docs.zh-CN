---
title: PidLidFileUnderList 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFileUnderList
api_type:
- COM
ms.assetid: a84d8143-5fe7-4a33-bce4-aebf7a824d5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 309c20be5c17746ec10495400d069f1f9b857556
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391435"
---
# <a name="pidlidfileunderlist-canonical-property"></a><span data-ttu-id="ac78e-103">PidLidFileUnderList 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac78e-103">PidLidFileUnderList Canonical Property</span></span>

  
  
<span data-ttu-id="ac78e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ac78e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ac78e-105">指定**dispidFileUnderId** ([PidLidFileUnderId](pidlidfileunderid-canonical-property.md)) 属性的可能值的列表。</span><span class="sxs-lookup"><span data-stu-id="ac78e-105">Specifies a list of possible values for the **dispidFileUnderId** ([PidLidFileUnderId](pidlidfileunderid-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ac78e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ac78e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ac78e-107">dispidFileUnderList</span><span class="sxs-lookup"><span data-stu-id="ac78e-107">dispidFileUnderList</span></span>  <br/> |
|<span data-ttu-id="ac78e-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ac78e-108">Property set:</span></span>  <br/> |<span data-ttu-id="ac78e-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="ac78e-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="ac78e-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ac78e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ac78e-111">0x00008026</span><span class="sxs-lookup"><span data-stu-id="ac78e-111">0x00008026</span></span>  <br/> |
|<span data-ttu-id="ac78e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ac78e-112">Data type:</span></span>  <br/> |<span data-ttu-id="ac78e-113">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="ac78e-113">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="ac78e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ac78e-114">Area:</span></span>  <br/> |<span data-ttu-id="ac78e-115">联系人</span><span class="sxs-lookup"><span data-stu-id="ac78e-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ac78e-116">说明</span><span class="sxs-lookup"><span data-stu-id="ac78e-116">Remarks</span></span>

<span data-ttu-id="ac78e-117">每个中的多值属性的值必须是**dispidFileUnderId** [[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中指定的允许值之一。</span><span class="sxs-lookup"><span data-stu-id="ac78e-117">Each value in the multi-value property must be one of the allowed values for **dispidFileUnderId** specified in [[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ac78e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="ac78e-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ac78e-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="ac78e-119">Protocol specifications</span></span>

<span data-ttu-id="ac78e-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac78e-120">[[MS-OXPROPS] ](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ac78e-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ac78e-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ac78e-122">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac78e-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ac78e-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="ac78e-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ac78e-124">头文件</span><span class="sxs-lookup"><span data-stu-id="ac78e-124">Header files</span></span>

<span data-ttu-id="ac78e-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ac78e-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="ac78e-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ac78e-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ac78e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac78e-127">See also</span></span>



[<span data-ttu-id="ac78e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ac78e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ac78e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac78e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ac78e-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ac78e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ac78e-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ac78e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
