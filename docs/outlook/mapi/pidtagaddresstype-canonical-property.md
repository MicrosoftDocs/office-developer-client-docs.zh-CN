---
title: PidTagAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAddressType
api_type:
- HeaderDef
ms.assetid: 986719d2-8837-46b4-8d04-c24508f5e19a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5398519dc841aa72f2c2655aac6c9f7acba7f335
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777315"
---
# <a name="pidtagaddresstype-canonical-property"></a><span data-ttu-id="2a37e-103">PidTagAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a37e-103">PidTagAddressType Canonical Property</span></span>

<span data-ttu-id="2a37e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2a37e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2a37e-105">包含消息的用户的电子邮件地址类型，如 SMTP。</span><span class="sxs-lookup"><span data-stu-id="2a37e-105">Contains the messaging user's email address type, such as SMTP.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2a37e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2a37e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2a37e-107">PR_ADDRTYPE，PR_ADDRTYPE_A，PR_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="2a37e-107">PR_ADDRTYPE, PR_ADDRTYPE_A, PR_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="2a37e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="2a37e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2a37e-109">0x3002</span><span class="sxs-lookup"><span data-stu-id="2a37e-109">0x3002</span></span>  <br/> |
|<span data-ttu-id="2a37e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2a37e-110">Data type:</span></span>  <br/> |<span data-ttu-id="2a37e-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="2a37e-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="2a37e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2a37e-112">Area:</span></span>  <br/> |<span data-ttu-id="2a37e-113">Address</span><span class="sxs-lookup"><span data-stu-id="2a37e-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2a37e-114">说明</span><span class="sxs-lookup"><span data-stu-id="2a37e-114">Remarks</span></span>

<span data-ttu-id="2a37e-115">这些属性是常见的基址属性的所有邮件用户的示例。</span><span class="sxs-lookup"><span data-stu-id="2a37e-115">These properties are examples of the base address properties common to all messaging users.</span></span> <span data-ttu-id="2a37e-116">指定 MAPI 使用处理给定的邮件的邮件系统。</span><span class="sxs-lookup"><span data-stu-id="2a37e-116">It specifies which messaging system MAPI uses to handle a given message.</span></span>
  
<span data-ttu-id="2a37e-117">此属性还决定**PR_EMAIL_ADRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 中的地址字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="2a37e-117">This property also determines the format of the address string in the **PR_EMAIL_ADRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)).</span></span> <span data-ttu-id="2a37e-118">它提供的字符串可以包含仅从 A 到 Z 为大写字母字符和从 0 到 9 的数字。</span><span class="sxs-lookup"><span data-stu-id="2a37e-118">The string it provides can contain only the uppercase alphabetic characters from A through Z and the numbers from 0 through 9.</span></span>
  
<span data-ttu-id="2a37e-119">有效的字符串的示例包括：</span><span class="sxs-lookup"><span data-stu-id="2a37e-119">Valid examples for the string include:</span></span> 
  
```cpp
FAX
MHS
PROFS
SMTP
X400

```

## <a name="related-resources"></a><span data-ttu-id="2a37e-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="2a37e-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2a37e-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="2a37e-121">Protocol specifications</span></span>

<span data-ttu-id="2a37e-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="2a37e-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2a37e-124">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-124">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-125">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="2a37e-125">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="2a37e-126">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-126">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-127">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="2a37e-127">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="2a37e-128">[[MS NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-128">[[MS-NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-129">处理与名称服务提供程序界面 (NSPI) 服务器的客户端的通信。</span><span class="sxs-lookup"><span data-stu-id="2a37e-129">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
<span data-ttu-id="2a37e-130">[[MS OXCDATA]](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-130">[[MS-OXCDATA]](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-131">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="2a37e-131">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="2a37e-132">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-132">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-133">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="2a37e-133">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="2a37e-134">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-134">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-135">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="2a37e-135">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="2a37e-136">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-136">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-137">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="2a37e-137">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="2a37e-138">[[MS OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-138">[[MS-OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-139">指定允许的操作的核心消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="2a37e-139">Specifies permissible operations for the core message store objects.</span></span>
    
<span data-ttu-id="2a37e-140">[[MS OXOABKT]](http://msdn.microsoft.com/library/cd5a3e78-1eeb-4a75-88eb-e82c8c96ff31%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-140">[[MS-OXOABKT]](http://msdn.microsoft.com/library/cd5a3e78-1eeb-4a75-88eb-e82c8c96ff31%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-141">指定的属性和操作所允许的地址簿模板。</span><span class="sxs-lookup"><span data-stu-id="2a37e-141">Specifies the properties and operations that are permissible for address book templates.</span></span>
    
<span data-ttu-id="2a37e-142">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-142">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-143">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="2a37e-143">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="2a37e-144">[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-144">[[MS-OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-145">处理传入的电子邮件服务器上。</span><span class="sxs-lookup"><span data-stu-id="2a37e-145">Manipulates incoming email messages on a server.</span></span>
    
<span data-ttu-id="2a37e-146">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a37e-146">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a37e-147">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="2a37e-147">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2a37e-148">头文件</span><span class="sxs-lookup"><span data-stu-id="2a37e-148">Header files</span></span>

<span data-ttu-id="2a37e-149">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2a37e-149">Mapidefs.h</span></span>
  
> <span data-ttu-id="2a37e-150">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2a37e-150">Provides data type definitions.</span></span>
    
<span data-ttu-id="2a37e-151">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2a37e-151">Mapitags.h</span></span>
  
> <span data-ttu-id="2a37e-152">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2a37e-152">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2a37e-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a37e-153">See also</span></span>



[<span data-ttu-id="2a37e-154">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2a37e-154">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2a37e-155">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a37e-155">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2a37e-156">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2a37e-156">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2a37e-157">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2a37e-157">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
  
[<span data-ttu-id="2a37e-158">MAPI 地址类型</span><span class="sxs-lookup"><span data-stu-id="2a37e-158">MAPI Address Types</span></span>](mapi-address-types.md)

