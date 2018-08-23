---
title: MAPI 属性概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02e5b23f-1bdb-4fbf-a27d-e3301a359573
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 40a71592e658110dab81c9bcb4aec97f9930d014
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576475"
---
# <a name="mapi-property-overview"></a><span data-ttu-id="fefca-103">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="fefca-103">MAPI Property Overview</span></span>

  
  
<span data-ttu-id="fefca-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fefca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fefca-105">属性是 MAPI 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="fefca-105">A property is an attribute of a MAPI object.</span></span> <span data-ttu-id="fefca-106">属性描述有关该对象，例如邮件或消息的用户的地址类型的主题行。</span><span class="sxs-lookup"><span data-stu-id="fefca-106">Properties describe something about the object, such as the subject line of a message or the address type of a messaging user.</span></span> <span data-ttu-id="fefca-107">MAPI 定义多个属性，某些来描述许多对象和一些仅适合特定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="fefca-107">MAPI defines many properties, some to describe many objects and some that are appropriate only for an object of a particular type.</span></span> <span data-ttu-id="fefca-108">客户端和服务提供商可以通过创建新的自定义属性扩展 MAPI 的一组预定义属性。</span><span class="sxs-lookup"><span data-stu-id="fefca-108">Clients and service providers can extend MAPI's set of predefined properties by creating new, custom properties.</span></span> <span data-ttu-id="fefca-109">客户端可以定义属性来描述新的邮件类，并且服务提供商可以定义属性来公开其邮件系统的独特功能。</span><span class="sxs-lookup"><span data-stu-id="fefca-109">Clients can define properties to describe new message classes, and service providers can define properties to expose the unique features of their messaging system.</span></span>
  
<span data-ttu-id="fefca-110">属性可以是永久或临时。</span><span class="sxs-lookup"><span data-stu-id="fefca-110">Properties can be persistent or temporary.</span></span> <span data-ttu-id="fefca-111">可以存储保留会话中的属性，其对象的数据或配置文件中。</span><span class="sxs-lookup"><span data-stu-id="fefca-111">Properties that persist from session to session can be stored with their objects' data or in the profile.</span></span> <span data-ttu-id="fefca-112">仅用于当前会话期间存在的临时属性。</span><span class="sxs-lookup"><span data-stu-id="fefca-112">Temporary properties exist only for the duration of the current session.</span></span> 
  
<span data-ttu-id="fefca-113">客户端和服务提供商可以显示为具有表或属性表的用户的属性。</span><span class="sxs-lookup"><span data-stu-id="fefca-113">Clients and service providers can show properties to users with either a table or a property sheet.</span></span> <span data-ttu-id="fefca-114">表为用户提供某些属于多个对象的属性的只读的视图。</span><span class="sxs-lookup"><span data-stu-id="fefca-114">Tables provide users with a read-only view of some of the properties belonging to multiple objects.</span></span> <span data-ttu-id="fefca-115">数据表示对象和属性的每个列的每个行显示行和列格式。</span><span class="sxs-lookup"><span data-stu-id="fefca-115">The data is displayed in row and column format, with each row representing an object and each column a property.</span></span> <span data-ttu-id="fefca-116">属性表是选项卡式显示相关的单个对象的属性对话框。</span><span class="sxs-lookup"><span data-stu-id="fefca-116">Property sheets are tabbed dialog boxes that display related properties for a single object.</span></span> <span data-ttu-id="fefca-117">属性表可以提供只读或读/写访问数据。</span><span class="sxs-lookup"><span data-stu-id="fefca-117">Property sheets can provide read-only or read/write access to the data.</span></span> <span data-ttu-id="fefca-118">允许用户更改由属性表的实施者。</span><span class="sxs-lookup"><span data-stu-id="fefca-118">Whether or not a user is allowed to make changes is up to the implementer of the property sheet.</span></span>
  
<span data-ttu-id="fefca-119">[IMAPIProp](imapipropiunknown.md)接口是用于处理属性的主接口。</span><span class="sxs-lookup"><span data-stu-id="fefca-119">The [IMAPIProp](imapipropiunknown.md) interface is the primary interface for working with properties.</span></span> <span data-ttu-id="fefca-120">支持属性的所有对象都实现**IMAPIProp**。</span><span class="sxs-lookup"><span data-stu-id="fefca-120">All objects that support properties implement **IMAPIProp**.</span></span> <span data-ttu-id="fefca-121">**IMAPIProp**包括方法用于检索属性值将复制属性、 更改和保存这些更改，属性名称和它们的标识符，之间的映射和检索以前错误的信息。</span><span class="sxs-lookup"><span data-stu-id="fefca-121">**IMAPIProp** includes methods for retrieving property values, copying properties, making changes and saving those changes, mapping between property names and their identifiers, and retrieving information about a prior error.</span></span> 
  
<span data-ttu-id="fefca-122">有几种数据结构，用于描述属性和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="fefca-122">There are several data structures for describing properties and information about properties.</span></span> <span data-ttu-id="fefca-123">最常用的结构是[SPropValue](spropvalue.md)结构和[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="fefca-123">The most commonly used structures are the [SPropValue](spropvalue.md) structure and the [SPropTagArray](sproptagarray.md) structure.</span></span> <span data-ttu-id="fefca-124">**SPropValue**结构包含描述属性信息的三个部分：</span><span class="sxs-lookup"><span data-stu-id="fefca-124">The **SPropValue** structure contains the three pieces of information that describe a property:</span></span> 
  
- <span data-ttu-id="fefca-125">数据或属性的值。</span><span class="sxs-lookup"><span data-stu-id="fefca-125">Data, or value, of the property.</span></span>
    
- <span data-ttu-id="fefca-126">该属性的值，如整数或 Boolean 数据类型。</span><span class="sxs-lookup"><span data-stu-id="fefca-126">Data type of the property's value, such as integer or Boolean.</span></span> 
    
- <span data-ttu-id="fefca-127">唯一标识的属性和组件负责维护其特定范围内的数值。</span><span class="sxs-lookup"><span data-stu-id="fefca-127">Numeric value within a particular range that uniquely identify the property and component responsible for maintaining it.</span></span> <span data-ttu-id="fefca-128">例如，没有保留内容定义 MAPI，另一个范围用来存储内容的邮件属性的属性由用于自定义邮件类别的客户端消息的区域。</span><span class="sxs-lookup"><span data-stu-id="fefca-128">For example, there is a range to hold message content properties defined by MAPI and another range to hold message content properties defined by a client for a custom message class.</span></span> 
    
<span data-ttu-id="fefca-129">属性类型和标识符合并到单个组件调用属性标记中。</span><span class="sxs-lookup"><span data-stu-id="fefca-129">The property type and identifier are combined into a single component called the property tag.</span></span> <span data-ttu-id="fefca-130">属性标记都是可用于轻松引用的属性的常量。</span><span class="sxs-lookup"><span data-stu-id="fefca-130">Property tags are constants that can be used to easily refer to the property.</span></span> <span data-ttu-id="fefca-131">定义的 MAPI 属性的属性标记包含在 MAPITAGS。H 头文件和**SPropValue**结构的**ulPropTag**成员。</span><span class="sxs-lookup"><span data-stu-id="fefca-131">Property tags for properties defined by MAPI are included in the MAPITAGS.H header file and in the **ulPropTag** member of an **SPropValue** structure.</span></span> <span data-ttu-id="fefca-132">客户端和服务提供商使用属性标记标识、 检索和更新的相应属性。</span><span class="sxs-lookup"><span data-stu-id="fefca-132">Clients and service providers use property tags to identify, retrieve, and update the corresponding properties.</span></span> 
  
<span data-ttu-id="fefca-133">**SPropTagArray**结构是属性标记的计数的阵列。</span><span class="sxs-lookup"><span data-stu-id="fefca-133">The **SPropTagArray** structure is a counted array of property tags.</span></span> <span data-ttu-id="fefca-134">用于描述属性使用**SPropTagArray**结构许多**IMAPIProp**和其他接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="fefca-134">Many of the methods in **IMAPIProp** and other interfaces use an **SPropTagArray** structure for describing properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fefca-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fefca-135">See also</span></span>



[<span data-ttu-id="fefca-136">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="fefca-136">MAPI Concepts</span></span>](mapi-concepts.md)

