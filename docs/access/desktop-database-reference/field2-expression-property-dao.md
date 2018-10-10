---
title: Field2.Expression Property (DAO)
TOCTitle: Expression Property
ms:assetid: 8ae9db2c-7460-5bfc-0dc4-3f87e5ab30ff
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197109(v=office.15)
ms:contentKeyID: 48546205
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7f3cbb7ca4078fb92ad721d85679dabee9237f85
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467723"
---
# <a name="field2expression-property-dao"></a><span data-ttu-id="36dd7-102">Field2.Expression Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="36dd7-102">Field2.Expression Property (DAO)</span></span>

<span data-ttu-id="36dd7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="36dd7-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="36dd7-104">获取或设置代表计算字段的公式的表达式。</span><span class="sxs-lookup"><span data-stu-id="36dd7-104">Gets or sets an expression that represents the formula for a calculated field.</span></span> <span data-ttu-id="36dd7-105">可读写 **String**。</span><span class="sxs-lookup"><span data-stu-id="36dd7-105">Read/write **String**.</span></span>

## <a name="version-information"></a><span data-ttu-id="36dd7-106">版本信息</span><span class="sxs-lookup"><span data-stu-id="36dd7-106">Version Information</span></span>

<span data-ttu-id="36dd7-107">添加的版本： Access 2010
</span><span class="sxs-lookup"><span data-stu-id="36dd7-107">Version Added: Access 2010</span></span>

## <a name="syntax"></a><span data-ttu-id="36dd7-108">语法</span><span class="sxs-lookup"><span data-stu-id="36dd7-108">Syntax</span></span>

<span data-ttu-id="36dd7-109">*表达式*。表达式</span><span class="sxs-lookup"><span data-stu-id="36dd7-109">*expression* .Expression</span></span>

<span data-ttu-id="36dd7-110">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="36dd7-110">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="36dd7-111">说明</span><span class="sxs-lookup"><span data-stu-id="36dd7-111">Remarks</span></span>

<span data-ttu-id="36dd7-112">您可以在 Access 2013 中创建计算值的表字段。</span><span class="sxs-lookup"><span data-stu-id="36dd7-112">In Access 2013, you can create table fields that calculate values.</span></span> <span data-ttu-id="36dd7-113">计算可以包括在同一个表以及内置访问函数从字段的值。</span><span class="sxs-lookup"><span data-stu-id="36dd7-113">The calculations can include values from fields in the same table as well as built-in Access functions.</span></span>

<span data-ttu-id="36dd7-114">计算不能包含其他表或查询中的字段。</span><span class="sxs-lookup"><span data-stu-id="36dd7-114">The calculation cannot include fields from other tables or queries.</span></span>

<span data-ttu-id="36dd7-115">计算的结果是只读的。</span><span class="sxs-lookup"><span data-stu-id="36dd7-115">The results of the calculation are read-only.</span></span>

## <a name="example"></a><span data-ttu-id="36dd7-116">示例</span><span class="sxs-lookup"><span data-stu-id="36dd7-116">Example</span></span>

<span data-ttu-id="36dd7-117">下面的示例演示如何创建计算的字段。</span><span class="sxs-lookup"><span data-stu-id="36dd7-117">The following example shows how to create a calculated field.</span></span> <span data-ttu-id="36dd7-118">CreateField 方法创建一个名为**FullName**字段。</span><span class="sxs-lookup"><span data-stu-id="36dd7-118">The CreateField method creates a field named **FullName**.</span></span> <span data-ttu-id="36dd7-119">然后表达式属性设置为计算字段的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="36dd7-119">The Expression property is then set to the expression that calculates the value of the field.</span></span>

<span data-ttu-id="36dd7-120">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="36dd7-120">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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

