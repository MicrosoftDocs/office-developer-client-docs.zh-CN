---
title: MAPI 属性标记
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 380dad4c-7fbf-4c49-b67c-ab612c923499
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 314d2d6987a8bc669239652b83a31b5927723c68
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22562923"
---
# <a name="mapi-property-tags"></a><span data-ttu-id="a6a96-103">MAPI 属性标记</span><span class="sxs-lookup"><span data-stu-id="a6a96-103">MAPI property tags</span></span>
  
<span data-ttu-id="a6a96-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a6a96-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a6a96-105">属性标记为包含 16 至 31 唯一属性标识符和 0 到 15 下图中所示位中的属性类型 32 位数字。</span><span class="sxs-lookup"><span data-stu-id="a6a96-105">A property tag is a 32-bit number that contains a unique property identifier in bits 16 through 31 and a property type in bits 0 through 15 as shown in the following illustration.</span></span> 
  
<span data-ttu-id="a6a96-106">**属性标记元素**</span><span class="sxs-lookup"><span data-stu-id="a6a96-106">**Property tag elements**</span></span>
  
<span data-ttu-id="a6a96-107">![属性标记元素](media/amapi_10.gif "属性标记元素")</span><span class="sxs-lookup"><span data-stu-id="a6a96-107">![Property tag elements](media/amapi_10.gif "Property tag elements")</span></span>
  
<span data-ttu-id="a6a96-108">属性标记用于确定 MAPI 属性，并且每个属性必须具有一个，无论是否通过 MAPI、 客户端或服务提供商定义属性。</span><span class="sxs-lookup"><span data-stu-id="a6a96-108">Property tags are used to identify MAPI properties and every property must have one, regardless of whether the property is defined by MAPI, a client, or a service provider.</span></span> <span data-ttu-id="a6a96-109">MAPI Mapitags.h 头文件; 中定义其属性的属性标记常量的一组这些属性被称为"MAPI 定义属性"。</span><span class="sxs-lookup"><span data-stu-id="a6a96-109">MAPI defines a set of property tag constants for its properties in the Mapitags.h header file; these properties are referred to as the "MAPI-defined properties".</span></span> 
  
<span data-ttu-id="a6a96-110">属性标记常量按照以保证一致性和易用性的命名约定。</span><span class="sxs-lookup"><span data-stu-id="a6a96-110">The property tag constants follow a naming convention for consistency and ease of use.</span></span> <span data-ttu-id="a6a96-111">有两个部分每个属性标记的名称： PR_ 前缀和一个或多个字符字符串，用于描述属性的内容。</span><span class="sxs-lookup"><span data-stu-id="a6a96-111">There are two parts to the name of each property tag: a PR_ prefix and one or more character strings that describe the contents of the property.</span></span> <span data-ttu-id="a6a96-112">使用下划线分隔多个字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="a6a96-112">Multiple character strings are separated by underscores.</span></span> <span data-ttu-id="a6a96-113">例如，邮件收件人的地址类型的属性标记为**PR\_ADDRTYPE** ([PidTagOrgAddrtype](http://msdn.microsoft.com/library/d40b5707-e4d5-4746-88d4-8616a3789789%28Office.15%29.aspx)) 并指定其接收的每个出站邮件的副本的文件夹的条目标识符是**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="a6a96-113">For example, the property tag for the address type of a message recipient is **PR\_ADDRTYPE** ([PidTagOrgAddrtype](http://msdn.microsoft.com/library/d40b5707-e4d5-4746-88d4-8616a3789789%28Office.15%29.aspx)) and the entry identifier for the folder designated to receive a copy of every outbound message is **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)).</span></span>
  
<span data-ttu-id="a6a96-114">几宏可供帮助[PROP_TYPE](prop_type.md)、 [PROP_ID](prop_id.md)和[PROP_TAG](prop_tag.md)处理属性标记，它们之间。</span><span class="sxs-lookup"><span data-stu-id="a6a96-114">A few macros are available to help work with property tags, among them [PROP_TYPE](prop_type.md), [PROP_ID](prop_id.md), and [PROP_TAG](prop_tag.md).</span></span> <span data-ttu-id="a6a96-115">**属性\_类型**属性标记; 中提取的属性类型**属性\_ID**提取标识符。</span><span class="sxs-lookup"><span data-stu-id="a6a96-115">**PROP\_TYPE** extracts the property type from the property tag; **PROP\_ID** extracts the identifier.</span></span> <span data-ttu-id="a6a96-116">**PROP_TAG**构建属性标记从属性类型和标识符。</span><span class="sxs-lookup"><span data-stu-id="a6a96-116">**PROP_TAG** builds a property tag from a property type and identifier.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a6a96-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6a96-117">See also</span></span>

- [<span data-ttu-id="a6a96-118">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="a6a96-118">MAPI Property Overview</span></span>](mapi-property-overview.md)

