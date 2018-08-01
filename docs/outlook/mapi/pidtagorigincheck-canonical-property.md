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
ms.openlocfilehash: bbf09cb841c633b6f13ae12ec20e120ea3fd7ef7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777991"
---
# <a name="pidtagorigincheck-canonical-property"></a><span data-ttu-id="03547-103">PidTagOriginCheck 规范属性</span><span class="sxs-lookup"><span data-stu-id="03547-103">PidTagOriginCheck Canonical Property</span></span>

  
  
<span data-ttu-id="03547-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="03547-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="03547-105">包含一个二进制验证值，它使验证原点的原始邮件送达报告收件人。</span><span class="sxs-lookup"><span data-stu-id="03547-105">Contains a binary verification value that enables a delivery report recipient to verify the origin of the original message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="03547-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="03547-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="03547-107">PR_ORIGIN_CHECK</span><span class="sxs-lookup"><span data-stu-id="03547-107">PR_ORIGIN_CHECK</span></span>  <br/> |
|<span data-ttu-id="03547-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="03547-108">Identifier:</span></span>  <br/> |<span data-ttu-id="03547-109">0x0027 表示</span><span class="sxs-lookup"><span data-stu-id="03547-109">0x0027</span></span>  <br/> |
|<span data-ttu-id="03547-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="03547-110">Data type:</span></span>  <br/> |<span data-ttu-id="03547-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="03547-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="03547-112">区域：</span><span class="sxs-lookup"><span data-stu-id="03547-112">Area:</span></span>  <br/> |<span data-ttu-id="03547-113">Server</span><span class="sxs-lookup"><span data-stu-id="03547-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="03547-114">说明</span><span class="sxs-lookup"><span data-stu-id="03547-114">Remarks</span></span>

<span data-ttu-id="03547-115">此属性为第三方，例如邮件传输代理 (MTA) 或消息用户接收的送达报告中，验证已提交的邮件来源提供一种方法。</span><span class="sxs-lookup"><span data-stu-id="03547-115">This property provides a means for a third party, such as a message transfer agent (MTA) or a messaging user receiving a delivery report, to verify the submitted message's origin.</span></span> <span data-ttu-id="03547-116">如果存在接收的消息，此属性应复制到任何响应邮件生成的送达报告。</span><span class="sxs-lookup"><span data-stu-id="03547-116">If present on a received message, this property should be copied onto any delivery report generated in response to the message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="03547-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="03547-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="03547-118">头文件</span><span class="sxs-lookup"><span data-stu-id="03547-118">Header files</span></span>

<span data-ttu-id="03547-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="03547-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="03547-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="03547-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="03547-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="03547-121">Mapitags.h</span></span>
  
> <span data-ttu-id="03547-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="03547-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="03547-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03547-123">See also</span></span>



[<span data-ttu-id="03547-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="03547-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="03547-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="03547-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="03547-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="03547-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="03547-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="03547-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

