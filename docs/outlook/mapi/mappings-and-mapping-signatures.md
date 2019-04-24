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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357636"
---
# <a name="mappings-and-mapping-signatures"></a><span data-ttu-id="1e471-103">映射和映射签名</span><span class="sxs-lookup"><span data-stu-id="1e471-103">Mappings and Mapping Signatures</span></span>

  
  
<span data-ttu-id="1e471-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1e471-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1e471-105">当服务提供程序支持命名属性时, 每组标识符和名称对称为一个映射。</span><span class="sxs-lookup"><span data-stu-id="1e471-105">When a service provider supports named properties, each set of identifier and name pairs is referred to as a mapping.</span></span> <span data-ttu-id="1e471-106">服务提供程序可以支持一个或多个映射。</span><span class="sxs-lookup"><span data-stu-id="1e471-106">Service providers can support one mapping or several.</span></span> <span data-ttu-id="1e471-107">也就是说, 一个邮件存储提供程序可以实现其所有邮件、文件夹和邮件存储对象的**GetIDsFromNames**和**GetNamesFromIDs**方法, 使其与单个名称列表及其对应的标识符一起使用。</span><span class="sxs-lookup"><span data-stu-id="1e471-107">That is, one message store provider, for example, can implement the **GetIDsFromNames** and **GetNamesFromIDs** methods for all of its message, folder, and message store objects to work with a single list of names and their corresponding identifiers.</span></span> <span data-ttu-id="1e471-108">另一个邮件存储提供程序可能有一个列表, 其中包含每个文件夹和其中包含的邮件, 或者为每个邮件和每个文件夹实现一个唯一的列表。</span><span class="sxs-lookup"><span data-stu-id="1e471-108">Another message store provider might have one list for every folder and the messages contained within it, or implement a unique list for every message and every folder.</span></span> <span data-ttu-id="1e471-109">对每个邮件使用唯一映射的邮件存储提供程序必须不允许命名属性出现在其文件夹内容表中, 因为对于给定的属性名称, 属性标识符将因邮件而异。</span><span class="sxs-lookup"><span data-stu-id="1e471-109">Message store providers that use a unique mapping for every message must not allow named properties to appear in their folder contents tables because for a given property name, the property identifier will differ from message to message.</span></span> <span data-ttu-id="1e471-110">MAPI 建议提供程序将其简化, 并对其所有对象 (包括表) 的单个列表运行。</span><span class="sxs-lookup"><span data-stu-id="1e471-110">MAPI recommends that providers keep it simple and operate with a single list for all of their objects including tables.</span></span> 
  
<span data-ttu-id="1e471-111">对于每个映射, 服务提供程序都必须提供映射签名。</span><span class="sxs-lookup"><span data-stu-id="1e471-111">For every mapping, service providers must supply a mapping signature.</span></span> <span data-ttu-id="1e471-112">映射签名是一个二进制值, 通常是一个 GUID, 它唯一标识一组属性标识符及其对应的名称。</span><span class="sxs-lookup"><span data-stu-id="1e471-112">A mapping signature is a binary value, usually a GUID, that uniquely identifies a set of property identifiers and their corresponding names.</span></span> <span data-ttu-id="1e471-113">映射签名存储在对象的**PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="1e471-113">Mapping signatures are stored in an object's **PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) property.</span></span> <span data-ttu-id="1e471-114">每当对它所表示的映射进行更改时, 服务提供程序必须更改其**PR_MAPPING_SIGNATURE**属性的值。</span><span class="sxs-lookup"><span data-stu-id="1e471-114">Service providers must change the value for their **PR_MAPPING_SIGNATURE** property whenever a change is made to the mapping that it represents.</span></span> <span data-ttu-id="1e471-115">例如, 如果向某个名称分配了新的标识符, 或者添加了新的名称和标识符对, 则必须更新**PR_MAPPING_SIGNATURE** 。</span><span class="sxs-lookup"><span data-stu-id="1e471-115">For example, **PR_MAPPING_SIGNATURE** must be updated if a new identifier is assigned to a name or a new name and identifier pair is added.</span></span> 
  
<span data-ttu-id="1e471-116">使用对象的命名属性的客户端在比较和复制操作中使用对象的**PR_MAPPING_SIGNATURE**属性。</span><span class="sxs-lookup"><span data-stu-id="1e471-116">Clients working with the named properties of objects use the objects' **PR_MAPPING_SIGNATURE** properties in comparison and copy operations.</span></span> <span data-ttu-id="1e471-117">若要比较属于两个对象的命名属性标识符, 不使用映射签名的客户端必须在两个对象上调用[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)以检索每个标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="1e471-117">To compare named property identifiers belonging to two objects, clients not using mapping signatures must call [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) on both objects to retrieve the names for each of the identifiers.</span></span> <span data-ttu-id="1e471-118">使用对象的映射签名可不必要地呈现此呼叫。</span><span class="sxs-lookup"><span data-stu-id="1e471-118">Using the mapping signatures of objects can render this call unnecessary.</span></span> <span data-ttu-id="1e471-119">当两个对象的**PR_MAPPING_SIGNATURE**属性具有相同的值时, 它们将使用相同的映射。</span><span class="sxs-lookup"><span data-stu-id="1e471-119">When two objects have the same value for their **PR_MAPPING_SIGNATURE** properties, they use the same mapping.</span></span> <span data-ttu-id="1e471-120">可以直接对使用相同映射的标识符进行比较。</span><span class="sxs-lookup"><span data-stu-id="1e471-120">Identifiers that use the same mapping can be compared directly.</span></span> <span data-ttu-id="1e471-121">实现[IMAPIProp:: CopyTo](imapiprop-copyto.md)和[IMAPIProp:: CopyProps](imapiprop-copyprops.md)的服务提供程序还可以利用对象的映射签名。</span><span class="sxs-lookup"><span data-stu-id="1e471-121">Service providers that implement [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md) can also take advantage of an object's mapping signature.</span></span> <span data-ttu-id="1e471-122">当复制对象之间的命名属性时, 当源和目标对象具有相同的映射签名时, 服务提供程序可以避免转换步骤。</span><span class="sxs-lookup"><span data-stu-id="1e471-122">When copying named properties between objects, service providers can avoid the conversion step when the source and destination objects have the same mapping signature.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1e471-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e471-123">See also</span></span>



[<span data-ttu-id="1e471-124">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1e471-124">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="1e471-125">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="1e471-125">MAPI Named Properties</span></span>](mapi-named-properties.md)

