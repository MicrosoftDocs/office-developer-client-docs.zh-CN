---
title: Field 对象 （访问桌面数据库参考 （英文）
TOCTitle: The Field Object
ms:assetid: 55531e04-d74f-6394-df64-1660e5d572ca
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249284(v=office.15)
ms:contentKeyID: 48544926
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b6841eb674aac04b979623a65b27ca84a8bc927c
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937143"
---
# <a name="field-object"></a><span data-ttu-id="a0795-102">Field 对象</span><span class="sxs-lookup"><span data-stu-id="a0795-102">Field Object</span></span>


<span data-ttu-id="a0795-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a0795-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a0795-p101">每个 **Field** 对象通常对应于数据库表中的一列。但是， **Field** 还可以表示指向另一个 **Recordset** 的指针，称为章节。本指南随后将介绍例外，例如章节列。</span><span class="sxs-lookup"><span data-stu-id="a0795-p101">Each **Field** object usually corresponds to a column in a database table. However, a **Field** can also represent a pointer to another **Recordset**, called a chapter. Exceptions, such as chapter columns, will be covered later in this guide.</span></span>

<span data-ttu-id="a0795-p102">使用 **Field** 对象的 **Value** 属性可以设置或返回当前记录的数据。取决于提供程序所公开的功能， **Field** 对象的某些集合、方法或属性可能不可用。</span><span class="sxs-lookup"><span data-stu-id="a0795-p102">Use the **Value** property of **Field** objects to set or return data for the current record. Depending on the functionality the provider exposes, some collections, methods, or properties of a **Field** object may not be available.</span></span>

<span data-ttu-id="a0795-109">使用 **Field** 对象的集合、方法和属性，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a0795-109">With the collections, methods, and properties of a **Field** object, you can do the following:</span></span>

  - <span data-ttu-id="a0795-110">通过使用 **Name** 属性返回字段的名称。</span><span class="sxs-lookup"><span data-stu-id="a0795-110">Return the name of a field by using the **Name** property.</span></span>

  - <span data-ttu-id="a0795-p103">通过使用 **Value** 属性查看或更改字段中的数据。 **Value** 是 **Field** 对象的默认属性。</span><span class="sxs-lookup"><span data-stu-id="a0795-p103">View or change the data in the field by using the **Value** property. **Value** is the default property of the **Field** object.</span></span>

  - <span data-ttu-id="a0795-113">通过使用 **Type** 、 **Precision** 和 **NumericScale** 属性，返回字段的基本特征。</span><span class="sxs-lookup"><span data-stu-id="a0795-113">Return the basic characteristics of a field by using the **Type**, **Precision**, and **NumericScale** properties.</span></span>

  - <span data-ttu-id="a0795-114">通过使用 **DefinedSize** 属性，返回字段的声明大小。</span><span class="sxs-lookup"><span data-stu-id="a0795-114">Return the declared size of a field by using the **DefinedSize** property.</span></span>

  - <span data-ttu-id="a0795-115">通过使用 **ActualSize** 属性，返回给定字段中数据的实际大小。</span><span class="sxs-lookup"><span data-stu-id="a0795-115">Return the actual size of the data in a given field by using the **ActualSize** property.</span></span>

  - <span data-ttu-id="a0795-116">通过使用 **Attributes** 属性和 **Properties** 集合，确定给定字段所支持的功能类型。</span><span class="sxs-lookup"><span data-stu-id="a0795-116">Determine what types of functionality are supported for a given field by using the **Attributes** property and **Properties** collection.</span></span>

  - <span data-ttu-id="a0795-117">通过使用 **AppendChunk** 和 **GetChunk** 方法，对包含长二进制或长字符数据的字段中的值进行操作。</span><span class="sxs-lookup"><span data-stu-id="a0795-117">Manipulate the values of fields containing long binary or long character data by using the **AppendChunk** and **GetChunk** methods.</span></span>

<span data-ttu-id="a0795-118">通过使用 **OriginalValue** 和 **UnderlyingValue** 属性，在批更新期间解析字段值中的误差（如果提供程序支持批更新）。</span><span class="sxs-lookup"><span data-stu-id="a0795-118">Resolve discrepancies in field values during batch updating by using the **OriginalValue** and **UnderlyingValue** properties, if the provider supports batch updates.</span></span>

## <a name="describing-a-field"></a><span data-ttu-id="a0795-119">描述字段</span><span class="sxs-lookup"><span data-stu-id="a0795-119">Describing a Field</span></span>

<span data-ttu-id="a0795-p104">后面的主题将讨论 [Field](field-object-ado.md) 对象的属性，这些属性提供了描述 **Field** 对象本身的信息 - 即有关字段的元数据。此信息可以用来确定有关 **Recordset** 架构的很多信息。这些属性包括 **Type** 、 **DefinedSize** 和 **ActualSize** 、 **Name** 以及 **NumericScale** 和 **Precision** 。</span><span class="sxs-lookup"><span data-stu-id="a0795-p104">The topics that follow will discuss properties of the [Field](field-object-ado.md) object that represent information that describes the **Field** object itself — that is, metadata about the field. This information can be used to determine much about the schema of the **Recordset**. These properties include **Type**, **DefinedSize** and **ActualSize**, **Name**, and **NumericScale** and **Precision**.</span></span>

## <a name="discovering-the-data-type"></a><span data-ttu-id="a0795-123">发现数据类型</span><span class="sxs-lookup"><span data-stu-id="a0795-123">Discovering the Data Type</span></span>

<span data-ttu-id="a0795-124">**Type** 属性用于指示字段的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a0795-124">The **Type** property indicates the data type of the field.</span></span> <span data-ttu-id="a0795-125">[DataTypeEnum](datatypeenum.md) *ADO 程序员参考*中描述了 ADO 支持的数据类型枚举常量。</span><span class="sxs-lookup"><span data-stu-id="a0795-125">The data type enumerated constants that are supported by ADO are described in [DataTypeEnum](datatypeenum.md) in the *ADO programmer's reference*.</span></span>

<span data-ttu-id="a0795-p106">有关 **adNumeric** 这样的浮点数值类型，可以获得其详细信息。 **NumericScale** 属性指示将用小数点右侧的多少位数来表示 **Field** 的值。 **Precision** 属性则指定用来表示 **Field** 值的最大位数。</span><span class="sxs-lookup"><span data-stu-id="a0795-p106">For floating point numeric types such **adNumeric**, you can obtain more information. The **NumericScale** property indicates how many digits to the right of the decimal point will be used to represent values for the **Field**. The **Precision** property specifies the maximum number of digits used to represent values for the **Field**.</span></span>

## <a name="determining-field-size"></a><span data-ttu-id="a0795-129">确定字段大小</span><span class="sxs-lookup"><span data-stu-id="a0795-129">Determining Field Size</span></span>

<span data-ttu-id="a0795-130">使用 **DefinedSize** 属性可以确定 **Field** 对象的数据容量。</span><span class="sxs-lookup"><span data-stu-id="a0795-130">Use the **DefinedSize** property to determine the data capacity of a **Field** object.</span></span>

<span data-ttu-id="a0795-p107">使用 **ActualSize** 属性可以返回 **Field** 对象值的实际长度。对于所有字段， **ActualSize** 属性都是只读的。如果 ADO 无法确定 **Field** 对象值的长度， **ActualSize** 属性将返回 **adUnknown** 。</span><span class="sxs-lookup"><span data-stu-id="a0795-p107">Use the **ActualSize** property to return the actual length of a **Field** object's value. For all fields, the **ActualSize** property is read-only. If ADO cannot determine the length of the **Field** object's value, the **ActualSize** property returns **adUnknown**.</span></span>

<span data-ttu-id="a0795-p108">**DefinedSize** 和 **ActualSize** 属性有不同的用途。例如，假设 **Field** 对象有声明类型 **adVarChar** 以及值为 50 的 **DefinedSize** 属性，其中包含单个字符。则它返回的 **ActualSize** 属性值是单个字符的字节长度。</span><span class="sxs-lookup"><span data-stu-id="a0795-p108">The **DefinedSize** and **ActualSize** properties have different purposes. For example, consider a **Field** object with a declared type of **adVarChar** and a **DefinedSize** property value of 50, containing a single character. The **ActualSize** property value it returns is the length in bytes of the single character.</span></span>

## <a name="determining-field-contents"></a><span data-ttu-id="a0795-137">确定字段内容</span><span class="sxs-lookup"><span data-stu-id="a0795-137">Determining Field Contents</span></span>

<span data-ttu-id="a0795-p109">数据源中的列的标识符是由 **Field** 的 **Name** 属性表示的。 **Field** 对象的 **Value** 属性返回或设置字段的实际数据内容。这是默认属性。</span><span class="sxs-lookup"><span data-stu-id="a0795-p109">The identifier of the column from the data source is represented by the **Name** property of the **Field**. The **Value** property of the **Field** object returns or sets the actual data content of the field. This is the default property.</span></span>

<span data-ttu-id="a0795-p110">若要更改字段中的数据，请将 **Value** 属性设置为等于正确类型的新值。游标类型必须支持更新，才能更改字段内容。在批模式下，不在这里进行数据库验证，因此在这种情况下需要在调用 **UpdateBatch** 时检查是否有错误。某些提供程序还支持 ADO **Field** 对象的 **UnderlyingValue** 和 **OriginalValue** 属性，以便在您试图执行批更新时帮助您解决冲突。有关如何解决这类冲突的详细信息，请参阅 [第 4 章：编辑数据](chapter-4-editing-data.md)。</span><span class="sxs-lookup"><span data-stu-id="a0795-p110">To change the data in a field, set the **Value** property equal to a new value of the correct type. Your cursor type must support updates to change the contents of a field. Database validation is not done here in batch mode, so you will need to check for errors when you call **UpdateBatch** in such a case. Some providers also support the ADO **Field** object's **UnderlyingValue** and **OriginalValue** properties to assist you with resolving conflicts when you attempt to perform batch updates. For details about how to resolve such conflicts, see [Chapter 4: Editing Data](chapter-4-editing-data.md).</span></span>


> [!NOTE]
> <P><span data-ttu-id="a0795-p111">[!注释] 将新的 <STRONG>Fields</STRONG> 追加到 <STRONG>Recordset</STRONG> 时不能设置 <STRONG>Recordset Field</STRONG> 值，但可以将新的 <STRONG>Fields</STRONG> 追加到已关闭的 <STRONG>Recordset</STRONG> 。然后，必须打开 <STRONG>Recordset</STRONG> ，只有这时才能将值赋给这些 <STRONG>Fields</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="a0795-p111"><STRONG>Recordset Field</STRONG> values cannot be set when appending new <STRONG>Fields</STRONG> to a <STRONG>Recordset</STRONG>. Rather, new <STRONG>Fields</STRONG> can be appended to a closed <STRONG>Recordset</STRONG>. Then the <STRONG>Recordset</STRONG> must be opened, and only then can values be assigned to these <STRONG>Fields</STRONG>.</span></span></P>



## <a name="getting-more-field-information"></a><span data-ttu-id="a0795-149">获取更多字段信息</span><span class="sxs-lookup"><span data-stu-id="a0795-149">Getting More Field Information</span></span>

<span data-ttu-id="a0795-p112">ADO 对象有两种类型的属性：内置和动态。到目前为止，只讨论了 **Field** 对象的内置属性。</span><span class="sxs-lookup"><span data-stu-id="a0795-p112">ADO objects have two types of properties: built-in and dynamic. To this point, only the built-in properties of the **Field** object have been discussed.</span></span>

<span data-ttu-id="a0795-152">内置属性是这些属性在 ADO 中实现并且立即可用到任何新的对象，使用语法。</span><span class="sxs-lookup"><span data-stu-id="a0795-152">Built-in properties are those properties implemented in ADO and immediately available to any new object, using the syntax.</span></span> <span data-ttu-id="a0795-153">内置属性不会作为 **Property** 对象出现在对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="a0795-153">They do not appear as **Property** objects in an object's **Properties** collection.</span></span>

<span data-ttu-id="a0795-154">动态属性是由基础数据提供程序定义的，它们出现在相应的 ADO 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="a0795-154">Dynamic properties are defined by the underlying data provider, and appear in the **Properties** collection for the appropriate ADO object.</span></span> <span data-ttu-id="a0795-155">例如，特定于提供程序的属性可以指示 **Recordset** 对象是否支持事务或更新。</span><span class="sxs-lookup"><span data-stu-id="a0795-155">For example, a property specific to the provider may indicate if a **Recordset** object supports transactions or updating.</span></span> <span data-ttu-id="a0795-156">这些额外的属性将作为 **Property** 对象出现在 **Recordset** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="a0795-156">These additional properties will appear as **Property** objects in that **Recordset** object's **Properties** collection.</span></span> <span data-ttu-id="a0795-157">动态属性可以仅通过集合，并使用语法 MyObject.Properties(0) 引用或 MyObject.Properties("Name")。</span><span class="sxs-lookup"><span data-stu-id="a0795-157">Dynamic properties can be referenced only through the collection, using the syntax MyObject.Properties(0) or or MyObject.Properties("Name") .</span></span>

<span data-ttu-id="a0795-158">这两种属性都是不可删除的。</span><span class="sxs-lookup"><span data-stu-id="a0795-158">You cannot delete either kind of property.</span></span>

<span data-ttu-id="a0795-159">动态 **Property** 对象有四个它自己的内置属性：</span><span class="sxs-lookup"><span data-stu-id="a0795-159">A dynamic **Property** object has four built-in properties of its own:</span></span>

  - <span data-ttu-id="a0795-160">**Name** 属性是用于标识该属性的字符串。</span><span class="sxs-lookup"><span data-stu-id="a0795-160">The **Name** property is a string that identifies the property.</span></span>

  - <span data-ttu-id="a0795-161">**Type** 属性是用于指定属性数据类型的整数。</span><span class="sxs-lookup"><span data-stu-id="a0795-161">The **Type** property is an integer that specifies the property data type.</span></span>

  - <span data-ttu-id="a0795-p115">**Value** 属性是包含属性设置的变量型。 **Value** 是 **Property** 对象的默认属性。</span><span class="sxs-lookup"><span data-stu-id="a0795-p115">The **Value** property is a variant that contains the property setting. **Value** is the default property for a **Property** object.</span></span>

  - <span data-ttu-id="a0795-164">**Attributes** 属性是 **Long** 值，用于指示特定于提供程序的属性的特征。</span><span class="sxs-lookup"><span data-stu-id="a0795-164">The **Attributes** property is a **Long** value that indicates characteristics of the property specific to the provider.</span></span>

<span data-ttu-id="a0795-p116">**Field** 对象的 **Properties** 集合包含有关字段的其他元数据。此集合的内容因提供程序而异。以下代码示例将检查本章开头引入的示例 **Recordset** 的 **Properties** 集合。它首先查看集合的内容。此代码使用 [OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md)，因此 **Properties** 集合包含该提供程序的相关信息。</span><span class="sxs-lookup"><span data-stu-id="a0795-p116">The **Properties** collection for the **Field** object contains additional metadata about the field. The contents of this collection vary depending upon the provider. The following code example examines the **Properties** collection of the sample **Recordset** introduced at the beginning of this chapter. It first looks at the contents of the collection. This code uses the [OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md), so the **Properties** collection contains information relevant to that provider.</span></span>

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

## <a name="dealing-with-binary-data"></a><span data-ttu-id="a0795-170">处理二进制数据</span><span class="sxs-lookup"><span data-stu-id="a0795-170">Dealing with Binary Data</span></span>

<span data-ttu-id="a0795-p117">使用 [Field](appendchunk-method-ado.md) 对象的 **AppendChunk** 方法可以用长二进制或字符数据来填充该对象。在系统内存有限的情况下，可以使用 **AppendChunk** 方法将长整型值作为几个部分进行操作，而不是作为整体来操作它们。</span><span class="sxs-lookup"><span data-stu-id="a0795-p117">Use the [AppendChunk](appendchunk-method-ado.md) method on a **Field** object to fill it with long binary or character data. In situations where system memory is limited, you can use the **AppendChunk** method to manipulate long values in portions rather than in their entirety.</span></span>

<span data-ttu-id="a0795-173">如果将 **Field** 对象的 **Attributes** 属性中的 **adFldLong** 位设置为 **True** ，则可以对该字段使用 **AppendChunk** 方法。</span><span class="sxs-lookup"><span data-stu-id="a0795-173">If the **adFldLong** bit in the **Attributes** property of a **Field** object is set to **True**, you can use the **AppendChunk** method for that field.</span></span>

<span data-ttu-id="a0795-p118">对 **Field** 对象第一次调用 **AppendChunk** 时，将数据写入字段，覆盖所有现有数据。之后调用 **AppendChunk** 时，在现有数据基础上进行添加。如果将数据追加到某个字段，然后设置或读取当前记录中另一个字段的值，那么 ADO 会假设您已完成了对第一个字段的数据追加。此时如果对第一个字段再次调用 **AppendChunk** 方法，则 ADO 会将调用解释为新的 **AppendChunk** 操作并覆盖现有数据。访问并非第一个 **Recordset** 对象克隆的其他 **Recordset** 对象中的字段时，不会中断 **AppendChunk** 操作。</span><span class="sxs-lookup"><span data-stu-id="a0795-p118">The first **AppendChunk** call on a **Field** object writes data to the field, overwriting any existing data. Subsequent **AppendChunk** calls add to existing data. If you are appending data to one field and then you set or read the value of another field in the current record, ADO assumes that you are finished appending data to the first field. If you call the **AppendChunk** method on the first field again, ADO interprets the call as a new **AppendChunk** operation and overwrites the existing data. Accessing fields in other **Recordset** objects that are not clones of the first **Recordset** object will not disrupt **AppendChunk** operations.</span></span>

<span data-ttu-id="a0795-p119">对 **Field** 对象使用 **GetChunk** 方法可以检索其部分或全部长整型二进制数据或字符数据。如果系统内存有限，则可以使用 **GetChunk** 方法对部分（而不是全部）长整型值进行操作。</span><span class="sxs-lookup"><span data-stu-id="a0795-p119">Use the **GetChunk** method on a **Field** object to retrieve part or all of its long binary or character data. In situations where system memory is limited, you can use the **GetChunk** method to manipulate long values in portions, rather than in their entirety.</span></span>

<span data-ttu-id="a0795-p120">**GetChunk** 调用返回的数据会分配给*变量*。如果 *Size* 大于剩余的数据，则 **GetChunk** 方法仅返回剩余的数据，而不会使用空格来填充*变量*。如果字段空白，则 **GetChunk** 方法返回一个 Null 值。</span><span class="sxs-lookup"><span data-stu-id="a0795-p120">The data that a **GetChunk** call returns is assigned to *variable*. If *Size* is greater than the remaining data, the **GetChunk** method returns only the remaining data without padding *variable* with empty spaces. If the field is empty, the **GetChunk** method returns a null value.</span></span>

<span data-ttu-id="a0795-p121">在随后每次调用 **GetChunk** 时，将从上一个 **GetChunk** 调用的离开位置开始检索数据。但是，如果正在从一个字段检索数据，然后设置或读取了当前记录中另一个字段的值，则 ADO 会假设您已经完成从第一个字段检索数据的操作。如果再次对第一个字段调用 **GetChunk** 方法，ADO 会将该调用解释为新的 **GetChunk** 操作，并开始从数据的开头进行读取。在访问其他 **Recordset** 对象的字段时，如果该对象不是第一个 **Recordset** 对象的克隆，则不会中断 **GetChunk** 操作。</span><span class="sxs-lookup"><span data-stu-id="a0795-p121">Each subsequent **GetChunk** call retrieves data starting from where the previous **GetChunk** call left off. However, if you are retrieving data from one field and then set or read the value of another field in the current record, ADO assumes you have finished retrieving data from the first field. If you call the **GetChunk** method on the first field again, ADO interprets the call as a new **GetChunk** operation and starts reading from the beginning of the data. Accessing fields in other **Recordset** objects that are not clones of the first **Recordset** object will not disrupt **GetChunk** operations.</span></span>

<span data-ttu-id="a0795-188">如果将 **Field** 对象的 **Attributes** 属性的 **adFldLong** 位设置为 **True** ，则可以对该字段使用 **GetChunk** 方法。</span><span class="sxs-lookup"><span data-stu-id="a0795-188">If the **adFldLong** bit in the **Attributes** property of a **Field** object is set to **True**, you can use the **GetChunk** method for that field.</span></span>

<span data-ttu-id="a0795-189">在使用 **Field** 对象的 **GetChunk** 或 **AppendChunk** 方法时，如果没有当前记录，则会发生错误 3021（无当前记录）。</span><span class="sxs-lookup"><span data-stu-id="a0795-189">If there is no current record when you use the **GetChunk** or **AppendChunk** method on a **Field** object, error 3021 (no current record) occurs.</span></span>

<span data-ttu-id="a0795-190">有关使用这些方法以操作二进制数据的示例，请参阅*ADO 程序员参考*中的[AppendChunk 方法](appendchunk-method-ado.md)和[GetChunk 方法](getchunk-method-ado.md)示例。</span><span class="sxs-lookup"><span data-stu-id="a0795-190">For an example of using these methods to manipulate binary data, see the [AppendChunk Method](appendchunk-method-ado.md) and [GetChunk Method](getchunk-method-ado.md) examples in the *ADO programmer's reference*.</span></span>

