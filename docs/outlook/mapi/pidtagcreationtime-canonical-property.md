---
title: PidTagCreationTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagCreationTime
api_type:
- HeaderDef
ms.assetid: 13122af2-06c8-4342-983d-e38178743d8f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: de853c66f0ef4270f4c443881bfa163d4abfa3e0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357895"
---
# <a name="pidtagcreationtime-canonical-property"></a><span data-ttu-id="83678-103">PidTagCreationTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="83678-103">PidTagCreationTime Canonical Property</span></span>

  
  
<span data-ttu-id="83678-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="83678-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="83678-105">包含邮件的创建日期和时间。</span><span class="sxs-lookup"><span data-stu-id="83678-105">Contains the creation date and time of a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="83678-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="83678-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="83678-107">PR_CREATION_TIME</span><span class="sxs-lookup"><span data-stu-id="83678-107">PR_CREATION_TIME</span></span>  <br/> |
|<span data-ttu-id="83678-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="83678-108">Identifier:</span></span>  <br/> |<span data-ttu-id="83678-109">0x3007</span><span class="sxs-lookup"><span data-stu-id="83678-109">0x3007</span></span>  <br/> |
|<span data-ttu-id="83678-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="83678-110">Data type:</span></span>  <br/> |<span data-ttu-id="83678-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="83678-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="83678-112">区域：</span><span class="sxs-lookup"><span data-stu-id="83678-112">Area:</span></span>  <br/> |<span data-ttu-id="83678-113">邮件时间</span><span class="sxs-lookup"><span data-stu-id="83678-113">Message time</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="83678-114">备注</span><span class="sxs-lookup"><span data-stu-id="83678-114">Remarks</span></span>

<span data-ttu-id="83678-115">邮件存储会为它创建的每封邮件设置此属性。</span><span class="sxs-lookup"><span data-stu-id="83678-115">A message store sets this property for each message that it creates.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="83678-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="83678-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="83678-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="83678-117">Protocol specifications</span></span>

<span data-ttu-id="83678-118">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="83678-118">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="83678-119">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="83678-119">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="83678-120">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="83678-120">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="83678-121">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="83678-121">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="83678-122">头文件</span><span class="sxs-lookup"><span data-stu-id="83678-122">Header files</span></span>

<span data-ttu-id="83678-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="83678-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="83678-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="83678-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="83678-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="83678-125">Mapitags.h</span></span>
  
> <span data-ttu-id="83678-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="83678-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="83678-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83678-127">See also</span></span>



[<span data-ttu-id="83678-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="83678-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="83678-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="83678-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="83678-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="83678-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="83678-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="83678-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

