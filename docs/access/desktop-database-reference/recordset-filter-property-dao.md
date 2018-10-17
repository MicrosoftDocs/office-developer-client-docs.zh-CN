---
title: Recordset.Filter Property (DAO)
TOCTitle: Filter Property
ms:assetid: feffa23b-c348-9718-ba4b-65db0f739789
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837300(v=office.15)
ms:contentKeyID: 48548953
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 906c3bd9e437ca5fc64067530ecbcaa033ea52d6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466920"
---
# <a name="recordsetfilter-property-dao"></a><span data-ttu-id="3c6a2-102">Recordset.Filter Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="3c6a2-102">Recordset.Filter Property (DAO)</span></span>

<span data-ttu-id="3c6a2-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3c6a2-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="3c6a2-p101">设置或返回一个值，该值确定在以后打开的 **Recordset** 对象中包含的记录（仅适用于 Microsoft Access 工作区）。可读写 **String**。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p101">Sets or returns a value that determines the records included in a subsequently opened **Recordset** object (Microsoft Access workspaces only). Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c6a2-106">语法</span><span class="sxs-lookup"><span data-stu-id="3c6a2-106">Syntax</span></span>

<span data-ttu-id="3c6a2-107">*表达式*。筛选器</span><span class="sxs-lookup"><span data-stu-id="3c6a2-107">*expression* .Filter</span></span>

<span data-ttu-id="3c6a2-108">*表达式*返回**Recordset**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-108">*expression* An expression that returns a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c6a2-109">注解</span><span class="sxs-lookup"><span data-stu-id="3c6a2-109">Remarks</span></span>

<span data-ttu-id="3c6a2-110">设置或返回值是一个 String 数据类型，它包含不带保留字 WHERE 的 SQL 语句的 WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-110">The setting or return value is a String data type that contains the WHERE clause of an SQL statement without the reserved word WHERE.</span></span>

<span data-ttu-id="3c6a2-111">使用**Filter**属性筛选器应用于动态集类型、 快照类型或仅向前类型**Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-111">Use the **Filter** property to apply a filter to a dynaset–, snapshot–, or forward–only–type **Recordset** object.</span></span>

<span data-ttu-id="3c6a2-112">可以使用 **Filter** 属性限制当基于现有 **Recordset** 对象打开新的 **Recordset** 对象时从现有对象返回的记录。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-112">You can use the **Filter** property to restrict the records returned from an existing object when a new **Recordset** object is opened based on an existing **Recordset** object.</span></span>

<span data-ttu-id="3c6a2-113">使用美国日期格式 （月-日-年） 时，您筛选字段包含日期，即使您没有使用 Microsoft Access 数据库引擎的美国版本 (在这种情况下必须通过连接字符串，例如，strMonth 组合任何日期 &"-"& strDay &"-"& strYear)。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-113">Use the U.S. date format (month-day-year) when you filter fields containing dates, even if you're not using the U.S. version of the Microsoft Access database engine (in which case you must assemble any dates by concatenating strings, for example, strMonth & "-" & strDay & "-" & strYear).</span></span> <span data-ttu-id="3c6a2-114">否则，日期数据可能不按您期望的方式进行筛选。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-114">Otherwise, the data may not be filtered as you expect.</span></span>

<span data-ttu-id="3c6a2-115">在许多情况下，使用包含 WHERE 子句的 SQL 语句打开新的 **Recordset** 对象会快一些。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-115">In many cases, it's faster to open a new **Recordset** object by using an SQL statement that includes a WHERE clause.</span></span>

<span data-ttu-id="3c6a2-116">如果属性设置为非 – 整数值时，连接字符串和系统参数指定非美国十进制字符，例如逗号分隔 (例如，strFilter ="价格\>"& lngPrice，和 lngPrice = 125,50)，当您尝试出错打开下一个**Recordset**。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-116">If you set the property to a string concatenated with a non–integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, strFilter = "PRICE \> " & lngPrice, and lngPrice = 125,50), an error occurs when you try to open the next **Recordset**.</span></span> <span data-ttu-id="3c6a2-117">这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-117">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and Microsoft Access SQL only accepts U.S. decimal characters.</span></span>

## <a name="example"></a><span data-ttu-id="3c6a2-118">示例</span><span class="sxs-lookup"><span data-stu-id="3c6a2-118">Example</span></span>

<span data-ttu-id="3c6a2-119">以下示例说明如何使用 Filter 属性确定要包含在稍后打开的 Recordset 中的记录。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-119">The following sample shows how to use the Filter property to determine the records to be included in a subsequently opened Recordset.</span></span>

<span data-ttu-id="3c6a2-120">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="3c6a2-120">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Dim dbs As DAO.Database
    Dim rst As DAO.Recordset
    Dim rstFiltered As DAO.Recordset
    Dim strCity As String
    
    Set dbs = CurrentDb
    
    'Create the first filtered Recordset, returning customer records
    'for those visited between 30-60 days ago.
    Set rest = dbs.OpenRecordset(_ 
        "SELECT * FROM Customers WHERE LastVisitDate BETWEEN Date()-60 " & _
        "AND Date()-30 ORDER BY LastVisitDate DESC")
    
    'Begin row processing
    Do While Not rst.EOF
        
        'Retrieve the name of the first city in the selected rows
        strCity = rst!City
    
        'Now filter the Recordset to return only the customers from that city
        rst.Filter = "City = '" & strCity & "'"
        Set rstFiltered = rst.OpenRecordset
    
        'Process the rows
        Do While Not rstFiltered.EOF
            rstFiltered.Edit
            rstFiltered!ToBeVisited = True
            rstFiltered.Update
            rstFiltered.MoveNext
        Loop
    
        'We've done what was needed. Now exit
        Exit Do
        rst.MoveNext
       
    Loop
    
    'Cleanup
    rstFiltered.Close
    rst.Close
    
    Set rstFiltered = Nothing
    Set rst = Nothing
```