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
ms.openlocfilehash: bd019378a8db7b2e356f0c8b2f30a59e685b9e8a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595431"
---
# <a name="pidtagoriginalauthoremailaddress-canonical-property"></a><span data-ttu-id="97098-103">PidTagOriginalAuthorEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="97098-103">PidTagOriginalAuthorEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="97098-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="97098-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="97098-105">包含一条消息，即之前正在转发或答复邮件的第一个版本的作者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="97098-105">Contains the email address of the author of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="97098-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="97098-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="97098-107">PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS，PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_A，PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="97098-107">PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS, PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_A, PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="97098-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="97098-108">Identifier:</span></span>  <br/> |<span data-ttu-id="97098-109">0x007A</span><span class="sxs-lookup"><span data-stu-id="97098-109">0x007A</span></span>  <br/> |
|<span data-ttu-id="97098-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="97098-110">Data type:</span></span>  <br/> |<span data-ttu-id="97098-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="97098-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="97098-112">区域：</span><span class="sxs-lookup"><span data-stu-id="97098-112">Area:</span></span>  <br/> |<span data-ttu-id="97098-113">Server</span><span class="sxs-lookup"><span data-stu-id="97098-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="97098-114">注解</span><span class="sxs-lookup"><span data-stu-id="97098-114">Remarks</span></span>

<span data-ttu-id="97098-115">这些属性是邮件的作者的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="97098-115">These properties are examples of the address properties for the author of a message.</span></span> <span data-ttu-id="97098-116">在首次提交邮件，客户端应用程序应将这些属性设置为**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="97098-116">At first submission of the message, the client application should set these properties to the value of the **PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) property.</span></span> <span data-ttu-id="97098-117">当转发或答复邮件永远不会更改它。</span><span class="sxs-lookup"><span data-stu-id="97098-117">It is never changed when the message is forwarded or replied to.</span></span>
  
<span data-ttu-id="97098-118">原始作者属性允许保留来自域外部的本地消息的信息。</span><span class="sxs-lookup"><span data-stu-id="97098-118">The original author properties allow for preservation of information from outside the local messaging domain.</span></span> <span data-ttu-id="97098-119">当邮件到达从其他邮件的域时，如从 Internet，这些属性提供一种方法，以确保原始信息不会丢失。</span><span class="sxs-lookup"><span data-stu-id="97098-119">When a message arrives from another messaging domain, such as from the Internet, these properties provide a way to ensure that original information is not lost.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="97098-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="97098-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="97098-121">头文件</span><span class="sxs-lookup"><span data-stu-id="97098-121">Header files</span></span>

<span data-ttu-id="97098-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="97098-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="97098-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="97098-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="97098-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="97098-124">Mapitags.h</span></span>
  
> <span data-ttu-id="97098-125">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="97098-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="97098-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97098-126">See also</span></span>



[<span data-ttu-id="97098-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="97098-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="97098-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="97098-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="97098-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="97098-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="97098-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="97098-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

