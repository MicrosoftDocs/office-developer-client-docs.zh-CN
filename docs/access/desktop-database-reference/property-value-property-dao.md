---
title: Property.Value Property (DAO)
TOCTitle: Value Property
ms:assetid: 26e47b3a-4f70-27b5-2498-b44ce4dfc99f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191905(v=office.15)
ms:contentKeyID: 48543824
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052994
f1_categories:
- Office.Version=v15
ms.openlocfilehash: cac6d4d1715599a71c082ebc988d3f07d76da2b7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888048"
---
# <a name="propertyvalue-property-dao"></a><span data-ttu-id="b7925-102">Property.Value Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="b7925-102">Property.Value Property (DAO)</span></span>


<span data-ttu-id="b7925-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b7925-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b7925-p101">设置或返回对象的值。可读/写 **Variant** 类型。</span><span class="sxs-lookup"><span data-stu-id="b7925-p101">Sets or returns the value of an object. Read/write **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7925-106">语法</span><span class="sxs-lookup"><span data-stu-id="b7925-106">Syntax</span></span>

<span data-ttu-id="b7925-107">*表达式*。值</span><span class="sxs-lookup"><span data-stu-id="b7925-107">*expression* .Value</span></span>

<span data-ttu-id="b7925-108">*表达式*一个代表**Property**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="b7925-108">*expression* A variable that represents a **Property** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7925-109">注解</span><span class="sxs-lookup"><span data-stu-id="b7925-109">Remarks</span></span>

<span data-ttu-id="b7925-110">设置或返回值是 Variant 数据类型，其计算结果值属于对象的 **Type** 属性所指定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b7925-110">The setting or return value is a Variant data type that evaluates to a value appropriate for the data type, as specified by the **Type** property of an object.</span></span>

<span data-ttu-id="b7925-111">通常， **Value** 属性用于检索和更改 **Recordset** 对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="b7925-111">Generally, the **Value** property is used to retrieve and alter data in **Recordset** objects.</span></span>

<span data-ttu-id="b7925-p102">**Value** 属性是 **Field**、 **Parameter** 和 **Property** 对象的默认属性。因此，您可以通过直接引用这些对象（而不是指定 **Value** 属性）来设置或返回这些对象之一的值。</span><span class="sxs-lookup"><span data-stu-id="b7925-p102">The **Value** property is the default property of the **Field**, **Parameter**, and **Property** objects. Therefore, you can set or return the value of one of these objects by referring to them directly instead of specifying the **Value** property.</span></span>

<span data-ttu-id="b7925-114">如果尝试在不正确的上下文中设置或返回 **Value** 属性（例如 **TableDef** 对象的 **Fields** 集合中 **Field** 对象的 **Value** 属性），则会导致可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="b7925-114">Trying to set or return the **Value** property in an inappropriate context (for example, the **Value** property of a **Field** object in the **Fields** collection of a **TableDef** object) will cause a trappable error.</span></span>


> [!NOTE]
> <P><span data-ttu-id="b7925-115">从 Microsoft SQL Server 数据库读取小数值时，在 Microsoft Access 工作区中将使用科学计数法设置这些值的格式，但是这些值在 ODBCDirect 工作区中仍显示为普通的小数值。</span><span class="sxs-lookup"><span data-stu-id="b7925-115">When reading decimal values from a Microsoft SQL Server database, they will be formatted using scientific notation through a Microsoft Access workspace, but will appear as normal decimal values through an ODBCDirect workspace.</span></span></P>


