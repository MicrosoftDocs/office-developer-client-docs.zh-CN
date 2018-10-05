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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387746"
---
# <a name="pidtagsearchrecipientemailbcc-canonical-property"></a><span data-ttu-id="257c8-103">PidTagSearchRecipientEmailBcc 规范属性</span><span class="sxs-lookup"><span data-stu-id="257c8-103">PidTagSearchRecipientEmailBcc Canonical Property</span></span>

  
  
<span data-ttu-id="257c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="257c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="257c8-105">包含所查询的电子邮件地址或显示名称的存储区上的未发送邮件**密件抄送**行中的收件人列表中的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="257c8-105">Contains a Unicode string that is being queried in the list of email addresses or display names of recipients addressed in the **BCC** line of unsent messages on the store.</span></span> 
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="257c8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="257c8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="257c8-107">PR_SEARCH_RECIP_EMAIL_BCC_W</span><span class="sxs-lookup"><span data-stu-id="257c8-107">PR_SEARCH_RECIP_EMAIL_BCC_W</span></span>  <br/> |
|<span data-ttu-id="257c8-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="257c8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="257c8-109">0x0EA8</span><span class="sxs-lookup"><span data-stu-id="257c8-109">0x0EA8</span></span>  <br/> |
|<span data-ttu-id="257c8-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="257c8-110">Property type:</span></span>  <br/> |<span data-ttu-id="257c8-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="257c8-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="257c8-112">访问权限</span><span class="sxs-lookup"><span data-stu-id="257c8-112">Access:</span></span>  <br/> |<span data-ttu-id="257c8-113">搜索</span><span class="sxs-lookup"><span data-stu-id="257c8-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="257c8-114">说明</span><span class="sxs-lookup"><span data-stu-id="257c8-114">Remarks</span></span>

<span data-ttu-id="257c8-115">此属性才相关的尚未发送，存储区上的邮件，因为已发送或接收的消息不包含密件抄送信息。</span><span class="sxs-lookup"><span data-stu-id="257c8-115">This property is only relevant to messages on the store that have not been sent, because messages that have been sent or received do not contain BCC information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="257c8-116">未可能在您当前拥有的可下载的头文件中定义搜索电子邮件地址或显示名称为密件抄送副本，发送邮件时使用此 MAPI 限制标记。</span><span class="sxs-lookup"><span data-stu-id="257c8-116">This MAPI restriction tag, used when searching for email addresses or display names to which the message will be sent as a blind carbon copy, might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="257c8-117">您可以将其添加到您的代码通过使用以下值： >`#define PR_SEARCH_RECIP_EMAIL_BCC_W PROP_TAG(PT_UNICODE, 0x0EA8)`</span><span class="sxs-lookup"><span data-stu-id="257c8-117">You can add it to your code by using the following value: >  `#define PR_SEARCH_RECIP_EMAIL_BCC_W PROP_TAG(PT_UNICODE, 0x0EA8)`</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="257c8-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="257c8-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="257c8-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="257c8-119">Protocol specifications</span></span>

<span data-ttu-id="257c8-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="257c8-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="257c8-121">提供了相关的 Microsoft Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="257c8-121">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="257c8-122">[[MS OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="257c8-122">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="257c8-123">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="257c8-123">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="257c8-124">头文件</span><span class="sxs-lookup"><span data-stu-id="257c8-124">Header files</span></span>

<span data-ttu-id="257c8-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="257c8-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="257c8-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="257c8-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="257c8-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="257c8-127">Mapitags.h</span></span>
  
> <span data-ttu-id="257c8-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="257c8-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="257c8-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="257c8-129">See also</span></span>



[<span data-ttu-id="257c8-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="257c8-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="257c8-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="257c8-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="257c8-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="257c8-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="257c8-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="257c8-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

