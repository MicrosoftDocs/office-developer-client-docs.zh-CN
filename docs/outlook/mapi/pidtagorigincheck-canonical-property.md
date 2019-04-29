---
title: PidTagOriginCheck 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginCheck
api_type:
- COM
ms.assetid: 27e0ab2f-b373-41ae-b922-2f45f9671ac6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a82b1351c9d2d19c32e34b03a537a12bf93deb8a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435759"
---
# <a name="pidtagorigincheck-canonical-property"></a><span data-ttu-id="fff8e-103">PidTagOriginCheck 规范属性</span><span class="sxs-lookup"><span data-stu-id="fff8e-103">PidTagOriginCheck Canonical Property</span></span>

  
  
<span data-ttu-id="fff8e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fff8e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fff8e-105">包含一个二进制验证值, 它使送达报告收件人能够验证原始邮件的来源。</span><span class="sxs-lookup"><span data-stu-id="fff8e-105">Contains a binary verification value that enables a delivery report recipient to verify the origin of the original message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fff8e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fff8e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fff8e-107">PR_ORIGIN_CHECK</span><span class="sxs-lookup"><span data-stu-id="fff8e-107">PR_ORIGIN_CHECK</span></span>  <br/> |
|<span data-ttu-id="fff8e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fff8e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fff8e-109">0x0027</span><span class="sxs-lookup"><span data-stu-id="fff8e-109">0x0027</span></span>  <br/> |
|<span data-ttu-id="fff8e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fff8e-110">Data type:</span></span>  <br/> |<span data-ttu-id="fff8e-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="fff8e-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="fff8e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fff8e-112">Area:</span></span>  <br/> |<span data-ttu-id="fff8e-113">服务器</span><span class="sxs-lookup"><span data-stu-id="fff8e-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fff8e-114">说明</span><span class="sxs-lookup"><span data-stu-id="fff8e-114">Remarks</span></span>

<span data-ttu-id="fff8e-115">此属性为第三方提供一种方法, 如邮件传输代理 (MTA) 或邮件用户接收传递报告, 以验证提交的邮件的来源。</span><span class="sxs-lookup"><span data-stu-id="fff8e-115">This property provides a means for a third party, such as a message transfer agent (MTA) or a messaging user receiving a delivery report, to verify the submitted message's origin.</span></span> <span data-ttu-id="fff8e-116">如果收到的邮件中有此属性, 应将此属性复制到为响应邮件而生成的任何送达报告中。</span><span class="sxs-lookup"><span data-stu-id="fff8e-116">If present on a received message, this property should be copied onto any delivery report generated in response to the message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fff8e-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="fff8e-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="fff8e-118">头文件</span><span class="sxs-lookup"><span data-stu-id="fff8e-118">Header files</span></span>

<span data-ttu-id="fff8e-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="fff8e-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="fff8e-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fff8e-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="fff8e-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="fff8e-121">Mapitags.h</span></span>
  
> <span data-ttu-id="fff8e-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fff8e-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fff8e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fff8e-123">See also</span></span>



[<span data-ttu-id="fff8e-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fff8e-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fff8e-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fff8e-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fff8e-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fff8e-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fff8e-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fff8e-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

