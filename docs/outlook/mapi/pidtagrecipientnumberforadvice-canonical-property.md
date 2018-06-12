---
title: PidTagRecipientNumberForAdvice 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientNumberForAdvice
api_type:
- COM
ms.assetid: 636c1e75-3024-43ca-a7dd-1bb480dfbb5b
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ac4da2d4082cac632548594411528b7bf1d6dc64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778146"
---
# <a name="pidtagrecipientnumberforadvice-canonical-property"></a><span data-ttu-id="3fd08-103">PidTagRecipientNumberForAdvice 规范属性</span><span class="sxs-lookup"><span data-stu-id="3fd08-103">PidTagRecipientNumberForAdvice Canonical Property</span></span>

  
  
<span data-ttu-id="3fd08-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3fd08-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3fd08-105">此属性包含要呼叫的物理传送一条消息告知的邮件收件人的电话号码。</span><span class="sxs-lookup"><span data-stu-id="3fd08-105">This property contains a message recipient's telephone number to call to advise of the physical delivery of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3fd08-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="3fd08-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3fd08-107">PR_RECIPIENT_NUMBER_FOR_ADVICE，PR_RECIPIENT_NUMBER_FOR_ADVICE_A，PR_RECIPIENT_NUMBER_FOR_ADVICE_W</span><span class="sxs-lookup"><span data-stu-id="3fd08-107">PR_RECIPIENT_NUMBER_FOR_ADVICE, PR_RECIPIENT_NUMBER_FOR_ADVICE_A, PR_RECIPIENT_NUMBER_FOR_ADVICE_W</span></span>  <br/> |
|<span data-ttu-id="3fd08-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3fd08-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3fd08-109">0x0C14</span><span class="sxs-lookup"><span data-stu-id="3fd08-109">0x0C14</span></span>  <br/> |
|<span data-ttu-id="3fd08-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3fd08-110">Data type:</span></span>  <br/> |<span data-ttu-id="3fd08-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3fd08-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3fd08-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3fd08-112">Area:</span></span>  <br/> |<span data-ttu-id="3fd08-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="3fd08-113">MAPI Recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3fd08-114">备注</span><span class="sxs-lookup"><span data-stu-id="3fd08-114">Remarks</span></span>

<span data-ttu-id="3fd08-115">这些属性是为了时 human 收件人不应存在于传递与传递到物理目标，而不是电子邮箱，配合使用。</span><span class="sxs-lookup"><span data-stu-id="3fd08-115">These properties are meant to be used in conjunction with delivery to a physical destination, rather than an electronic mailbox, when the human recipient is not expected to be present at delivery.</span></span> <span data-ttu-id="3fd08-116">例如，传真封面工作表上的电话号码。</span><span class="sxs-lookup"><span data-stu-id="3fd08-116">An example is the telephone number on a fax cover sheet.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3fd08-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="3fd08-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="3fd08-118">头文件</span><span class="sxs-lookup"><span data-stu-id="3fd08-118">Header files</span></span>

<span data-ttu-id="3fd08-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3fd08-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="3fd08-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3fd08-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="3fd08-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3fd08-121">Mapitags.h</span></span>
  
> <span data-ttu-id="3fd08-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3fd08-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3fd08-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fd08-123">See also</span></span>



[<span data-ttu-id="3fd08-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3fd08-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3fd08-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3fd08-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3fd08-126">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3fd08-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3fd08-127">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3fd08-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

