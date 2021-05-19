---
title: PidTagInternetMessageId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInternetMessageId
api_type:
- HeaderDef
ms.assetid: 5c93d00c-a199-4d45-9bf6-87bd2ffe4784
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c2cc0eabd9c329953d9b0d252418549ea1c588a1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358561"
---
# <a name="pidtaginternetmessageid-canonical-property"></a><span data-ttu-id="e2265-103">PidTagInternetMessageId 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2265-103">PidTagInternetMessageId Canonical Property</span></span>

  
  
<span data-ttu-id="e2265-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e2265-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e2265-105">对应于 [RFC2822] 中指定的邮件 ID 字段。</span><span class="sxs-lookup"><span data-stu-id="e2265-105">Corresponds to the message ID field as specified in [RFC2822].</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e2265-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e2265-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e2265-107">PR_INTERNET_MESSAGE_ID、PR_INTERNET_MESSAGE_ID_A、PR_INTERNET_MESSAGE_ID_W</span><span class="sxs-lookup"><span data-stu-id="e2265-107">PR_INTERNET_MESSAGE_ID, PR_INTERNET_MESSAGE_ID_A, PR_INTERNET_MESSAGE_ID_W</span></span>  <br/> |
|<span data-ttu-id="e2265-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e2265-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e2265-109">0x1035</span><span class="sxs-lookup"><span data-stu-id="e2265-109">0x1035</span></span>  <br/> |
|<span data-ttu-id="e2265-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e2265-110">Data type:</span></span>  <br/> |<span data-ttu-id="e2265-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e2265-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e2265-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e2265-112">Area:</span></span>  <br/> |<span data-ttu-id="e2265-113">MIME</span><span class="sxs-lookup"><span data-stu-id="e2265-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e2265-114">备注</span><span class="sxs-lookup"><span data-stu-id="e2265-114">Remarks</span></span>

<span data-ttu-id="e2265-115">这些属性应存在于所有电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="e2265-115">These properties should be present on all email messages.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e2265-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="e2265-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e2265-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="e2265-117">Protocol specifications</span></span>

<span data-ttu-id="e2265-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2265-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e2265-119">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="e2265-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e2265-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2265-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e2265-121">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e2265-121">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e2265-122">头文件</span><span class="sxs-lookup"><span data-stu-id="e2265-122">Header files</span></span>

<span data-ttu-id="e2265-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e2265-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="e2265-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e2265-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="e2265-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e2265-125">Mapitags.h</span></span>
  
> <span data-ttu-id="e2265-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e2265-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e2265-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2265-127">See also</span></span>



[<span data-ttu-id="e2265-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e2265-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e2265-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2265-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e2265-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e2265-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e2265-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e2265-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

