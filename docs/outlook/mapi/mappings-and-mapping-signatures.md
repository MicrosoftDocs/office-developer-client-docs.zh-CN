---
title: 映射和映射签名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 773f6671-cc21-4d1f-a11d-308bc71c852d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cd26ce4bc2da3da639b4a611fc9a69f39b13e5f3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410012"
---
# <a name="mappings-and-mapping-signatures"></a><span data-ttu-id="a5061-103">映射和映射签名</span><span class="sxs-lookup"><span data-stu-id="a5061-103">Mappings and Mapping Signatures</span></span>

  
  
<span data-ttu-id="a5061-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a5061-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a5061-105">当服务提供商支持命名属性时，每组标识符和名称对都称为映射。</span><span class="sxs-lookup"><span data-stu-id="a5061-105">When a service provider supports named properties, each set of identifier and name pairs is referred to as a mapping.</span></span> <span data-ttu-id="a5061-106">服务提供商可以支持一个或多个映射。</span><span class="sxs-lookup"><span data-stu-id="a5061-106">Service providers can support one mapping or several.</span></span> <span data-ttu-id="a5061-107">也就是说，例如，一个邮件存储提供程序可以针对其所有邮件、文件夹和邮件存储对象实现 **GetIDsFromNames** 和 **GetNamesFromIDs** 方法，以使用单个名称列表及其对应的标识符。</span><span class="sxs-lookup"><span data-stu-id="a5061-107">That is, one message store provider, for example, can implement the **GetIDsFromNames** and **GetNamesFromIDs** methods for all of its message, folder, and message store objects to work with a single list of names and their corresponding identifiers.</span></span> <span data-ttu-id="a5061-108">另一个邮件存储提供程序可能针对每个文件夹及其中包含的邮件具有一个列表，或者针对每封邮件和每个文件夹实现一个唯一列表。</span><span class="sxs-lookup"><span data-stu-id="a5061-108">Another message store provider might have one list for every folder and the messages contained within it, or implement a unique list for every message and every folder.</span></span> <span data-ttu-id="a5061-109">对每封邮件使用唯一映射的邮件存储提供程序不得允许命名属性显示在其文件夹内容表中，因为对于给定的属性名称，属性标识符将因邮件不同而不同。</span><span class="sxs-lookup"><span data-stu-id="a5061-109">Message store providers that use a unique mapping for every message must not allow named properties to appear in their folder contents tables because for a given property name, the property identifier will differ from message to message.</span></span> <span data-ttu-id="a5061-110">MAPI 建议提供程序保持简单，并针对其所有对象（包括表）使用单个列表。</span><span class="sxs-lookup"><span data-stu-id="a5061-110">MAPI recommends that providers keep it simple and operate with a single list for all of their objects including tables.</span></span> 
  
<span data-ttu-id="a5061-111">对于每个映射，服务提供商必须提供映射签名。</span><span class="sxs-lookup"><span data-stu-id="a5061-111">For every mapping, service providers must supply a mapping signature.</span></span> <span data-ttu-id="a5061-112">映射签名是一个二进制值，通常为 GUID，用于唯一标识一组属性标识符及其相应的名称。</span><span class="sxs-lookup"><span data-stu-id="a5061-112">A mapping signature is a binary value, usually a GUID, that uniquely identifies a set of property identifiers and their corresponding names.</span></span> <span data-ttu-id="a5061-113">映射签名存储在对象的 PR_MAPPING_SIGNATURE ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性中。 </span><span class="sxs-lookup"><span data-stu-id="a5061-113">Mapping signatures are stored in an object's **PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) property.</span></span> <span data-ttu-id="a5061-114">只要对它表示的映射进行了PR_MAPPING_SIGNATURE，服务提供商就必须更改其 PR_MAPPING_SIGNATURE 属性的值。 </span><span class="sxs-lookup"><span data-stu-id="a5061-114">Service providers must change the value for their **PR_MAPPING_SIGNATURE** property whenever a change is made to the mapping that it represents.</span></span> <span data-ttu-id="a5061-115">例如 **，PR_MAPPING_SIGNATURE** 新标识符或添加了新名称和标识符对，则必须更新该标识符。</span><span class="sxs-lookup"><span data-stu-id="a5061-115">For example, **PR_MAPPING_SIGNATURE** must be updated if a new identifier is assigned to a name or a new name and identifier pair is added.</span></span> 
  
<span data-ttu-id="a5061-116">使用对象的命名属性的客户端在比较 **和复制操作PR_MAPPING_SIGNATURE** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="a5061-116">Clients working with the named properties of objects use the objects' **PR_MAPPING_SIGNATURE** properties in comparison and copy operations.</span></span> <span data-ttu-id="a5061-117">为了比较属于两个对象的命名属性标识符，没有使用映射签名的客户端必须调用这两个对象上的 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 以检索每个标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="a5061-117">To compare named property identifiers belonging to two objects, clients not using mapping signatures must call [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) on both objects to retrieve the names for each of the identifiers.</span></span> <span data-ttu-id="a5061-118">使用对象的映射签名会使此调用成为不必要的。</span><span class="sxs-lookup"><span data-stu-id="a5061-118">Using the mapping signatures of objects can render this call unnecessary.</span></span> <span data-ttu-id="a5061-119">当两个对象的两个属性 **PR_MAPPING_SIGNATURE相同时** ，它们使用相同的映射。</span><span class="sxs-lookup"><span data-stu-id="a5061-119">When two objects have the same value for their **PR_MAPPING_SIGNATURE** properties, they use the same mapping.</span></span> <span data-ttu-id="a5061-120">可以直接比较使用相同映射的标识符。</span><span class="sxs-lookup"><span data-stu-id="a5061-120">Identifiers that use the same mapping can be compared directly.</span></span> <span data-ttu-id="a5061-121">实现 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 和 [IMAPIProp：：CopyProps](imapiprop-copyprops.md) 的服务提供商还可以利用对象的映射签名。</span><span class="sxs-lookup"><span data-stu-id="a5061-121">Service providers that implement [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md) can also take advantage of an object's mapping signature.</span></span> <span data-ttu-id="a5061-122">在对象之间复制命名属性时，当源对象和目标对象具有相同的映射签名时，服务提供商可以避免转换步骤。</span><span class="sxs-lookup"><span data-stu-id="a5061-122">When copying named properties between objects, service providers can avoid the conversion step when the source and destination objects have the same mapping signature.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a5061-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5061-123">See also</span></span>



[<span data-ttu-id="a5061-124">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a5061-124">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="a5061-125">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="a5061-125">MAPI Named Properties</span></span>](mapi-named-properties.md)

