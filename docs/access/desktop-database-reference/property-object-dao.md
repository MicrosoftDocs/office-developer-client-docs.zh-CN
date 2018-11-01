---
title: Property Object (DAO)
TOCTitle: Property Object
ms:assetid: a1ecb0db-bb93-a7b5-23c3-0b73f275dfe0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff820932(v=office.15)
ms:contentKeyID: 48546744
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 50f7cc2b977b25602e8aec440796f105055a7437
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875629"
---
# <a name="property-object-dao"></a><span data-ttu-id="2552a-102">Property Object (DAO)</span><span class="sxs-lookup"><span data-stu-id="2552a-102">Property Object (DAO)</span></span>


<span data-ttu-id="2552a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2552a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2552a-104">**Property** 对象代表 DAO 对象的内部特征或用户定义特征。</span><span class="sxs-lookup"><span data-stu-id="2552a-104">A **Property** object represents a built-in or user-defined characteristic of a DAO object.</span></span>

## <a name="remarks"></a><span data-ttu-id="2552a-105">注解</span><span class="sxs-lookup"><span data-stu-id="2552a-105">Remarks</span></span>

<span data-ttu-id="2552a-p101">除 **Connection** 和 **Error** 对象外，每个 DAO 对象都包含一个 **Properties** 集合，该集合具有与该 DAO 对象的内置属性相对应的 **Property** 对象。用户也可以定义 **Property** 对象，并将其追加到某些 DAO 对象的 **Properties** 集合。这些 **Property** 对象（通常就称为属性）唯一地描述了对象的该实例。</span><span class="sxs-lookup"><span data-stu-id="2552a-p101">Every DAO object except the **Connection** and **Error** objects contains a **Properties** collection which has **Property** objects corresponding to built-in properties of that DAO object. The user can also define **Property** objects and append them to the **Properties** collection of some DAO objects. These **Property** objects (which are often just called properties) uniquely characterize that instance of the object.</span></span>

<span data-ttu-id="2552a-109">可以为下列对象创建用户定义属性：</span><span class="sxs-lookup"><span data-stu-id="2552a-109">You can create user-defined properties for the following objects:</span></span>

  - <span data-ttu-id="2552a-110">**Database**、 **Index**、 **QueryDef** 和 **TableDef** 对象</span><span class="sxs-lookup"><span data-stu-id="2552a-110">**Database**, **Index**, **QueryDef**, and **TableDef** objects</span></span>

  - <span data-ttu-id="2552a-111">**QueryDef** 和 **TableDef** 对象的 **Fields** 集合中的 **Field** 对象</span><span class="sxs-lookup"><span data-stu-id="2552a-111">**Field** objects in **Fields** collections of **QueryDef** and **TableDef** objects</span></span>

<span data-ttu-id="2552a-p102">要添加用户定义属性，请使用 **CreateProperty** 方法创建一个具有唯一的 **Name** 属性设置的 **Property** 对象。创建新的 **Property** 对象的 **Type** 和 **Value** 属性，然后将该对象追加到相应对象的 **Properties** 集合。要为其添加用户定义属性的对象必须已经追加到集合中。如果引用尚未追加到 **Properties** 集合的用户定义的 **Property** 对象，则会发生错误；如果将用户定义的 **Property** 对象追加到包含同名 **Property** 对象的 **Properties** 集合中，也会发生错误。</span><span class="sxs-lookup"><span data-stu-id="2552a-p102">To add a user-defined property, use the **CreateProperty** method to create a **Property** object with a unique **Name** property setting. Set the **Type** and **Value** properties of the new **Property** object, and then append it to the **Properties** collection of the appropriate object. The object to which you are adding the user-defined property must already be appended to a collection. Referencing a user-defined **Property** object that has not yet been appended to a **Properties** collection will cause an error, as will appending a user-defined **Property** object to a **Properties** collection containing a **Property** object of the same name.</span></span>

<span data-ttu-id="2552a-116">可以从 **Properties** 集合中删除用户定义属性，但是不能删除内置属性。</span><span class="sxs-lookup"><span data-stu-id="2552a-116">You can delete user-defined properties from the **Properties** collection, but you can't delete built-in properties.</span></span>


> [!NOTE]
> <P><span data-ttu-id="2552a-p103">[!注释] 一个用户定义的 <STRONG>Property</STRONG> 对象只与一个对象的特定实例相关联。属性并不是为选定类型的对象的所有实例定义的。</span><span class="sxs-lookup"><span data-stu-id="2552a-p103">A user-defined <STRONG>Property</STRONG> object is associated only with the specific instance of an object. The property isn't defined for all instances of objects of the selected type.</span></span></P>



<span data-ttu-id="2552a-p104">可以使用对象的 **Properties** 集合来枚举该对象的内置属性和用户定义属性。不需要事先确切地知道存在哪些属性或其特征（**Name** 和 **Type** 属性）是什么，就可处理这些属性。但是，如果尝试读取一个只写属性（例如 **Workspace** 对象的 **Password** 属性），或尝试读取或写入不适当的上下文中的属性（例如 **TableDef** 对象的 **Fields** 集合中的 **Field** 对象的 **Value** 属性设置），则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="2552a-p104">You can use the **Properties** collection of an object to enumerate the object's built-in and user-defined properties. You don't need to know beforehand exactly which properties exist or what their characteristics (**Name** and **Type** properties) are to manipulate them. However, if you try to read a write-only property, such as the **Password** property of a **Workspace** object, or try to read or write a property in an inappropriate context, such as the **Value** property setting of a **Field** object in the **Fields** collection of a **TableDef** object, an error occurs.</span></span>

<span data-ttu-id="2552a-122">**Property** 对象还包括四个内置属性：</span><span class="sxs-lookup"><span data-stu-id="2552a-122">The **Property** object also has four built-in properties:</span></span>

  - <span data-ttu-id="2552a-123">**Name** 属性，一个 **String**，用于对属性进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="2552a-123">The **Name** property, a **String** that uniquely identifies the property.</span></span>

  - <span data-ttu-id="2552a-124">**Type** 属性，一个 **Integer**，用于指定属性数据类型。</span><span class="sxs-lookup"><span data-stu-id="2552a-124">The **Type** property, an **Integer** that specifies the property data type.</span></span>

  - <span data-ttu-id="2552a-125">**Value** 属性，一个 **Variant**，包含了属性设置。</span><span class="sxs-lookup"><span data-stu-id="2552a-125">The **Value** property, a **Variant** that contains the property setting.</span></span>

  - <span data-ttu-id="2552a-p105">**Inherited** 属性，一个 **Boolean**，指示属性是否是从另一个对象继承的。例如， **Recordset** 对象的 **Fields** 集合中的 **Field** 对象可以从 **TableDef** 或 **QueryDef** 基础对象继承属性。</span><span class="sxs-lookup"><span data-stu-id="2552a-p105">The **Inherited** property, a **Boolean** that indicates whether the property is inherited from another object. For example, a **Field** object in a **Fields** collection of a **Recordset** object can inherit properties from the underlying **TableDef** or **QueryDef** object.</span></span>

<span data-ttu-id="2552a-128">若要按照序号或 **Name** 属性设置来引用集合中的内置 **Property** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="2552a-128">To refer to a built-in **Property** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

  - <span data-ttu-id="2552a-129">\* 对象 \***。属性**(0)</span><span class="sxs-lookup"><span data-stu-id="2552a-129">\*object\***.Properties**(0)</span></span>

  - <span data-ttu-id="2552a-130">\*对象 \***。属性**("\* 名称 \*")</span><span class="sxs-lookup"><span data-stu-id="2552a-130">*object\***.Properties**("* name\*")</span></span>

  - <span data-ttu-id="2552a-131">\*对象 \***。属性**\!\* 名称 \*\]</span><span class="sxs-lookup"><span data-stu-id="2552a-131">*object\***.Properties**\!\[* name\*\]</span></span>

<span data-ttu-id="2552a-132">对于内置属性，还可以使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2552a-132">For a built-in property, you can also use this syntax:</span></span>

  - <span data-ttu-id="2552a-133">*对象*。*名称*</span><span class="sxs-lookup"><span data-stu-id="2552a-133">*object*.*name*</span></span>


> [!NOTE]
> <P><span data-ttu-id="2552a-134">对于用户定义的属性，您必须使用完整的<EM>对象</EM><STRONG>。属性</STRONG>（"<EM>name</EM>"） 语法。</span><span class="sxs-lookup"><span data-stu-id="2552a-134">For a user-defined property, you must use the full <EM>object</EM><STRONG>.Properties</STRONG>("<EM>name</EM>") syntax.</span></span></P>



<span data-ttu-id="2552a-p106">使用同样的语法格式，还可以引用 **Property** 对象的 **Value** 属性。引用的上下文将确定是引用 **Property** 对象自身，还是引用 **Property** 对象的 **Value** 属性。</span><span class="sxs-lookup"><span data-stu-id="2552a-p106">With the same syntax forms, you can also refer to the **Value** property of a **Property** object. The context of the reference will determine whether you are referring to the **Property** object itself or the **Value** property of the **Property** object.</span></span>

