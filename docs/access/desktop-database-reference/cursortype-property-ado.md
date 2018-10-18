---
<<<<<<< 标头标题： CursorType 属性 (ADO) TOCTitle: CursorType 属性 (ADO) === 标题： CursorType 属性 (ADO) TOCTitle: CursorType 属性 (ADO)
>>>>>>> 母版页 ms:assetid: f42ded8f-9f92-ef03-a198-ffb892324611 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250239(v=office.15) ms:contentKeyID: 48548682 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="cursortype-property-ado"></a>CursorType 属性 (ADO)
=======
# <a name="cursortype-property-ado"></a>CursorType 属性 (ADO)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

指示在 [Recordset](recordset-object-ado.md) 对象中使用的游标类型。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置或返回 [CursorTypeEnum](cursortypeenum.md) 值。默认值为 **adOpenForwardOnly** 。

## <a name="remarks"></a>备注

使用 **CursorType** 属性可以指定打开 **Recordset** 对象时应使用的游标类型。

如果 **CursorLocation** 属性设置为 [adUseClient](cursorlocation-property-ado.md) ，则仅支持 **adOpenStatic** 设置。如果设置了不受支持的值，则不会导致出错；因此应改用最接近的受支持的 **CursorType** 。

如果提供程序不支持所请求的游标类型，它可能会返回另一个游标类型。打开 **Recordset** 对象时， [CursorType](recordset-object-ado.md) 属性将更改为与实际使用的游标类型相匹配的值。若要验证返回的游标的特定功能，请使用 [Supports](supports-method-ado.md) 方法。关闭 **Recordset** 后， **CursorType** 属性将恢复为其原始设置。

下面的图表显示了每种游标类型所需要的提供程序功能（由 **Supports** 方法常量进行标识）。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>对于使用此 CursorType 的 Recordset</p></th>
<th><p>Supports 方法必须为以下所有常量返回 True</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adOpenForwardOnly</strong></p></td>
<td><p>无</p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenKeyset</strong></p></td>
<td><p><strong>adBookmark</strong> <strong>adHoldRecords</strong>、 <strong>adMovePrevious</strong>、 <strong>adResync</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>adOpenDynamic</strong></p></td>
<td><p><strong>adMovePrevious</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>为 adOpenStatic</strong></p></td>
<td><p><strong>adBookmark</strong> <strong>adHoldRecords</strong>、 <strong>adMovePrevious</strong>、 <strong>adResync</strong></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>虽然 <STRONG>Supports</STRONG>(<STRONG>adUpdateBatch</STRONG>) 对于动态游标和只进游标为 true，但对于批更新，应使用键集游标或静态游标。请将 <A href="locktype-property-ado.md">LockType</A> 属性设置为 <STRONG>adLockBatchOptimistic</STRONG>，并将 <STRONG>CursorLocation</STRONG> 属性设置为 <STRONG>adUseClient</STRONG>，以启用批更新所必需的 Cursor Service for OLE DB。</P>



当 **Recordset** 关闭时， **CursorType** 属性为可读/写属性，而当其打开时为只读属性。

**远程数据服务用法**当客户端 Recordset 对象上使用时， **CursorType**属性可以设置仅为**adOpenStatic**。

