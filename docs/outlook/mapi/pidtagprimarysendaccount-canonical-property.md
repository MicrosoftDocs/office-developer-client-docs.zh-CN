---
title: PidTagPrimarySendAccount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPrimarySendAccount
api_type:
- COM
ms.assetid: 2f268b3b-2e4c-4aea-8879-bdd0ac1df35c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2c32cc61fea63cd38215c30e04e8a467d4901cc9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339373"
---
# <a name="pidtagprimarysendaccount-canonical-property"></a><span data-ttu-id="8ec93-103">PidTagPrimarySendAccount 规范属性</span><span class="sxs-lookup"><span data-stu-id="8ec93-103">PidTagPrimarySendAccount Canonical Property</span></span>

  
  
<span data-ttu-id="8ec93-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8ec93-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8ec93-105">包含命名用于发送邮件的第一台服务器的字符串。</span><span class="sxs-lookup"><span data-stu-id="8ec93-105">Contains a string that names the first server that is used to send the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8ec93-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8ec93-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8ec93-107">PR_PRIMARY_SEND_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="8ec93-107">PR_PRIMARY_SEND_ACCOUNT</span></span>  <br/> |
|<span data-ttu-id="8ec93-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8ec93-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8ec93-109">0x0E28</span><span class="sxs-lookup"><span data-stu-id="8ec93-109">0x0E28</span></span>  <br/> |
|<span data-ttu-id="8ec93-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8ec93-110">Data type:</span></span>  <br/> |<span data-ttu-id="8ec93-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8ec93-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="8ec93-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8ec93-112">Area:</span></span>  <br/> |<span data-ttu-id="8ec93-113">帐户</span><span class="sxs-lookup"><span data-stu-id="8ec93-113">Account</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8ec93-114">注解</span><span class="sxs-lookup"><span data-stu-id="8ec93-114">Remarks</span></span>

<span data-ttu-id="8ec93-115">指定客户端用于发送邮件的第一台服务器。</span><span class="sxs-lookup"><span data-stu-id="8ec93-115">Specifies the first server that a client should use to send the mail.</span></span> <span data-ttu-id="8ec93-116">这些属性的格式是依赖于实现的。</span><span class="sxs-lookup"><span data-stu-id="8ec93-116">The format of these properties is implementation dependent.</span></span> <span data-ttu-id="8ec93-117">客户端可以使用这些属性来确定要将邮件定向到哪个服务器, 但这是可选的, 并且值对服务器没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="8ec93-117">These properties can be used by the client to determine which server to direct the mail through, but is optional and the value has no meaning to the server.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8ec93-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="8ec93-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8ec93-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="8ec93-119">Protocol specifications</span></span>

<span data-ttu-id="8ec93-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8ec93-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8ec93-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="8ec93-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8ec93-122">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8ec93-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8ec93-123">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8ec93-123">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8ec93-124">头文件</span><span class="sxs-lookup"><span data-stu-id="8ec93-124">Header files</span></span>

<span data-ttu-id="8ec93-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8ec93-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="8ec93-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8ec93-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="8ec93-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8ec93-127">Mapitags.h</span></span>
  
> <span data-ttu-id="8ec93-128">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8ec93-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8ec93-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ec93-129">See also</span></span>



[<span data-ttu-id="8ec93-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8ec93-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8ec93-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8ec93-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8ec93-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8ec93-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8ec93-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8ec93-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

