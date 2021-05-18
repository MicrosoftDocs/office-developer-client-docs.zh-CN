---
title: MAPI 属性标记
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 380dad4c-7fbf-4c49-b67c-ab612c923499
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 96211d3b6e1e4dfbd4c93a98c8dd04de10eac884
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328231"
---
# <a name="mapi-property-tags"></a><span data-ttu-id="81d9a-103">MAPI 属性标记</span><span class="sxs-lookup"><span data-stu-id="81d9a-103">MAPI property tags</span></span>
  
<span data-ttu-id="81d9a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81d9a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="81d9a-105">属性标记是一个 32 位数字，其中包含位 16 到 31 中的唯一属性标识符，以及位 0 到 15 的属性类型，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="81d9a-105">A property tag is a 32-bit number that contains a unique property identifier in bits 16 through 31 and a property type in bits 0 through 15 as shown in the following illustration.</span></span> 
  
<span data-ttu-id="81d9a-106">**属性标记元素**</span><span class="sxs-lookup"><span data-stu-id="81d9a-106">**Property tag elements**</span></span>
  
<span data-ttu-id="81d9a-107">![属性标记元素](media/amapi_10.gif "属性标记元素")</span><span class="sxs-lookup"><span data-stu-id="81d9a-107">![Property tag elements](media/amapi_10.gif "Property tag elements")</span></span>
  
<span data-ttu-id="81d9a-108">属性标记用于标识 MAPI 属性，并且每个属性都必须有一个，无论该属性是由 MAPI、客户端还是服务提供商定义的。</span><span class="sxs-lookup"><span data-stu-id="81d9a-108">Property tags are used to identify MAPI properties and every property must have one, regardless of whether the property is defined by MAPI, a client, or a service provider.</span></span> <span data-ttu-id="81d9a-109">MAPI 为 Mapitags.h 头文件中的属性定义一组属性标记常量;这些属性称为"MAPI 定义属性"。</span><span class="sxs-lookup"><span data-stu-id="81d9a-109">MAPI defines a set of property tag constants for its properties in the Mapitags.h header file; these properties are referred to as the "MAPI-defined properties".</span></span> 
  
<span data-ttu-id="81d9a-110">属性标记常量遵循命名约定，以确保一致性和易用性。</span><span class="sxs-lookup"><span data-stu-id="81d9a-110">The property tag constants follow a naming convention for consistency and ease of use.</span></span> <span data-ttu-id="81d9a-111">每个属性标记的名称有两个部分：一个PR_前缀和一个或多个描述属性内容的字符串。</span><span class="sxs-lookup"><span data-stu-id="81d9a-111">There are two parts to the name of each property tag: a PR_ prefix and one or more character strings that describe the contents of the property.</span></span> <span data-ttu-id="81d9a-112">用下划线分隔多个字符串。</span><span class="sxs-lookup"><span data-stu-id="81d9a-112">Multiple character strings are separated by underscores.</span></span> <span data-ttu-id="81d9a-113">例如，邮件收件人的地址类型的属性标记是 **PR \_ ADDRTYPE** ([PidTagOrgAddrtype](https://msdn.microsoft.com/library/d40b5707-e4d5-4746-88d4-8616a3789789%28Office.15%29.aspx)) 指定为接收每个出站邮件副本的文件夹的条目标识符为 **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="81d9a-113">For example, the property tag for the address type of a message recipient is **PR\_ADDRTYPE** ([PidTagOrgAddrtype](https://msdn.microsoft.com/library/d40b5707-e4d5-4746-88d4-8616a3789789%28Office.15%29.aspx)) and the entry identifier for the folder designated to receive a copy of every outbound message is **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)).</span></span>
  
<span data-ttu-id="81d9a-114">可以使用一些宏来帮助处理属性标记，其中包括PROP_TYPE、PROP_ID 和[](prop_type.md) [PROP_TAG](prop_tag.md)。 [](prop_id.md)</span><span class="sxs-lookup"><span data-stu-id="81d9a-114">A few macros are available to help work with property tags, among them [PROP_TYPE](prop_type.md), [PROP_ID](prop_id.md), and [PROP_TAG](prop_tag.md).</span></span> <span data-ttu-id="81d9a-115">**PROP \_TYPE** 从属性标记中提取属性类型; **PROP \_ID** 提取标识符。</span><span class="sxs-lookup"><span data-stu-id="81d9a-115">**PROP\_TYPE** extracts the property type from the property tag; **PROP\_ID** extracts the identifier.</span></span> <span data-ttu-id="81d9a-116">**PROP_TAG** 属性类型和标识符生成属性标记。</span><span class="sxs-lookup"><span data-stu-id="81d9a-116">**PROP_TAG** builds a property tag from a property type and identifier.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="81d9a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81d9a-117">See also</span></span>

- [<span data-ttu-id="81d9a-118">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="81d9a-118">MAPI Property Overview</span></span>](mapi-property-overview.md)

