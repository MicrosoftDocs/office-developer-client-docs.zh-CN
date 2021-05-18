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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408325"
---
# <a name="mapi-property-overview"></a><span data-ttu-id="1789d-103">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="1789d-103">MAPI Property Overview</span></span>

  
  
<span data-ttu-id="1789d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1789d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1789d-105">属性是 MAPI 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="1789d-105">A property is an attribute of a MAPI object.</span></span> <span data-ttu-id="1789d-106">属性描述有关对象的信息，例如邮件的主题行或邮件用户的地址类型。</span><span class="sxs-lookup"><span data-stu-id="1789d-106">Properties describe something about the object, such as the subject line of a message or the address type of a messaging user.</span></span> <span data-ttu-id="1789d-107">MAPI 定义了许多属性，一些属性用于描述许多对象，有些属性仅适用于特定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="1789d-107">MAPI defines many properties, some to describe many objects and some that are appropriate only for an object of a particular type.</span></span> <span data-ttu-id="1789d-108">客户端和服务提供商可以通过创建新的自定义属性来扩展 MAPI 的预定义属性集。</span><span class="sxs-lookup"><span data-stu-id="1789d-108">Clients and service providers can extend MAPI's set of predefined properties by creating new, custom properties.</span></span> <span data-ttu-id="1789d-109">客户端可以定义属性来描述新的邮件类，而服务提供商可以定义属性来公开其邮件系统的独特功能。</span><span class="sxs-lookup"><span data-stu-id="1789d-109">Clients can define properties to describe new message classes, and service providers can define properties to expose the unique features of their messaging system.</span></span>
  
<span data-ttu-id="1789d-110">属性可以是永久性的或临时的。</span><span class="sxs-lookup"><span data-stu-id="1789d-110">Properties can be persistent or temporary.</span></span> <span data-ttu-id="1789d-111">在会话和会话期间保留的属性可以与对象的数据或配置文件一起存储。</span><span class="sxs-lookup"><span data-stu-id="1789d-111">Properties that persist from session to session can be stored with their objects' data or in the profile.</span></span> <span data-ttu-id="1789d-112">临时属性仅在当前会话期间存在。</span><span class="sxs-lookup"><span data-stu-id="1789d-112">Temporary properties exist only for the duration of the current session.</span></span> 
  
<span data-ttu-id="1789d-113">客户端和服务提供商可以向具有表或属性的用户显示属性表。</span><span class="sxs-lookup"><span data-stu-id="1789d-113">Clients and service providers can show properties to users with either a table or a property sheet.</span></span> <span data-ttu-id="1789d-114">表为用户提供了属于多个对象的一些属性的只读视图。</span><span class="sxs-lookup"><span data-stu-id="1789d-114">Tables provide users with a read-only view of some of the properties belonging to multiple objects.</span></span> <span data-ttu-id="1789d-115">数据以行和列格式显示，每行表示一个对象，每一列表示一个属性。</span><span class="sxs-lookup"><span data-stu-id="1789d-115">The data is displayed in row and column format, with each row representing an object and each column a property.</span></span> <span data-ttu-id="1789d-116">属性表是选项卡式对话框，用于显示单个对象的相关属性。</span><span class="sxs-lookup"><span data-stu-id="1789d-116">Property sheets are tabbed dialog boxes that display related properties for a single object.</span></span> <span data-ttu-id="1789d-117">属性表可提供对数据的只读或读/写访问权限。</span><span class="sxs-lookup"><span data-stu-id="1789d-117">Property sheets can provide read-only or read/write access to the data.</span></span> <span data-ttu-id="1789d-118">是否允许用户进行更改取决于项目实施者属性表。</span><span class="sxs-lookup"><span data-stu-id="1789d-118">Whether or not a user is allowed to make changes is up to the implementer of the property sheet.</span></span>
  
<span data-ttu-id="1789d-119">[IMAPIProp](imapipropiunknown.md)接口是处理属性的主要接口。</span><span class="sxs-lookup"><span data-stu-id="1789d-119">The [IMAPIProp](imapipropiunknown.md) interface is the primary interface for working with properties.</span></span> <span data-ttu-id="1789d-120">支持属性的所有对象都实现 **IMAPIProp**。</span><span class="sxs-lookup"><span data-stu-id="1789d-120">All objects that support properties implement **IMAPIProp**.</span></span> <span data-ttu-id="1789d-121">**IMAPIProp** 包括用于检索属性值、复制属性、进行更改和保存这些更改、在属性名称及其标识符之间映射以及检索有关之前错误的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="1789d-121">**IMAPIProp** includes methods for retrieving property values, copying properties, making changes and saving those changes, mapping between property names and their identifiers, and retrieving information about a prior error.</span></span> 
  
<span data-ttu-id="1789d-122">有几个数据结构用于描述属性和有关属性的信息。</span><span class="sxs-lookup"><span data-stu-id="1789d-122">There are several data structures for describing properties and information about properties.</span></span> <span data-ttu-id="1789d-123">最常用的结构是 [SPropValue](spropvalue.md) 结构和 [SPropTagArray](sproptagarray.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="1789d-123">The most commonly used structures are the [SPropValue](spropvalue.md) structure and the [SPropTagArray](sproptagarray.md) structure.</span></span> <span data-ttu-id="1789d-124">**SPropValue** 结构包含描述属性的三条信息：</span><span class="sxs-lookup"><span data-stu-id="1789d-124">The **SPropValue** structure contains the three pieces of information that describe a property:</span></span> 
  
- <span data-ttu-id="1789d-125">属性的数据或值。</span><span class="sxs-lookup"><span data-stu-id="1789d-125">Data, or value, of the property.</span></span>
    
- <span data-ttu-id="1789d-126">属性值的数据类型，如整数或布尔值。</span><span class="sxs-lookup"><span data-stu-id="1789d-126">Data type of the property's value, such as integer or Boolean.</span></span> 
    
- <span data-ttu-id="1789d-127">特定范围内用于唯一标识负责维护该属性和组件的数值。</span><span class="sxs-lookup"><span data-stu-id="1789d-127">Numeric value within a particular range that uniquely identify the property and component responsible for maintaining it.</span></span> <span data-ttu-id="1789d-128">例如，有一个保留 MAPI 定义的邮件内容属性的范围，还有一个保留客户端为自定义邮件类定义的邮件内容属性的范围。</span><span class="sxs-lookup"><span data-stu-id="1789d-128">For example, there is a range to hold message content properties defined by MAPI and another range to hold message content properties defined by a client for a custom message class.</span></span> 
    
<span data-ttu-id="1789d-129">属性类型和标识符组合到一个称为属性标记的组件中。</span><span class="sxs-lookup"><span data-stu-id="1789d-129">The property type and identifier are combined into a single component called the property tag.</span></span> <span data-ttu-id="1789d-130">属性标记是可用于轻松引用该属性的常量。</span><span class="sxs-lookup"><span data-stu-id="1789d-130">Property tags are constants that can be used to easily refer to the property.</span></span> <span data-ttu-id="1789d-131">MAPITAGS 中包含 MAPI 定义的属性的属性标记。H 头文件和 **SPropValue** 结构的 **ulPropTag** 成员。</span><span class="sxs-lookup"><span data-stu-id="1789d-131">Property tags for properties defined by MAPI are included in the MAPITAGS.H header file and in the **ulPropTag** member of an **SPropValue** structure.</span></span> <span data-ttu-id="1789d-132">客户端和服务提供商使用属性标记来标识、检索和更新相应的属性。</span><span class="sxs-lookup"><span data-stu-id="1789d-132">Clients and service providers use property tags to identify, retrieve, and update the corresponding properties.</span></span> 
  
<span data-ttu-id="1789d-133">**SPropTagArray** 结构是属性标记的计数数组。</span><span class="sxs-lookup"><span data-stu-id="1789d-133">The **SPropTagArray** structure is a counted array of property tags.</span></span> <span data-ttu-id="1789d-134">**IMAPIProp 和其他** 接口中的许多方法都使用 **SPropTagArray** 结构来描述属性。</span><span class="sxs-lookup"><span data-stu-id="1789d-134">Many of the methods in **IMAPIProp** and other interfaces use an **SPropTagArray** structure for describing properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1789d-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1789d-135">See also</span></span>



[<span data-ttu-id="1789d-136">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="1789d-136">MAPI Concepts</span></span>](mapi-concepts.md)

