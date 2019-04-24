---
title: MAPI 属性概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02e5b23f-1bdb-4fbf-a27d-e3301a359573
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 99887bab2b576e6e6c05414ee9daf1bd6e8d0463
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328199"
---
# <a name="mapi-property-overview"></a><span data-ttu-id="2eb08-103">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="2eb08-103">MAPI Property Overview</span></span>

  
  
<span data-ttu-id="2eb08-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2eb08-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2eb08-105">属性是 MAPI 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="2eb08-105">A property is an attribute of a MAPI object.</span></span> <span data-ttu-id="2eb08-106">属性描述有关对象的内容, 如邮件的主题行或邮件用户的地址类型。</span><span class="sxs-lookup"><span data-stu-id="2eb08-106">Properties describe something about the object, such as the subject line of a message or the address type of a messaging user.</span></span> <span data-ttu-id="2eb08-107">MAPI 定义了许多属性, 有些用于描述许多对象, 而有些则仅适用于特定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="2eb08-107">MAPI defines many properties, some to describe many objects and some that are appropriate only for an object of a particular type.</span></span> <span data-ttu-id="2eb08-108">客户端和服务提供程序可以通过创建新的自定义属性来扩展 MAPI 的一组预定义属性。</span><span class="sxs-lookup"><span data-stu-id="2eb08-108">Clients and service providers can extend MAPI's set of predefined properties by creating new, custom properties.</span></span> <span data-ttu-id="2eb08-109">客户端可以定义用于描述新邮件类的属性, 服务提供程序可以定义属性来公开其邮件系统的独特功能。</span><span class="sxs-lookup"><span data-stu-id="2eb08-109">Clients can define properties to describe new message classes, and service providers can define properties to expose the unique features of their messaging system.</span></span>
  
<span data-ttu-id="2eb08-110">属性可以是永久性的, 也可以是临时的。</span><span class="sxs-lookup"><span data-stu-id="2eb08-110">Properties can be persistent or temporary.</span></span> <span data-ttu-id="2eb08-111">从 session to session 中保留的属性可以与它们的对象数据或配置文件存储在一起。</span><span class="sxs-lookup"><span data-stu-id="2eb08-111">Properties that persist from session to session can be stored with their objects' data or in the profile.</span></span> <span data-ttu-id="2eb08-112">临时属性仅存在于当前会话的持续时间中。</span><span class="sxs-lookup"><span data-stu-id="2eb08-112">Temporary properties exist only for the duration of the current session.</span></span> 
  
<span data-ttu-id="2eb08-113">客户端和服务提供程序可以向具有表或属性表的用户显示属性。</span><span class="sxs-lookup"><span data-stu-id="2eb08-113">Clients and service providers can show properties to users with either a table or a property sheet.</span></span> <span data-ttu-id="2eb08-114">表为用户提供了属于多个对象的某些属性的只读视图。</span><span class="sxs-lookup"><span data-stu-id="2eb08-114">Tables provide users with a read-only view of some of the properties belonging to multiple objects.</span></span> <span data-ttu-id="2eb08-115">数据按行和列的格式显示, 每行表示一个对象, 每个列都是一个属性。</span><span class="sxs-lookup"><span data-stu-id="2eb08-115">The data is displayed in row and column format, with each row representing an object and each column a property.</span></span> <span data-ttu-id="2eb08-116">属性表是用于显示单个对象的相关属性的选项卡式对话框。</span><span class="sxs-lookup"><span data-stu-id="2eb08-116">Property sheets are tabbed dialog boxes that display related properties for a single object.</span></span> <span data-ttu-id="2eb08-117">属性表可以提供对数据的只读或读/写访问权限。</span><span class="sxs-lookup"><span data-stu-id="2eb08-117">Property sheets can provide read-only or read/write access to the data.</span></span> <span data-ttu-id="2eb08-118">是否允许用户进行更改是由属性表的实施者决定的。</span><span class="sxs-lookup"><span data-stu-id="2eb08-118">Whether or not a user is allowed to make changes is up to the implementer of the property sheet.</span></span>
  
<span data-ttu-id="2eb08-119">[IMAPIProp](imapipropiunknown.md)接口是用于处理属性的主要接口。</span><span class="sxs-lookup"><span data-stu-id="2eb08-119">The [IMAPIProp](imapipropiunknown.md) interface is the primary interface for working with properties.</span></span> <span data-ttu-id="2eb08-120">支持属性的所有对象都实现**IMAPIProp**。</span><span class="sxs-lookup"><span data-stu-id="2eb08-120">All objects that support properties implement **IMAPIProp**.</span></span> <span data-ttu-id="2eb08-121">**IMAPIProp**包含用于检索属性值、复制属性、更改和保存这些更改、属性名称与其标识符之间的映射以及检索有关前一个错误的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="2eb08-121">**IMAPIProp** includes methods for retrieving property values, copying properties, making changes and saving those changes, mapping between property names and their identifiers, and retrieving information about a prior error.</span></span> 
  
<span data-ttu-id="2eb08-122">有几个用于描述属性的数据结构和有关属性的信息。</span><span class="sxs-lookup"><span data-stu-id="2eb08-122">There are several data structures for describing properties and information about properties.</span></span> <span data-ttu-id="2eb08-123">最常使用的结构是[SPropValue](spropvalue.md)结构和[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="2eb08-123">The most commonly used structures are the [SPropValue](spropvalue.md) structure and the [SPropTagArray](sproptagarray.md) structure.</span></span> <span data-ttu-id="2eb08-124">**SPropValue**结构包含描述属性的三部分信息:</span><span class="sxs-lookup"><span data-stu-id="2eb08-124">The **SPropValue** structure contains the three pieces of information that describe a property:</span></span> 
  
- <span data-ttu-id="2eb08-125">属性的数据或值。</span><span class="sxs-lookup"><span data-stu-id="2eb08-125">Data, or value, of the property.</span></span>
    
- <span data-ttu-id="2eb08-126">属性值的数据类型, 如 integer 或 Boolean。</span><span class="sxs-lookup"><span data-stu-id="2eb08-126">Data type of the property's value, such as integer or Boolean.</span></span> 
    
- <span data-ttu-id="2eb08-127">特定范围内的数值, 用于唯一标识负责维护该属性和组件的值。</span><span class="sxs-lookup"><span data-stu-id="2eb08-127">Numeric value within a particular range that uniquely identify the property and component responsible for maintaining it.</span></span> <span data-ttu-id="2eb08-128">例如, 有一个范围来保存 MAPI 定义的邮件内容属性和另一个范围, 以保留客户端为自定义邮件类别定义的邮件内容属性。</span><span class="sxs-lookup"><span data-stu-id="2eb08-128">For example, there is a range to hold message content properties defined by MAPI and another range to hold message content properties defined by a client for a custom message class.</span></span> 
    
<span data-ttu-id="2eb08-129">属性类型和标识符组合成一个称为属性标记的组件。</span><span class="sxs-lookup"><span data-stu-id="2eb08-129">The property type and identifier are combined into a single component called the property tag.</span></span> <span data-ttu-id="2eb08-130">属性标记是可用于轻松引用属性的常量。</span><span class="sxs-lookup"><span data-stu-id="2eb08-130">Property tags are constants that can be used to easily refer to the property.</span></span> <span data-ttu-id="2eb08-131">由 MAPI 定义的属性的属性标记包含在 MAPITAGS 中。H 头文件, 在**SPropValue**结构的**ulPropTag**成员中。</span><span class="sxs-lookup"><span data-stu-id="2eb08-131">Property tags for properties defined by MAPI are included in the MAPITAGS.H header file and in the **ulPropTag** member of an **SPropValue** structure.</span></span> <span data-ttu-id="2eb08-132">客户端和服务提供程序使用属性标记来标识、检索和更新相应的属性。</span><span class="sxs-lookup"><span data-stu-id="2eb08-132">Clients and service providers use property tags to identify, retrieve, and update the corresponding properties.</span></span> 
  
<span data-ttu-id="2eb08-133">**SPropTagArray**结构是一个计数的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="2eb08-133">The **SPropTagArray** structure is a counted array of property tags.</span></span> <span data-ttu-id="2eb08-134">**IMAPIProp**和其他接口中的许多方法都使用**SPropTagArray**结构来描述属性。</span><span class="sxs-lookup"><span data-stu-id="2eb08-134">Many of the methods in **IMAPIProp** and other interfaces use an **SPropTagArray** structure for describing properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2eb08-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2eb08-135">See also</span></span>



[<span data-ttu-id="2eb08-136">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="2eb08-136">MAPI Concepts</span></span>](mapi-concepts.md)

