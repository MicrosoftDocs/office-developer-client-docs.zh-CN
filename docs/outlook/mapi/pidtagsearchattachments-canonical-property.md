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
ms.openlocfilehash: 95729474db29fe21f808ec5c8f571bec4600db70
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382832"
---
# <a name="pidtagsearchattachments-canonical-property"></a><span data-ttu-id="d6ef6-103">PidTagSearchAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6ef6-103">PidTagSearchAttachments Canonical Property</span></span>

  
  
<span data-ttu-id="d6ef6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6ef6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d6ef6-105">包含在存储区上的附件内容所查询的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="d6ef6-105">Contains a Unicode string that is being queried in attachment contents on the store.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="d6ef6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d6ef6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d6ef6-107">PR_SEARCH_ATTACHMENTS_W</span><span class="sxs-lookup"><span data-stu-id="d6ef6-107">PR_SEARCH_ATTACHMENTS_W</span></span>  <br/> |
|<span data-ttu-id="d6ef6-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d6ef6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d6ef6-109">0x0EA5</span><span class="sxs-lookup"><span data-stu-id="d6ef6-109">0x0EA5</span></span>  <br/> |
|<span data-ttu-id="d6ef6-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="d6ef6-110">Property type:</span></span>  <br/> |<span data-ttu-id="d6ef6-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d6ef6-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="d6ef6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d6ef6-112">Area:</span></span>  <br/> |<span data-ttu-id="d6ef6-113">搜索</span><span class="sxs-lookup"><span data-stu-id="d6ef6-113">Search</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="d6ef6-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="d6ef6-114">Related resources</span></span>

> [!NOTE]
> <span data-ttu-id="d6ef6-115">未可能在您当前拥有的可下载的头文件中定义您所搜索附件内容时使用此 MAPI 限制标记。</span><span class="sxs-lookup"><span data-stu-id="d6ef6-115">This MAPI restriction tag, used when you are searching for attachment contents, might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="d6ef6-116">您可以将其添加到您的代码通过使用以下值： >`#define PR_SEARCH_ATTACHMENTS_W PROP_TAG(PT_UNICODE, 0x0EA5)`</span><span class="sxs-lookup"><span data-stu-id="d6ef6-116">You can add it to your code by using the following value: >  `#define PR_SEARCH_ATTACHMENTS_W PROP_TAG(PT_UNICODE, 0x0EA5)`</span></span>
  
### <a name="protocol-specifications"></a><span data-ttu-id="d6ef6-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="d6ef6-117">Protocol specifications</span></span>

<span data-ttu-id="d6ef6-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d6ef6-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d6ef6-119">提供了相关的 Microsoft Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="d6ef6-119">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d6ef6-120">[[MS OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d6ef6-120">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d6ef6-121">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="d6ef6-121">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d6ef6-122">头文件</span><span class="sxs-lookup"><span data-stu-id="d6ef6-122">Header files</span></span>

<span data-ttu-id="d6ef6-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d6ef6-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="d6ef6-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d6ef6-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="d6ef6-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d6ef6-125">Mapitags.h</span></span>
  
> <span data-ttu-id="d6ef6-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d6ef6-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d6ef6-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6ef6-127">See also</span></span>



[<span data-ttu-id="d6ef6-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d6ef6-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d6ef6-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6ef6-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d6ef6-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d6ef6-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d6ef6-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d6ef6-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

