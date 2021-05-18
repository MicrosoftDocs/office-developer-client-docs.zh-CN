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
ms.openlocfilehash: 6051d3403cede21fa4aebdb6ca561dd3efb46771
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360082"
---
# <a name="pidtagaddresstype-canonical-property"></a><span data-ttu-id="a0f1c-103">PidTagAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="a0f1c-103">PidTagAddressType Canonical Property</span></span>

<span data-ttu-id="a0f1c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a0f1c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a0f1c-105">包含邮件用户的电子邮件地址类型，如 SMTP。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-105">Contains the messaging user's email address type, such as SMTP.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a0f1c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a0f1c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a0f1c-107">PR_ADDRTYPE、PR_ADDRTYPE_A、PR_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="a0f1c-107">PR_ADDRTYPE, PR_ADDRTYPE_A, PR_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="a0f1c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a0f1c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a0f1c-109">0x3002</span><span class="sxs-lookup"><span data-stu-id="a0f1c-109">0x3002</span></span>  <br/> |
|<span data-ttu-id="a0f1c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a0f1c-110">Data type:</span></span>  <br/> |<span data-ttu-id="a0f1c-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="a0f1c-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="a0f1c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a0f1c-112">Area:</span></span>  <br/> |<span data-ttu-id="a0f1c-113">地址</span><span class="sxs-lookup"><span data-stu-id="a0f1c-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a0f1c-114">备注</span><span class="sxs-lookup"><span data-stu-id="a0f1c-114">Remarks</span></span>

<span data-ttu-id="a0f1c-115">这些属性是通用于所有邮件用户的基本地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-115">These properties are examples of the base address properties common to all messaging users.</span></span> <span data-ttu-id="a0f1c-116">它指定 MAPI 用于处理给定邮件的邮件系统。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-116">It specifies which messaging system MAPI uses to handle a given message.</span></span>
  
<span data-ttu-id="a0f1c-117">此属性还确定[PidTagEmailAddress](pidtagemailaddress-canonical-property.md) PR_EMAIL_ADRESS (地址字符串) 。 </span><span class="sxs-lookup"><span data-stu-id="a0f1c-117">This property also determines the format of the address string in the **PR_EMAIL_ADRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)).</span></span> <span data-ttu-id="a0f1c-118">它提供的字符串只能包含 A 到 Z 的大写字母字符以及从 0 到 9 的数字。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-118">The string it provides can contain only the uppercase alphabetic characters from A through Z and the numbers from 0 through 9.</span></span>
  
<span data-ttu-id="a0f1c-119">字符串的有效示例包括：</span><span class="sxs-lookup"><span data-stu-id="a0f1c-119">Valid examples for the string include:</span></span> 
  
```cpp
FAX
MHS
PROFS
SMTP
X400

```

## <a name="related-resources"></a><span data-ttu-id="a0f1c-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="a0f1c-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a0f1c-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="a0f1c-121">Protocol specifications</span></span>

<span data-ttu-id="a0f1c-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-123">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a0f1c-124">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-124">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-125">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-125">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="a0f1c-126">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-126">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-127">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-127">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="a0f1c-128">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-128">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-129">处理客户端与 NSPI 服务器的名称服务提供程序 (的通信) 。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-129">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
<span data-ttu-id="a0f1c-130">[[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-130">[[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-131">定义远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-131">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="a0f1c-132">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-132">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-133">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-133">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="a0f1c-134">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-134">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-135">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-135">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="a0f1c-136">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-136">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-137">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-137">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="a0f1c-138">[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-138">[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-139">指定核心邮件存储对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-139">Specifies permissible operations for the core message store objects.</span></span>
    
<span data-ttu-id="a0f1c-140">[[MS-OXOABKT]](https://msdn.microsoft.com/library/cd5a3e78-1eeb-4a75-88eb-e82c8c96ff31%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-140">[[MS-OXOABKT]](https://msdn.microsoft.com/library/cd5a3e78-1eeb-4a75-88eb-e82c8c96ff31%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-141">指定允许通讯簿模板使用的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-141">Specifies the properties and operations that are permissible for address book templates.</span></span>
    
<span data-ttu-id="a0f1c-142">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-142">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-143">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-143">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="a0f1c-144">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-144">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-145">在服务器上处理传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-145">Manipulates incoming email messages on a server.</span></span>
    
<span data-ttu-id="a0f1c-146">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0f1c-146">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0f1c-147">指定用于操作搜索文件夹列表配置的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-147">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a0f1c-148">头文件</span><span class="sxs-lookup"><span data-stu-id="a0f1c-148">Header files</span></span>

<span data-ttu-id="a0f1c-149">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a0f1c-149">Mapidefs.h</span></span>
  
> <span data-ttu-id="a0f1c-150">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-150">Provides data type definitions.</span></span>
    
<span data-ttu-id="a0f1c-151">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a0f1c-151">Mapitags.h</span></span>
  
> <span data-ttu-id="a0f1c-152">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a0f1c-152">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a0f1c-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0f1c-153">See also</span></span>



[<span data-ttu-id="a0f1c-154">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a0f1c-154">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a0f1c-155">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a0f1c-155">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a0f1c-156">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a0f1c-156">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a0f1c-157">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a0f1c-157">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
  
[<span data-ttu-id="a0f1c-158">MAPI 地址类型</span><span class="sxs-lookup"><span data-stu-id="a0f1c-158">MAPI Address Types</span></span>](mapi-address-types.md)

