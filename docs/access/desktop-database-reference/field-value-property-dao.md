---
title: Field 值属性 (DAO)
TOCTitle: Value Property
ms:assetid: 6c0f9a8d-f51a-b8cf-8830-f8d960a1d08c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195493(v=office.15)
ms:contentKeyID: 48545465
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a9b51bb4e08546531f95e3795074f90b5d94d4c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292921"
---
# <a name="fieldvalue-property-dao"></a><span data-ttu-id="111d8-102">Field 值属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="111d8-102">Field.Value property (DAO)</span></span>


<span data-ttu-id="111d8-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="111d8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="111d8-104">设置或返回对象的值。</span><span class="sxs-lookup"><span data-stu-id="111d8-104">Sets or returns the value of an object.</span></span> <span data-ttu-id="111d8-105">读/写 **Variant**。</span><span class="sxs-lookup"><span data-stu-id="111d8-105">Read/write **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="111d8-106">语法</span><span class="sxs-lookup"><span data-stu-id="111d8-106">Syntax</span></span>

<span data-ttu-id="111d8-107">*表达式*。增值</span><span class="sxs-lookup"><span data-stu-id="111d8-107">*expression* .Value</span></span>

<span data-ttu-id="111d8-108">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="111d8-108">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="111d8-109">注解</span><span class="sxs-lookup"><span data-stu-id="111d8-109">Remarks</span></span>

<span data-ttu-id="111d8-110">设置或返回值是 Variant 数据类型，其计算结果值属于对象的 **Type** 属性所指定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="111d8-110">The setting or return value is a Variant data type that evaluates to a value appropriate for the data type, as specified by the **Type** property of an object.</span></span>

<span data-ttu-id="111d8-111">通常， **Value** 属性用于检索和更改 **Recordset** 对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="111d8-111">Generally, the **Value** property is used to retrieve and alter data in **Recordset** objects.</span></span>

<span data-ttu-id="111d8-p102">**Value** 属性是 **Field**、 **Parameter** 和 **Property** 对象的默认属性。因此，您可以通过直接引用这些对象（而不是指定 **Value** 属性）来设置或返回这些对象之一的值。</span><span class="sxs-lookup"><span data-stu-id="111d8-p102">The **Value** property is the default property of the **Field**, **Parameter**, and **Property** objects. Therefore, you can set or return the value of one of these objects by referring to them directly instead of specifying the **Value** property.</span></span>

<span data-ttu-id="111d8-114">如果尝试在不正确的上下文中设置或返回 **Value** 属性（例如 **TableDef** 对象的 **Fields** 集合中 **Field** 对象的 **Value** 属性），则会导致可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="111d8-114">Trying to set or return the **Value** property in an inappropriate context (for example, the **Value** property of a **Field** object in the **Fields** collection of a **TableDef** object) will cause a trappable error.</span></span>


> [!NOTE]
> <span data-ttu-id="111d8-115">从 Microsoft SQL Server 数据库读取小数值时，在 Microsoft Access 工作区中将使用科学计数法设置这些值的格式，但是这些值在 ODBCDirect 工作区中仍显示为普通的小数值。</span><span class="sxs-lookup"><span data-stu-id="111d8-115">When reading decimal values from a Microsoft SQL Server database, they will be formatted using scientific notation through a Microsoft Access workspace, but will appear as normal decimal values through an ODBCDirect workspace.</span></span>


