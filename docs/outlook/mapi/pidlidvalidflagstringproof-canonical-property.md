---
title: PidLidValidFlagStringProof 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidValidFlagStringProof
api_type:
- COM
ms.assetid: e5a94968-7e84-4faf-8104-9ea36d35fa1a
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 90f16f33e7e116e124384f9988c0c7dddaad2da5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777159"
---
# <a name="pidlidvalidflagstringproof-canonical-property"></a><span data-ttu-id="36c16-103">PidLidValidFlagStringProof 规范属性</span><span class="sxs-lookup"><span data-stu-id="36c16-103">PidLidValidFlagStringProof Canonical Property</span></span>

  
  
<span data-ttu-id="36c16-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="36c16-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="36c16-105">验证是否由代理知道**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 属性的值设置**dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="36c16-105">Validates whether the **dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) property's value was set by an agent who knew the value of the **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="36c16-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="36c16-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="36c16-107">dispidValidFlagStringProof</span><span class="sxs-lookup"><span data-stu-id="36c16-107">dispidValidFlagStringProof</span></span>  <br/> |
|<span data-ttu-id="36c16-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="36c16-108">Property set:</span></span>  <br/> |<span data-ttu-id="36c16-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="36c16-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="36c16-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="36c16-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="36c16-111">0x000085BF</span><span class="sxs-lookup"><span data-stu-id="36c16-111">0x000085BF</span></span>  <br/> |
|<span data-ttu-id="36c16-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="36c16-112">Data type:</span></span>  <br/> |<span data-ttu-id="36c16-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="36c16-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="36c16-114">区域：</span><span class="sxs-lookup"><span data-stu-id="36c16-114">Area:</span></span>  <br/> |<span data-ttu-id="36c16-115">任务</span><span class="sxs-lookup"><span data-stu-id="36c16-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="36c16-116">备注</span><span class="sxs-lookup"><span data-stu-id="36c16-116">Remarks</span></span>

<span data-ttu-id="36c16-117">非可发送的对象 （收到的邮件和非邮件对象），客户端应将该值设置为**PR_MESSAGE_DELIVERY_TIME**的值修改**dispidRequest**时。</span><span class="sxs-lookup"><span data-stu-id="36c16-117">On non-sendable objects (received mail and non-mail objects), clients should set this value to the value of **PR_MESSAGE_DELIVERY_TIME** when modifying **dispidRequest**.</span></span>
  
<span data-ttu-id="36c16-118">由于无法发件人，预测**PR_MESSAGE_DELIVERY_TIME**的值，如果此属性的值等于**PR_MESSAGE_DELIVERY_TIME**的值，它是合理特定的**dispidRequest**值没有源自消息的发件人。</span><span class="sxs-lookup"><span data-stu-id="36c16-118">Since the value of **PR_MESSAGE_DELIVERY_TIME** cannot be predicted by the sender, if the value of this property is equal to the value of **PR_MESSAGE_DELIVERY_TIME**, it is reasonably certain that the value of **dispidRequest** did not originate from the sender of the message.</span></span> <span data-ttu-id="36c16-119">客户端可以决定如何向最终用户基于客户端的特定的安全策略根据此比较结果显示**dispidRequest**的值。</span><span class="sxs-lookup"><span data-stu-id="36c16-119">A client can decide how to present the value of **dispidRequest** to the end user based on the result of this comparison in accordance with the specific security policy of the client.</span></span> <span data-ttu-id="36c16-120">如果由于**dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) 的值的状态，则忽略**dispidRequest**的值，则必须忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="36c16-120">If the value of **dispidRequest** is ignored due to the presence of a value for **dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)), this property must be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="36c16-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="36c16-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="36c16-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="36c16-122">Protocol specifications</span></span>

<span data-ttu-id="36c16-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="36c16-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="36c16-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="36c16-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="36c16-125">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="36c16-125">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="36c16-126">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="36c16-126">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="36c16-127">头文件</span><span class="sxs-lookup"><span data-stu-id="36c16-127">Header files</span></span>

<span data-ttu-id="36c16-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="36c16-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="36c16-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="36c16-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="36c16-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36c16-130">See also</span></span>



[<span data-ttu-id="36c16-131">PidTagMessageDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="36c16-131">PidTagMessageDeliveryTime Canonical Property</span></span>](pidtagmessagedeliverytime-canonical-property.md)


[<span data-ttu-id="36c16-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="36c16-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="36c16-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="36c16-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="36c16-134">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="36c16-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="36c16-135">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="36c16-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

