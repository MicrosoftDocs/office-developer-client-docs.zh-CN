---
title: PidLidDistributionListName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidDistributionListName
api_type:
- COM
ms.assetid: 06fe4d20-c3f5-4f4f-b7b7-5a4f5257079b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d3a1229f4d29bae36b90eb1daf0b6426f358b598
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341963"
---
# <a name="pidliddistributionlistname-canonical-property"></a><span data-ttu-id="0d569-103">PidLidDistributionListName 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d569-103">PidLidDistributionListName Canonical Property</span></span>

  
  
<span data-ttu-id="0d569-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d569-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d569-105">指定个人通讯组列表的名称。</span><span class="sxs-lookup"><span data-stu-id="0d569-105">Specifies the name of the personal distribution list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0d569-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0d569-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0d569-107">dispidDLName</span><span class="sxs-lookup"><span data-stu-id="0d569-107">dispidDLName</span></span>  <br/> |
|<span data-ttu-id="0d569-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="0d569-108">Property set:</span></span>  <br/> |<span data-ttu-id="0d569-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="0d569-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="0d569-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="0d569-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="0d569-111">0x00008053</span><span class="sxs-lookup"><span data-stu-id="0d569-111">0x00008053</span></span>  <br/> |
|<span data-ttu-id="0d569-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0d569-112">Data type:</span></span>  <br/> |<span data-ttu-id="0d569-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0d569-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0d569-114">区域：</span><span class="sxs-lookup"><span data-stu-id="0d569-114">Area:</span></span>  <br/> |<span data-ttu-id="0d569-115">Contact</span><span class="sxs-lookup"><span data-stu-id="0d569-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0d569-116">注解</span><span class="sxs-lookup"><span data-stu-id="0d569-116">Remarks</span></span>

<span data-ttu-id="0d569-117">此属性的值应与**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="0d569-117">The value of this property should be the same as the value of the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0d569-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="0d569-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0d569-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="0d569-119">Protocol specifications</span></span>

<span data-ttu-id="0d569-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0d569-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0d569-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="0d569-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0d569-122">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0d569-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0d569-123">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="0d569-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0d569-124">头文件</span><span class="sxs-lookup"><span data-stu-id="0d569-124">Header files</span></span>

<span data-ttu-id="0d569-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0d569-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="0d569-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0d569-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0d569-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d569-127">See also</span></span>



[<span data-ttu-id="0d569-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0d569-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0d569-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d569-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0d569-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0d569-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0d569-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0d569-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

