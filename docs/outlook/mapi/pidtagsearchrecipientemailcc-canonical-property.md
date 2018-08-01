---
title: PidTagSearchRecipientEmailCc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 38fe217d-cf2e-51de-c97a-acb015129fd3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6fe59bf837d6123e5655e853531d6ab53393af91
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778371"
---
# <a name="pidtagsearchrecipientemailcc-canonical-property"></a><span data-ttu-id="8abe9-103">PidTagSearchRecipientEmailCc 规范属性</span><span class="sxs-lookup"><span data-stu-id="8abe9-103">PidTagSearchRecipientEmailCc Canonical Property</span></span>

  
  
<span data-ttu-id="8abe9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8abe9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8abe9-105">包含所查询的电子邮件地址或显示名称上存储的消息**CC**行中所述的收件人列表中的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="8abe9-105">Contains a Unicode string that is being queried in the list of email addresses or display names of recipients that are addressed in the **CC** line of messages on the store.</span></span> 
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="8abe9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8abe9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8abe9-107">PR_SEARCH_RECIP_EMAIL_CC_W</span><span class="sxs-lookup"><span data-stu-id="8abe9-107">PR_SEARCH_RECIP_EMAIL_CC_W</span></span>  <br/> |
|<span data-ttu-id="8abe9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8abe9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8abe9-109">0x0EA7</span><span class="sxs-lookup"><span data-stu-id="8abe9-109">0x0EA7</span></span>  <br/> |
|<span data-ttu-id="8abe9-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="8abe9-110">Property type:</span></span>  <br/> |<span data-ttu-id="8abe9-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8abe9-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="8abe9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8abe9-112">Area:</span></span>  <br/> |<span data-ttu-id="8abe9-113">搜索</span><span class="sxs-lookup"><span data-stu-id="8abe9-113">Search</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="8abe9-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="8abe9-114">Related resources</span></span>

> [!NOTE]
> <span data-ttu-id="8abe9-115">未可能在您当前拥有的可下载的头文件中定义搜索电子邮件地址或显示的名称为抄送邮件发送到时使用此 MAPI 限制标记。</span><span class="sxs-lookup"><span data-stu-id="8abe9-115">This MAPI restriction tag, used when you search for email addresses or display names to which the message is sent as a carbon copy, might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="8abe9-116">您可以将其添加到您的代码通过使用以下值： >`#define PR_SEARCH_RECIP_EMAIL_CC_W PROP_TAG(PT_UNICODE, 0x0EA7)`</span><span class="sxs-lookup"><span data-stu-id="8abe9-116">You can add it to your code by using the following value: >  `#define PR_SEARCH_RECIP_EMAIL_CC_W PROP_TAG(PT_UNICODE, 0x0EA7)`</span></span>
  
### <a name="protocol-specifications"></a><span data-ttu-id="8abe9-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="8abe9-117">Protocol specifications</span></span>

<span data-ttu-id="8abe9-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8abe9-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8abe9-119">提供了相关的 Microsoft Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="8abe9-119">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8abe9-120">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8abe9-120">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8abe9-121">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="8abe9-121">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8abe9-122">头文件</span><span class="sxs-lookup"><span data-stu-id="8abe9-122">Header files</span></span>

<span data-ttu-id="8abe9-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8abe9-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="8abe9-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8abe9-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="8abe9-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8abe9-125">Mapitags.h</span></span>
  
> <span data-ttu-id="8abe9-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8abe9-126">Contains definitions of properties that are listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8abe9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8abe9-127">See also</span></span>



[<span data-ttu-id="8abe9-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8abe9-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8abe9-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8abe9-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8abe9-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8abe9-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8abe9-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8abe9-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

