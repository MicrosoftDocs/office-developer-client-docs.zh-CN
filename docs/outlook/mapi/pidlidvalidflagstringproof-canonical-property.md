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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315384"
---
# <a name="pidlidvalidflagstringproof-canonical-property"></a><span data-ttu-id="24dea-103">PidLidValidFlagStringProof 规范属性</span><span class="sxs-lookup"><span data-stu-id="24dea-103">PidLidValidFlagStringProof Canonical Property</span></span>

  
  
<span data-ttu-id="24dea-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24dea-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24dea-105">验证 **dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 属性的值是否由知道 PR_MESSAGE_DELIVERY_TIME ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md) **)** 属性值的代理设置。</span><span class="sxs-lookup"><span data-stu-id="24dea-105">Validates whether the **dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) property's value was set by an agent who knew the value of the **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="24dea-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="24dea-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="24dea-107">dispidValidFlagStringProof</span><span class="sxs-lookup"><span data-stu-id="24dea-107">dispidValidFlagStringProof</span></span>  <br/> |
|<span data-ttu-id="24dea-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="24dea-108">Property set:</span></span>  <br/> |<span data-ttu-id="24dea-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="24dea-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="24dea-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="24dea-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="24dea-111">0x000085BF</span><span class="sxs-lookup"><span data-stu-id="24dea-111">0x000085BF</span></span>  <br/> |
|<span data-ttu-id="24dea-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="24dea-112">Data type:</span></span>  <br/> |<span data-ttu-id="24dea-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="24dea-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="24dea-114">区域：</span><span class="sxs-lookup"><span data-stu-id="24dea-114">Area:</span></span>  <br/> |<span data-ttu-id="24dea-115">任务</span><span class="sxs-lookup"><span data-stu-id="24dea-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="24dea-116">备注</span><span class="sxs-lookup"><span data-stu-id="24dea-116">Remarks</span></span>

<span data-ttu-id="24dea-117">对于不可发送 (接收的邮件和非邮件) ，客户端应在修改 **dispidRequest** PR_MESSAGE_DELIVERY_TIME此值。 </span><span class="sxs-lookup"><span data-stu-id="24dea-117">On non-sendable objects (received mail and non-mail objects), clients should set this value to the value of **PR_MESSAGE_DELIVERY_TIME** when modifying **dispidRequest**.</span></span>
  
<span data-ttu-id="24dea-118">由于 **发件人无法** 预测 **PR_MESSAGE_DELIVERY_TIME** 的值，因此，如果此属性的值等于 PR_MESSAGE_DELIVERY_TIME 的值，则合理确定 **dispidRequest** 的值并非源自邮件的发件人。</span><span class="sxs-lookup"><span data-stu-id="24dea-118">Since the value of **PR_MESSAGE_DELIVERY_TIME** cannot be predicted by the sender, if the value of this property is equal to the value of **PR_MESSAGE_DELIVERY_TIME**, it is reasonably certain that the value of **dispidRequest** did not originate from the sender of the message.</span></span> <span data-ttu-id="24dea-119">根据客户端的特定安全策略，客户端可以决定如何根据此比较结果向最终用户显示 **dispidRequest** 的值。</span><span class="sxs-lookup"><span data-stu-id="24dea-119">A client can decide how to present the value of **dispidRequest** to the end user based on the result of this comparison in accordance with the specific security policy of the client.</span></span> <span data-ttu-id="24dea-120">如果由于 **dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)) 值而忽略 **dispidRequest** 的值，则必须忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="24dea-120">If the value of **dispidRequest** is ignored due to the presence of a value for **dispidFlagStringEnum** ([PidLidFlagString](pidlidflagstring-canonical-property.md)), this property must be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="24dea-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="24dea-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="24dea-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="24dea-122">Protocol specifications</span></span>

<span data-ttu-id="24dea-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24dea-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24dea-124">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="24dea-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="24dea-125">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24dea-125">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24dea-126">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="24dea-126">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="24dea-127">头文件</span><span class="sxs-lookup"><span data-stu-id="24dea-127">Header files</span></span>

<span data-ttu-id="24dea-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="24dea-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="24dea-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="24dea-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="24dea-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24dea-130">See also</span></span>



[<span data-ttu-id="24dea-131">PidTagMessageDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="24dea-131">PidTagMessageDeliveryTime Canonical Property</span></span>](pidtagmessagedeliverytime-canonical-property.md)


[<span data-ttu-id="24dea-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="24dea-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="24dea-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="24dea-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="24dea-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="24dea-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="24dea-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="24dea-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

