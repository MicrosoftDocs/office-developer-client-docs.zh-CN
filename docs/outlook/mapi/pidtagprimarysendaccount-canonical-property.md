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
ms.openlocfilehash: 222ca10e58b50fa06876718658d1a6f3843da2f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778050"
---
# <a name="pidtagprimarysendaccount-canonical-property"></a><span data-ttu-id="2a1fc-103">PidTagPrimarySendAccount 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a1fc-103">PidTagPrimarySendAccount Canonical Property</span></span>

  
  
<span data-ttu-id="2a1fc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2a1fc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2a1fc-105">包含一个字符串，用于将邮件发送第一台服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="2a1fc-105">Contains a string that names the first server that is used to send the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2a1fc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2a1fc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2a1fc-107">PR_PRIMARY_SEND_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="2a1fc-107">PR_PRIMARY_SEND_ACCOUNT</span></span>  <br/> |
|<span data-ttu-id="2a1fc-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="2a1fc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2a1fc-109">0x0E28</span><span class="sxs-lookup"><span data-stu-id="2a1fc-109">0x0E28</span></span>  <br/> |
|<span data-ttu-id="2a1fc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2a1fc-110">Data type:</span></span>  <br/> |<span data-ttu-id="2a1fc-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2a1fc-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2a1fc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2a1fc-112">Area:</span></span>  <br/> |<span data-ttu-id="2a1fc-113">Account</span><span class="sxs-lookup"><span data-stu-id="2a1fc-113">Account</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2a1fc-114">说明</span><span class="sxs-lookup"><span data-stu-id="2a1fc-114">Remarks</span></span>

<span data-ttu-id="2a1fc-115">指定客户端用于将邮件发送第一台服务器。</span><span class="sxs-lookup"><span data-stu-id="2a1fc-115">Specifies the first server that a client should use to send the mail.</span></span> <span data-ttu-id="2a1fc-116">这些属性的格式是实现相关。</span><span class="sxs-lookup"><span data-stu-id="2a1fc-116">The format of these properties is implementation dependent.</span></span> <span data-ttu-id="2a1fc-117">这些属性可由客户端用来确定哪些服务器直接通过，邮件是可选但值没有任何意义到服务器。</span><span class="sxs-lookup"><span data-stu-id="2a1fc-117">These properties can be used by the client to determine which server to direct the mail through, but is optional and the value has no meaning to the server.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2a1fc-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="2a1fc-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2a1fc-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="2a1fc-119">Protocol specifications</span></span>

<span data-ttu-id="2a1fc-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a1fc-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a1fc-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="2a1fc-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2a1fc-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a1fc-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a1fc-123">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="2a1fc-123">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2a1fc-124">头文件</span><span class="sxs-lookup"><span data-stu-id="2a1fc-124">Header files</span></span>

<span data-ttu-id="2a1fc-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2a1fc-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="2a1fc-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2a1fc-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="2a1fc-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2a1fc-127">Mapitags.h</span></span>
  
> <span data-ttu-id="2a1fc-128">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2a1fc-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2a1fc-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a1fc-129">See also</span></span>



[<span data-ttu-id="2a1fc-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2a1fc-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2a1fc-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a1fc-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2a1fc-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2a1fc-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2a1fc-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2a1fc-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

