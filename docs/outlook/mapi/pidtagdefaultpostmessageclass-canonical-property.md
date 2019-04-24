---
title: PidTagDefaultPostMessageClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefaultPostMessageClass
api_type:
- HeaderDef
ms.assetid: 231c288f-547b-4463-9442-1499661b925e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0ab904625d3a23462a4fedf3b64f49c54b34ad28
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357902"
---
# <a name="pidtagdefaultpostmessageclass-canonical-property"></a><span data-ttu-id="5d6dc-103">PidTagDefaultPostMessageClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d6dc-103">PidTagDefaultPostMessageClass Canonical Property</span></span>

  
  
<span data-ttu-id="5d6dc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d6dc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d6dc-105">包含自定义窗体邮件类的名称。</span><span class="sxs-lookup"><span data-stu-id="5d6dc-105">Contains the name of a custom form Message class.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5d6dc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5d6dc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5d6dc-107">PR_DEF_POST_MSGCLASS</span><span class="sxs-lookup"><span data-stu-id="5d6dc-107">PR_DEF_POST_MSGCLASS</span></span>  <br/> |
|<span data-ttu-id="5d6dc-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5d6dc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5d6dc-109">0x36E5</span><span class="sxs-lookup"><span data-stu-id="5d6dc-109">0x36E5</span></span>  <br/> |
|<span data-ttu-id="5d6dc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5d6dc-110">Data type:</span></span>  <br/> |<span data-ttu-id="5d6dc-111">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="5d6dc-111">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="5d6dc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5d6dc-112">Area:</span></span>  <br/> |<span data-ttu-id="5d6dc-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="5d6dc-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5d6dc-114">注解</span><span class="sxs-lookup"><span data-stu-id="5d6dc-114">Remarks</span></span>

<span data-ttu-id="5d6dc-115">如果在文件夹上设置了此属性, 则该值必须包含完全的基本邮件类 (例如, "IPM。"联系人" 文件夹或 "IPM" 的联系人。"日历" 文件夹的 "约会"), 或以基本邮件类 (例如, "IPM。MyContact ")。</span><span class="sxs-lookup"><span data-stu-id="5d6dc-115">If this property is set on a folder, the value must contain either exactly the base message class (for example, "IPM.Contact" for a contacts folder or "IPM.Appointment" for a calendar folder), or begin with the base message class (for example, "IPM.Contact.MyContact").</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5d6dc-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="5d6dc-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5d6dc-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="5d6dc-117">Protocol specifications</span></span>

<span data-ttu-id="5d6dc-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d6dc-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5d6dc-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="5d6dc-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5d6dc-120">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d6dc-120">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5d6dc-121">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5d6dc-121">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5d6dc-122">头文件</span><span class="sxs-lookup"><span data-stu-id="5d6dc-122">Header files</span></span>

<span data-ttu-id="5d6dc-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="5d6dc-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="5d6dc-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5d6dc-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="5d6dc-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="5d6dc-125">Mapitags.h</span></span>
  
> <span data-ttu-id="5d6dc-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5d6dc-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5d6dc-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d6dc-127">See also</span></span>



[<span data-ttu-id="5d6dc-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5d6dc-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5d6dc-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d6dc-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5d6dc-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5d6dc-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5d6dc-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5d6dc-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

