---
title: 使用 Visual C++ Extensions
TOCTitle: Using Visual C++ Extensions
ms:assetid: 0fb1014c-7ab6-6add-d09f-e5e48b2b32cb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248866(v=office.15)
ms:contentKeyID: 48543270
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bcfde7e343a37d65356e1f9ed8d879030913f5ed
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868782"
---
# <a name="using-visual-c-extensions"></a>使用 Visual C++ Extensions


**适用于**： Access 2013、 Office 2013

## <a name="the-iadorecordbinding-interface"></a>IADORecordBinding 接口

Microsoft Visual C++ Extensions for ADO 将 [Recordset](recordset-object-ado.md) 对象的字段关联或绑定到 C/C++ 变量。只要绑定的 **Recordset** 的当前行发生更改，则 **Recordset** 中的所有绑定字段都将复制到 C/C++ 变量。如有必要，复制的数据将转换为 C/C++ 变量的已声明数据类型。

**IADORecordBinding** 接口的 **BindToRecordset** 方法将字段绑定到 C/C++ 变量。 **AddNew** 方法在绑定的 **Recordset** 中添加新的行。 **Update** 方法用 C/C++ 变量的值填充 **Recordset** 新行中的字段或更新现有行中的字段。

**IADORecordBinding** 接口由 **Recordset** 对象实现。您无需自己编写实现代码。

## <a name="binding-entries"></a>绑定项

Visual C++ Extensions for ADO 将 [Recordset](recordset-object-ado.md) 对象的字段映射到 C/C++ 变量。字段与变量之间的映射的定义称为*绑定项*。宏为数值数据、定长数据和可变长度数据提供了绑定项。绑定项和 C/C++ 变量在派生自 Visual C++ Extensions 类 **CADORecordBinding** 的类中声明。**CADORecordBinding** 类由绑定项宏在内部定义。

ADO 将这些宏中的参数内部映射到 OLE DB **DBBINDING** 结构，并创建一个 OLE DB **Accessor** 对象来管理字段与变量之间的数据移动和转换。OLE DB 将数据定义为包含以下三个部分：*缓冲区*，用于存储数据；*状态*，用于指示字段是否成功地存储在缓冲区中或变量应当如何还原为字段；数据的*长度*。（有关详细信息，请参阅 *《OLE DB 程序员参考》* 中的第 6 章“获取和设置数据”。）

## <a name="header-file"></a>头文件

若要使用 Visual C++ Extensions for ADO，请在应用程序中包括以下文件：

```cpp 
 
#include <icrsint.h> 
```

## <a name="binding-recordset-fields"></a>绑定 Recordset 字段

**将 Recordset 字段绑定到 C/C++ 变量**

1.  创建一个派生自 **CADORecordBinding** 类的类。

2.  在派生类中指定绑定项和相应的 C/C++ 变量。 括号之间的绑定项**开始\_ADO\_绑定**和**最终\_ADO\_绑定**宏。 宏不要以逗号或冒号结束。 每个宏会自动指定适当的分隔符。 为要映射到 C/C++ 变量的每个字段指定一个绑定项。 使用从相应成员**ADO\_固定\_长度\_条目**， **ADO\_数值\_条目**，或**ADO\_变量\_长度\_条目**系列的宏。

3.  在应用程序中，创建一个派生自 **CADORecordBinding** 类的类实例。从 **Recordset** 获取 **IADORecordBinding** 接口。然后调用 **BindToRecordset** 方法将 **Recordset** 字段绑定到 C/C++ 变量。

有关详细信息，请参阅 [Visual C++ Extensions 示例](visual-c-extensions-example.md)。

## <a name="interface-methods"></a>接口方法

**IADORecordBinding** 接口具有以下三个方法： **BindToRecordset** 、 **AddNew** 和 **Update** 。每个方法的唯一参数是一个指向派生自 **CADORecordBinding** 的类的实例的指针。因此， **AddNew** 和 **Update** 方法不能指定与其同名的 ADO 方法的任何参数。

**语法**

**BindToRecordset** 方法将 **Recordset** 字段与 C/C++ 变量关联。

`BindToRecordset(CADORecordBinding *binding)` 

**AddNew** 方法调用与其同名的 ADO [AddNew](addnew-method-ado.md) 方法，以在 **Recordset** 中添加新行。

`AddNew(CADORecordBinding *binding)` 

**Update** 方法调用与其同名的 ADO [Update](update-method-ado.md) 方法，以更新 **Recordset** 。

`Update(CADORecordBinding *binding)` 

## <a name="binding-entry-macros"></a>绑定项宏

绑定项宏用于定义 **Recordset** 字段与变量的关联。各绑定项之间用开始宏和结束宏分隔。

对于定长数据（如 **adDate** 或 **adBoolean** ）、数值数据（如 **adTinyInt** 、 **adInteger** 或 **adDouble** ）和可变长度数据（如 **adChar** 、 **adVarChar** 或 **adVarBinary** ），均提供了宏系列。除 **adVarNumeric** 之外的所有数值类型也是定长类型。每个系列具有不同的参数集，以便您可以排除不感兴趣的绑定信息。

请参阅*OLE DB 程序员参考*附录 a： 数据类型的其他信息。

_**开始绑定项**_

**开始\_ADO\_绑定**（*类*）

_**固定长度的数据**_

**ADO\_固定\_长度\_条目**（*序号、 DataType、 缓冲区、 状态、 修改*）  
**ADO\_固定\_长度\_ENTRY2**（*序号、 DataType、 缓冲区，修改*）

_**数值数据**_

**ADO\_数值\_条目**（*序号、 DataType、 缓冲区、 精度、 缩放、 状态、 修改*）  
**ADO\_数值\_ENTRY2**（*序号、 DataType、 缓冲区、 精度、 缩放、 修改*）

_**可变长度数据**_

**ADO\_变量\_长度\_条目**（*序号、 DataType、 缓冲区、 大小、 状态、 长度、 修改*）  
**ADO\_变量\_长度\_ENTRY2**（*序号、 DataType、 缓冲区、 大小、 状态、 修改*）  
**ADO\_变量\_长度\_ENTRY3**（*序号、 DataType、 缓冲区、 大小、 长度、 修改*）  
**ADO\_变量\_长度\_ENTRY4**（*序号、 DataType、 缓冲区、 大小、 修改*）

_**结束绑定项**_

**最终\_ADO\_绑定**()

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Class</em></p></td>
<td><p>在其中定义绑定项和 C/C++ 变量的类。</p></td>
</tr>
<tr class="even">
<td><p><em>Ordinal</em></p></td>
<td><p>与 C/C++ 变量对应的 <strong>Recordset</strong> 字段的序号，从 1 开始计数。</p></td>
</tr>
<tr class="odd">
<td><p><em>DataType</em></p></td>
<td><p>C/C++ 变量的等效 ADO 数据类型（有关有效数据类型的列表，请参阅 <a href="datatypeenum.md">DataTypeEnum</a>）。如有必要，<strong>Recordset</strong> 字段的值将转换为此数据类型。</p></td>
</tr>
<tr class="even">
<td><p><em>Buffer</em></p></td>
<td><p>存储 <strong>Recordset</strong> 字段的 C/C++ 变量的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>Size</em></p></td>
<td><p><em>Buffer</em> 的最大大小，以字节计。如果 <em>Buffer</em> 包含可变长度字符串，则还为终止字符零留出了空间。</p></td>
</tr>
<tr class="even">
<td><p><em>Status</em></p></td>
<td><p>变量名称，用于指示 <em>Buffer</em> 的内容是否有效，以及字段是否成功转换为 <em>DataType</em>。
 此变量有两个最重要的值：一个是 <strong>adFldOK</strong>，表示转换成功；另一个是 <strong>adFldNull</strong>，表示字段的值为 VT_NULL 类型的 VARIANT，但不仅仅为空。 在下表中，列出<em>状态</em>的可能值&quot;状态值。&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>修改</em></p></td>
<td><p>布尔型标志。如果为 TRUE，则指示允许 ADO 用 <em>Buffer</em> 中所包含的值更新相应的 <strong>Recordset</strong> 字段。
 如果要让 ADO 更新绑定字段，则将布尔型 <em>Modify</em> 参数设置为 TRUE。如果要检查字段但不进行更改，则设置为 FALSE。</p></td>
</tr>
<tr class="even">
<td><p><em>Precision</em></p></td>
<td><p>可以用数值变量表示的数字位数。</p></td>
</tr>
<tr class="odd">
<td><p><em>小数位数</em></p></td>
<td><p>用数值变量表示的小数位数。</p></td>
</tr>
<tr class="even">
<td><p><em>Length</em></p></td>
<td><p>4 字节变量的名称，包含 <em>Buffer</em> 中数据的实际长度。</p></td>
</tr>
</tbody>
</table>


## <a name="status-values"></a>状态值

*Status*变量的值指示是否字段是否成功复制到变量。

在设置数据时，*Status* 可以设置为 **adFldNull**，以指示 **Recordset** 字段应设置为 Null。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adFldOK</strong></p></td>
<td><p>0</p></td>
<td><p>返回非 Null 字段值。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldBadAccessor</strong></p></td>
<td><p>1</p></td>
<td><p>绑定无效。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldCantConvertValue</strong></p></td>
<td><p>2</p></td>
<td><p>由于符号不匹配或数据溢出之外的原因，值无法转换。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldNull</strong></p></td>
<td><p>3</p></td>
<td><p>在获取字段时，指示返回空值。
 在设置字段时，指示当字段自身无法编码 <strong>NULL</strong>（如一个字符数组或整数）时字段应设置为 <strong>NULL</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldTruncated</strong></p></td>
<td><p>4</p></td>
<td><p>截断可变长度数据或数字。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldSignMismatch</strong></p></td>
<td><p>5</p></td>
<td><p>值有符号，变量数据类型无符号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldDataOverFlow</strong></p></td>
<td><p>6</p></td>
<td><p>值大于变量数据类型中可存储的大小。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldCantCreate</strong></p></td>
<td><p>7</p></td>
<td><p>打开了未知的列类型和字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldUnavailable</strong></p></td>
<td><p>8</p></td>
<td><p>无法确定字段值 - 例如，在一个无默认值的新的未赋值字段上。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldPermissionDenied</strong></p></td>
<td><p>9</p></td>
<td><p>更新时，无权写数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldIntegrityViolation</strong></p></td>
<td><p>10</p></td>
<td><p>更新时，字段值与列完整性冲突。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldSchemaViolation</strong></p></td>
<td><p>11</p></td>
<td><p>更新时，字段值与列架构冲突。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldBadStatus</strong></p></td>
<td><p>12</p></td>
<td><p>更新时，状态参数无效。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldDefault</strong></p></td>
<td><p>13</p></td>
<td><p>更新时，使用默认值。</p></td>
</tr>
</tbody>
</table>

