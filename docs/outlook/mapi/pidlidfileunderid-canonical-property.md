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
ms.openlocfilehash: 7af30866a5fd2846327223b7a58c6de91f5fef7a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355704"
---
# <a name="pidlidfileunderid-canonical-property"></a><span data-ttu-id="3cca0-103">PidLidFileUnderId 规范属性</span><span class="sxs-lookup"><span data-stu-id="3cca0-103">PidLidFileUnderId Canonical Property</span></span>

  
  
<span data-ttu-id="3cca0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3cca0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3cca0-105">指定当其他联系人姓名属性更改时如何生成和重新计算 **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3cca0-105">Specifies how to generate and recompute the value of the **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) property when other contact name properties change.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3cca0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3cca0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3cca0-107">dispidFileUnderId</span><span class="sxs-lookup"><span data-stu-id="3cca0-107">dispidFileUnderId</span></span>  <br/> |
|<span data-ttu-id="3cca0-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="3cca0-108">Property set:</span></span>  <br/> |<span data-ttu-id="3cca0-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="3cca0-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="3cca0-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="3cca0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="3cca0-111">0x00008006</span><span class="sxs-lookup"><span data-stu-id="3cca0-111">0x00008006</span></span>  <br/> |
|<span data-ttu-id="3cca0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3cca0-112">Data type:</span></span>  <br/> |<span data-ttu-id="3cca0-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="3cca0-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="3cca0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="3cca0-114">Area:</span></span>  <br/> |<span data-ttu-id="3cca0-115">联系人</span><span class="sxs-lookup"><span data-stu-id="3cca0-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3cca0-116">备注</span><span class="sxs-lookup"><span data-stu-id="3cca0-116">Remarks</span></span>

<span data-ttu-id="3cca0-117">如果此属性缺失或设置为下表或 [[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中未详细说明的值，应用程序可以选择自己的逻辑，以重新编译 **dispidFileUnder** 的值，因为其他联系人姓名属性会发生变化。</span><span class="sxs-lookup"><span data-stu-id="3cca0-117">If this property is missing or set to a value not detailed in the table below or in [[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx), the application can choose its own logic to recompute the value of the **dispidFileUnder** as other contact name properties change.</span></span> 
  
<span data-ttu-id="3cca0-118">在下表中，表示 <PropertyName> 法用于指定"PropertyName 的值"。</span><span class="sxs-lookup"><span data-stu-id="3cca0-118">In the following table, the notation <PropertyName> is used to specify "the value of PropertyName".</span></span> <span data-ttu-id="3cca0-119">例如，如果 **PR_SURNAME** ([PidTagSurname](pidtagsurname-canonical-property.md)) 属性的值为"Smith"，而 **PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md)) 属性的值为"Ben"，则" " 指定字符串 <PidTagGivenName> <PidTagSurname> "Ben Smith"。</span><span class="sxs-lookup"><span data-stu-id="3cca0-119">For example, if the value of the **PR_SURNAME** ([PidTagSurname](pidtagsurname-canonical-property.md)) property is "Smith", and the value of the **PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md)) property is "Ben", then "<PidTagGivenName> <PidTagSurname>" specifies the string "Ben Smith".</span></span> <span data-ttu-id="3cca0-120">在表中，"\r"指定回车符，"\n"指定换行符，并 <space> 代表空格字符。</span><span class="sxs-lookup"><span data-stu-id="3cca0-120">In the table, "\r" specifies a carriage return character, "\n" specifies a line-feed character, and <space> represents a space character.</span></span>
  
|<span data-ttu-id="3cca0-121">\*\*\*\*dispidFileUnderId 属性的值\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3cca0-121">**Value of the **dispidFileUnderId** property**</span></span>|<span data-ttu-id="3cca0-122">\*\*\*\*dispidFileUnder 属性\*\* 的说明\*\*</span><span class="sxs-lookup"><span data-stu-id="3cca0-122">**Description of the **dispidFileUnder** property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3cca0-123">0x00000000</span><span class="sxs-lookup"><span data-stu-id="3cca0-123">0x00000000</span></span>  <br/> |<span data-ttu-id="3cca0-124">空PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="3cca0-124">Empty PT_UNICODE.</span></span>  <br/> |
|<span data-ttu-id="3cca0-125">0x00003001</span><span class="sxs-lookup"><span data-stu-id="3cca0-125">0x00003001</span></span>  <br/> |<span data-ttu-id="3cca0-126">" \< PidTagDisplayName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-126">"\<PidTagDisplayName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-127">0x00003A06</span><span class="sxs-lookup"><span data-stu-id="3cca0-127">0x00003A06</span></span>  <br/> |<span data-ttu-id="3cca0-128">" \< PidTagGivenName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-128">"\<PidTagGivenName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-129">0x00003A11</span><span class="sxs-lookup"><span data-stu-id="3cca0-129">0x00003A11</span></span>  <br/> |<span data-ttu-id="3cca0-130">" \< PidTagSurname \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-130">"\<PidTagSurname\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-131">0x00003A16</span><span class="sxs-lookup"><span data-stu-id="3cca0-131">0x00003A16</span></span>  <br/> |<span data-ttu-id="3cca0-132">" \< PidTagCompanyName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-132">"\<PidTagCompanyName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-133">0x00008017</span><span class="sxs-lookup"><span data-stu-id="3cca0-133">0x00008017</span></span>  <br/> |<span data-ttu-id="3cca0-134">" \< PidTagSurname \> ， space \< \> \< PidTagGivenName space \> \< \> \< PidTagMiddleName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-134">"\<PidTagSurname\>,\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-135">0x00008018</span><span class="sxs-lookup"><span data-stu-id="3cca0-135">0x00008018</span></span>  <br/> |<span data-ttu-id="3cca0-136">" \< PidTagCompanyName \>\r\n\< PidTagSurname \> ， space \< \> \< PidTagGivenName space \> \< \> \< PidTagMiddleName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-136">"\<PidTagCompanyName\>\r\n\<PidTagSurname\>,\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-137">0x00008019</span><span class="sxs-lookup"><span data-stu-id="3cca0-137">0x00008019</span></span>  <br/> |<span data-ttu-id="3cca0-138">" \< PidTagSurname \> ， space \< \> \< PidTagGivenName space \> \< \> \< PidTagMiddleName\r\n\> \< PidTagCompanyName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-138">"\<PidTagSurname\>,\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-139">0x00008030</span><span class="sxs-lookup"><span data-stu-id="3cca0-139">0x00008030</span></span>  <br/> |<span data-ttu-id="3cca0-140">" \< PidTagSurname \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-140">"\<PidTagSurname\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-141">0x00008031</span><span class="sxs-lookup"><span data-stu-id="3cca0-141">0x00008031</span></span>  <br/> |<span data-ttu-id="3cca0-142">" \< PidTagSurname \> \< space \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-142">"\<PidTagSurname\>\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-143">0x00008032</span><span class="sxs-lookup"><span data-stu-id="3cca0-143">0x00008032</span></span>  <br/> |<span data-ttu-id="3cca0-144">" \< PidTagCompanyName \>\r\n\< \> \< PidTagSurname PidTagGivenName \> \< space \> \< PidTagMiddleName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-144">"\<PidTagCompanyName\>\r\n\<PidTagSurname\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-145">0x00008033</span><span class="sxs-lookup"><span data-stu-id="3cca0-145">0x00008033</span></span>  <br/> |<span data-ttu-id="3cca0-146">" \< PidTagCompanyName \>\r\n\< \> \< PidTagSurname space \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-146">"\<PidTagCompanyName\>\r\n\<PidTagSurname\>\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-147">0x00008034</span><span class="sxs-lookup"><span data-stu-id="3cca0-147">0x00008034</span></span>  <br/> |<span data-ttu-id="3cca0-148">" \< PidTagSurname \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \>\r\n\< PidTagCompanyName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-148">"\<PidTagSurname\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-149">0x00008035</span><span class="sxs-lookup"><span data-stu-id="3cca0-149">0x00008035</span></span>  <br/> |<span data-ttu-id="3cca0-150">" \< PidTagSurname \> \< space \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName\r\n\> \< PidTagCompanyName \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-150">"\<PidTagSurname\>\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-151">0x00008036</span><span class="sxs-lookup"><span data-stu-id="3cca0-151">0x00008036</span></span>  <br/> |<span data-ttu-id="3cca0-152">" \< PidTagSurname \> \< space \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName space \> \< \> \< PidTagGeneration \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-152">"\<PidTagSurname\>\<space\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\<space\>\<PidTagGeneration\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-153">0x00008037</span><span class="sxs-lookup"><span data-stu-id="3cca0-153">0x00008037</span></span>  <br/> |<span data-ttu-id="3cca0-154">" \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> \< space \> \< PidTagSurname space \> \< \> \< PidTagGeneration \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-154">"\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\<space\>\<PidTagSurname\>\<space\>\<PidTagGeneration\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-155">0x00008038</span><span class="sxs-lookup"><span data-stu-id="3cca0-155">0x00008038</span></span>  <br/> |<span data-ttu-id="3cca0-156">" \< PidTagSurname \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> \< space \> \< PidTagGeneration \> "</span><span class="sxs-lookup"><span data-stu-id="3cca0-156">"\<PidTagSurname\>\<PidTagGivenName\>\<space\>\<PidTagMiddleName\>\<space\>\<PidTagGeneration\>"</span></span>  <br/> |
|<span data-ttu-id="3cca0-157">0xfffffffd</span><span class="sxs-lookup"><span data-stu-id="3cca0-157">0xfffffffd</span></span>  <br/> |<span data-ttu-id="3cca0-158">指定在显示联系人时，应用程序应尝试使用 **dispidFileUnder** 的当前值和其他联系人属性查找 **dispidFileUnderId** 与此表中之前值之一的"最佳匹配"。</span><span class="sxs-lookup"><span data-stu-id="3cca0-158">Specifies that, when displaying the contact, the application should attempt to use the current value of **dispidFileUnder** and other contact properties to find a "best match" for **dispidFileUnderId** to one of the previous values in this table.</span></span>  <br/> |
|<span data-ttu-id="3cca0-159">0xfffffffe</span><span class="sxs-lookup"><span data-stu-id="3cca0-159">0xfffffffe</span></span>  <br/> |<span data-ttu-id="3cca0-160">指定在显示联系人时，应用程序应该根据 **dispidFileUnderId** 的语言区域设置 (选择适当的默认值) ，并更新 **dispidFileUnder** 以匹配该选择。</span><span class="sxs-lookup"><span data-stu-id="3cca0-160">Specifies that, when displaying the contact, the application should choose the appropriate default values (according to the language locale) for **dispidFileUnderId** and update **dispidFileUnder** to match the choice.</span></span>  <br/> |
|<span data-ttu-id="3cca0-161">0xffffffff</span><span class="sxs-lookup"><span data-stu-id="3cca0-161">0xffffffff</span></span>  <br/> |<span data-ttu-id="3cca0-162">**dispidFileUnder** 是用户提供的PT_UNICODE，不应在更改其他联系人姓名属性时进行更改。</span><span class="sxs-lookup"><span data-stu-id="3cca0-162">**dispidFileUnder** is a user-provided PT_UNICODE, and should not be changed when another contact name property changes.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="3cca0-163">相关资源</span><span class="sxs-lookup"><span data-stu-id="3cca0-163">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3cca0-164">协议规范</span><span class="sxs-lookup"><span data-stu-id="3cca0-164">Protocol specifications</span></span>

<span data-ttu-id="3cca0-165">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3cca0-165">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3cca0-166">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="3cca0-166">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3cca0-167">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3cca0-167">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3cca0-168">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="3cca0-168">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3cca0-169">头文件</span><span class="sxs-lookup"><span data-stu-id="3cca0-169">Header files</span></span>

<span data-ttu-id="3cca0-170">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3cca0-170">Mapidefs.h</span></span>
  
> <span data-ttu-id="3cca0-171">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3cca0-171">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3cca0-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cca0-172">See also</span></span>



[<span data-ttu-id="3cca0-173">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3cca0-173">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3cca0-174">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3cca0-174">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3cca0-175">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3cca0-175">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3cca0-176">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3cca0-176">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

