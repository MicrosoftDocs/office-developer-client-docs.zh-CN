---
title: PidTagSearchAttachments 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 534c3881-e12f-f228-7760-788fe2b72ae8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 80d1fc3f711369471eb2c1473700f13a6b995594
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578505"
---
# <a name="pidtagsearchattachments-canonical-property"></a><span data-ttu-id="433a4-103">PidTagSearchAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="433a4-103">PidTagSearchAttachments Canonical Property</span></span>

  
  
<span data-ttu-id="433a4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="433a4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="433a4-105">包含在存储区上的附件内容所查询的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="433a4-105">Contains a Unicode string that is being queried in attachment contents on the store.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="433a4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="433a4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="433a4-107">PR_SEARCH_ATTACHMENTS_W</span><span class="sxs-lookup"><span data-stu-id="433a4-107">PR_SEARCH_ATTACHMENTS_W</span></span>  <br/> |
|<span data-ttu-id="433a4-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="433a4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="433a4-109">0x0EA5</span><span class="sxs-lookup"><span data-stu-id="433a4-109">0x0EA5</span></span>  <br/> |
|<span data-ttu-id="433a4-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="433a4-110">Property type:</span></span>  <br/> |<span data-ttu-id="433a4-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="433a4-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="433a4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="433a4-112">Area:</span></span>  <br/> |<span data-ttu-id="433a4-113">搜索</span><span class="sxs-lookup"><span data-stu-id="433a4-113">Search</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="433a4-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="433a4-114">Related resources</span></span>

> [!NOTE]
> <span data-ttu-id="433a4-115">未可能在您当前拥有的可下载的头文件中定义您所搜索附件内容时使用此 MAPI 限制标记。</span><span class="sxs-lookup"><span data-stu-id="433a4-115">This MAPI restriction tag, used when you are searching for attachment contents, might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="433a4-116">您可以将其添加到您的代码通过使用以下值： >`#define PR_SEARCH_ATTACHMENTS_W PROP_TAG(PT_UNICODE, 0x0EA5)`</span><span class="sxs-lookup"><span data-stu-id="433a4-116">You can add it to your code by using the following value: >  `#define PR_SEARCH_ATTACHMENTS_W PROP_TAG(PT_UNICODE, 0x0EA5)`</span></span>
  
### <a name="protocol-specifications"></a><span data-ttu-id="433a4-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="433a4-117">Protocol specifications</span></span>

<span data-ttu-id="433a4-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="433a4-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="433a4-119">提供了相关的 Microsoft Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="433a4-119">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="433a4-120">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="433a4-120">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="433a4-121">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="433a4-121">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="433a4-122">头文件</span><span class="sxs-lookup"><span data-stu-id="433a4-122">Header files</span></span>

<span data-ttu-id="433a4-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="433a4-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="433a4-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="433a4-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="433a4-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="433a4-125">Mapitags.h</span></span>
  
> <span data-ttu-id="433a4-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="433a4-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="433a4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="433a4-127">See also</span></span>



[<span data-ttu-id="433a4-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="433a4-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="433a4-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="433a4-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="433a4-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="433a4-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="433a4-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="433a4-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

