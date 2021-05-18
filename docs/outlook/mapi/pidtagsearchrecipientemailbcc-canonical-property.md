---
title: PidTagSearchRecipientEmailBcc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d9561d13-8d52-500c-5369-15a2cf5c92c3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5b0db4b3bc7903aae74fa7275d3e27e22d628514
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359155"
---
# <a name="pidtagsearchrecipientemailbcc-canonical-property"></a><span data-ttu-id="068fa-103">PidTagSearchRecipientEmailBcc 规范属性</span><span class="sxs-lookup"><span data-stu-id="068fa-103">PidTagSearchRecipientEmailBcc Canonical Property</span></span>

  
  
<span data-ttu-id="068fa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="068fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="068fa-105">包含一个 Unicode 字符串，该字符串正在电子邮件地址列表中查询，或在存储上未发送邮件的 **"BCC"** 行中显示收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="068fa-105">Contains a Unicode string that is being queried in the list of email addresses or display names of recipients addressed in the **BCC** line of unsent messages on the store.</span></span> 
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="068fa-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="068fa-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="068fa-107">PR_SEARCH_RECIP_EMAIL_BCC_W</span><span class="sxs-lookup"><span data-stu-id="068fa-107">PR_SEARCH_RECIP_EMAIL_BCC_W</span></span>  <br/> |
|<span data-ttu-id="068fa-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="068fa-108">Identifier:</span></span>  <br/> |<span data-ttu-id="068fa-109">0x0EA8</span><span class="sxs-lookup"><span data-stu-id="068fa-109">0x0EA8</span></span>  <br/> |
|<span data-ttu-id="068fa-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="068fa-110">Property type:</span></span>  <br/> |<span data-ttu-id="068fa-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="068fa-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="068fa-112">访问权限</span><span class="sxs-lookup"><span data-stu-id="068fa-112">Access:</span></span>  <br/> |<span data-ttu-id="068fa-113">搜索</span><span class="sxs-lookup"><span data-stu-id="068fa-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="068fa-114">备注</span><span class="sxs-lookup"><span data-stu-id="068fa-114">Remarks</span></span>

<span data-ttu-id="068fa-115">此属性仅与存储上尚未发送的邮件相关，因为已发送或接收的邮件不包含 BCC 信息。</span><span class="sxs-lookup"><span data-stu-id="068fa-115">This property is only relevant to messages on the store that have not been sent, because messages that have been sent or received do not contain BCC information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="068fa-116">此 MAPI 限制标记（在搜索电子邮件地址或显示邮件将作为副本发送到的名称）时可能未在当前具有的可下载头文件中定义。</span><span class="sxs-lookup"><span data-stu-id="068fa-116">This MAPI restriction tag, used when searching for email addresses or display names to which the message will be sent as a blind carbon copy, might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="068fa-117">可以使用以下值将其添加到代码中：>  `#define PR_SEARCH_RECIP_EMAIL_BCC_W PROP_TAG(PT_UNICODE, 0x0EA8)`</span><span class="sxs-lookup"><span data-stu-id="068fa-117">You can add it to your code by using the following value: >  `#define PR_SEARCH_RECIP_EMAIL_BCC_W PROP_TAG(PT_UNICODE, 0x0EA8)`</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="068fa-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="068fa-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="068fa-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="068fa-119">Protocol specifications</span></span>

<span data-ttu-id="068fa-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="068fa-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="068fa-121">提供对相关协议Microsoft Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="068fa-121">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="068fa-122">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="068fa-122">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="068fa-123">指定用于操作搜索文件夹列表配置的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="068fa-123">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="068fa-124">头文件</span><span class="sxs-lookup"><span data-stu-id="068fa-124">Header files</span></span>

<span data-ttu-id="068fa-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="068fa-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="068fa-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="068fa-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="068fa-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="068fa-127">Mapitags.h</span></span>
  
> <span data-ttu-id="068fa-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="068fa-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="068fa-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="068fa-129">See also</span></span>



[<span data-ttu-id="068fa-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="068fa-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="068fa-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="068fa-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="068fa-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="068fa-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="068fa-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="068fa-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

