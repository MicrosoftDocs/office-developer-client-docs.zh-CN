---
title: PidTagNextSendAcct 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNextSendAcct
api_type:
- HeaderDef
ms.assetid: b7429c2e-0d9d-4921-9f56-9ecad817f8cb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eff053fda58266afd5500e322559059f051d5ac3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329391"
---
# <a name="pidtagnextsendacct-canonical-property"></a><span data-ttu-id="29d53-103">PidTagNextSendAcct 规范属性</span><span class="sxs-lookup"><span data-stu-id="29d53-103">PidTagNextSendAcct Canonical Property</span></span>

  
  
<span data-ttu-id="29d53-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29d53-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29d53-105">指定客户端当前尝试用于发送电子邮件的服务器。</span><span class="sxs-lookup"><span data-stu-id="29d53-105">Specifies the server that a client is currently attempting to use to send email.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="29d53-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="29d53-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="29d53-107">PR_NEXT_SEND_ACCT</span><span class="sxs-lookup"><span data-stu-id="29d53-107">PR_NEXT_SEND_ACCT</span></span>  <br/> |
|<span data-ttu-id="29d53-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="29d53-108">Identifier:</span></span>  <br/> |<span data-ttu-id="29d53-109">0x0E29</span><span class="sxs-lookup"><span data-stu-id="29d53-109">0x0E29</span></span>  <br/> |
|<span data-ttu-id="29d53-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="29d53-110">Data type:</span></span>  <br/> |<span data-ttu-id="29d53-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="29d53-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="29d53-112">区域：</span><span class="sxs-lookup"><span data-stu-id="29d53-112">Area:</span></span>  <br/> |<span data-ttu-id="29d53-113">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="29d53-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="29d53-114">注解</span><span class="sxs-lookup"><span data-stu-id="29d53-114">Remarks</span></span>

<span data-ttu-id="29d53-115">此属性的格式是依赖于实现的。</span><span class="sxs-lookup"><span data-stu-id="29d53-115">The format of this property is implementation dependent.</span></span> <span data-ttu-id="29d53-116">客户端可以使用此属性来确定将电子邮件定向到哪台服务器, 但此属性是可选的, 并且值对服务器没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="29d53-116">This property can be used by the client to determine which server to direct the email to, but is optional and the value has no meaning to the server.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="29d53-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="29d53-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="29d53-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="29d53-118">Protocol specifications</span></span>

<span data-ttu-id="29d53-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="29d53-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="29d53-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="29d53-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="29d53-121">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="29d53-121">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="29d53-122">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="29d53-122">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="29d53-123">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="29d53-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="29d53-124">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="29d53-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="29d53-125">头文件</span><span class="sxs-lookup"><span data-stu-id="29d53-125">Header files</span></span>

<span data-ttu-id="29d53-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="29d53-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="29d53-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="29d53-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="29d53-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="29d53-128">Mapitags.h</span></span>
  
> <span data-ttu-id="29d53-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="29d53-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="29d53-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29d53-130">See also</span></span>



[<span data-ttu-id="29d53-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="29d53-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="29d53-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="29d53-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="29d53-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="29d53-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="29d53-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="29d53-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

