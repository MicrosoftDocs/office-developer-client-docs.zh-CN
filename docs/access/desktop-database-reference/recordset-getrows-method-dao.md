---
title: Recordset.GetRows Method (DAO)
TOCTitle: GetRows Method
ms:assetid: 59f6e4f0-e7b1-db60-31c7-3338b66d3345
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194427(v=office.15)
ms:contentKeyID: 48545031
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053362
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 565e049fdb92da645b7ad743c74a99f829f12bca
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468996"
---
# <a name="recordsetgetrows-method-dao"></a><span data-ttu-id="e3df8-102">Recordset.GetRows Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="e3df8-102">Recordset.GetRows Method (DAO)</span></span>


<span data-ttu-id="e3df8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e3df8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e3df8-104">检索 **[Recordset](recordset-object-dao.md)** 对象中的多行。</span><span class="sxs-lookup"><span data-stu-id="e3df8-104">Retrieves multiple rows from a **[Recordset](recordset-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3df8-105">语法</span><span class="sxs-lookup"><span data-stu-id="e3df8-105">Syntax</span></span>

<span data-ttu-id="e3df8-106">*表达式*。GetRows (***NumRows***)</span><span class="sxs-lookup"><span data-stu-id="e3df8-106">*expression* .GetRows(***NumRows***)</span></span>

<span data-ttu-id="e3df8-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e3df8-107">*expression* A variable that represents a **Recordset** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="e3df8-108">参数</span><span class="sxs-lookup"><span data-stu-id="e3df8-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e3df8-109">名称</span><span class="sxs-lookup"><span data-stu-id="e3df8-109">Name</span></span></p></th>
<th><p><span data-ttu-id="e3df8-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="e3df8-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="e3df8-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="e3df8-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="e3df8-112">说明</span><span class="sxs-lookup"><span data-stu-id="e3df8-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3df8-113">NumRows</span><span class="sxs-lookup"><span data-stu-id="e3df8-113">NumRows</span></span></p></td>
<td><p><span data-ttu-id="e3df8-114">可选</span><span class="sxs-lookup"><span data-stu-id="e3df8-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="e3df8-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="e3df8-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="e3df8-116">要检索的行数。</span><span class="sxs-lookup"><span data-stu-id="e3df8-116">The number of rows to retrieve.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="return-value"></a><span data-ttu-id="e3df8-117">返回值</span><span class="sxs-lookup"><span data-stu-id="e3df8-117">Return Value</span></span>

<span data-ttu-id="e3df8-118">Variant</span><span class="sxs-lookup"><span data-stu-id="e3df8-118">Variant</span></span>

## <a name="remarks"></a><span data-ttu-id="e3df8-119">说明</span><span class="sxs-lookup"><span data-stu-id="e3df8-119">Remarks</span></span>

<span data-ttu-id="e3df8-p101">使用 **GetRows** 方法从 **Recordset** 复制记录。**GetRows** 返回二维数组。第一个下标标识字段，第二个下标标识行号。例如，intField 表示字段，intRecord 标识行号：</span><span class="sxs-lookup"><span data-stu-id="e3df8-p101">Use the **GetRows** method to copy records from a **Recordset**. **GetRows** returns a two-dimensional array. The first subscript identifies the field and the second identifies the row number. For example, intField represents the field, and intRecord identifies the row number:</span></span>

<span data-ttu-id="e3df8-124">（intField、 intRecord） 后，avarRecords</span><span class="sxs-lookup"><span data-stu-id="e3df8-124">avarRecords(intField, intRecord)</span></span>

<span data-ttu-id="e3df8-125">若要获取返回的第二行中的第一个字段值，请使用类似如下的代码：</span><span class="sxs-lookup"><span data-stu-id="e3df8-125">To get the first field value in the second row returned, use code like the following:</span></span>

<span data-ttu-id="e3df8-126">field1 = avarRecords(0,1)</span><span class="sxs-lookup"><span data-stu-id="e3df8-126">field1 = avarRecords(0,1)</span></span>

<span data-ttu-id="e3df8-127">若要获取第一行中的第二个字段值，请使用类似如下的代码：</span><span class="sxs-lookup"><span data-stu-id="e3df8-127">To get the second field value in the first row, use code like the following:</span></span>

<span data-ttu-id="e3df8-128">field2 = avarRecords(1,0)</span><span class="sxs-lookup"><span data-stu-id="e3df8-128">field2 = avarRecords(1,0)</span></span>

<span data-ttu-id="e3df8-129">**GetRows** 返回数据后，avarRecords 变量自动成为二维数组。</span><span class="sxs-lookup"><span data-stu-id="e3df8-129">The avarRecords variable automatically becomes a two-dimensional array when **GetRows** returns data.</span></span>

<span data-ttu-id="e3df8-130">如果请求的行数多于可用行数，则 **GetRows** 仅返回可用行的数目。</span><span class="sxs-lookup"><span data-stu-id="e3df8-130">If you request more rows than are available, then **GetRows** returns only the number of available rows.</span></span> <span data-ttu-id="e3df8-131">由于数组的大小进行了调整以适合返回的行数，因此可以使用 Visual Basic for Applications **UBound** 函数确定 **GetRows** 实际上检索了多少行。</span><span class="sxs-lookup"><span data-stu-id="e3df8-131">You can use the Visual Basic for Applications **UBound** function to determine how many rows **GetRows** actually retrieved, because the array is sized to fit the number of returned rows.</span></span> <span data-ttu-id="e3df8-132">例如，如果将结果返回到**Variant**调用 varA 时，您可以使用下面的代码来确定实际返回多少行：</span><span class="sxs-lookup"><span data-stu-id="e3df8-132">For example, if you returned the results into a **Variant** called varA, you could use the following code to determine how many rows were actually returned:</span></span>

<span data-ttu-id="e3df8-133">numReturned = UBound(varA,2) + 1</span><span class="sxs-lookup"><span data-stu-id="e3df8-133">numReturned = UBound(varA,2) + 1</span></span>

<span data-ttu-id="e3df8-p103">需要使用 "+ 1"，因为返回的第一行位于数组的 0 元素中。可以检索的行数受可用内存量的限制。如果表较大的话，不应使用 **GetRows** 将整个表检索到数组中。</span><span class="sxs-lookup"><span data-stu-id="e3df8-p103">You need to use "+ 1" because the first row returned is in the 0 element of the array. The number of rows that you can retrieve is constrained by the amount of available memory. You shouldn't use **GetRows** to retrieve an entire table into an array if it is large.</span></span>

<span data-ttu-id="e3df8-137">由于 **GetRows** 将 **Recordset** 的所有字段返回到包括"备注"和"长二进制"型字段的数组中，因此可能需要使用能够限制返回字段的查询。</span><span class="sxs-lookup"><span data-stu-id="e3df8-137">Because **GetRows** returns all fields of the **Recordset** into the array, including Memo and Long Binary fields, you might want to use a query that restricts the fields returned.</span></span>

<span data-ttu-id="e3df8-138">调用 **GetRows** 后，当前记录将被定位在下一个未读行上。</span><span class="sxs-lookup"><span data-stu-id="e3df8-138">After you call **GetRows**, the current record is positioned at the next unread row.</span></span> <span data-ttu-id="e3df8-139">即**GetRows**具有**移动**numrows 对当前记录相同的效果。</span><span class="sxs-lookup"><span data-stu-id="e3df8-139">That is, **GetRows** has the same effect on the current record as **Move** numrows.</span></span>

<span data-ttu-id="e3df8-p105">如果尝试使用多个 **GetRows** 调用检索所有行，请使用 **[EOF](recordset-eof-property-dao.md)** 属性，以确保位于 **Recordset** 的末尾。如果 **GetRows** 位于 **Recordset** 的末尾，或者无法在请求的范围内检索到某行，那么它返回的结果数将少于请求数目。例如，如果您尝试检索 10 条记录，但是无法检索第 5 条记录， **GetRows** 将返回 4 条记录，同时将第 5 条记录设置为当前记录。这不会生成运行时错误。如果另一个用户删除了动态集类型 **Recordset** 中的某条记录，则可能发生这种情况。有关如何处理这种情况的演示，请参阅示例。</span><span class="sxs-lookup"><span data-stu-id="e3df8-p105">If you are trying to retrieve all the rows by using multiple **GetRows** calls, use the **[EOF](recordset-eof-property-dao.md)** property to be sure that you're at the end of the **Recordset**. **GetRows** returns less than the number requested if it's at the end of the **Recordset**, or if it can't retrieve a row in the range requested. For example, if you're trying to retrieve 10 records, but you can't retrieve the fifth record, **GetRows** returns four records and makes the fifth record the current record. This will not generate a run-time error. This might occur if another user deletes a record in a dynaset-type **Recordset**. See the example for a demonstration of how to handle this.</span></span>

## <a name="example"></a><span data-ttu-id="e3df8-146">示例</span><span class="sxs-lookup"><span data-stu-id="e3df8-146">Example</span></span>

<span data-ttu-id="e3df8-p106">以下示例使用 **GetRows** 方法从 **Recordset** 中检索指定行数，并使用生成的数据填充数组。 **GetRows** 方法在以下两种情况下返回的行数少于所需的行数：已到达 **EOF**，或 **GetRows** 尝试检索已被其他用户删除的记录。只有当发生第二种情况时，函数才返回 **False**。若要使该过程运行，需要使用 GetRowsOK 函数。</span><span class="sxs-lookup"><span data-stu-id="e3df8-p106">This example uses the **GetRows** method to retrieve a specified number of rows from a **Recordset** and to fill an array with the resulting data. The **GetRows** method will return fewer than the desired number of rows in two cases: either if **EOF** has been reached, or if **GetRows** tried to retrieve a record that was deleted by another user. The function returns **False** only if the second case occurs. The GetRowsOK function is required for this procedure to run.</span></span>

```vb
    Sub GetRowsX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim strMessage As String 
     Dim intRows As Integer 
     Dim avarRecords As Variant 
     Dim intRecord As Integer 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = dbsNorthwind.OpenRecordset( _ 
     "SELECT FirstName, LastName, Title " & _ 
     "FROM Employees ORDER BY LastName", dbOpenSnapshot) 
     
     With rstEmployees 
     Do While True 
     ' Get user input for number of rows. 
     strMessage = "Enter number of rows to retrieve." 
     intRows = Val(InputBox(strMessage)) 
     
     If intRows <= 0 Then Exit Do 
     
     ' If GetRowsOK is successful, print the results, 
     ' noting if the end of the file was reached. 
     If GetRowsOK(rstEmployees, intRows, _ 
     avarRecords) Then 
     If intRows > UBound(avarRecords, 2) + 1 Then 
     Debug.Print "(Not enough records in " & _ 
     "Recordset to retrieve " & intRows & _ 
     " rows.)" 
     End If 
     Debug.Print UBound(avarRecords, 2) + 1 & _ 
     " records found." 
     
     ' Print the retrieved data. 
     For intRecord = 0 To UBound(avarRecords, 2) 
     Debug.Print " " & _ 
     avarRecords(0, intRecord) & " " & _ 
     avarRecords(1, intRecord) & ", " & _ 
     avarRecords(2, intRecord) 
     Next intRecord 
     Else 
     ' Assuming the GetRows error was due to data 
     ' changes by another user, use Requery to 
     ' refresh the Recordset and start over. 
     If .Restartable Then 
     If MsgBox("GetRows failed--retry?", _ 
     vbYesNo) = vbYes Then 
     .Requery 
     Else 
     Debug.Print "GetRows failed!" 
     Exit Do 
     End If 
     Else 
     Debug.Print "GetRows failed! " & _ 
     "Recordset not Restartable!" 
     Exit Do 
     End If 
     End If 
     
     ' Because using GetRows leaves the current record 
     ' pointer at the last record accessed, move the 
     ' pointer back to the beginning of the Recordset 
     ' before looping back for another search. 
     .MoveFirst 
     Loop 
     End With 
     
     rstEmployees.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Function GetRowsOK(rstTemp As Recordset, _ 
     intNumber As Integer, avarData As Variant) As Boolean 
     
     ' Store results of GetRows method in array. 
     avarData = rstTemp.GetRows(intNumber) 
     ' Return False only if fewer than the desired number of 
     ' rows were returned, but not because the end of the 
     ' Recordset was reached. 
     If intNumber > UBound(avarData, 2) + 1 And _ 
     Not rstTemp.EOF Then 
     GetRowsOK = False 
     Else 
     GetRowsOK = True 
     End If 
     
    End Function
```