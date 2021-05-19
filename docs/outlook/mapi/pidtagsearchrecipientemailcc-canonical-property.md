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
ms.openlocfilehash: 03501e14740d7b27bd54d761ae701e8863ad79dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358945"
---
# <a name="pidtagsearchrecipientemailcc-canonical-property"></a><span data-ttu-id="d8d93-103">PidTagSearchRecipientEmailCc 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8d93-103">PidTagSearchRecipientEmailCc Canonical Property</span></span>

  
  
<span data-ttu-id="d8d93-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d8d93-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d8d93-105">包含一个 Unicode 字符串，该字符串正在电子邮件地址列表中查询或在存储上邮件 **的"抄** 送"行中寻址的收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d8d93-105">Contains a Unicode string that is being queried in the list of email addresses or display names of recipients that are addressed in the **CC** line of messages on the store.</span></span> 
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="d8d93-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d8d93-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d8d93-107">PR_SEARCH_RECIP_EMAIL_CC_W</span><span class="sxs-lookup"><span data-stu-id="d8d93-107">PR_SEARCH_RECIP_EMAIL_CC_W</span></span>  <br/> |
|<span data-ttu-id="d8d93-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d8d93-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d8d93-109">0x0EA7</span><span class="sxs-lookup"><span data-stu-id="d8d93-109">0x0EA7</span></span>  <br/> |
|<span data-ttu-id="d8d93-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="d8d93-110">Property type:</span></span>  <br/> |<span data-ttu-id="d8d93-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d8d93-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="d8d93-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d8d93-112">Area:</span></span>  <br/> |<span data-ttu-id="d8d93-113">搜索</span><span class="sxs-lookup"><span data-stu-id="d8d93-113">Search</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="d8d93-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="d8d93-114">Related resources</span></span>

> [!NOTE]
> <span data-ttu-id="d8d93-115">当您搜索电子邮件地址或显示邮件作为抄送发送到的名称时，可能不会在当前具有的可下载头文件中定义此 MAPI 限制标记。</span><span class="sxs-lookup"><span data-stu-id="d8d93-115">This MAPI restriction tag, used when you search for email addresses or display names to which the message is sent as a carbon copy, might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="d8d93-116">可以使用以下值将其添加到代码中：>  `#define PR_SEARCH_RECIP_EMAIL_CC_W PROP_TAG(PT_UNICODE, 0x0EA7)`</span><span class="sxs-lookup"><span data-stu-id="d8d93-116">You can add it to your code by using the following value: >  `#define PR_SEARCH_RECIP_EMAIL_CC_W PROP_TAG(PT_UNICODE, 0x0EA7)`</span></span>
  
### <a name="protocol-specifications"></a><span data-ttu-id="d8d93-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="d8d93-117">Protocol specifications</span></span>

<span data-ttu-id="d8d93-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d8d93-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d8d93-119">提供对相关协议Microsoft Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="d8d93-119">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d8d93-120">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d8d93-120">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d8d93-121">指定用于操作搜索文件夹列表配置的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="d8d93-121">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d8d93-122">头文件</span><span class="sxs-lookup"><span data-stu-id="d8d93-122">Header files</span></span>

<span data-ttu-id="d8d93-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d8d93-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="d8d93-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d8d93-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="d8d93-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d8d93-125">Mapitags.h</span></span>
  
> <span data-ttu-id="d8d93-126">包含列为备用名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d8d93-126">Contains definitions of properties that are listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d8d93-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8d93-127">See also</span></span>



[<span data-ttu-id="d8d93-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d8d93-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d8d93-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8d93-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d8d93-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d8d93-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d8d93-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d8d93-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

