---
title: PidTagFormMessageBehavior 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFormMessageBehavior
api_type:
- HeaderDef
ms.assetid: 8fd82432-9fd9-49ed-aa52-72109db04dc9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8bfb7e5af2e2e5e1a51225dc1cf20baf897752c1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432882"
---
# <a name="pidtagformmessagebehavior-canonical-property"></a><span data-ttu-id="a3943-103">PidTagFormMessageBehavior 规范属性</span><span class="sxs-lookup"><span data-stu-id="a3943-103">PidTagFormMessageBehavior Canonical Property</span></span>

  
  
<span data-ttu-id="a3943-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a3943-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a3943-105">如果邮件应在当前文件夹中撰写，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="a3943-105">Contains TRUE if a message should be composed in the current folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a3943-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a3943-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a3943-107">PR_FORM_MESSAGE_BEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="a3943-107">PR_FORM_MESSAGE_BEHAVIOR</span></span>  <br/> |
|<span data-ttu-id="a3943-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a3943-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a3943-109">0x330A</span><span class="sxs-lookup"><span data-stu-id="a3943-109">0x330A</span></span>  <br/> |
|<span data-ttu-id="a3943-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a3943-110">Data type:</span></span>  <br/> |<span data-ttu-id="a3943-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="a3943-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="a3943-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a3943-112">Area:</span></span>  <br/> |<span data-ttu-id="a3943-113">MAPI common</span><span class="sxs-lookup"><span data-stu-id="a3943-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a3943-114">备注</span><span class="sxs-lookup"><span data-stu-id="a3943-114">Remarks</span></span>

<span data-ttu-id="a3943-115">FALSE 值指示邮件应撰写为任何其他社会性邮件，即发件箱文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a3943-115">A value of FALSE indicates that the message should be composed as any other interpersonal message, that is, in the Outbox folder.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a3943-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="a3943-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="a3943-117">头文件</span><span class="sxs-lookup"><span data-stu-id="a3943-117">Header files</span></span>

<span data-ttu-id="a3943-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a3943-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="a3943-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a3943-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="a3943-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a3943-120">Mapitags.h</span></span>
  
> <span data-ttu-id="a3943-121">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a3943-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a3943-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3943-122">See also</span></span>



[<span data-ttu-id="a3943-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a3943-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a3943-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a3943-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a3943-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a3943-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a3943-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a3943-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

