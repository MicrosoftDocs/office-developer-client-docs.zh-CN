---
title: 映射和映射签名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 773f6671-cc21-4d1f-a11d-308bc71c852d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b5c8fd8c757de995e2a2e4239be614cf171fcb44
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566185"
---
# <a name="mappings-and-mapping-signatures"></a><span data-ttu-id="ba50f-103">映射和映射签名</span><span class="sxs-lookup"><span data-stu-id="ba50f-103">Mappings and Mapping Signatures</span></span>

  
  
<span data-ttu-id="ba50f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ba50f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ba50f-105">如果服务提供商支持命名的属性，每组标识符和名称对称为映射。</span><span class="sxs-lookup"><span data-stu-id="ba50f-105">When a service provider supports named properties, each set of identifier and name pairs is referred to as a mapping.</span></span> <span data-ttu-id="ba50f-106">一个映射或几个可支持服务提供商。</span><span class="sxs-lookup"><span data-stu-id="ba50f-106">Service providers can support one mapping or several.</span></span> <span data-ttu-id="ba50f-107">是，一个消息存储提供程序，例如，可以实现其消息、 文件夹和消息存储对象，以使用单个列表的名称和其相应的标识符的所有**GetIDsFromNames**和**GetNamesFromIDs**方法。</span><span class="sxs-lookup"><span data-stu-id="ba50f-107">That is, one message store provider, for example, can implement the **GetIDsFromNames** and **GetNamesFromIDs** methods for all of its message, folder, and message store objects to work with a single list of names and their corresponding identifiers.</span></span> <span data-ttu-id="ba50f-108">其他消息存储提供程序可能对每个文件夹和邮件，其中包含一个列表或实现的每条消息和每个文件夹的唯一列表。</span><span class="sxs-lookup"><span data-stu-id="ba50f-108">Another message store provider might have one list for every folder and the messages contained within it, or implement a unique list for every message and every folder.</span></span> <span data-ttu-id="ba50f-109">消息存储提供程序的唯一映射用于每个邮件必须不允许其文件夹内容表中显示，因为属性标识符将给定的属性名称，不同消息消息的命名的属性。</span><span class="sxs-lookup"><span data-stu-id="ba50f-109">Message store providers that use a unique mapping for every message must not allow named properties to appear in their folder contents tables because for a given property name, the property identifier will differ from message to message.</span></span> <span data-ttu-id="ba50f-110">MAPI 建议提供程序使简单，并包括表其对象的所有单个列表执行操作。</span><span class="sxs-lookup"><span data-stu-id="ba50f-110">MAPI recommends that providers keep it simple and operate with a single list for all of their objects including tables.</span></span> 
  
<span data-ttu-id="ba50f-111">对于每个映射，服务提供商必须提供映射签名。</span><span class="sxs-lookup"><span data-stu-id="ba50f-111">For every mapping, service providers must supply a mapping signature.</span></span> <span data-ttu-id="ba50f-112">映射签名是二进制值，通常标识的 GUID，唯一一组属性标识符和其相应的名称。</span><span class="sxs-lookup"><span data-stu-id="ba50f-112">A mapping signature is a binary value, usually a GUID, that uniquely identifies a set of property identifiers and their corresponding names.</span></span> <span data-ttu-id="ba50f-113">映射签名存储在对象的**PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ba50f-113">Mapping signatures are stored in an object's **PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) property.</span></span> <span data-ttu-id="ba50f-114">对它所表示的映射进行更改时，服务提供商必须更改其**PR_MAPPING_SIGNATURE**属性的值。</span><span class="sxs-lookup"><span data-stu-id="ba50f-114">Service providers must change the value for their **PR_MAPPING_SIGNATURE** property whenever a change is made to the mapping that it represents.</span></span> <span data-ttu-id="ba50f-115">例如，如果新标识符分配给的名称或新名称和标识符对添加，则必须更新**PR_MAPPING_SIGNATURE** 。</span><span class="sxs-lookup"><span data-stu-id="ba50f-115">For example, **PR_MAPPING_SIGNATURE** must be updated if a new identifier is assigned to a name or a new name and identifier pair is added.</span></span> 
  
<span data-ttu-id="ba50f-116">客户端使用的对象的命名属性在比较和复制操作中使用的对象的**PR_MAPPING_SIGNATURE**属性。</span><span class="sxs-lookup"><span data-stu-id="ba50f-116">Clients working with the named properties of objects use the objects' **PR_MAPPING_SIGNATURE** properties in comparison and copy operations.</span></span> <span data-ttu-id="ba50f-117">要比较名为属性属于两个对象的标识符，不使用映射签名的客户端必须调用[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)上两个对象来检索每个标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="ba50f-117">To compare named property identifiers belonging to two objects, clients not using mapping signatures must call [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) on both objects to retrieve the names for each of the identifiers.</span></span> <span data-ttu-id="ba50f-118">使用的对象的映射签名会导致此呼叫不必要。</span><span class="sxs-lookup"><span data-stu-id="ba50f-118">Using the mapping signatures of objects can render this call unnecessary.</span></span> <span data-ttu-id="ba50f-119">当两个对象及其**PR_MAPPING_SIGNATURE**属性的值相同时，他们使用相同的映射。</span><span class="sxs-lookup"><span data-stu-id="ba50f-119">When two objects have the same value for their **PR_MAPPING_SIGNATURE** properties, they use the same mapping.</span></span> <span data-ttu-id="ba50f-120">使用相同的映射的标识符可以直接进行比较。</span><span class="sxs-lookup"><span data-stu-id="ba50f-120">Identifiers that use the same mapping can be compared directly.</span></span> <span data-ttu-id="ba50f-121">服务提供商实现[IMAPIProp::CopyTo](imapiprop-copyto.md)和[IMAPIProp::CopyProps](imapiprop-copyprops.md)还可以利用对象的映射签名。</span><span class="sxs-lookup"><span data-stu-id="ba50f-121">Service providers that implement [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md) can also take advantage of an object's mapping signature.</span></span> <span data-ttu-id="ba50f-122">复制命名对象之间的属性，当服务提供商可以避免转换步骤时的源和目标对象具有相同的映射签名。</span><span class="sxs-lookup"><span data-stu-id="ba50f-122">When copying named properties between objects, service providers can avoid the conversion step when the source and destination objects have the same mapping signature.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ba50f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba50f-123">See also</span></span>



[<span data-ttu-id="ba50f-124">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ba50f-124">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="ba50f-125">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="ba50f-125">MAPI Named Properties</span></span>](mapi-named-properties.md)

