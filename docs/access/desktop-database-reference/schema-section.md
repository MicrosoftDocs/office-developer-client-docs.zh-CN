---
title: 架构部分 (Access desktop database reference)
TOCTitle: Schema Section
ms:assetid: 59b42ffb-0524-adc3-8bcd-6e4cd2c505ce
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249304(v=office.15)
ms:contentKeyID: 48545023
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f8c479c430dd6d0ca742fefb4948544d31ba2e61
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308937"
---
# <a name="schema-section"></a>架构部分

**适用于**：Access 2013、Office 2013

## <a name="schema-section"></a>Schema 节

Schema 节是必需的。如上例所示，ADO 会写出有关每一列的详细元数据，从而尽可能多地保留数据值的语义以进行更新。不过，若要以 XML 的格式加载，ADO 只需要列的名称以及列所属的行集。下面是最小架构的示例：

```xml 
 
<xml xmlns:s="uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C14882" 
    xmlns:rs="urn:schemas-microsoft-com:rowset" 
    xmlns:z="#RowsetSchema"> 
  <s:Schema id="RowsetSchema"> 
    <s:ElementType name="row" content="eltOnly"> 
      <s:AttributeType name="ShipperID"/> 
      <s:AttributeType name="CompanyName"/> 
      <s:AttributeType name="Phone"/> 
      <s:Extends type="rs:rowbase"/> 
    </s:ElementType> 
  </s:Schema> 
  <rs:data> 
... 
  </rs:data> 
</xml> 
```

在上例中，ADO 将数据视为长度可变的字符串，因为架构中不包括任何类型信息。

## <a name="creating-aliases-for-column-names"></a>为列名创建别名

使用 **rs:name** 属性可以为列名创建别名，以便可以在行集所显示的列信息中显示一个友好的名称，并在数据节中使用一个较短的名称。例如，可以修改上面的架构，使 ShipperID（货主ID）映射到 s1，使 CompanyName（公司名称）映射到 s2，使 Phone（电话）映射到 s3，如下所示：

```xml 
 
<s:Schema id="RowsetSchema">  
<s:ElementType name="row" content="eltOnly" rs:updatable="true">  
<s:AttributeType name="s1" rs:name="ShipperID" rs:number="1" ...>  
... 
</s:AttributeType>  
<s:AttributeType name="s2" rs:name="CompanyName" rs:number="2" ...>  
... 
</s:AttributeType>  
<s:AttributeType name="s3" rs:name="Phone" rs:number="3" ...>  
... 
</s:AttributeType>  
... 
</s:ElementType>  
</s:Schema>  
```

然后，在数据节中，该行将使用 **name** 属性（而非 **rs:name**）来引用此列：

```xml 
 
"<row s1="1" s2="Speedy Express" s3="(503) 555-9831"/> 
```

当列名不是 XML 中的合法属性或标记名时，需要为列名创建别名。例如，"Last Name"必须有一个别名，因为带有嵌入空格的名称是非法属性。XML 分析器无法正确处理下面的代码行，因此，必须将别名创建为不包含嵌入空格的其他名称：

```xml 
 
<row last name="Jones"/> 
```

无论对 **name** 属性使用什么值，都必须在 XML 文档的架构和数据节中引用该列的所有位置以一致的方式使用该值。以下示例演示如何以一致的方式使用 s1：

```xml 
 
<s:Schema id="RowsetSchema"> 
  <s:ElementType name="row" content="eltOnly"> 
    <s:attribute type="s1"/> 
    <s:attribute type="CompanyName"/> 
    <s:attribute type="s3"/> 
    <s:extends type="rs:rowbase"/> 
  </s:ElementType> 
  <s:AttributeType name="s1" rs:name="ShipperID" rs:number="1"  
    rs:maydefer="true" rs:writeunknown="true"> 
    <s:datatype dt:type="i4" dt:maxLength="4" rs:precision="10"  
      rs:fixedlength="true" rs:maybenull="true"/> 
  </s:AttributeType> 
</s:Schema> 
<rs:data> 
  <z:row s1="1" CompanyName="Speedy Express" s3="(503) 555-9831"/> 
</rs:data> 
```

同样，因为没有为上例的 CompanyName（公司名称）定义别名，所以必须在整个文档中以一致的方式使用 CompanyName（公司名称）。

## <a name="data-types"></a>数据类型

可以向具有 **dt:type** 属性的列应用数据类型。可以使用下列两种方法指定数据类型：直接针对列定义本身指定 **dt:type** 属性，或者将 **s:datatype** 结构用作列定义的嵌套元素。例如，

```xml 
 
<s:AttributeType name="Phone" > 
  <s:datatype dt:type="string"/> 
</s:AttributeType> 
```

等效于

```xml 
 
<s:AttributeType name="Phone" dt:type="string"/> 
```

如果您在行定义中完全省略 **dt:type** 属性，则在默认情况下，列的类型将是可变长度的字符串。

如果您的类型信息远不只是类型名称（例如，**dt:maxLength**），则使用 **s:datatype** 子元素会增强可读性。但是，这只是一个约定，不是必需的。

以下示例进一步演示如何在架构中包括类型信息：

```xml 
 
<!-- 1. String with no max length --> 
<s:AttributeType name="title_id"/> 
<! — or --> 
<s:AttributeType name="title_id" dt:type="string"/> 
 
<! — 2. Fixed length string with max length of 6 --> 
<s:AttributeType name="title_id"> 
    <s:datatype dt:type="string" dt:maxLength="6" rs:fixedlength="true" /> 
</s:AttributeType> 
 
<! — 3. Variable length string with max length of 6 --> 
<s:AttributeType name="title_id"> 
    <s:datatype dt:type="string" dt:maxLength="6" /> 
</s:AttributeType> 
 
<! — 4. Integer --> 
<s:AttributeType name="title_id" dt:type="int"/> 
```

在第二个示例中，巧妙地使用了 **rs:fixedlength** 属性。 **rs:fixedlength** 属性设置为 true 的列表示必须在架构中定义数据的长度。 在这种情况下, 标题\_id 的合法值是 "123456", 如 "123"。 但是，"123"将无效，因为它的长度为 3（而非 6）。 有关 **fixedlength** 属性的更完整说明，请参阅《OLE DB 程序员指南》。

## <a name="handling-nulls"></a>处理 Null

Null 值由 **rs:maybenull** 属性进行处理。如果将此属性设置为 true，则该列的内容可能包含 null 值。而且，如果无法在数据行中找到该列，则从行集向后读取数据的用户将从 **IRowset::GetData()** 获得 null 状态。请考虑 Shippers（货主）表中下面的列定义：

```xml 
 
<s:AttributeType name="ShipperID"> 
  <s:datatype dt:type="int" dt:maxLength="4"/> 
</s:AttributeType> 
<s:AttributeType name="CompanyName"> 
  <s:datatype dt:type="string" dt:maxLength="40" rs:maybenull="true"/> 
</s:AttributeType> 
```

该定义允许 CompanyName（公司名称）为 null，但是 ShipperID（货主ID）不能包含 null 值。 如果数据节包含以下行, 则持久性提供器会将 "公司名称" 列的数据的状态设置为 OLE DB 状态常量 DBSTATUS\_S\_ISNULL:

```xml 
 
<z:row ShipperID="1"/> 
```

如果行完全为空, 则持久性提供程序将返回\_DBSTATUS E\_不可用于 ShipperID 和 DBSTATUS\_S\_的 OLE DB 状态。公司名称。

```xml 
 
<z:row/>  
```

请注意，零长度字符串与 null 并不相同。

```xml 
 
<z:row ShipperID="1" CompanyName=""/> 
```

对于前面的行, 持久性提供程序将为这两列返回 OLE DB\_状态\_DBSTATUS S OK。 在这种情况下，CompanyName（公司名称）只是 ""（零长度字符串）。

有关可用在 OLE DB XML 文档架构中的 OLE DB 结构的进一步信息，请参阅"urn:schemas-microsoft-com:rowset"的定义和《OLE DB 程序员指南》。

