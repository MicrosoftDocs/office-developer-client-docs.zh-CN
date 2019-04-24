---
title: PidTagControlId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagControlId
api_type:
- HeaderDef
ms.assetid: 281bc3e0-7c69-461b-bf09-4281abbb5e1b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b27f59e0bfdcac8eca1751af2f07139f12e2b3a7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334739"
---
# <a name="pidtagcontrolid-canonical-property"></a><span data-ttu-id="6b634-103">PidTagControlId 规范属性</span><span class="sxs-lookup"><span data-stu-id="6b634-103">PidTagControlId Canonical Property</span></span>

  
  
<span data-ttu-id="6b634-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6b634-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6b634-105">包含对话框中使用的控件的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6b634-105">Contains a unique identifier for a control used in a dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6b634-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6b634-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6b634-107">PR_CONTROL_ID</span><span class="sxs-lookup"><span data-stu-id="6b634-107">PR_CONTROL_ID</span></span>  <br/> |
|<span data-ttu-id="6b634-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6b634-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6b634-109">0x3F07</span><span class="sxs-lookup"><span data-stu-id="6b634-109">0x3F07</span></span>  <br/> |
|<span data-ttu-id="6b634-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6b634-110">Data type:</span></span>  <br/> |<span data-ttu-id="6b634-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6b634-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6b634-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6b634-112">Area:</span></span>  <br/> |<span data-ttu-id="6b634-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="6b634-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6b634-114">注解</span><span class="sxs-lookup"><span data-stu-id="6b634-114">Remarks</span></span>

<span data-ttu-id="6b634-115">此属性包含控件的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6b634-115">This property contains a unique identifier for the control.</span></span> <span data-ttu-id="6b634-116">此标识符应包含[GUID](guid.md)结构和**LONG**类型的二进制值。</span><span class="sxs-lookup"><span data-stu-id="6b634-116">This identifier should contain a [GUID](guid.md) structure and a binary value of type **LONG**.</span></span> <span data-ttu-id="6b634-117">对话框中的所有控件都应使用相同的**GUID**来标识服务提供程序, 并且每个控件应使用唯一的**长整型**值, 以确保控件不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="6b634-117">All controls in the dialog box should use the same **GUID** to identify the service provider, and each control should use a unique **LONG** value to ensure that the controls do not collide.</span></span> 
  
<span data-ttu-id="6b634-118">此属性在通知中使用。</span><span class="sxs-lookup"><span data-stu-id="6b634-118">This property is used in notifications.</span></span> <span data-ttu-id="6b634-119">例如, 在显示表上发送的通知必须设置该属性来唯一标识要更新的控件。</span><span class="sxs-lookup"><span data-stu-id="6b634-119">For example, notifications sent on the display table must set this property to uniquely identify the control to update.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6b634-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="6b634-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="6b634-121">头文件</span><span class="sxs-lookup"><span data-stu-id="6b634-121">Header files</span></span>

<span data-ttu-id="6b634-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6b634-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="6b634-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6b634-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="6b634-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="6b634-124">Mapitags.h</span></span>
  
> <span data-ttu-id="6b634-125">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6b634-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6b634-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b634-126">See also</span></span>



[<span data-ttu-id="6b634-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6b634-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6b634-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6b634-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6b634-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6b634-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6b634-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6b634-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

