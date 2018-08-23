---
title: PidLidFileUnderId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFileUnderId
api_type:
- COM
ms.assetid: 917431a9-fd90-4b4d-b042-886e3dbf47c0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0a4fdb94877fb9491005fc650c206ffefd3f8b94
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578414"
---
# <a name="pidlidfileunderid-canonical-property"></a><span data-ttu-id="70b7b-103">PidLidFileUnderId 规范属性</span><span class="sxs-lookup"><span data-stu-id="70b7b-103">PidLidFileUnderId Canonical Property</span></span>

  
  
<span data-ttu-id="70b7b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70b7b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70b7b-105">指定如何生成和其他联系人命名属性更改时，重新计算**dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="70b7b-105">Specifies how to generate and recompute the value of the **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) property when other contact name properties change.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="70b7b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="70b7b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="70b7b-107">dispidFileUnderId</span><span class="sxs-lookup"><span data-stu-id="70b7b-107">dispidFileUnderId</span></span>  <br/> |
|<span data-ttu-id="70b7b-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="70b7b-108">Property set:</span></span>  <br/> |<span data-ttu-id="70b7b-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="70b7b-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="70b7b-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="70b7b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="70b7b-111">0x00008006</span><span class="sxs-lookup"><span data-stu-id="70b7b-111">0x00008006</span></span>  <br/> |
|<span data-ttu-id="70b7b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="70b7b-112">Data type:</span></span>  <br/> |<span data-ttu-id="70b7b-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="70b7b-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="70b7b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="70b7b-114">Area:</span></span>  <br/> |<span data-ttu-id="70b7b-115">联系人</span><span class="sxs-lookup"><span data-stu-id="70b7b-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="70b7b-116">注解</span><span class="sxs-lookup"><span data-stu-id="70b7b-116">Remarks</span></span>

<span data-ttu-id="70b7b-117">如果此属性缺失或设置为不具体的下表中或在[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)的值，该应用程序可以选择自己的逻辑重新计算的其他联系人姓名属性更改为**dispidFileUnder**值。</span><span class="sxs-lookup"><span data-stu-id="70b7b-117">If this property is missing or set to a value not detailed in the table below or in [[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx), the application can choose its own logic to recompute the value of the **dispidFileUnder** as other contact name properties change.</span></span> 
  
<span data-ttu-id="70b7b-118">在下面的表中，表示法<PropertyName>用于指定"的值的属性名称"。</span><span class="sxs-lookup"><span data-stu-id="70b7b-118">In the following table, the notation <PropertyName> is used to specify "the value of PropertyName".</span></span> <span data-ttu-id="70b7b-119">例如，如果**PR_SURNAME** ([PidTagSurname](pidtagsurname-canonical-property.md)) 属性的值是"Smith"，并且**PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md)) 属性的值为"Ben"，然后"<PidTagGivenName> <PidTagSurname>"指定"Ben Smith"的字符串。</span><span class="sxs-lookup"><span data-stu-id="70b7b-119">For example, if the value of the **PR_SURNAME** ([PidTagSurname](pidtagsurname-canonical-property.md)) property is "Smith", and the value of the **PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md)) property is "Ben", then "<PidTagGivenName> <PidTagSurname>" specifies the string "Ben Smith".</span></span> <span data-ttu-id="70b7b-120">在表中，"\r"指定回车符，"\n"指定换行字符，并且<space>表示空格字符。</span><span class="sxs-lookup"><span data-stu-id="70b7b-120">In the table, "\r" specifies a carriage return character, "\n" specifies a line-feed character, and <space> represents a space character.</span></span>
  
|<span data-ttu-id="70b7b-121">****DispidFileUnderId**属性的值**</span><span class="sxs-lookup"><span data-stu-id="70b7b-121">**Value of the **dispidFileUnderId** property**</span></span>|<span data-ttu-id="70b7b-122">****DispidFileUnder**属性的说明**</span><span class="sxs-lookup"><span data-stu-id="70b7b-122">**Description of the **dispidFileUnder** property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70b7b-123">0x00000000</span><span class="sxs-lookup"><span data-stu-id="70b7b-123">0x00000000</span></span>  <br/> |<span data-ttu-id="70b7b-124">空 PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="70b7b-124">Empty PT_UNICODE.</span></span>  <br/> |
|<span data-ttu-id="70b7b-125">0x00003001</span><span class="sxs-lookup"><span data-stu-id="70b7b-125">0x00003001</span></span>  <br/> |<span data-ttu-id="70b7b-126">"\<PidTagDisplayName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-126">"\<PidTagDisplayName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-127">0x00003A06</span><span class="sxs-lookup"><span data-stu-id="70b7b-127">0x00003A06</span></span>  <br/> |<span data-ttu-id="70b7b-128">"\<PidTagGivenName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-128">"\<PidTagGivenName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-129">0x00003A11</span><span class="sxs-lookup"><span data-stu-id="70b7b-129">0x00003A11</span></span>  <br/> |<span data-ttu-id="70b7b-130">"\<PidTagSurname\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-130">"\<PidTagSurname\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-131">0x00003A16</span><span class="sxs-lookup"><span data-stu-id="70b7b-131">0x00003A16</span></span>  <br/> |<span data-ttu-id="70b7b-132">"\<PidTagCompanyName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-132">"\<PidTagCompanyName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-133">0x00008017</span><span class="sxs-lookup"><span data-stu-id="70b7b-133">0x00008017</span></span>  <br/> |<span data-ttu-id="70b7b-134">"\<PidTagSurname\>，\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-134">"\<PidTagSurname\>,\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-135">0x00008018</span><span class="sxs-lookup"><span data-stu-id="70b7b-135">0x00008018</span></span>  <br/> |<span data-ttu-id="70b7b-136">"\<PidTagCompanyName\>\r\n\<PidTagSurname\>，\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-136">"\<PidTagCompanyName\>\r\n\<PidTagSurname\>,\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-137">0x00008019</span><span class="sxs-lookup"><span data-stu-id="70b7b-137">0x00008019</span></span>  <br/> |<span data-ttu-id="70b7b-138">"\<PidTagSurname\>，\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-138">"\<PidTagSurname\>,\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-139">0x00008030</span><span class="sxs-lookup"><span data-stu-id="70b7b-139">0x00008030</span></span>  <br/> |<span data-ttu-id="70b7b-140">"\<PidTagSurname\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-140">"\<PidTagSurname\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-141">0x00008031</span><span class="sxs-lookup"><span data-stu-id="70b7b-141">0x00008031</span></span>  <br/> |<span data-ttu-id="70b7b-142">"\<PidTagSurname\>\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-142">"\<PidTagSurname\>\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-143">0x00008032</span><span class="sxs-lookup"><span data-stu-id="70b7b-143">0x00008032</span></span>  <br/> |<span data-ttu-id="70b7b-144">"\<PidTagCompanyName\>\r\n\<PidTagSurname\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-144">"\<PidTagCompanyName\>\r\n\<PidTagSurname\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-145">0x00008033</span><span class="sxs-lookup"><span data-stu-id="70b7b-145">0x00008033</span></span>  <br/> |<span data-ttu-id="70b7b-146">"\<PidTagCompanyName\>\r\n\<PidTagSurname\>\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-146">"\<PidTagCompanyName\>\r\n\<PidTagSurname\>\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-147">0x00008034</span><span class="sxs-lookup"><span data-stu-id="70b7b-147">0x00008034</span></span>  <br/> |<span data-ttu-id="70b7b-148">"\<PidTagSurname\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-148">"\<PidTagSurname\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-149">0x00008035</span><span class="sxs-lookup"><span data-stu-id="70b7b-149">0x00008035</span></span>  <br/> |<span data-ttu-id="70b7b-150">"\<PidTagSurname\>\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-150">"\<PidTagSurname\>\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-151">0x00008036</span><span class="sxs-lookup"><span data-stu-id="70b7b-151">0x00008036</span></span>  <br/> |<span data-ttu-id="70b7b-152">"\<PidTagSurname\>\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\<空间\>\<PidTagGeneration\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-152">"\<PidTagSurname\>\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\<space\>\<PidTagGeneration\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-153">0x00008037</span><span class="sxs-lookup"><span data-stu-id="70b7b-153">0x00008037</span></span>  <br/> |<span data-ttu-id="70b7b-154">"\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\<空间\>\<PidTagSurname\>\<空间\>\<PidTagGeneration\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-154">"\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\<space\>\<PidTagSurname\>\<space\>\<PidTagGeneration\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-155">0x00008038</span><span class="sxs-lookup"><span data-stu-id="70b7b-155">0x00008038</span></span>  <br/> |<span data-ttu-id="70b7b-156">"\<PidTagSurname\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\<空间\>\<PidTagGeneration\>"</span><span class="sxs-lookup"><span data-stu-id="70b7b-156">"\<PidTagSurname\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\<space\>\<PidTagGeneration\>"</span></span>  <br/> |
|<span data-ttu-id="70b7b-157">0xfffffffd</span><span class="sxs-lookup"><span data-stu-id="70b7b-157">0xfffffffd</span></span>  <br/> |<span data-ttu-id="70b7b-158">指定，显示该联系人时, 应用程序应尝试使用**dispidFileUnder**和其他联系人属性的当前值的"最佳匹配"查找**dispidFileUnderId**此表中，以前的值之一。</span><span class="sxs-lookup"><span data-stu-id="70b7b-158">Specifies that, when displaying the contact, the application should attempt to use the current value of **dispidFileUnder** and other contact properties to find a "best match" for **dispidFileUnderId** to one of the previous values in this table.</span></span>  <br/> |
|<span data-ttu-id="70b7b-159">0xfffffffe</span><span class="sxs-lookup"><span data-stu-id="70b7b-159">0xfffffffe</span></span>  <br/> |<span data-ttu-id="70b7b-160">指定时显示该联系人，应用程序应为**dispidFileUnderId**选择适当的默认值 （根据语言区域设置） 并更新**dispidFileUnder**匹配选项。</span><span class="sxs-lookup"><span data-stu-id="70b7b-160">Specifies that, when displaying the contact, the application should choose the appropriate default values (according to the language locale) for **dispidFileUnderId** and update **dispidFileUnder** to match the choice.</span></span>  <br/> |
|<span data-ttu-id="70b7b-161">0xffffffff</span><span class="sxs-lookup"><span data-stu-id="70b7b-161">0xffffffff</span></span>  <br/> |<span data-ttu-id="70b7b-162">**dispidFileUnder**为用户提供 PT_UNICODE，并另一个联系人姓名属性更改时不应被更改。</span><span class="sxs-lookup"><span data-stu-id="70b7b-162">**dispidFileUnder** is a user-provided PT_UNICODE, and should not be changed when another contact name property changes.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="70b7b-163">相关资源</span><span class="sxs-lookup"><span data-stu-id="70b7b-163">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="70b7b-164">协议规范</span><span class="sxs-lookup"><span data-stu-id="70b7b-164">Protocol specifications</span></span>

<span data-ttu-id="70b7b-165">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="70b7b-165">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="70b7b-166">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="70b7b-166">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="70b7b-167">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="70b7b-167">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="70b7b-168">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="70b7b-168">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="70b7b-169">头文件</span><span class="sxs-lookup"><span data-stu-id="70b7b-169">Header files</span></span>

<span data-ttu-id="70b7b-170">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="70b7b-170">Mapidefs.h</span></span>
  
> <span data-ttu-id="70b7b-171">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="70b7b-171">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="70b7b-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70b7b-172">See also</span></span>



[<span data-ttu-id="70b7b-173">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="70b7b-173">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="70b7b-174">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="70b7b-174">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="70b7b-175">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="70b7b-175">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="70b7b-176">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="70b7b-176">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

