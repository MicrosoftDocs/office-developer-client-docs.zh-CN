---
title: PidTagOriginalSenderEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSenderEmailAddress
api_type:
- COM
ms.assetid: cc86505c-e264-435f-ae21-4a10f0bbf082
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ed3d84667d7be9c06d0ddf4d896b8888694edc12
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355270"
---
# <a name="pidtagoriginalsenderemailaddress-canonical-property"></a><span data-ttu-id="2e0ae-103">PidTagOriginalSenderEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e0ae-103">PidTagOriginalSenderEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="2e0ae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e0ae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e0ae-105">包含邮件第一个版本的发件人的电子邮件地址，即转发或答复前的邮件。</span><span class="sxs-lookup"><span data-stu-id="2e0ae-105">Contains the email address of the sender of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2e0ae-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2e0ae-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2e0ae-107">PR_ORIGINAL_SENDER_EMAIL_ADDRESS、PR_ORIGINAL_SENDER_EMAIL_ADDRESS_A、PR_ORIGINAL_SENDER_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="2e0ae-107">PR_ORIGINAL_SENDER_EMAIL_ADDRESS, PR_ORIGINAL_SENDER_EMAIL_ADDRESS_A, PR_ORIGINAL_SENDER_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="2e0ae-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2e0ae-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2e0ae-109">0x0067</span><span class="sxs-lookup"><span data-stu-id="2e0ae-109">0x0067</span></span>  <br/> |
|<span data-ttu-id="2e0ae-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2e0ae-110">Data type:</span></span>  <br/> |<span data-ttu-id="2e0ae-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2e0ae-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2e0ae-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2e0ae-112">Area:</span></span>  <br/> |<span data-ttu-id="2e0ae-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="2e0ae-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2e0ae-114">备注</span><span class="sxs-lookup"><span data-stu-id="2e0ae-114">Remarks</span></span>

<span data-ttu-id="2e0ae-115">这些属性是邮件的原始发件人的地址属性示例。</span><span class="sxs-lookup"><span data-stu-id="2e0ae-115">These properties are examples of the address properties for the original sender of a message.</span></span> <span data-ttu-id="2e0ae-116">首次提交邮件时，客户端应用程序应该将此属性设置为 PR_SENDER_EMAIL_ADDRESS ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="2e0ae-116">At first submission of the message, the client application should set this property to the value of **PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)).</span></span> <span data-ttu-id="2e0ae-117">转发或答复邮件时从不更改。</span><span class="sxs-lookup"><span data-stu-id="2e0ae-117">It is never changed when the message is forwarded or replied to.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2e0ae-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="2e0ae-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2e0ae-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="2e0ae-119">Protocol specifications</span></span>

<span data-ttu-id="2e0ae-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e0ae-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e0ae-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="2e0ae-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2e0ae-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e0ae-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e0ae-123">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2e0ae-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2e0ae-124">头文件</span><span class="sxs-lookup"><span data-stu-id="2e0ae-124">Header files</span></span>

<span data-ttu-id="2e0ae-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2e0ae-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="2e0ae-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2e0ae-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="2e0ae-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2e0ae-127">Mapitags.h</span></span>
  
> <span data-ttu-id="2e0ae-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2e0ae-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2e0ae-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e0ae-129">See also</span></span>



[<span data-ttu-id="2e0ae-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2e0ae-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2e0ae-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e0ae-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2e0ae-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2e0ae-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2e0ae-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2e0ae-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

