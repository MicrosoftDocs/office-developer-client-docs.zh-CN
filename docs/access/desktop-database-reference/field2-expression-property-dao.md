---
title: Field2 属性 (DAO)
TOCTitle: Expression Property
ms:assetid: 8ae9db2c-7460-5bfc-0dc4-3f87e5ab30ff
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197109(v=office.15)
ms:contentKeyID: 48546205
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 603dfaa9a54ddfe769b96a57b790b4657abbeb14
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292816"
---
# <a name="field2expression-property-dao"></a><span data-ttu-id="022bf-102">Field2 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="022bf-102">Field2.Expression property (DAO)</span></span>

<span data-ttu-id="022bf-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="022bf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="022bf-104">获取或设置一个表达式, 该表达式代表计算字段的公式。</span><span class="sxs-lookup"><span data-stu-id="022bf-104">Gets or sets an expression that represents the formula for a calculated field.</span></span> <span data-ttu-id="022bf-105">读/写 **String**。</span><span class="sxs-lookup"><span data-stu-id="022bf-105">Read/write **String**.</span></span>

## <a name="version-information"></a><span data-ttu-id="022bf-106">版本信息</span><span class="sxs-lookup"><span data-stu-id="022bf-106">Version information</span></span>

<span data-ttu-id="022bf-107">添加的版本: Access 2010</span><span class="sxs-lookup"><span data-stu-id="022bf-107">Version added: Access 2010</span></span>

## <a name="syntax"></a><span data-ttu-id="022bf-108">语法</span><span class="sxs-lookup"><span data-stu-id="022bf-108">Syntax</span></span>

<span data-ttu-id="022bf-109">*表达式*。表达式</span><span class="sxs-lookup"><span data-stu-id="022bf-109">*expression* .Expression</span></span>

<span data-ttu-id="022bf-110">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="022bf-110">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="022bf-111">注解</span><span class="sxs-lookup"><span data-stu-id="022bf-111">Remarks</span></span>

<span data-ttu-id="022bf-112">在 Access 2013 中, 可以创建用于计算值的表字段。</span><span class="sxs-lookup"><span data-stu-id="022bf-112">In Access 2013, you can create table fields that calculate values.</span></span> <span data-ttu-id="022bf-113">计算可以包含来自同一个表中的字段以及内置的 Access 函数的值。</span><span class="sxs-lookup"><span data-stu-id="022bf-113">The calculations can include values from fields in the same table as well as built-in Access functions.</span></span>

<span data-ttu-id="022bf-114">计算不能包含其他表或查询中的字段。</span><span class="sxs-lookup"><span data-stu-id="022bf-114">The calculation cannot include fields from other tables or queries.</span></span>

<span data-ttu-id="022bf-115">计算结果为只读。</span><span class="sxs-lookup"><span data-stu-id="022bf-115">The results of the calculation are read-only.</span></span>

## <a name="example"></a><span data-ttu-id="022bf-116">示例</span><span class="sxs-lookup"><span data-stu-id="022bf-116">Example</span></span>

<span data-ttu-id="022bf-117">以下示例显示了如何创建计算字段。</span><span class="sxs-lookup"><span data-stu-id="022bf-117">The following example shows how to create a calculated field.</span></span> <span data-ttu-id="022bf-118">CreateField 方法将创建名为 **FullName** 的字段。</span><span class="sxs-lookup"><span data-stu-id="022bf-118">The CreateField method creates a field named **FullName**.</span></span> <span data-ttu-id="022bf-119">Expression 属性随后将被设为用于计算字段值的表达式。</span><span class="sxs-lookup"><span data-stu-id="022bf-119">The Expression property is then set to the expression that calculates the value of the field.</span></span>

<span data-ttu-id="022bf-120">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="022bf-120">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Sub CreateCalculatedField()
        Dim dbs As DAO.Database
        Dim tdf As DAO.TableDef
        Dim fld As DAO.Field2
        
        ' get the database
        Set dbs = CurrentDb()
        
        ' create the table
        Set tdf = dbs.CreateTableDef("tblContactsCalcField")
        
        ' create the fields: first name, last name
        tdf.Fields.Append tdf.CreateField("FirstName", dbText, 20)
        tdf.Fields.Append tdf.CreateField("LastName", dbText, 20)
        
        ' create the calculated field: full name
        Set fld = tdf.CreateField("FullName", dbText, 50)
        fld.Expression = "[FirstName] & "" "" & [LastName]"
        tdf.Fields.Append fld
        
        ' append the table and cleanup
        dbs.TableDefs.Append tdf
        
    Cleanup:
        Set fld = Nothing
        Set tdf = Nothing
        Set dbs = Nothing
    End Sub
```

