---
title: 架构部分 （访问桌面数据库参考 （英文）
TOCTitle: Schema Section
ms:assetid: 59b42ffb-0524-adc3-8bcd-6e4cd2c505ce
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249304(v=office.15)
ms:contentKeyID: 48545023
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd1a67ebd992d90abf182c042bd3d68a6d0d4ce2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468345"
---
# <a name="schema-section"></a><span data-ttu-id="d957a-102">Schema 节</span><span class="sxs-lookup"><span data-stu-id="d957a-102">Schema Section</span></span>

<span data-ttu-id="d957a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d957a-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="schema-section"></a><span data-ttu-id="d957a-104">Schema 节</span><span class="sxs-lookup"><span data-stu-id="d957a-104">Schema Section</span></span>

<span data-ttu-id="d957a-p101">Schema 节是必需的。如上例所示，ADO 会写出有关每一列的详细元数据，从而尽可能多地保留数据值的语义以进行更新。不过，若要以 XML 的格式加载，ADO 只需要列的名称以及列所属的行集。下面是最小架构的示例：</span><span class="sxs-lookup"><span data-stu-id="d957a-p101">The schema section is required. As the previous example shows, ADO writes out detailed metadata about each column to preserve the semantics of the data values as much as possible for updating. However, to load in the XML, ADO only requires the names of the columns and the rowset to which they belong. Here is an example of a minimal schema:</span></span>

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

<span data-ttu-id="d957a-109">在上例中，ADO 将数据视为长度可变的字符串，因为架构中不包括任何类型信息。</span><span class="sxs-lookup"><span data-stu-id="d957a-109">In the case above, ADO will treat the data as variable length strings because no type information is included in the schema.</span></span>

## <a name="creating-aliases-for-column-names"></a><span data-ttu-id="d957a-110">为列名创建别名</span><span class="sxs-lookup"><span data-stu-id="d957a-110">Creating Aliases for Column Names</span></span>

<span data-ttu-id="d957a-p102">使用 **rs:name** 属性可以为列名创建别名，以便可以在行集所显示的列信息中显示一个友好的名称，并在数据节中使用一个较短的名称。例如，可以修改上面的架构，使 ShipperID（货主ID）映射到 s1，使 CompanyName（公司名称）映射到 s2，使 Phone（电话）映射到 s3，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d957a-p102">The **rs:name** attribute allows you to create an alias for a column name so that a friendly name may appear in the column information exposed by the rowset and a shorter name may be used in the data section. For example, the schema above could be modified to map ShipperID to s1, CompanyName to s2, and Phone to s3 as follows:</span></span>

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

<span data-ttu-id="d957a-113">然后，在数据节中，该行将使用 **name** 属性（而非 **rs:name**）来引用此列：</span><span class="sxs-lookup"><span data-stu-id="d957a-113">Then, in the data section, the row would use the **name** attribute (not **rs:name**) to refer to that column:</span></span>

```xml 
 
"<row s1="1" s2="Speedy Express" s3="(503) 555-9831"/> 
```

<span data-ttu-id="d957a-p103">当列名不是 XML 中的合法属性或标记名时，需要为列名创建别名。例如，"Last Name"必须有一个别名，因为带有嵌入空格的名称是非法属性。XML 分析器无法正确处理下面的代码行，因此，必须将别名创建为不包含嵌入空格的其他名称：</span><span class="sxs-lookup"><span data-stu-id="d957a-p103">Creating aliases for column names is required whenever a column name is not a legal attribute or tag name in XML. For example, "Last Name" must have an alias because names with embedded spaces are illegal attributes. The following line won't be correctly handled by the XML parser, so you must create an alias to some other name that does not have an embedded space:</span></span>

```xml 
 
<row last name="Jones"/> 
```

<span data-ttu-id="d957a-p104">无论对 **name** 属性使用什么值，都必须在 XML 文档的架构和数据节中引用该列的所有位置以一致的方式使用该值。以下示例演示如何以一致的方式使用 s1：</span><span class="sxs-lookup"><span data-stu-id="d957a-p104">Whatever value you use for the **name** attribute must be used consistently in each place that the column is referenced in both the schema and data sections of the XML document. The following example shows the consistent use of s1:</span></span>

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

<span data-ttu-id="d957a-119">同样，因为没有为上例的 CompanyName（公司名称）定义别名，所以必须在整个文档中以一致的方式使用 CompanyName（公司名称）。</span><span class="sxs-lookup"><span data-stu-id="d957a-119">Similarly, because there is no alias defined for CompanyName above, CompanyName must be used consistently throughout the document.</span></span>

## <a name="data-types"></a><span data-ttu-id="d957a-120">数据类型</span><span class="sxs-lookup"><span data-stu-id="d957a-120">Data Types</span></span>

<span data-ttu-id="d957a-p105">可以向具有 **dt:type** 属性的列应用数据类型。可以使用下列两种方法指定数据类型：直接针对列定义本身指定 **dt:type** 属性，或者将 **s:datatype** 结构用作列定义的嵌套元素。例如，</span><span class="sxs-lookup"><span data-stu-id="d957a-p105">You can apply a data type to a column with the **dt:type** attribute. You can specify a data type in two ways: either specify the **dt:type** attribute directly on the column definition itself or use the **s:datatype** construct as a nested element of the column definition. For example,</span></span>

```xml 
 
<s:AttributeType name="Phone" > 
  <s:datatype dt:type="string"/> 
</s:AttributeType> 
```

<span data-ttu-id="d957a-124">等效于</span><span class="sxs-lookup"><span data-stu-id="d957a-124">is equivalent to</span></span>

```xml 
 
<s:AttributeType name="Phone" dt:type="string"/> 
```

<span data-ttu-id="d957a-125">如果您在行定义中完全省略 **dt:type** 属性，则在默认情况下，列的类型将是可变长度的字符串。</span><span class="sxs-lookup"><span data-stu-id="d957a-125">If you omit the **dt:type** attribute entirely from the row definition, by default, the column's type will be a variable length string.</span></span>

<span data-ttu-id="d957a-p106">如果您的类型信息远不只是类型名称（例如，**dt:maxLength**），则使用 **s:datatype** 子元素会增强可读性。但是，这只是一个约定，不是必需的。</span><span class="sxs-lookup"><span data-stu-id="d957a-p106">If you have more type information than simply the type name (for example, **dt:maxLength**), it makes it more readable to use the **s:datatype** child element. This is merely a convention, however, and not a requirement.</span></span>

<span data-ttu-id="d957a-128">以下示例进一步演示如何在架构中包括类型信息：</span><span class="sxs-lookup"><span data-stu-id="d957a-128">The following examples show further how to include type information in your schema:</span></span>

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

<span data-ttu-id="d957a-129">在第二个示例中，巧妙地使用了 **rs:fixedlength** 属性。</span><span class="sxs-lookup"><span data-stu-id="d957a-129">There is a subtle use of the **rs:fixedlength** attribute in the second example.</span></span> <span data-ttu-id="d957a-130">**rs:fixedlength** 属性设置为 true 的列表示必须在架构中定义数据的长度。</span><span class="sxs-lookup"><span data-stu-id="d957a-130">A column with the **rs:fixedlength** attribute set to true means that the data must have the length defined in the schema.</span></span> <span data-ttu-id="d957a-131">法律在这种情况下，对于标题值\_id 是"123456，"按原样"123。"</span><span class="sxs-lookup"><span data-stu-id="d957a-131">In this case, a legal value for title\_id is "123456," as is "123 ."</span></span> <span data-ttu-id="d957a-132">但是，"123"将无效，因为它的长度为 3（而非 6）。</span><span class="sxs-lookup"><span data-stu-id="d957a-132">However, "123" would not be valid because its length is 3, not 6.</span></span> <span data-ttu-id="d957a-133">有关 **fixedlength** 属性的更完整说明，请参阅《OLE DB 程序员指南》。</span><span class="sxs-lookup"><span data-stu-id="d957a-133">See the OLE DB Programmer's Guide for a more complete description of the **fixedlength** property.</span></span>

## <a name="handling-nulls"></a><span data-ttu-id="d957a-134">处理 Null</span><span class="sxs-lookup"><span data-stu-id="d957a-134">Handling Nulls</span></span>

<span data-ttu-id="d957a-p108">Null 值由 **rs:maybenull** 属性进行处理。如果将此属性设置为 true，则该列的内容可能包含 null 值。而且，如果无法在数据行中找到该列，则从行集向后读取数据的用户将从 **IRowset::GetData()** 获得 null 状态。请考虑 Shippers（货主）表中下面的列定义：</span><span class="sxs-lookup"><span data-stu-id="d957a-p108">Null values are handled by the **rs:maybenull** attribute. If this attribute is set to true, the contents of the column may contain a null value. Furthermore, if the column is not found in a row of data, the user reading the data back from the rowset will get a null status from **IRowset::GetData()**. Consider the following column definitions from the Shippers table:</span></span>

```xml 
 
<s:AttributeType name="ShipperID"> 
  <s:datatype dt:type="int" dt:maxLength="4"/> 
</s:AttributeType> 
<s:AttributeType name="CompanyName"> 
  <s:datatype dt:type="string" dt:maxLength="40" rs:maybenull="true"/> 
</s:AttributeType> 
```

<span data-ttu-id="d957a-139">该定义允许 CompanyName（公司名称）为 null，但是 ShipperID（货主ID）不能包含 null 值。</span><span class="sxs-lookup"><span data-stu-id="d957a-139">The definition allows CompanyName to be null, but ShipperID cannot contain a null value.</span></span> <span data-ttu-id="d957a-140">如果数据部分包含以下行，Persistence Provider 将公司名称列的数据的状态设置为 OLE DB 状态常数 DBSTATUS\_S\_ISNULL:</span><span class="sxs-lookup"><span data-stu-id="d957a-140">If the data section contained the following row, the Persistence Provider would set the status of the data for the CompanyName column to the OLE DB status constant DBSTATUS\_S\_ISNULL:</span></span>

```xml 
 
<z:row ShipperID="1"/> 
```

<span data-ttu-id="d957a-141">如果该行是全部为空，，如下所示，Persistence Provider 将返回 OLE DB 状态的 DBSTATUS\_E\_不可用的 DBSTATUS 货主 Id\_S\_ISNULL 的公司名称。</span><span class="sxs-lookup"><span data-stu-id="d957a-141">If the row was entirely empty, as follows, the Persistence Provider would return an OLE DB status of DBSTATUS\_E\_UNAVAILABLE for ShipperID and DBSTATUS\_S\_ISNULL for CompanyName.</span></span>

```xml 
 
<z:row/>  
```

<span data-ttu-id="d957a-142">请注意，零长度字符串与 null 并不相同。</span><span class="sxs-lookup"><span data-stu-id="d957a-142">Note that a zero-length string is not the same as null.</span></span>

```xml 
 
<z:row ShipperID="1" CompanyName=""/> 
```

<span data-ttu-id="d957a-143">对于上述的行，Persistence Provider 将返回 OLE DB 状态的 DBSTATUS\_S\_确定两个列。</span><span class="sxs-lookup"><span data-stu-id="d957a-143">For the preceding row, the Persistence Provider will return an OLE DB status of DBSTATUS\_S\_OK for both columns.</span></span> <span data-ttu-id="d957a-144">在这种情况下，CompanyName（公司名称）只是 ""（零长度字符串）。</span><span class="sxs-lookup"><span data-stu-id="d957a-144">The CompanyName in this case is simply "" (a zero-length string).</span></span>

<span data-ttu-id="d957a-145">有关可用在 OLE DB XML 文档架构中的 OLE DB 结构的进一步信息，请参阅"urn:schemas-microsoft-com:rowset"的定义和《OLE DB 程序员指南》。</span><span class="sxs-lookup"><span data-stu-id="d957a-145">For further information about the OLE DB constructs available for use within the schema of an XML document for OLE DB, see the definition of "urn:schemas-microsoft-com:rowset" and the OLE DB Programmer's Guide.</span></span>

