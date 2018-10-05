---
title: PidTagInternetReferences 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInternetReferences
api_type:
- HeaderDef
ms.assetid: 645fe61d-414a-455e-b034-db3cfd003b9d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 431a212b6e024d695fe2de084080996d8b1054d6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395698"
---
# <a name="pidtaginternetreferences-canonical-property"></a><span data-ttu-id="12b17-103">PidTagInternetReferences 规范属性</span><span class="sxs-lookup"><span data-stu-id="12b17-103">PidTagInternetReferences Canonical Property</span></span>

  
  
<span data-ttu-id="12b17-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12b17-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12b17-105">包含多用途 Internet 邮件扩展 (MIME) 消息的引用标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="12b17-105">Contains the value of a Multipurpose Internet Mail Extensions (MIME) message's References header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="12b17-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="12b17-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="12b17-107">PR_INTERNET_REFERENCES，PR_INTERNET_REFERENCES_A，PR_INTERNET_REFERENCES_W</span><span class="sxs-lookup"><span data-stu-id="12b17-107">PR_INTERNET_REFERENCES, PR_INTERNET_REFERENCES_A, PR_INTERNET_REFERENCES_W</span></span>  <br/> |
|<span data-ttu-id="12b17-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="12b17-108">Identifier:</span></span>  <br/> |<span data-ttu-id="12b17-109">0x1039</span><span class="sxs-lookup"><span data-stu-id="12b17-109">0x1039</span></span>  <br/> |
|<span data-ttu-id="12b17-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="12b17-110">Data type:</span></span>  <br/> |<span data-ttu-id="12b17-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="12b17-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="12b17-112">区域：</span><span class="sxs-lookup"><span data-stu-id="12b17-112">Area:</span></span>  <br/> |<span data-ttu-id="12b17-113">MIME</span><span class="sxs-lookup"><span data-stu-id="12b17-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="12b17-114">说明</span><span class="sxs-lookup"><span data-stu-id="12b17-114">Remarks</span></span>

<span data-ttu-id="12b17-115">若要生成一个引用标头字段，客户端必须将这些属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="12b17-115">To generate a References header field, clients must set these properties to the desired value.</span></span> <span data-ttu-id="12b17-116">MIME 作者必须将这些属性的值复制到引用标头字段。</span><span class="sxs-lookup"><span data-stu-id="12b17-116">MIME writers must copy the value of these properties to the References header field.</span></span>
  
<span data-ttu-id="12b17-117">若要设置这些属性的值，MIME 客户端必须所需的值都写入到一个引用标头字段中。</span><span class="sxs-lookup"><span data-stu-id="12b17-117">To set the value of these properties, MIME clients must write the desired value to a References header field.</span></span> <span data-ttu-id="12b17-118">MIME 读者必须将引用标头字段的值复制到这些属性。</span><span class="sxs-lookup"><span data-stu-id="12b17-118">MIME readers must copy the value of the References header field to these properties.</span></span> <span data-ttu-id="12b17-119">MIME 读者可能会截断这些属性的值，如果它的长度超过 64 KB。</span><span class="sxs-lookup"><span data-stu-id="12b17-119">MIME readers may truncate the value of these properties if it exceeds 64KB in length.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="12b17-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="12b17-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="12b17-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="12b17-121">Protocol specifications</span></span>

<span data-ttu-id="12b17-122">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12b17-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12b17-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="12b17-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="12b17-124">[[MS OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12b17-124">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12b17-125">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="12b17-125">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="12b17-126">头文件</span><span class="sxs-lookup"><span data-stu-id="12b17-126">Header files</span></span>

<span data-ttu-id="12b17-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="12b17-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="12b17-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="12b17-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="12b17-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="12b17-129">Mapitags.h</span></span>
  
> <span data-ttu-id="12b17-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="12b17-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="12b17-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12b17-131">See also</span></span>



[<span data-ttu-id="12b17-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="12b17-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="12b17-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="12b17-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="12b17-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="12b17-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="12b17-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="12b17-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

