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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 79ef85955f15e0ca829ac6f206dddc17031b0562
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420638"
---
# <a name="pidtagrecipientnumberforadvice-canonical-property"></a><span data-ttu-id="ca5b5-103">PidTagRecipientNumberForAdvice 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca5b5-103">PidTagRecipientNumberForAdvice Canonical Property</span></span>

  
  
<span data-ttu-id="ca5b5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca5b5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca5b5-105">此属性包含要呼叫的邮件收件人的电话号码，用于通知邮件的物理传递。</span><span class="sxs-lookup"><span data-stu-id="ca5b5-105">This property contains a message recipient's telephone number to call to advise of the physical delivery of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ca5b5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ca5b5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ca5b5-107">PR_RECIPIENT_NUMBER_FOR_ADVICE、PR_RECIPIENT_NUMBER_FOR_ADVICE_A、PR_RECIPIENT_NUMBER_FOR_ADVICE_W</span><span class="sxs-lookup"><span data-stu-id="ca5b5-107">PR_RECIPIENT_NUMBER_FOR_ADVICE, PR_RECIPIENT_NUMBER_FOR_ADVICE_A, PR_RECIPIENT_NUMBER_FOR_ADVICE_W</span></span>  <br/> |
|<span data-ttu-id="ca5b5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ca5b5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ca5b5-109">0x0C14</span><span class="sxs-lookup"><span data-stu-id="ca5b5-109">0x0C14</span></span>  <br/> |
|<span data-ttu-id="ca5b5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ca5b5-110">Data type:</span></span>  <br/> |<span data-ttu-id="ca5b5-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ca5b5-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ca5b5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ca5b5-112">Area:</span></span>  <br/> |<span data-ttu-id="ca5b5-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="ca5b5-113">MAPI Recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ca5b5-114">备注</span><span class="sxs-lookup"><span data-stu-id="ca5b5-114">Remarks</span></span>

<span data-ttu-id="ca5b5-115">当预期人工收件人在传递时不应存在时，这些属性旨在与传递到物理目标（而不是电子邮箱）结合使用。</span><span class="sxs-lookup"><span data-stu-id="ca5b5-115">These properties are meant to be used in conjunction with delivery to a physical destination, rather than an electronic mailbox, when the human recipient is not expected to be present at delivery.</span></span> <span data-ttu-id="ca5b5-116">例如，传真封面上的电话号码。</span><span class="sxs-lookup"><span data-stu-id="ca5b5-116">An example is the telephone number on a fax cover sheet.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ca5b5-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="ca5b5-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ca5b5-118">头文件</span><span class="sxs-lookup"><span data-stu-id="ca5b5-118">Header files</span></span>

<span data-ttu-id="ca5b5-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ca5b5-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="ca5b5-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ca5b5-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="ca5b5-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ca5b5-121">Mapitags.h</span></span>
  
> <span data-ttu-id="ca5b5-122">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ca5b5-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ca5b5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca5b5-123">See also</span></span>



[<span data-ttu-id="ca5b5-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ca5b5-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ca5b5-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca5b5-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ca5b5-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ca5b5-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ca5b5-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ca5b5-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

