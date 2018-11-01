---
title: Field 对象 （访问桌面数据库参考 （英文）
TOCTitle: The Field Object
ms:assetid: 55531e04-d74f-6394-df64-1660e5d572ca
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249284(v=office.15)
ms:contentKeyID: 48544926
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0b01232e7afd4f32411a53dec6ae233c786c1c08
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873402"
---
# <a name="field-object"></a>Field 对象


**适用于**： Access 2013、 Office 2013

每个 **Field** 对象通常对应于数据库表中的一列。但是， **Field** 还可以表示指向另一个 **Recordset** 的指针，称为章节。本指南随后将介绍例外，例如章节列。

使用 **Field** 对象的 **Value** 属性可以设置或返回当前记录的数据。取决于提供程序所公开的功能， **Field** 对象的某些集合、方法或属性可能不可用。

使用 **Field** 对象的集合、方法和属性，可以执行以下操作：

  - 通过使用 **Name** 属性返回字段的名称。

  - 通过使用 **Value** 属性查看或更改字段中的数据。 **Value** 是 **Field** 对象的默认属性。

  - 通过使用 **Type** 、 **Precision** 和 **NumericScale** 属性，返回字段的基本特征。

  - 通过使用 **DefinedSize** 属性，返回字段的声明大小。

  - 通过使用 **ActualSize** 属性，返回给定字段中数据的实际大小。

  - 通过使用 **Attributes** 属性和 **Properties** 集合，确定给定字段所支持的功能类型。

  - 通过使用 **AppendChunk** 和 **GetChunk** 方法，对包含长二进制或长字符数据的字段中的值进行操作。

通过使用 **OriginalValue** 和 **UnderlyingValue** 属性，在批更新期间解析字段值中的误差（如果提供程序支持批更新）。

## <a name="describing-a-field"></a>描述字段

后面的主题将讨论 [Field](field-object-ado.md) 对象的属性，这些属性提供了描述 **Field** 对象本身的信息 - 即有关字段的元数据。此信息可以用来确定有关 **Recordset** 架构的很多信息。这些属性包括 **Type** 、 **DefinedSize** 和 **ActualSize** 、 **Name** 以及 **NumericScale** 和 **Precision** 。

## <a name="discovering-the-data-type"></a>发现数据类型

**Type** 属性用于指示字段的数据类型。*《ADO 程序员参考》* 中的 [DataTypeEnum](datatypeenum.md) 描述了 ADO 所支持的数据类型枚举常量。

有关 **adNumeric** 这样的浮点数值类型，可以获得其详细信息。 **NumericScale** 属性指示将用小数点右侧的多少位数来表示 **Field** 的值。 **Precision** 属性则指定用来表示 **Field** 值的最大位数。

## <a name="determining-field-size"></a>确定字段大小

使用 **DefinedSize** 属性可以确定 **Field** 对象的数据容量。

使用 **ActualSize** 属性可以返回 **Field** 对象值的实际长度。对于所有字段， **ActualSize** 属性都是只读的。如果 ADO 无法确定 **Field** 对象值的长度， **ActualSize** 属性将返回 **adUnknown** 。

**DefinedSize** 和 **ActualSize** 属性有不同的用途。例如，假设 **Field** 对象有声明类型 **adVarChar** 以及值为 50 的 **DefinedSize** 属性，其中包含单个字符。则它返回的 **ActualSize** 属性值是单个字符的字节长度。

## <a name="determining-field-contents"></a>确定字段内容

数据源中的列的标识符是由 **Field** 的 **Name** 属性表示的。 **Field** 对象的 **Value** 属性返回或设置字段的实际数据内容。这是默认属性。

若要更改字段中的数据，请将 **Value** 属性设置为等于正确类型的新值。游标类型必须支持更新，才能更改字段内容。在批模式下，不在这里进行数据库验证，因此在这种情况下需要在调用 **UpdateBatch** 时检查是否有错误。某些提供程序还支持 ADO **Field** 对象的 **UnderlyingValue** 和 **OriginalValue** 属性，以便在您试图执行批更新时帮助您解决冲突。有关如何解决这类冲突的详细信息，请参阅 [第 4 章：编辑数据](chapter-4-editing-data.md)。


> [!NOTE]
> <P>[!注释] 将新的 <STRONG>Fields</STRONG> 追加到 <STRONG>Recordset</STRONG> 时不能设置 <STRONG>Recordset Field</STRONG> 值，但可以将新的 <STRONG>Fields</STRONG> 追加到已关闭的 <STRONG>Recordset</STRONG> 。然后，必须打开 <STRONG>Recordset</STRONG> ，只有这时才能将值赋给这些 <STRONG>Fields</STRONG> 。</P>



## <a name="getting-more-field-information"></a>获取更多字段信息

ADO 对象有两种类型的属性：内置和动态。到目前为止，只讨论了 **Field** 对象的内置属性。

内置属性是这些属性在 ADO 中实现并且立即可用到任何新的对象，使用语法。 内置属性不会作为 **Property** 对象出现在对象的 **Properties** 集合中。

动态属性是由基础数据提供程序定义的，它们出现在相应的 ADO 对象的 **Properties** 集合中。 例如，特定于提供程序的属性可以指示 **Recordset** 对象是否支持事务或更新。 这些额外的属性将作为 **Property** 对象出现在 **Recordset** 对象的 **Properties** 集合中。 动态属性可以仅通过集合，并使用语法 MyObject.Properties(0) 引用或 MyObject.Properties("Name")。

这两种属性都是不可删除的。

动态 **Property** 对象有四个它自己的内置属性：

  - **Name** 属性是用于标识该属性的字符串。

  - **Type** 属性是用于指定属性数据类型的整数。

  - **Value** 属性是包含属性设置的变量型。 **Value** 是 **Property** 对象的默认属性。

  - **Attributes** 属性是 **Long** 值，用于指示特定于提供程序的属性的特征。

**Field** 对象的 **Properties** 集合包含有关字段的其他元数据。此集合的内容因提供程序而异。以下代码示例将检查本章开头引入的示例 **Recordset** 的 **Properties** 集合。它首先查看集合的内容。此代码使用 [OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md)，因此 **Properties** 集合包含该提供程序的相关信息。

```vb 
 
'BeginFieldProps 
 Dim objProp As ADODB.Property 
 
 For intLoop = 0 To (objFields.Count - 1) 
 Debug.Print objFields.Item(intLoop).Name 
 
 For Each objProp In objFields(intLoop).Properties 
 Debug.Print vbTab & objProp.Name & " = " & objProp.Value 
 Next objProp 
 Next intLoop 
'EndFieldProps 
```

## <a name="dealing-with-binary-data"></a>处理二进制数据

使用 [Field](appendchunk-method-ado.md) 对象的 **AppendChunk** 方法可以用长二进制或字符数据来填充该对象。在系统内存有限的情况下，可以使用 **AppendChunk** 方法将长整型值作为几个部分进行操作，而不是作为整体来操作它们。

如果将 **Field** 对象的 **Attributes** 属性中的 **adFldLong** 位设置为 **True** ，则可以对该字段使用 **AppendChunk** 方法。

对 **Field** 对象第一次调用 **AppendChunk** 时，将数据写入字段，覆盖所有现有数据。之后调用 **AppendChunk** 时，在现有数据基础上进行添加。如果将数据追加到某个字段，然后设置或读取当前记录中另一个字段的值，那么 ADO 会假设您已完成了对第一个字段的数据追加。此时如果对第一个字段再次调用 **AppendChunk** 方法，则 ADO 会将调用解释为新的 **AppendChunk** 操作并覆盖现有数据。访问并非第一个 **Recordset** 对象克隆的其他 **Recordset** 对象中的字段时，不会中断 **AppendChunk** 操作。

对 **Field** 对象使用 **GetChunk** 方法可以检索其部分或全部长整型二进制数据或字符数据。如果系统内存有限，则可以使用 **GetChunk** 方法对部分（而不是全部）长整型值进行操作。

**GetChunk** 调用返回的数据会分配给*变量*。如果 *Size* 大于剩余的数据，则 **GetChunk** 方法仅返回剩余的数据，而不会使用空格来填充*变量*。如果字段空白，则 **GetChunk** 方法返回一个 Null 值。

在随后每次调用 **GetChunk** 时，将从上一个 **GetChunk** 调用的离开位置开始检索数据。但是，如果正在从一个字段检索数据，然后设置或读取了当前记录中另一个字段的值，则 ADO 会假设您已经完成从第一个字段检索数据的操作。如果再次对第一个字段调用 **GetChunk** 方法，ADO 会将该调用解释为新的 **GetChunk** 操作，并开始从数据的开头进行读取。在访问其他 **Recordset** 对象的字段时，如果该对象不是第一个 **Recordset** 对象的克隆，则不会中断 **GetChunk** 操作。

如果将 **Field** 对象的 **Attributes** 属性的 **adFldLong** 位设置为 **True** ，则可以对该字段使用 **GetChunk** 方法。

在使用 **Field** 对象的 **GetChunk** 或 **AppendChunk** 方法时，如果没有当前记录，则会发生错误 3021（无当前记录）。

有关使用这些方法来操作二进制数据的示例，请参阅 *《ADO 程序员参考》* 中的 [AppendChunk 方法](appendchunk-method-ado.md)和 [GetChunk 方法](getchunk-method-ado.md)示例。

