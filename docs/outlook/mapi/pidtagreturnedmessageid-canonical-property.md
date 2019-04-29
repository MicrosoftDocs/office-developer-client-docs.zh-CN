---
title: PidTagReturnedMessageid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 1f0f13e2-7554-41fc-a7a9-a90c34181c96
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e56d7851b1fe28ddea1703d9ec3ffb7737abeda6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435626"
---
# <a name="pidtagreturnedmessageid-canonical-property"></a><span data-ttu-id="88ef9-103">PidTagReturnedMessageid 规范属性</span><span class="sxs-lookup"><span data-stu-id="88ef9-103">PidTagReturnedMessageid Canonical Property</span></span>

  
  
<span data-ttu-id="88ef9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88ef9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="88ef9-105">如果原始邮件是使用未读报告返回的, 则为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="88ef9-105">Contains TRUE if the original message is being returned with a nonread report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="88ef9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="88ef9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="88ef9-107">PR_RETURNED_IPM</span><span class="sxs-lookup"><span data-stu-id="88ef9-107">PR_RETURNED_IPM</span></span>  <br/> |
|<span data-ttu-id="88ef9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="88ef9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="88ef9-109">0x0033</span><span class="sxs-lookup"><span data-stu-id="88ef9-109">0x0033</span></span>  <br/> |
|<span data-ttu-id="88ef9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="88ef9-110">Data type:</span></span>  <br/> |<span data-ttu-id="88ef9-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="88ef9-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="88ef9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="88ef9-112">Area:</span></span>  <br/> |<span data-ttu-id="88ef9-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="88ef9-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="88ef9-114">说明</span><span class="sxs-lookup"><span data-stu-id="88ef9-114">Remarks</span></span>

<span data-ttu-id="88ef9-115">X. 400 传输提供程序在未读报告中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="88ef9-115">An X.400 transport provider sets this property in the unread report.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="88ef9-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="88ef9-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="88ef9-117">头文件</span><span class="sxs-lookup"><span data-stu-id="88ef9-117">Header files</span></span>

<span data-ttu-id="88ef9-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="88ef9-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="88ef9-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="88ef9-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="88ef9-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="88ef9-120">Mapitags.h</span></span>
  
> <span data-ttu-id="88ef9-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="88ef9-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="88ef9-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88ef9-122">See also</span></span>



[<span data-ttu-id="88ef9-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="88ef9-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="88ef9-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="88ef9-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="88ef9-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="88ef9-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="88ef9-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="88ef9-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

