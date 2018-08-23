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
ms.openlocfilehash: 2868533e0383309e013bb82aaa4300a0a40e335a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577511"
---
# <a name="pidtagcontrolid-canonical-property"></a><span data-ttu-id="6018f-103">PidTagControlId 规范属性</span><span class="sxs-lookup"><span data-stu-id="6018f-103">PidTagControlId Canonical Property</span></span>

  
  
<span data-ttu-id="6018f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6018f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6018f-105">包含在对话框中使用的控件的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6018f-105">Contains a unique identifier for a control used in a dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6018f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6018f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6018f-107">PR_CONTROL_ID</span><span class="sxs-lookup"><span data-stu-id="6018f-107">PR_CONTROL_ID</span></span>  <br/> |
|<span data-ttu-id="6018f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="6018f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6018f-109">0x3F07</span><span class="sxs-lookup"><span data-stu-id="6018f-109">0x3F07</span></span>  <br/> |
|<span data-ttu-id="6018f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6018f-110">Data type:</span></span>  <br/> |<span data-ttu-id="6018f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6018f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6018f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6018f-112">Area:</span></span>  <br/> |<span data-ttu-id="6018f-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="6018f-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6018f-114">注解</span><span class="sxs-lookup"><span data-stu-id="6018f-114">Remarks</span></span>

<span data-ttu-id="6018f-115">此属性包含控件的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6018f-115">This property contains a unique identifier for the control.</span></span> <span data-ttu-id="6018f-116">此标识符应包含一个[GUID](guid.md)结构和**LONG**类型的二进制值。</span><span class="sxs-lookup"><span data-stu-id="6018f-116">This identifier should contain a [GUID](guid.md) structure and a binary value of type **LONG**.</span></span> <span data-ttu-id="6018f-117">在对话框中的所有控件应都使用相同的**GUID**标识服务提供商，并每个控件应都使用唯一**LONG**值，以确保控件不互相冲突。</span><span class="sxs-lookup"><span data-stu-id="6018f-117">All controls in the dialog box should use the same **GUID** to identify the service provider, and each control should use a unique **LONG** value to ensure that the controls do not collide.</span></span> 
  
<span data-ttu-id="6018f-118">在通知中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="6018f-118">This property is used in notifications.</span></span> <span data-ttu-id="6018f-119">例如，显示表上发送的通知必须设置此属性来唯一地标识要更新的控件。</span><span class="sxs-lookup"><span data-stu-id="6018f-119">For example, notifications sent on the display table must set this property to uniquely identify the control to update.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6018f-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="6018f-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="6018f-121">头文件</span><span class="sxs-lookup"><span data-stu-id="6018f-121">Header files</span></span>

<span data-ttu-id="6018f-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6018f-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="6018f-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6018f-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="6018f-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6018f-124">Mapitags.h</span></span>
  
> <span data-ttu-id="6018f-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6018f-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6018f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6018f-126">See also</span></span>



[<span data-ttu-id="6018f-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6018f-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6018f-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6018f-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6018f-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6018f-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6018f-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6018f-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

