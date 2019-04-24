---
title: 使用 Visual C++ Extensions
TOCTitle: Using Visual C++ Extensions
ms:assetid: 0fb1014c-7ab6-6add-d09f-e5e48b2b32cb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248866(v=office.15)
ms:contentKeyID: 48543270
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8bf2234e5935c2a1a13871e7e45c980fb9f33109
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312059"
---
# <a name="using-visual-c-extensions"></a><span data-ttu-id="0ef1b-102">使用 Visual C++ 扩展</span><span class="sxs-lookup"><span data-stu-id="0ef1b-102">Using Visual C++ Extensions</span></span>


<span data-ttu-id="0ef1b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0ef1b-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="the-iadorecordbinding-interface"></a><span data-ttu-id="0ef1b-104">IADORecordBinding 接口</span><span class="sxs-lookup"><span data-stu-id="0ef1b-104">The IADORecordBinding Interface</span></span>

<span data-ttu-id="0ef1b-p101">Microsoft Visual C++ Extensions for ADO 将 [Recordset](recordset-object-ado.md) 对象的字段关联或绑定到 C/C++ 变量。只要绑定的 **Recordset** 的当前行发生更改，则 **Recordset** 中的所有绑定字段都将复制到 C/C++ 变量。如有必要，复制的数据将转换为 C/C++ 变量的已声明数据类型。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p101">The Microsoft Visual C++ Extensions for ADO associate, or bind, fields of a [Recordset](recordset-object-ado.md) object to C/C++ variables. Whenever the current row of the bound **Recordset** changes, all the bound fields in the **Recordset** are copied to the C/C++ variables. If necessary, the copied data is converted to the declared data type of the C/C++ variable.</span></span>

<span data-ttu-id="0ef1b-p102">**IADORecordBinding** 接口的 **BindToRecordset** 方法将字段绑定到 C/C++ 变量。 **AddNew** 方法在绑定的 **Recordset** 中添加新的行。 **Update** 方法用 C/C++ 变量的值填充 **Recordset** 新行中的字段或更新现有行中的字段。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p102">The **BindToRecordset** method of the **IADORecordBinding** interface binds fields to C/C++ variables. The **AddNew** method adds a new row to the bound **Recordset**. The **Update** method populates fields in new rows of the **Recordset**, or updates fields in existing rows, with the value of the C/C++ variables.</span></span>

<span data-ttu-id="0ef1b-p103">**IADORecordBinding** 接口由 **Recordset** 对象实现。您无需自己编写实现代码。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p103">The **IADORecordBinding** interface is implemented by the **Recordset** object. You do not code the implementation yourself.</span></span>

## <a name="binding-entries"></a><span data-ttu-id="0ef1b-113">绑定项</span><span class="sxs-lookup"><span data-stu-id="0ef1b-113">Binding Entries</span></span>

<span data-ttu-id="0ef1b-p104">Visual C++ Extensions for ADO 将 [Recordset](recordset-object-ado.md) 对象的字段映射到 C/C++ 变量。字段与变量之间的映射的定义称为*绑定项*。宏为数值数据、定长数据和可变长度数据提供了绑定项。绑定项和 C/C++ 变量在派生自 Visual C++ Extensions 类 **CADORecordBinding** 的类中声明。**CADORecordBinding** 类由绑定项宏在内部定义。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p104">The Visual C++ Extensions for ADO map fields of a [Recordset](recordset-object-ado.md) object to C/C++ variables. The definition of a mapping between a field and a variable is called a *binding entry*. Macros provide binding entries for numeric, fixed-length, and variable-length data. The binding entries and C/C++ variables are declared in a class derived from the Visual C++ Extensions class, **CADORecordBinding**. The **CADORecordBinding** class is defined internally by the binding entry macros.</span></span>

<span data-ttu-id="0ef1b-p105">ADO 将这些宏中的参数内部映射到 OLE DB **DBBINDING** 结构，并创建一个 OLE DB **Accessor** 对象来管理字段与变量之间的数据移动和转换。OLE DB 将数据定义为包含以下三个部分：*缓冲区*，用于存储数据；*状态*，用于指示字段是否成功地存储在缓冲区中或变量应当如何还原为字段；数据的*长度*。（有关详细信息，请参阅 *《OLE DB 程序员参考》* 中的第 6 章“获取和设置数据”。）</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p105">ADO internally maps the parameters in these macros to an OLE DB **DBBINDING** structure and creates an OLE DB **Accessor** object to manage the movement and conversion of data between fields and variables. OLE DB defines data as consisting of three parts: A *buffer* where the data is stored; a *status* that indicates whether a field was successfully stored in the buffer, or how the variable should be restored to the field; and the *length* of the data. (See the *OLE DB Programmer's Reference*, Chapter 6: Getting and Setting Data for more information.)</span></span>

## <a name="header-file"></a><span data-ttu-id="0ef1b-122">头文件</span><span class="sxs-lookup"><span data-stu-id="0ef1b-122">Header File</span></span>

<span data-ttu-id="0ef1b-123">若要使用 Visual C++ Extensions for ADO，请在应用程序中包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="0ef1b-123">Include the following file in your application in order to use the Visual C++ Extensions for ADO:</span></span>

```cpp 
 
#include <icrsint.h> 
```

## <a name="binding-recordset-fields"></a><span data-ttu-id="0ef1b-124">绑定 Recordset 字段</span><span class="sxs-lookup"><span data-stu-id="0ef1b-124">Binding Recordset Fields</span></span>

<span data-ttu-id="0ef1b-125">**将 Recordset 字段绑定到 C/C++ 变量**</span><span class="sxs-lookup"><span data-stu-id="0ef1b-125">**To Bind Recordset Fields to C/C++ Variables**</span></span>

1.  <span data-ttu-id="0ef1b-126">创建一个派生自 **CADORecordBinding** 类的类。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-126">Create a class derived from the **CADORecordBinding** class.</span></span>

2.  <span data-ttu-id="0ef1b-127">在派生类中指定绑定项和相应的 C/C++ 变量。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-127">Specify binding entries and corresponding C/C++ variables in the derived class.</span></span> <span data-ttu-id="0ef1b-128">在**\_BEGIN ado\_binding**和**END\_ado\_绑定**宏之间括出绑定条目。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-128">Bracket the binding entries between **BEGIN\_ADO\_BINDING** and **END\_ADO\_BINDING** macros.</span></span> <span data-ttu-id="0ef1b-129">宏不要以逗号或冒号结束。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-129">Do not terminate the macros with commas or semicolons.</span></span> <span data-ttu-id="0ef1b-130">每个宏会自动指定适当的分隔符。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-130">Appropriate delimiters are specified automatically by each macro.</span></span> <span data-ttu-id="0ef1b-131">为要映射到 C/C++ 变量的每个字段指定一个绑定项。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-131">Specify one binding entry for each field to be mapped to a C/C++ variable.</span></span> <span data-ttu-id="0ef1b-132">使用**\_ado\_固定长度\_项**、 **ado\_数字\_条目**或**ado\_可变\_长度\_条目**族中的相应成员。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-132">Use an appropriate member from the **ADO\_FIXED\_LENGTH\_ENTRY**, **ADO\_NUMERIC\_ENTRY**, or **ADO\_VARIABLE\_LENGTH\_ENTRY** family of macros.</span></span>

3.  <span data-ttu-id="0ef1b-p107">在应用程序中，创建一个派生自 **CADORecordBinding** 类的类实例。从 **Recordset** 获取 **IADORecordBinding** 接口。然后调用 **BindToRecordset** 方法将 **Recordset** 字段绑定到 C/C++ 变量。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p107">In your application, create an instance of the class derived from **CADORecordBinding**. Get the **IADORecordBinding** interface from the **Recordset**. Then call the **BindToRecordset** method to bind the **Recordset** fields to the C/C++ variables.</span></span>

<span data-ttu-id="0ef1b-136">有关详细信息，请参阅 [Visual C++ Extensions 示例](visual-c-extensions-example.md)。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-136">See the [Visual C++ Extensions Example](visual-c-extensions-example.md) for more information.</span></span>

## <a name="interface-methods"></a><span data-ttu-id="0ef1b-137">接口方法</span><span class="sxs-lookup"><span data-stu-id="0ef1b-137">Interface Methods</span></span>

<span data-ttu-id="0ef1b-p108">**IADORecordBinding** 接口具有以下三个方法：**BindToRecordset**、**AddNew** 和 **Update**。每个方法的唯一参数是一个指向派生自 **CADORecordBinding** 的类的实例的指针。因此，**AddNew** 和 **Update** 方法不能指定与其同名的 ADO 方法的任何参数。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p108">The **IADORecordBinding** interface has three methods: **BindToRecordset**, **AddNew**, and **Update**. The sole argument to each method is a pointer to an instance of the class derived from **CADORecordBinding**. Therefore, the **AddNew** and **Update** methods cannot specify any of the parameters of their ADO method namesakes.</span></span>

<span data-ttu-id="0ef1b-141">**语法**</span><span class="sxs-lookup"><span data-stu-id="0ef1b-141">**Syntax**</span></span>

<span data-ttu-id="0ef1b-142">**BindToRecordset** 方法将 **Recordset** 字段与 C/C++ 变量关联。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-142">The **BindToRecordset** method associates the **Recordset** fields with C/C++ variables.</span></span>

`BindToRecordset(CADORecordBinding *binding)` 

<span data-ttu-id="0ef1b-143">**AddNew** 方法调用与其同名的 ADO [AddNew](addnew-method-ado.md) 方法，以在 **Recordset** 中添加新行。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-143">The **AddNew** method invokes its namesake, the ADO [AddNew](addnew-method-ado.md) method, to add a new row to the **Recordset**.</span></span>

`AddNew(CADORecordBinding *binding)` 

<span data-ttu-id="0ef1b-144">**Update** 方法调用与其同名的 ADO [Update](update-method-ado.md) 方法，以更新 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-144">The **Update** method invokes its namesake, the ADO [Update](update-method-ado.md) method, to update the **Recordset**.</span></span>

`Update(CADORecordBinding *binding)` 

## <a name="binding-entry-macros"></a><span data-ttu-id="0ef1b-145">绑定项宏</span><span class="sxs-lookup"><span data-stu-id="0ef1b-145">Binding Entry Macros</span></span>

<span data-ttu-id="0ef1b-p109">绑定项宏用于定义 **Recordset** 字段与变量的关联。各绑定项之间用开始宏和结束宏分隔。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p109">Binding entry macros define the association of a **Recordset** field and a variable. A beginning and ending macro delimits the set of binding entries.</span></span>

<span data-ttu-id="0ef1b-p110">对于定长数据（如 **adDate** 或 **adBoolean** ）、数值数据（如 **adTinyInt** 、 **adInteger** 或 **adDouble** ）和可变长度数据（如 **adChar** 、 **adVarChar** 或 **adVarBinary** ），均提供了宏系列。除 **adVarNumeric** 之外的所有数值类型也是定长类型。每个系列具有不同的参数集，以便您可以排除不感兴趣的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p110">Families of macros are provided for fixed-length data, such as **adDate** or **adBoolean**; numeric data, such as **adTinyInt**, **adInteger**, or **adDouble**; and variable-length data, such as **adChar**, **adVarChar** or **adVarBinary**. All numeric types, except for **adVarNumeric**, are also fixed-length types. Each family has differing sets of parameters so that you can exclude binding information that is of no interest.</span></span>

<span data-ttu-id="0ef1b-151">有关详细信息，请参阅 *《OLE DB 程序员参考》* 中的“附录 A：数据类型”。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-151">See the *OLE DB Programmer's Reference,* Appendix A: Data Types for additional information.</span></span>

<span data-ttu-id="0ef1b-152">_**开始绑定项**_</span><span class="sxs-lookup"><span data-stu-id="0ef1b-152">_**Begin Binding Entries**_</span></span>

<span data-ttu-id="0ef1b-153">**开始\_ADO\_绑定**(*类*)</span><span class="sxs-lookup"><span data-stu-id="0ef1b-153">**BEGIN\_ADO\_BINDING**(*Class*)</span></span>

<span data-ttu-id="0ef1b-154">_**定长数据**_</span><span class="sxs-lookup"><span data-stu-id="0ef1b-154">_**Fixed-Length Data**_</span></span>

<span data-ttu-id="0ef1b-155">**ADO\_固定\_长度\_项**(*序号、数据类型、缓冲区、状态、修改*)</span><span class="sxs-lookup"><span data-stu-id="0ef1b-155">**ADO\_FIXED\_LENGTH\_ENTRY**(*Ordinal, DataType, Buffer, Status, Modify*)</span></span>  
<span data-ttu-id="0ef1b-156">**ADO\_固定\_长度\_的 ENTRY2**(*序数、DataType、Buffer、Modify*)</span><span class="sxs-lookup"><span data-stu-id="0ef1b-156">**ADO\_FIXED\_LENGTH\_ENTRY2**(*Ordinal, DataType, Buffer, Modify*)</span></span>

<span data-ttu-id="0ef1b-157">_**数值数据**_</span><span class="sxs-lookup"><span data-stu-id="0ef1b-157">_**Numeric Data**_</span></span>

<span data-ttu-id="0ef1b-158">**ADO\_数字\_条目**(*序号、数据类型、缓冲区、精度、小数位数、状态、修改*)</span><span class="sxs-lookup"><span data-stu-id="0ef1b-158">**ADO\_NUMERIC\_ENTRY**(*Ordinal, DataType, Buffer, Precision, Scale, Status, Modify*)</span></span>  
<span data-ttu-id="0ef1b-159">**ADO\_数值\_ENTRY2**(*序数、DataType、Buffer、Precision、Scale、Modify*)</span><span class="sxs-lookup"><span data-stu-id="0ef1b-159">**ADO\_NUMERIC\_ENTRY2**(*Ordinal, DataType, Buffer, Precision, Scale, Modify*)</span></span>

<span data-ttu-id="0ef1b-160">_**可变长度数据**_</span><span class="sxs-lookup"><span data-stu-id="0ef1b-160">_**Variable-Length Data**_</span></span>

<span data-ttu-id="0ef1b-161">**ADO\_可变\_长度\_项**(*序号、数据类型、缓冲区、大小、状态、长度、修改*)</span><span class="sxs-lookup"><span data-stu-id="0ef1b-161">**ADO\_VARIABLE\_LENGTH\_ENTRY**(*Ordinal, DataType, Buffer, Size, Status, Length, Modify*)</span></span>  
<span data-ttu-id="0ef1b-162">**ADO\_变量\_长度\_ENTRY2**(*序号、DataType、缓冲区、大小、状态、修改*)</span><span class="sxs-lookup"><span data-stu-id="0ef1b-162">**ADO\_VARIABLE\_LENGTH\_ENTRY2**(*Ordinal, DataType, Buffer, Size, Status, Modify*)</span></span>  
<span data-ttu-id="0ef1b-163">**ADO\_变量\_长度\_ENTRY3**(*序数、DataType、Buffer、Size、LENGTH、Modify*)</span><span class="sxs-lookup"><span data-stu-id="0ef1b-163">**ADO\_VARIABLE\_LENGTH\_ENTRY3**(*Ordinal, DataType, Buffer, Size, Length, Modify*)</span></span>  
<span data-ttu-id="0ef1b-164">**ADO\_变量\_长度\_ENTRY4**(*序号、DataType、缓冲区、大小、修改*)</span><span class="sxs-lookup"><span data-stu-id="0ef1b-164">**ADO\_VARIABLE\_LENGTH\_ENTRY4**(*Ordinal, DataType, Buffer, Size, Modify*)</span></span>

<span data-ttu-id="0ef1b-165">_**结束绑定项**_</span><span class="sxs-lookup"><span data-stu-id="0ef1b-165">_**End Binding Entries**_</span></span>

<span data-ttu-id="0ef1b-166">**结束\_ADO\_绑定**()</span><span class="sxs-lookup"><span data-stu-id="0ef1b-166">**END\_ADO\_BINDING**()</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0ef1b-167">参数</span><span class="sxs-lookup"><span data-stu-id="0ef1b-167">Parameter</span></span></p></th>
<th><p><span data-ttu-id="0ef1b-168">描述</span><span class="sxs-lookup"><span data-stu-id="0ef1b-168">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-169"><em>Class</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-169"><em>Class</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-170">在其中定义绑定项和 C/C++ 变量的类。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-170">Class in which the binding entries and C/C++ variables are defined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-171"><em>Ordinal</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-171"><em>Ordinal</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-172">与 C/C++ 变量对应的 <strong>Recordset</strong> 字段的序号，从 1 开始计数。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-172">Ordinal number, counting from one, of the <strong>Recordset</strong> field corresponding to your C/C++ variable.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-173"><em>DataType</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-173"><em>DataType</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-p111">C/C++ 变量的等效 ADO 数据类型（有关有效数据类型的列表，请参阅 <a href="datatypeenum.md">DataTypeEnum</a>）。如有必要，<strong>Recordset</strong> 字段的值将转换为此数据类型。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-p111">Equivalent ADO data type of the C/C++ variable (see <a href="datatypeenum.md">DataTypeEnum</a> for a list of valid data types). The value of the <strong>Recordset</strong> field will be converted to this data type if necessary.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-176"><em>Buffer</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-176"><em>Buffer</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-177">存储 <strong>Recordset</strong> 字段的 C/C++ 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-177">Name of the C/C++ variable where the <strong>Recordset</strong> field will be stored.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-178"><em>Size</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-178"><em>Size</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-179"><em>Buffer</em> 的最大大小，以字节计。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-179">Maximum size in bytes of <em>Buffer</em>.</span></span> <span data-ttu-id="0ef1b-180">如果 <em>Buffer</em> 包含可变长度字符串，则还为终止字符零留出了空间。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-180">If <em>Buffer</em> will contain a variable-length string, allow room for a terminating zero.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-181"><em>Status</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-181"><em>Status</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-182">变量名称，用于指示 <em>Buffer</em> 的内容是否有效，以及字段是否成功转换为 <em>DataType</em>。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-182">Name of a variable that will indicate whether the contents of <em>Buffer</em> are valid, and whether the conversion of the field to <em>DataType</em> was successful.</span></span> <span data-ttu-id="0ef1b-183">此变量有两个最重要的值：一个是 <strong>adFldOK</strong>，表示转换成功；另一个是 <strong>adFldNull</strong>，表示字段的值为 VT_NULL 类型的 VARIANT，但不仅仅为空。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-183">The two most important values for this variable are <strong>adFldOK</strong>, which means the conversion was successful; and <strong>adFldNull</strong>, which means the value of the field would be a VARIANT of type VT_NULL and not merely empty.</span></span> <span data-ttu-id="0ef1b-184">"<em>状态</em>" 的可能值在下表中列出&quot;, 即 "status" 值。&quot;</span><span class="sxs-lookup"><span data-stu-id="0ef1b-184">Possible values for <em>Status</em> are listed in the next table, &quot;Status Values.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-185"><em>Modify</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-185"><em>Modify</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-186">布尔型标志。如果为 TRUE，则指示允许 ADO 用 <em>Buffer</em> 中所包含的值更新相应的 <strong>Recordset</strong> 字段。
</span><span class="sxs-lookup"><span data-stu-id="0ef1b-186">Boolean flag; if TRUE, indicates ADO is allowed to update the corresponding <strong>Recordset</strong> field with the value contained in <em>Buffer</em>.</span></span> <span data-ttu-id="0ef1b-187">如果要让 ADO 更新绑定字段，则将布尔型 <em>Modify</em> 参数设置为 TRUE。如果要检查字段但不进行更改，则设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-187">Set the Boolean <em>modify</em> parameter to TRUE to enable ADO to update the bound field, and FALSE if you want to examine the field but not change it.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-188"><em>精密</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-188"><em>Precision</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-189">可以用数值变量表示的数字位数。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-189">Number of digits that can be represented in a numeric variable.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-190"><em>小数位数</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-190"><em>Scale</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-191">用数值变量表示的小数位数。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-191">Number of decimal places in a numeric variable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-192"><em>Length</em></span><span class="sxs-lookup"><span data-stu-id="0ef1b-192"><em>Length</em></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-193">4 字节变量的名称，包含 <em>Buffer</em> 中数据的实际长度。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-193">Name of a four-byte variable that will contain the actual length of the data in <em>Buffer</em>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="status-values"></a><span data-ttu-id="0ef1b-194">状态值</span><span class="sxs-lookup"><span data-stu-id="0ef1b-194">Status Values</span></span>

<span data-ttu-id="0ef1b-195">*Status* 变量的值用于指示字段是否成功复制到变量。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-195">The value of the *Status* variable indicates whether a field was successfully copied to a variable.</span></span>

<span data-ttu-id="0ef1b-196">在设置数据时，*Status* 可以设置为 **adFldNull**，以指示 **Recordset** 字段应设置为 Null。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-196">When setting data, *Status* may be set to **adFldNull** to indicate the **Recordset** field should be set to null.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0ef1b-197">常量</span><span class="sxs-lookup"><span data-stu-id="0ef1b-197">Constant</span></span></p></th>
<th><p><span data-ttu-id="0ef1b-198">值</span><span class="sxs-lookup"><span data-stu-id="0ef1b-198">Value</span></span></p></th>
<th><p><span data-ttu-id="0ef1b-199">说明</span><span class="sxs-lookup"><span data-stu-id="0ef1b-199">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-200"><strong>adFldOK</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-200"><strong>adFldOK</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-201">0</span><span class="sxs-lookup"><span data-stu-id="0ef1b-201">0</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-202">返回非 Null 字段值。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-202">A non-null field value was returned.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-203"><strong>adFldBadAccessor</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-203"><strong>adFldBadAccessor</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-204">1</span><span class="sxs-lookup"><span data-stu-id="0ef1b-204">1</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-205">绑定无效。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-205">Binding was invalid.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-206"><strong>adFldCantConvertValue</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-206"><strong>adFldCantConvertValue</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-207">双面</span><span class="sxs-lookup"><span data-stu-id="0ef1b-207">2</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-208">由于符号不匹配或数据溢出之外的原因，值无法转换。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-208">Value couldn't be converted for reasons other than sign mismatch or data overflow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-209"><strong>adFldNull</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-209"><strong>adFldNull</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-210">第三章</span><span class="sxs-lookup"><span data-stu-id="0ef1b-210">3</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-211">在获取字段时，指示返回空值。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-211">When getting a field, indicates a null value was returned.</span></span> <span data-ttu-id="0ef1b-212">在设置字段时，指示当字段自身无法编码 <strong>NULL</strong>（如一个字符数组或整数）时字段应设置为 <strong>NULL</strong>。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-212">When setting a field, indicates the field should be set to <strong>NULL</strong> when the field cannot encode <strong>NULL</strong> itself (for example, a character array or an integer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-213"><strong>adFldTruncated</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-213"><strong>adFldTruncated</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-214">4</span><span class="sxs-lookup"><span data-stu-id="0ef1b-214">4</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-215">截断可变长度数据或数字。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-215">Variable-length data or numeric digits were truncated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-216"><strong>adFldSignMismatch</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-216"><strong>adFldSignMismatch</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-217">5</span><span class="sxs-lookup"><span data-stu-id="0ef1b-217">5</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-218">值有符号，变量数据类型无符号。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-218">Value is signed and variable data type is unsigned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-219"><strong>adFldDataOverFlow</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-219"><strong>adFldDataOverFlow</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-220">型</span><span class="sxs-lookup"><span data-stu-id="0ef1b-220">6</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-221">值大于变量数据类型中可存储的大小。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-221">Value is larger than could be stored in the variable data type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-222"><strong>adFldCantCreate</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-222"><strong>adFldCantCreate</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-223">步</span><span class="sxs-lookup"><span data-stu-id="0ef1b-223">7</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-224">打开了未知的列类型和字段。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-224">Unknown column type and field already open.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-225"><strong>adFldUnavailable</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-225"><strong>adFldUnavailable</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-226">utf-8</span><span class="sxs-lookup"><span data-stu-id="0ef1b-226">8</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-227">无法确定字段值 - 例如，在一个无默认值的新的未赋值字段上。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-227">Field value could not be determined — for example, on a new, unassigned field with no default value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-228"><strong>adFldPermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-228"><strong>adFldPermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-229">第</span><span class="sxs-lookup"><span data-stu-id="0ef1b-229">9</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-230">更新时，无权写数据。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-230">When updating, no permission to write data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-231"><strong>adFldIntegrityViolation</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-231"><strong>adFldIntegrityViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-232">10</span><span class="sxs-lookup"><span data-stu-id="0ef1b-232">10</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-233">更新时，字段值与列完整性冲突。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-233">When updating, field value would violate column integrity.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-234"><strong>adFldSchemaViolation</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-234"><strong>adFldSchemaViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-235">11x17</span><span class="sxs-lookup"><span data-stu-id="0ef1b-235">11</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-236">更新时，字段值与列架构冲突。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-236">When updating, field value would violate column schema.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ef1b-237"><strong>adFldBadStatus</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-237"><strong>adFldBadStatus</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-238">12</span><span class="sxs-lookup"><span data-stu-id="0ef1b-238">12</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-239">更新时，状态参数无效。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-239">When updating, invalid status parameter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ef1b-240"><strong>adFldDefault</strong></span><span class="sxs-lookup"><span data-stu-id="0ef1b-240"><strong>adFldDefault</strong></span></span></p></td>
<td><p><span data-ttu-id="0ef1b-241">13</span><span class="sxs-lookup"><span data-stu-id="0ef1b-241">13</span></span></p></td>
<td><p><span data-ttu-id="0ef1b-242">更新时，使用默认值。</span><span class="sxs-lookup"><span data-stu-id="0ef1b-242">When updating, a default value was used.</span></span></p></td>
</tr>
</tbody>
</table>

