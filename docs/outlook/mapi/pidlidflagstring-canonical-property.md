---
title: PidLidFlagString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFlagString
api_type:
- COM
ms.assetid: 4cf1e08b-c869-4965-a1e4-512a0684700f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3cd88db7e93b53990cf0181af623ebca75f0c6e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357783"
---
# <a name="pidlidflagstring-canonical-property"></a><span data-ttu-id="8b619-103">PidLidFlagString 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b619-103">PidLidFlagString Canonical Property</span></span>

  
  
<span data-ttu-id="8b619-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8b619-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8b619-105">包含标识与标志关联的一组预定义的文本字符串之一的索引。</span><span class="sxs-lookup"><span data-stu-id="8b619-105">Contains an index that identifies one of a set of pre-defined text strings associated with the flag.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8b619-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8b619-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8b619-107">dispidFlagStringEnum</span><span class="sxs-lookup"><span data-stu-id="8b619-107">dispidFlagStringEnum</span></span>  <br/> |
|<span data-ttu-id="8b619-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="8b619-108">Property set:</span></span>  <br/> |<span data-ttu-id="8b619-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="8b619-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="8b619-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="8b619-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="8b619-111">0x000085C0</span><span class="sxs-lookup"><span data-stu-id="8b619-111">0x000085C0</span></span>  <br/> |
|<span data-ttu-id="8b619-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8b619-112">Data type:</span></span>  <br/> |<span data-ttu-id="8b619-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8b619-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8b619-114">区域：</span><span class="sxs-lookup"><span data-stu-id="8b619-114">Area:</span></span>  <br/> |<span data-ttu-id="8b619-115">任务</span><span class="sxs-lookup"><span data-stu-id="8b619-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8b619-116">注解</span><span class="sxs-lookup"><span data-stu-id="8b619-116">Remarks</span></span>

<span data-ttu-id="8b619-117">如果设置了此属性, 客户端应使用下表中相应的字符串值 (例如, 替换转换为当前用户语言的字符串), 并且应忽略**dispidFlagRequest**中设置的值 ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 和**dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="8b619-117">If this property is set, clients should use the corresponding string value in the tables below (for example, to substitute a string that is translated into the current user's language), and should ignore the value set in **dispidFlagRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) and **dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md)).</span></span> 
  
<span data-ttu-id="8b619-118">为联系人对象的用户建议的默认值如下所示:</span><span class="sxs-lookup"><span data-stu-id="8b619-118">Defaults suggested to the user for contact objects are as follows:</span></span>
  
|<span data-ttu-id="8b619-119">**值**</span><span class="sxs-lookup"><span data-stu-id="8b619-119">**Value**</span></span>|<span data-ttu-id="8b619-120">**英文字符串**</span><span class="sxs-lookup"><span data-stu-id="8b619-120">**English string**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b619-121">0x00000000 或不存在</span><span class="sxs-lookup"><span data-stu-id="8b619-121">0x00000000 or not present</span></span>  <br/> | <span data-ttu-id="8b619-122">按照与显示**dispidFlagRequest**相关的指导进行操作。</span><span class="sxs-lookup"><span data-stu-id="8b619-122">Follow the guidance related to displaying **dispidFlagRequest**.</span></span>  <br/> |
|<span data-ttu-id="8b619-123">0x0000006E</span><span class="sxs-lookup"><span data-stu-id="8b619-123">0x0000006E</span></span>  <br/> |<span data-ttu-id="8b619-124">"后续"</span><span class="sxs-lookup"><span data-stu-id="8b619-124">"Follow up"</span></span>  <br/> |
|<span data-ttu-id="8b619-125">0x0000006F</span><span class="sxs-lookup"><span data-stu-id="8b619-125">0x0000006F</span></span>  <br/> |<span data-ttu-id="8b619-126">对</span><span class="sxs-lookup"><span data-stu-id="8b619-126">"Call"</span></span>  <br/> |
|<span data-ttu-id="8b619-127">0x00000070</span><span class="sxs-lookup"><span data-stu-id="8b619-127">0x00000070</span></span>  <br/> |<span data-ttu-id="8b619-128">"安排会议"</span><span class="sxs-lookup"><span data-stu-id="8b619-128">"Arrange Meeting"</span></span>  <br/> |
|<span data-ttu-id="8b619-129">0x00000071</span><span class="sxs-lookup"><span data-stu-id="8b619-129">0x00000071</span></span>  <br/> |<span data-ttu-id="8b619-130">"发送电子邮件"</span><span class="sxs-lookup"><span data-stu-id="8b619-130">"Send Email"</span></span>  <br/> |
|<span data-ttu-id="8b619-131">0x00000072</span><span class="sxs-lookup"><span data-stu-id="8b619-131">0x00000072</span></span>  <br/> |<span data-ttu-id="8b619-132">"发送信件"</span><span class="sxs-lookup"><span data-stu-id="8b619-132">"Send Letter"</span></span>  <br/> |
   
<span data-ttu-id="8b619-133">为用户建议的所有其他 message 对象的默认值如下所示:</span><span class="sxs-lookup"><span data-stu-id="8b619-133">Defaults suggested to the user for all other message objects are as follows:</span></span>
  
|<span data-ttu-id="8b619-134">**值**</span><span class="sxs-lookup"><span data-stu-id="8b619-134">**Value**</span></span>|<span data-ttu-id="8b619-135">**英文字符串**</span><span class="sxs-lookup"><span data-stu-id="8b619-135">**English string**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b619-136">0x00000000 或不存在</span><span class="sxs-lookup"><span data-stu-id="8b619-136">0x00000000 or not present</span></span>  <br/> | <span data-ttu-id="8b619-137">按照与显示**dispidFlagRequest**相关的指导进行操作。</span><span class="sxs-lookup"><span data-stu-id="8b619-137">Follow the guidance related to displaying **dispidFlagRequest**.</span></span>  <br/> |
|<span data-ttu-id="8b619-138">0x00000001</span><span class="sxs-lookup"><span data-stu-id="8b619-138">0x00000001</span></span>  <br/> |<span data-ttu-id="8b619-139">对</span><span class="sxs-lookup"><span data-stu-id="8b619-139">"Call"</span></span>  <br/> |
|<span data-ttu-id="8b619-140">0x00000002</span><span class="sxs-lookup"><span data-stu-id="8b619-140">0x00000002</span></span>  <br/> |<span data-ttu-id="8b619-141">"不要转发"</span><span class="sxs-lookup"><span data-stu-id="8b619-141">"Do not Forward"</span></span>  <br/> |
|<span data-ttu-id="8b619-142">0x00000003</span><span class="sxs-lookup"><span data-stu-id="8b619-142">0x00000003</span></span>  <br/> |<span data-ttu-id="8b619-143">"后续"</span><span class="sxs-lookup"><span data-stu-id="8b619-143">"Follow up"</span></span>  <br/> |
|<span data-ttu-id="8b619-144">0x00000004</span><span class="sxs-lookup"><span data-stu-id="8b619-144">0x00000004</span></span>  <br/> |<span data-ttu-id="8b619-145">"获取信息"</span><span class="sxs-lookup"><span data-stu-id="8b619-145">"For Your Information"</span></span>  <br/> |
|<span data-ttu-id="8b619-146">0x00000005</span><span class="sxs-lookup"><span data-stu-id="8b619-146">0x00000005</span></span>  <br/> |<span data-ttu-id="8b619-147">前后</span><span class="sxs-lookup"><span data-stu-id="8b619-147">"Forward"</span></span>  <br/> |
|<span data-ttu-id="8b619-148">0x00000006</span><span class="sxs-lookup"><span data-stu-id="8b619-148">0x00000006</span></span>  <br/> |<span data-ttu-id="8b619-149">"无需响应"</span><span class="sxs-lookup"><span data-stu-id="8b619-149">"No Response Necessary"</span></span>  <br/> |
|<span data-ttu-id="8b619-150">0x00000007</span><span class="sxs-lookup"><span data-stu-id="8b619-150">0x00000007</span></span>  <br/> |<span data-ttu-id="8b619-151">自述</span><span class="sxs-lookup"><span data-stu-id="8b619-151">"Read"</span></span>  <br/> |
|<span data-ttu-id="8b619-152">0x00000008</span><span class="sxs-lookup"><span data-stu-id="8b619-152">0x00000008</span></span>  <br/> |<span data-ttu-id="8b619-153">响应</span><span class="sxs-lookup"><span data-stu-id="8b619-153">"Reply"</span></span>  <br/> |
|<span data-ttu-id="8b619-154">0x00000009</span><span class="sxs-lookup"><span data-stu-id="8b619-154">0x00000009</span></span>  <br/> |<span data-ttu-id="8b619-155">"全部答复"</span><span class="sxs-lookup"><span data-stu-id="8b619-155">"Reply to All"</span></span>  <br/> |
|<span data-ttu-id="8b619-156">0x0000000A</span><span class="sxs-lookup"><span data-stu-id="8b619-156">0x0000000A</span></span>  <br/> |<span data-ttu-id="8b619-157">概述</span><span class="sxs-lookup"><span data-stu-id="8b619-157">"Review"</span></span>  <br/> |
   
<span data-ttu-id="8b619-158">如果需要, 可以将上面指定的所有字符串转换为用户的语言。</span><span class="sxs-lookup"><span data-stu-id="8b619-158">All strings specified above can be translated to the user's language, if appropriate.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8b619-159">相关资源</span><span class="sxs-lookup"><span data-stu-id="8b619-159">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8b619-160">协议规范</span><span class="sxs-lookup"><span data-stu-id="8b619-160">Protocol specifications</span></span>

<span data-ttu-id="8b619-161">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8b619-161">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8b619-162">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="8b619-162">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8b619-163">[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8b619-163">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8b619-164">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8b619-164">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8b619-165">头文件</span><span class="sxs-lookup"><span data-stu-id="8b619-165">Header files</span></span>

<span data-ttu-id="8b619-166">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8b619-166">Mapidefs.h</span></span>
  
> <span data-ttu-id="8b619-167">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8b619-167">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8b619-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b619-168">See also</span></span>



[<span data-ttu-id="8b619-169">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8b619-169">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8b619-170">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b619-170">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8b619-171">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8b619-171">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8b619-172">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8b619-172">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

