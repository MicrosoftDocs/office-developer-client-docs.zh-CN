---
title: PidLidLogEnd 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLogEnd
api_type:
- COM
ms.assetid: 621459ea-adf5-4420-9f0f-6f31b9b95508
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bed1692a4860d59ba7a6c297ab8e88645b023a86
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336923"
---
# <a name="pidlidlogend-canonical-property"></a><span data-ttu-id="fddba-103">PidLidLogEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="fddba-103">PidLidLogEnd Canonical Property</span></span>

  
  
<span data-ttu-id="fddba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fddba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fddba-105">表示日记邮件的结束日期和时间。</span><span class="sxs-lookup"><span data-stu-id="fddba-105">Represents the end date and time for the journal message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fddba-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fddba-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fddba-107">dispidLogEnd</span><span class="sxs-lookup"><span data-stu-id="fddba-107">dispidLogEnd</span></span>  <br/> |
|<span data-ttu-id="fddba-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="fddba-108">Property set:</span></span>  <br/> |<span data-ttu-id="fddba-109">PSETID_Log</span><span class="sxs-lookup"><span data-stu-id="fddba-109">PSETID_Log</span></span>  <br/> |
|<span data-ttu-id="fddba-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="fddba-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="fddba-111">0x00008708</span><span class="sxs-lookup"><span data-stu-id="fddba-111">0x00008708</span></span>  <br/> |
|<span data-ttu-id="fddba-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fddba-112">Data type:</span></span>  <br/> |<span data-ttu-id="fddba-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="fddba-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="fddba-114">区域：</span><span class="sxs-lookup"><span data-stu-id="fddba-114">Area:</span></span>  <br/> |<span data-ttu-id="fddba-115">日志</span><span class="sxs-lookup"><span data-stu-id="fddba-115">Journal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fddba-116">备注</span><span class="sxs-lookup"><span data-stu-id="fddba-116">Remarks</span></span>

<span data-ttu-id="fddba-117">活动以协调世界时结束的时间 协调世界时 (UTC) ，必须等于 **dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) 属性，并且大于或等于 **dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="fddba-117">The time when the activity ended in Coordinated Universal Time The (UTC), which must be equal to the **dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) property and greater than or equal to **dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fddba-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="fddba-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fddba-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="fddba-119">Protocol specifications</span></span>

<span data-ttu-id="fddba-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fddba-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fddba-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="fddba-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fddba-122">[[MS-OXOJRNL]](https://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fddba-122">[[MS-OXOJRNL]](https://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fddba-123">指定允许用于日记的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="fddba-123">Specifies the properties and operations that are permissible for journals.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fddba-124">头文件</span><span class="sxs-lookup"><span data-stu-id="fddba-124">Header files</span></span>

<span data-ttu-id="fddba-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fddba-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="fddba-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fddba-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fddba-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fddba-127">See also</span></span>



[<span data-ttu-id="fddba-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fddba-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fddba-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fddba-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fddba-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fddba-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fddba-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fddba-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

