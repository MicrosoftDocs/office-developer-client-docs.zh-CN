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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dfe3b57c246e247eda365bed46af2e0f35f0e54b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391953"
---
# <a name="pidlidvalidflagstringproof-canonical-property"></a><span data-ttu-id="374f8-103">PidLidValidFlagStringProof 规范属性</span><span class="sxs-lookup"><span data-stu-id="374f8-103">PidLidValidFlagStringProof Canonical Property</span></span>

  
  
<span data-ttu-id="374f8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="374f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="374f8-105">验证是否由代理知道**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 属性的值设置**dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="374f8-105">Validates whether the **dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) property's value was set by an agent who knew the value of the **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="374f8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="374f8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="374f8-107">dispidValidFlagStringProof</span><span class="sxs-lookup"><span data-stu-id="374f8-107">dispidValidFlagStringProof</span></span>  <br/> |
|<span data-ttu-id="374f8-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="374f8-108">Property set:</span></span>  <br/> |<span data-ttu-id="374f8-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="374f8-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="374f8-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="374f8-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="374f8-111">0x000085BF</span><span class="sxs-lookup"><span data-stu-id="374f8-111">0x000085BF</span></span>  <br/> |
|<span data-ttu-id="374f8-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="374f8-112">Data type:</span></span>  <br/> |<span data-ttu-id="374f8-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="374f8-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="374f8-114">区域：</span><span class="sxs-lookup"><span data-stu-id="374f8-114">Area:</span></span>  <br/> |<span data-ttu-id="374f8-115">Task</span><span class="sxs-lookup"><span data-stu-id="374f8-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="374f8-116">说明</span><span class="sxs-lookup"><span data-stu-id="374f8-116">Remarks</span></span>

<span data-ttu-id="374f8-117">非可发送的对象 （收到的邮件和非邮件对象），客户端应将该值设置为**PR_MESSAGE_DELIVERY_TIME**的值修改**dispidRequest**时。</span><span class="sxs-lookup"><span data-stu-id="374f8-117">On non-sendable objects (received mail and non-mail objects), clients should set this value to the value of **PR_MESSAGE_DELIVERY_TIME** when modifying **dispidRequest**.</span></span>
  
<span data-ttu-id="374f8-118">由于无法发件人，预测**PR_MESSAGE_DELIVERY_TIME**的值，如果此属性的值等于**PR_MESSAGE_DELIVERY_TIME**的值，它是合理特定的**dispidRequest**值没有源自消息的发件人。</span><span class="sxs-lookup"><span data-stu-id="374f8-118">Since the value of **PR_MESSAGE_DELIVERY_TIME** cannot be predicted by the sender, if the value of this property is equal to the value of **PR_MESSAGE_DELIVERY_TIME**, it is reasonably certain that the value of **dispidRequest** did not originate from the sender of the message.</span></span> <span data-ttu-id="374f8-119">客户端可以决定如何向最终用户基于客户端的特定的安全策略根据此比较结果显示**dispidRequest**的值。</span><span class="sxs-lookup"><span data-stu-id="374f8-119">A client can decide how to present the value of **dispidRequest** to the end user based on the result of this comparison in accordance with the specific security policy of the client.</span></span> <span data-ttu-id="374f8-120">如果由于**dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) 的值的状态，则忽略**dispidRequest**的值，则必须忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="374f8-120">If the value of **dispidRequest** is ignored due to the presence of a value for **dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)), this property must be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="374f8-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="374f8-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="374f8-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="374f8-122">Protocol specifications</span></span>

<span data-ttu-id="374f8-123">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="374f8-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="374f8-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="374f8-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="374f8-125">[[MS OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="374f8-125">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="374f8-126">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="374f8-126">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="374f8-127">头文件</span><span class="sxs-lookup"><span data-stu-id="374f8-127">Header files</span></span>

<span data-ttu-id="374f8-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="374f8-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="374f8-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="374f8-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="374f8-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="374f8-130">See also</span></span>



[<span data-ttu-id="374f8-131">PidTagMessageDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="374f8-131">PidTagMessageDeliveryTime Canonical Property</span></span>](pidtagmessagedeliverytime-canonical-property.md)


[<span data-ttu-id="374f8-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="374f8-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="374f8-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="374f8-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="374f8-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="374f8-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="374f8-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="374f8-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

