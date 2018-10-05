---
title: PidTagLanguage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLanguage
api_type:
- HeaderDef
ms.assetid: 74b7bdd0-89d1-4013-a6f1-8ea102974f19
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 820c00d9b375734343af8226fdbd1dca3b8a506e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401158"
---
# <a name="pidtaglanguage-canonical-property"></a><span data-ttu-id="0b905-103">PidTagLanguage 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b905-103">PidTagLanguage Canonical Property</span></span>

  
  
<span data-ttu-id="0b905-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0b905-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0b905-105">包含一个值，指示邮件的用户在其中写入消息的语言。</span><span class="sxs-lookup"><span data-stu-id="0b905-105">Contains a value that indicates the language in which the messaging user is writing messages.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0b905-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0b905-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0b905-107">PR_LANGUAGE，PR_LANGUAGE_A，PR_LANGUAGE_W</span><span class="sxs-lookup"><span data-stu-id="0b905-107">PR_LANGUAGE, PR_LANGUAGE_A, PR_LANGUAGE_W</span></span>  <br/> |
|<span data-ttu-id="0b905-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="0b905-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0b905-109">0x3A0C</span><span class="sxs-lookup"><span data-stu-id="0b905-109">0x3A0C</span></span>  <br/> |
|<span data-ttu-id="0b905-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0b905-110">Data type:</span></span>  <br/> |<span data-ttu-id="0b905-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="0b905-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="0b905-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0b905-112">Area:</span></span>  <br/> |<span data-ttu-id="0b905-113">Address</span><span class="sxs-lookup"><span data-stu-id="0b905-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0b905-114">说明</span><span class="sxs-lookup"><span data-stu-id="0b905-114">Remarks</span></span>

<span data-ttu-id="0b905-115">该字符串包含单个双字符国家/地区代码。</span><span class="sxs-lookup"><span data-stu-id="0b905-115">The string contains a single two-character country/region code.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0b905-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="0b905-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0b905-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="0b905-117">Protocol specifications</span></span>

<span data-ttu-id="0b905-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b905-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b905-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="0b905-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0b905-120">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b905-120">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b905-121">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="0b905-121">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="0b905-122">[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b905-122">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b905-123">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="0b905-123">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0b905-124">头文件</span><span class="sxs-lookup"><span data-stu-id="0b905-124">Header files</span></span>

<span data-ttu-id="0b905-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0b905-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="0b905-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0b905-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="0b905-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0b905-127">Mapitags.h</span></span>
  
> <span data-ttu-id="0b905-128">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0b905-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0b905-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b905-129">See also</span></span>



[<span data-ttu-id="0b905-130">PidTagLanguages 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b905-130">PidTagLanguages Canonical Property</span></span>](pidtaglanguages-canonical-property.md)


[<span data-ttu-id="0b905-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0b905-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0b905-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b905-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0b905-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0b905-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0b905-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0b905-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

