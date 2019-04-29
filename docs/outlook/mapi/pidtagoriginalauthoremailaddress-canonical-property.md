---
title: PidTagOriginalAuthorEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorEmailAddress
api_type:
- COM
ms.assetid: 67cda756-ba71-4f29-a601-55359e44d93b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7918c5d5b585ffb199bfbc140edfb8286b499b40
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436165"
---
# <a name="pidtagoriginalauthoremailaddress-canonical-property"></a><span data-ttu-id="f37a9-103">PidTagOriginalAuthorEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="f37a9-103">PidTagOriginalAuthorEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="f37a9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f37a9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f37a9-105">包含邮件第一版的作者的电子邮件地址, 即邮件转发或答复前的邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f37a9-105">Contains the email address of the author of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f37a9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f37a9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f37a9-107">PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS、PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_A、PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="f37a9-107">PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS, PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_A, PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="f37a9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f37a9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f37a9-109">0x007A</span><span class="sxs-lookup"><span data-stu-id="f37a9-109">0x007A</span></span>  <br/> |
|<span data-ttu-id="f37a9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f37a9-110">Data type:</span></span>  <br/> |<span data-ttu-id="f37a9-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f37a9-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="f37a9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f37a9-112">Area:</span></span>  <br/> |<span data-ttu-id="f37a9-113">服务器</span><span class="sxs-lookup"><span data-stu-id="f37a9-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f37a9-114">说明</span><span class="sxs-lookup"><span data-stu-id="f37a9-114">Remarks</span></span>

<span data-ttu-id="f37a9-115">这些属性是邮件作者地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="f37a9-115">These properties are examples of the address properties for the author of a message.</span></span> <span data-ttu-id="f37a9-116">首次提交邮件时, 客户端应用程序应将这些属性设置为**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="f37a9-116">At first submission of the message, the client application should set these properties to the value of the **PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) property.</span></span> <span data-ttu-id="f37a9-117">转发或答复邮件时, 它永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="f37a9-117">It is never changed when the message is forwarded or replied to.</span></span>
  
<span data-ttu-id="f37a9-118">原始作者属性允许保留本地邮件域外部的信息。</span><span class="sxs-lookup"><span data-stu-id="f37a9-118">The original author properties allow for preservation of information from outside the local messaging domain.</span></span> <span data-ttu-id="f37a9-119">当邮件到达其他邮件域 (例如从 Internet) 时, 这些属性提供了一种确保原始信息不会丢失的方法。</span><span class="sxs-lookup"><span data-stu-id="f37a9-119">When a message arrives from another messaging domain, such as from the Internet, these properties provide a way to ensure that original information is not lost.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f37a9-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="f37a9-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f37a9-121">头文件</span><span class="sxs-lookup"><span data-stu-id="f37a9-121">Header files</span></span>

<span data-ttu-id="f37a9-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f37a9-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="f37a9-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f37a9-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="f37a9-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="f37a9-124">Mapitags.h</span></span>
  
> <span data-ttu-id="f37a9-125">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f37a9-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f37a9-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f37a9-126">See also</span></span>



[<span data-ttu-id="f37a9-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f37a9-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f37a9-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f37a9-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f37a9-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f37a9-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f37a9-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f37a9-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

