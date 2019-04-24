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
# <a name="pidtagsearchrecipientemailbcc-canonical-property"></a><span data-ttu-id="e2e73-103">PidTagSearchRecipientEmailBcc 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2e73-103">PidTagSearchRecipientEmailBcc Canonical Property</span></span>

  
  
<span data-ttu-id="e2e73-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e2e73-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e2e73-105">包含在电子邮件地址列表中查询的 Unicode 字符串或在存储区上未发送邮件的 **"密件抄送**" 行中寻址的收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="e2e73-105">Contains a Unicode string that is being queried in the list of email addresses or display names of recipients addressed in the **BCC** line of unsent messages on the store.</span></span> 
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="e2e73-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e2e73-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e2e73-107">PR_SEARCH_RECIP_EMAIL_BCC_W</span><span class="sxs-lookup"><span data-stu-id="e2e73-107">PR_SEARCH_RECIP_EMAIL_BCC_W</span></span>  <br/> |
|<span data-ttu-id="e2e73-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e2e73-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e2e73-109">0x0EA8</span><span class="sxs-lookup"><span data-stu-id="e2e73-109">0x0EA8</span></span>  <br/> |
|<span data-ttu-id="e2e73-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="e2e73-110">Property type:</span></span>  <br/> |<span data-ttu-id="e2e73-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e2e73-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e2e73-112">访问权限</span><span class="sxs-lookup"><span data-stu-id="e2e73-112">Access:</span></span>  <br/> |<span data-ttu-id="e2e73-113">搜索</span><span class="sxs-lookup"><span data-stu-id="e2e73-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e2e73-114">注解</span><span class="sxs-lookup"><span data-stu-id="e2e73-114">Remarks</span></span>

<span data-ttu-id="e2e73-115">此属性仅与存储区上尚未发送的邮件相关, 因为发送或接收的邮件不包含 BCC 信息。</span><span class="sxs-lookup"><span data-stu-id="e2e73-115">This property is only relevant to messages on the store that have not been sent, because messages that have been sent or received do not contain BCC information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2e73-116">在您当前拥有的可下载头文件中搜索将邮件作为密件抄送发送的电子邮件地址或显示名称时, 将使用此 MAPI 限制标记。</span><span class="sxs-lookup"><span data-stu-id="e2e73-116">This MAPI restriction tag, used when searching for email addresses or display names to which the message will be sent as a blind carbon copy, might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="e2e73-117">您可以使用以下值将其添加到代码中: >`#define PR_SEARCH_RECIP_EMAIL_BCC_W PROP_TAG(PT_UNICODE, 0x0EA8)`</span><span class="sxs-lookup"><span data-stu-id="e2e73-117">You can add it to your code by using the following value: >  `#define PR_SEARCH_RECIP_EMAIL_BCC_W PROP_TAG(PT_UNICODE, 0x0EA8)`</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e2e73-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="e2e73-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e2e73-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="e2e73-119">Protocol specifications</span></span>

<span data-ttu-id="e2e73-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2e73-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e2e73-121">提供对相关 Microsoft Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e2e73-121">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e2e73-122">[[毫秒-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2e73-122">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e2e73-123">指定用于操作搜索文件夹列表配置的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e2e73-123">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e2e73-124">头文件</span><span class="sxs-lookup"><span data-stu-id="e2e73-124">Header files</span></span>

<span data-ttu-id="e2e73-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e2e73-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="e2e73-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e2e73-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="e2e73-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="e2e73-127">Mapitags.h</span></span>
  
> <span data-ttu-id="e2e73-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e2e73-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e2e73-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2e73-129">See also</span></span>



[<span data-ttu-id="e2e73-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e2e73-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e2e73-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2e73-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e2e73-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e2e73-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e2e73-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e2e73-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

