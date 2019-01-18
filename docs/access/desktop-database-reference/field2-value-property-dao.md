---
title: Field2.Value 属性 (DAO)
TOCTitle: Value Property
ms:assetid: 6ead6ba8-1613-99c7-7968-56f5b81b2385
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195566(v=office.15)
ms:contentKeyID: 48545515
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4324917fcabd768a9527b11fceadbfc2dc9ef2b3
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707763"
---
# <a name="field2value-property-dao"></a><span data-ttu-id="b7fa4-102">Field2.Value 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="b7fa4-102">Field2.Value property (DAO)</span></span>


<span data-ttu-id="b7fa4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b7fa4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b7fa4-p101">设置或返回对象的值。可读/写 **Variant** 类型。</span><span class="sxs-lookup"><span data-stu-id="b7fa4-p101">Sets or returns the value of an object. Read/write **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7fa4-106">语法</span><span class="sxs-lookup"><span data-stu-id="b7fa4-106">Syntax</span></span>

<span data-ttu-id="b7fa4-107">*表达式*。值</span><span class="sxs-lookup"><span data-stu-id="b7fa4-107">*expression* .Value</span></span>

<span data-ttu-id="b7fa4-108">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="b7fa4-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7fa4-109">注解</span><span class="sxs-lookup"><span data-stu-id="b7fa4-109">Remarks</span></span>

<span data-ttu-id="b7fa4-110">设置或返回值是 Variant 数据类型，其计算结果值属于对象的 **Type** 属性所指定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b7fa4-110">The setting or return value is a Variant data type that evaluates to a value appropriate for the data type, as specified by the **Type** property of an object.</span></span>

<span data-ttu-id="b7fa4-111">通常， **Value** 属性用于检索和更改 **Recordset** 对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="b7fa4-111">Generally, the **Value** property is used to retrieve and alter data in **Recordset** objects.</span></span>

<span data-ttu-id="b7fa4-p102">**Value** 属性是 **Field2**、 **Parameter** 和 **Property** 对象的默认属性。因此，您可以通过直接引用这些对象（而不是指定 **Value** 属性）来设置或返回这些对象之一的值。</span><span class="sxs-lookup"><span data-stu-id="b7fa4-p102">The **Value** property is the default property of the **Field2**, **Parameter**, and **Property** objects. Therefore, you can set or return the value of one of these objects by referring to them directly instead of specifying the **Value** property.</span></span>

<span data-ttu-id="b7fa4-114">如果尝试在不正确的上下文中设置或返回 **Value** 属性（例如 **TableDef** 对象的 **Fields** 集合中的 **Field2** 对象的 **Value** 属性），则会导致可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="b7fa4-114">Trying to set or return the **Value** property in an inappropriate context (for example, the **Value** property of a **Field2** object in the **Fields** collection of a **TableDef** object) will cause a trappable error.</span></span>


> [!NOTE]
> <span data-ttu-id="b7fa4-115">从 Microsoft SQL Server 数据库读取小数值时，在 Microsoft Access 工作区中将使用科学计数法设置这些值的格式，但是这些值在 ODBCDirect 工作区中仍显示为普通的小数值。</span><span class="sxs-lookup"><span data-stu-id="b7fa4-115">When reading decimal values from a Microsoft SQL Server database, they will be formatted using scientific notation through a Microsoft Access workspace, but will appear as normal decimal values through an ODBCDirect workspace.</span></span>


