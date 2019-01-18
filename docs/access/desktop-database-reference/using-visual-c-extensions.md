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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713777"
---
# <a name="using-visual-c-extensions"></a><span data-ttu-id="26f10-102">使用 Visual C++ Extensions</span><span class="sxs-lookup"><span data-stu-id="26f10-102">Using Visual C++ Extensions</span></span>


<span data-ttu-id="26f10-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="26f10-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="the-iadorecordbinding-interface"></a><span data-ttu-id="26f10-104">IADORecordBinding 接口</span><span class="sxs-lookup"><span data-stu-id="26f10-104">The IADORecordBinding Interface</span></span>

<span data-ttu-id="26f10-p101">Microsoft Visual C++ Extensions for ADO 将 [Recordset](recordset-object-ado.md) 对象的字段关联或绑定到 C/C++ 变量。只要绑定的 **Recordset** 的当前行发生更改，则 **Recordset** 中的所有绑定字段都将复制到 C/C++ 变量。如有必要，复制的数据将转换为 C/C++ 变量的已声明数据类型。</span><span class="sxs-lookup"><span data-stu-id="26f10-p101">The Microsoft Visual C++ Extensions for ADO associate, or bind, fields of a [Recordset](recordset-object-ado.md) object to C/C++ variables. Whenever the current row of the bound **Recordset** changes, all the bound fields in the **Recordset** are copied to the C/C++ variables. If necessary, the copied data is converted to the declared data type of the C/C++ variable.</span></span>

<span data-ttu-id="26f10-p102">**IADORecordBinding** 接口的 **BindToRecordset** 方法将字段绑定到 C/C++ 变量。 **AddNew** 方法在绑定的 **Recordset** 中添加新的行。 **Update** 方法用 C/C++ 变量的值填充 **Recordset** 新行中的字段或更新现有行中的字段。</span><span class="sxs-lookup"><span data-stu-id="26f10-p102">The **BindToRecordset** method of the **IADORecordBinding** interface binds fields to C/C++ variables. The **AddNew** method adds a new row to the bound **Recordset**. The **Update** method populates fields in new rows of the **Recordset**, or updates fields in existing rows, with the value of the C/C++ variables.</span></span>

<span data-ttu-id="26f10-p103">**IADORecordBinding** 接口由 **Recordset** 对象实现。您无需自己编写实现代码。</span><span class="sxs-lookup"><span data-stu-id="26f10-p103">The **IADORecordBinding** interface is implemented by the **Recordset** object. You do not code the implementation yourself.</span></span>

## <a name="binding-entries"></a><span data-ttu-id="26f10-113">绑定项</span><span class="sxs-lookup"><span data-stu-id="26f10-113">Binding Entries</span></span>

<span data-ttu-id="26f10-p104">Visual C++ Extensions for ADO 将 [Recordset](recordset-object-ado.md) 对象的字段映射到 C/C++ 变量。字段与变量之间的映射的定义称为*绑定项*。宏为数值数据、定长数据和可变长度数据提供了绑定项。绑定项和 C/C++ 变量在派生自 Visual C++ Extensions 类 **CADORecordBinding** 的类中声明。**CADORecordBinding** 类由绑定项宏在内部定义。</span><span class="sxs-lookup"><span data-stu-id="26f10-p104">The Visual C++ Extensions for ADO map fields of a [Recordset](recordset-object-ado.md) object to C/C++ variables. The definition of a mapping between a field and a variable is called a *binding entry*. Macros provide binding entries for numeric, fixed-length, and variable-length data. The binding entries and C/C++ variables are declared in a class derived from the Visual C++ Extensions class, **CADORecordBinding**. The **CADORecordBinding** class is defined internally by the binding entry macros.</span></span>

<span data-ttu-id="26f10-p105">ADO 将这些宏中的参数内部映射到 OLE DB **DBBINDING** 结构，并创建一个 OLE DB **Accessor** 对象来管理字段与变量之间的数据移动和转换。OLE DB 将数据定义为包含以下三个部分：*缓冲区*，用于存储数据；*状态*，用于指示字段是否成功地存储在缓冲区中或变量应当如何还原为字段；数据的*长度*。（有关详细信息，请参阅 *《OLE DB 程序员参考》* 中的第 6 章“获取和设置数据”。）</span><span class="sxs-lookup"><span data-stu-id="26f10-p105">ADO internally maps the parameters in these macros to an OLE DB **DBBINDING** structure and creates an OLE DB **Accessor** object to manage the movement and conversion of data between fields and variables. OLE DB defines data as consisting of three parts: A *buffer* where the data is stored; a *status* that indicates whether a field was successfully stored in the buffer, or how the variable should be restored to the field; and the *length* of the data. (See the *OLE DB Programmer's Reference*, Chapter 6: Getting and Setting Data for more information.)</span></span>

## <a name="header-file"></a><span data-ttu-id="26f10-122">头文件</span><span class="sxs-lookup"><span data-stu-id="26f10-122">Header File</span></span>

<span data-ttu-id="26f10-123">若要使用 Visual C++ Extensions for ADO，请在应用程序中包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="26f10-123">Include the following file in your application in order to use the Visual C++ Extensions for ADO:</span></span>

```cpp 
 
#include <icrsint.h> 
```

## <a name="binding-recordset-fields"></a><span data-ttu-id="26f10-124">绑定 Recordset 字段</span><span class="sxs-lookup"><span data-stu-id="26f10-124">Binding Recordset Fields</span></span>

<span data-ttu-id="26f10-125">**将 Recordset 字段绑定到 C/C++ 变量**</span><span class="sxs-lookup"><span data-stu-id="26f10-125">**To Bind Recordset Fields to C/C++ Variables**</span></span>

1.  <span data-ttu-id="26f10-126">创建一个派生自 **CADORecordBinding** 类的类。</span><span class="sxs-lookup"><span data-stu-id="26f10-126">Create a class derived from the **CADORecordBinding** class.</span></span>

2.  <span data-ttu-id="26f10-127">在派生类中指定绑定项和相应的 C/C++ 变量。</span><span class="sxs-lookup"><span data-stu-id="26f10-127">Specify binding entries and corresponding C/C++ variables in the derived class.</span></span> <span data-ttu-id="26f10-128">括号之间的绑定项**开始\_ADO\_绑定**和**最终\_ADO\_绑定**宏。</span><span class="sxs-lookup"><span data-stu-id="26f10-128">Bracket the binding entries between **BEGIN\_ADO\_BINDING** and **END\_ADO\_BINDING** macros.</span></span> <span data-ttu-id="26f10-129">宏不要以逗号或冒号结束。</span><span class="sxs-lookup"><span data-stu-id="26f10-129">Do not terminate the macros with commas or semicolons.</span></span> <span data-ttu-id="26f10-130">每个宏会自动指定适当的分隔符。</span><span class="sxs-lookup"><span data-stu-id="26f10-130">Appropriate delimiters are specified automatically by each macro.</span></span> <span data-ttu-id="26f10-131">为要映射到 C/C++ 变量的每个字段指定一个绑定项。</span><span class="sxs-lookup"><span data-stu-id="26f10-131">Specify one binding entry for each field to be mapped to a C/C++ variable.</span></span> <span data-ttu-id="26f10-132">使用从相应成员**ADO\_固定\_长度\_条目**， **ADO\_数值\_条目**，或**ADO\_变量\_长度\_条目**系列的宏。</span><span class="sxs-lookup"><span data-stu-id="26f10-132">Use an appropriate member from the **ADO\_FIXED\_LENGTH\_ENTRY**, **ADO\_NUMERIC\_ENTRY**, or **ADO\_VARIABLE\_LENGTH\_ENTRY** family of macros.</span></span>

3.  <span data-ttu-id="26f10-p107">在应用程序中，创建一个派生自 **CADORecordBinding** 类的类实例。从 **Recordset** 获取 **IADORecordBinding** 接口。然后调用 **BindToRecordset** 方法将 **Recordset** 字段绑定到 C/C++ 变量。</span><span class="sxs-lookup"><span data-stu-id="26f10-p107">In your application, create an instance of the class derived from **CADORecordBinding**. Get the **IADORecordBinding** interface from the **Recordset**. Then call the **BindToRecordset** method to bind the **Recordset** fields to the C/C++ variables.</span></span>

<span data-ttu-id="26f10-136">有关详细信息，请参阅 [Visual C++ Extensions 示例](visual-c-extensions-example.md)。</span><span class="sxs-lookup"><span data-stu-id="26f10-136">See the [Visual C++ Extensions Example](visual-c-extensions-example.md) for more information.</span></span>

## <a name="interface-methods"></a><span data-ttu-id="26f10-137">接口方法</span><span class="sxs-lookup"><span data-stu-id="26f10-137">Interface Methods</span></span>

<span data-ttu-id="26f10-p108">**IADORecordBinding** 接口具有以下三个方法： **BindToRecordset** 、 **AddNew** 和 **Update** 。每个方法的唯一参数是一个指向派生自 **CADORecordBinding** 的类的实例的指针。因此， **AddNew** 和 **Update** 方法不能指定与其同名的 ADO 方法的任何参数。</span><span class="sxs-lookup"><span data-stu-id="26f10-p108">The **IADORecordBinding** interface has three methods: **BindToRecordset**, **AddNew**, and **Update**. The sole argument to each method is a pointer to an instance of the class derived from **CADORecordBinding**. Therefore, the **AddNew** and **Update** methods cannot specify any of the parameters of their ADO method namesakes.</span></span>

<span data-ttu-id="26f10-141">**语法**</span><span class="sxs-lookup"><span data-stu-id="26f10-141">**Syntax**</span></span>

<span data-ttu-id="26f10-142">**BindToRecordset** 方法将 **Recordset** 字段与 C/C++ 变量关联。</span><span class="sxs-lookup"><span data-stu-id="26f10-142">The **BindToRecordset** method associates the **Recordset** fields with C/C++ variables.</span></span>

`BindToRecordset(CADORecordBinding *binding)` 

<span data-ttu-id="26f10-143">**AddNew** 方法调用与其同名的 ADO [AddNew](addnew-method-ado.md) 方法，以在 **Recordset** 中添加新行。</span><span class="sxs-lookup"><span data-stu-id="26f10-143">The **AddNew** method invokes its namesake, the ADO [AddNew](addnew-method-ado.md) method, to add a new row to the **Recordset**.</span></span>

`AddNew(CADORecordBinding *binding)` 

<span data-ttu-id="26f10-144">**Update** 方法调用与其同名的 ADO [Update](update-method-ado.md) 方法，以更新 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="26f10-144">The **Update** method invokes its namesake, the ADO [Update](update-method-ado.md) method, to update the **Recordset**.</span></span>

`Update(CADORecordBinding *binding)` 

## <a name="binding-entry-macros"></a><span data-ttu-id="26f10-145">绑定项宏</span><span class="sxs-lookup"><span data-stu-id="26f10-145">Binding Entry Macros</span></span>

<span data-ttu-id="26f10-p109">绑定项宏用于定义 **Recordset** 字段与变量的关联。各绑定项之间用开始宏和结束宏分隔。</span><span class="sxs-lookup"><span data-stu-id="26f10-p109">Binding entry macros define the association of a **Recordset** field and a variable. A beginning and ending macro delimits the set of binding entries.</span></span>

<span data-ttu-id="26f10-p110">对于定长数据（如 **adDate** 或 **adBoolean** ）、数值数据（如 **adTinyInt** 、 **adInteger** 或 **adDouble** ）和可变长度数据（如 **adChar** 、 **adVarChar** 或 **adVarBinary** ），均提供了宏系列。除 **adVarNumeric** 之外的所有数值类型也是定长类型。每个系列具有不同的参数集，以便您可以排除不感兴趣的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="26f10-p110">Families of macros are provided for fixed-length data, such as **adDate** or **adBoolean**; numeric data, such as **adTinyInt**, **adInteger**, or **adDouble**; and variable-length data, such as **adChar**, **adVarChar** or **adVarBinary**. All numeric types, except for **adVarNumeric**, are also fixed-length types. Each family has differing sets of parameters so that you can exclude binding information that is of no interest.</span></span>

<span data-ttu-id="26f10-151">请参阅*OLE DB 程序员参考*附录 a： 数据类型的其他信息。</span><span class="sxs-lookup"><span data-stu-id="26f10-151">See the *OLE DB Programmer's Reference,* Appendix A: Data Types for additional information.</span></span>

<span data-ttu-id="26f10-152">_**开始绑定项**_</span><span class="sxs-lookup"><span data-stu-id="26f10-152">_**Begin Binding Entries**_</span></span>

<span data-ttu-id="26f10-153">**开始\_ADO\_绑定**（*类*）</span><span class="sxs-lookup"><span data-stu-id="26f10-153">**BEGIN\_ADO\_BINDING**(*Class*)</span></span>

<span data-ttu-id="26f10-154">_**固定长度的数据**_</span><span class="sxs-lookup"><span data-stu-id="26f10-154">_**Fixed-Length Data**_</span></span>

<span data-ttu-id="26f10-155">**ADO\_固定\_长度\_条目**（*序号、 DataType、 缓冲区、 状态、 修改*）</span><span class="sxs-lookup"><span data-stu-id="26f10-155">**ADO\_FIXED\_LENGTH\_ENTRY**(*Ordinal, DataType, Buffer, Status, Modify*)</span></span>  
<span data-ttu-id="26f10-156">**ADO\_固定\_长度\_ENTRY2**（*序号、 DataType、 缓冲区，修改*）</span><span class="sxs-lookup"><span data-stu-id="26f10-156">**ADO\_FIXED\_LENGTH\_ENTRY2**(*Ordinal, DataType, Buffer, Modify*)</span></span>

<span data-ttu-id="26f10-157">_**数值数据**_</span><span class="sxs-lookup"><span data-stu-id="26f10-157">_**Numeric Data**_</span></span>

<span data-ttu-id="26f10-158">**ADO\_数值\_条目**（*序号、 DataType、 缓冲区、 精度、 缩放、 状态、 修改*）</span><span class="sxs-lookup"><span data-stu-id="26f10-158">**ADO\_NUMERIC\_ENTRY**(*Ordinal, DataType, Buffer, Precision, Scale, Status, Modify*)</span></span>  
<span data-ttu-id="26f10-159">**ADO\_数值\_ENTRY2**（*序号、 DataType、 缓冲区、 精度、 缩放、 修改*）</span><span class="sxs-lookup"><span data-stu-id="26f10-159">**ADO\_NUMERIC\_ENTRY2**(*Ordinal, DataType, Buffer, Precision, Scale, Modify*)</span></span>

<span data-ttu-id="26f10-160">_**可变长度数据**_</span><span class="sxs-lookup"><span data-stu-id="26f10-160">_**Variable-Length Data**_</span></span>

<span data-ttu-id="26f10-161">**ADO\_变量\_长度\_条目**（*序号、 DataType、 缓冲区、 大小、 状态、 长度、 修改*）</span><span class="sxs-lookup"><span data-stu-id="26f10-161">**ADO\_VARIABLE\_LENGTH\_ENTRY**(*Ordinal, DataType, Buffer, Size, Status, Length, Modify*)</span></span>  
<span data-ttu-id="26f10-162">**ADO\_变量\_长度\_ENTRY2**（*序号、 DataType、 缓冲区、 大小、 状态、 修改*）</span><span class="sxs-lookup"><span data-stu-id="26f10-162">**ADO\_VARIABLE\_LENGTH\_ENTRY2**(*Ordinal, DataType, Buffer, Size, Status, Modify*)</span></span>  
<span data-ttu-id="26f10-163">**ADO\_变量\_长度\_ENTRY3**（*序号、 DataType、 缓冲区、 大小、 长度、 修改*）</span><span class="sxs-lookup"><span data-stu-id="26f10-163">**ADO\_VARIABLE\_LENGTH\_ENTRY3**(*Ordinal, DataType, Buffer, Size, Length, Modify*)</span></span>  
<span data-ttu-id="26f10-164">**ADO\_变量\_长度\_ENTRY4**（*序号、 DataType、 缓冲区、 大小、 修改*）</span><span class="sxs-lookup"><span data-stu-id="26f10-164">**ADO\_VARIABLE\_LENGTH\_ENTRY4**(*Ordinal, DataType, Buffer, Size, Modify*)</span></span>

<span data-ttu-id="26f10-165">_**结束绑定项**_</span><span class="sxs-lookup"><span data-stu-id="26f10-165">_**End Binding Entries**_</span></span>

<span data-ttu-id="26f10-166">**最终\_ADO\_绑定**()</span><span class="sxs-lookup"><span data-stu-id="26f10-166">**END\_ADO\_BINDING**()</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="26f10-167">参数</span><span class="sxs-lookup"><span data-stu-id="26f10-167">Parameter</span></span></p></th>
<th><p><span data-ttu-id="26f10-168">说明</span><span class="sxs-lookup"><span data-stu-id="26f10-168">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26f10-169"><em>Class</em></span><span class="sxs-lookup"><span data-stu-id="26f10-169"><em>Class</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-170">在其中定义绑定项和 C/C++ 变量的类。</span><span class="sxs-lookup"><span data-stu-id="26f10-170">Class in which the binding entries and C/C++ variables are defined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-171"><em>Ordinal</em></span><span class="sxs-lookup"><span data-stu-id="26f10-171"><em>Ordinal</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-172">与 C/C++ 变量对应的 <strong>Recordset</strong> 字段的序号，从 1 开始计数。</span><span class="sxs-lookup"><span data-stu-id="26f10-172">Ordinal number, counting from one, of the <strong>Recordset</strong> field corresponding to your C/C++ variable.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-173"><em>DataType</em></span><span class="sxs-lookup"><span data-stu-id="26f10-173"><em>DataType</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-p111">C/C++ 变量的等效 ADO 数据类型（有关有效数据类型的列表，请参阅 <a href="datatypeenum.md">DataTypeEnum</a>）。如有必要，<strong>Recordset</strong> 字段的值将转换为此数据类型。</span><span class="sxs-lookup"><span data-stu-id="26f10-p111">Equivalent ADO data type of the C/C++ variable (see <a href="datatypeenum.md">DataTypeEnum</a> for a list of valid data types). The value of the <strong>Recordset</strong> field will be converted to this data type if necessary.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-176"><em>Buffer</em></span><span class="sxs-lookup"><span data-stu-id="26f10-176"><em>Buffer</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-177">存储 <strong>Recordset</strong> 字段的 C/C++ 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="26f10-177">Name of the C/C++ variable where the <strong>Recordset</strong> field will be stored.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-178"><em>Size</em></span><span class="sxs-lookup"><span data-stu-id="26f10-178"><em>Size</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-p112"><em>Buffer</em> 的最大大小，以字节计。如果 <em>Buffer</em> 包含可变长度字符串，则还为终止字符零留出了空间。</span><span class="sxs-lookup"><span data-stu-id="26f10-p112">Maximum size in bytes of <em>Buffer</em>. If <em>Buffer</em> will contain a variable-length string, allow room for a terminating zero.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-181"><em>Status</em></span><span class="sxs-lookup"><span data-stu-id="26f10-181"><em>Status</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-182">变量名称，用于指示 <em>Buffer</em> 的内容是否有效，以及字段是否成功转换为 <em>DataType</em>。
</span><span class="sxs-lookup"><span data-stu-id="26f10-182">Name of a variable that will indicate whether the contents of <em>Buffer</em> are valid, and whether the conversion of the field to <em>DataType</em> was successful.</span></span> <span data-ttu-id="26f10-183">此变量有两个最重要的值：一个是 <strong>adFldOK</strong>，表示转换成功；另一个是 <strong>adFldNull</strong>，表示字段的值为 VT_NULL 类型的 VARIANT，但不仅仅为空。</span><span class="sxs-lookup"><span data-stu-id="26f10-183">The two most important values for this variable are <strong>adFldOK</strong>, which means the conversion was successful; and <strong>adFldNull</strong>, which means the value of the field would be a VARIANT of type VT_NULL and not merely empty.</span></span> <span data-ttu-id="26f10-184">在下表中，列出<em>状态</em>的可能值&quot;状态值。&quot;</span><span class="sxs-lookup"><span data-stu-id="26f10-184">Possible values for <em>Status</em> are listed in the next table, &quot;Status Values.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-185"><em>Modify</em></span><span class="sxs-lookup"><span data-stu-id="26f10-185"><em>Modify</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-186">布尔型标志。如果为 TRUE，则指示允许 ADO 用 <em>Buffer</em> 中所包含的值更新相应的 <strong>Recordset</strong> 字段。
</span><span class="sxs-lookup"><span data-stu-id="26f10-186">Boolean flag; if TRUE, indicates ADO is allowed to update the corresponding <strong>Recordset</strong> field with the value contained in <em>Buffer</em>.</span></span> <span data-ttu-id="26f10-187">如果要让 ADO 更新绑定字段，则将布尔型 <em>Modify</em> 参数设置为 TRUE。如果要检查字段但不进行更改，则设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="26f10-187">Set the Boolean <em>modify</em> parameter to TRUE to enable ADO to update the bound field, and FALSE if you want to examine the field but not change it.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-188"><em>Precision</em></span><span class="sxs-lookup"><span data-stu-id="26f10-188"><em>Precision</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-189">可以用数值变量表示的数字位数。</span><span class="sxs-lookup"><span data-stu-id="26f10-189">Number of digits that can be represented in a numeric variable.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-190"><em>小数位数</em></span><span class="sxs-lookup"><span data-stu-id="26f10-190"><em>Scale</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-191">用数值变量表示的小数位数。</span><span class="sxs-lookup"><span data-stu-id="26f10-191">Number of decimal places in a numeric variable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-192"><em>Length</em></span><span class="sxs-lookup"><span data-stu-id="26f10-192"><em>Length</em></span></span></p></td>
<td><p><span data-ttu-id="26f10-193">4 字节变量的名称，包含 <em>Buffer</em> 中数据的实际长度。</span><span class="sxs-lookup"><span data-stu-id="26f10-193">Name of a four-byte variable that will contain the actual length of the data in <em>Buffer</em>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="status-values"></a><span data-ttu-id="26f10-194">状态值</span><span class="sxs-lookup"><span data-stu-id="26f10-194">Status Values</span></span>

<span data-ttu-id="26f10-195">*Status*变量的值指示是否字段是否成功复制到变量。</span><span class="sxs-lookup"><span data-stu-id="26f10-195">The value of the *Status* variable indicates whether a field was successfully copied to a variable.</span></span>

<span data-ttu-id="26f10-196">在设置数据时，*Status* 可以设置为 **adFldNull**，以指示 **Recordset** 字段应设置为 Null。</span><span class="sxs-lookup"><span data-stu-id="26f10-196">When setting data, *Status* may be set to **adFldNull** to indicate the **Recordset** field should be set to null.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="26f10-197">常量</span><span class="sxs-lookup"><span data-stu-id="26f10-197">Constant</span></span></p></th>
<th><p><span data-ttu-id="26f10-198">值</span><span class="sxs-lookup"><span data-stu-id="26f10-198">Value</span></span></p></th>
<th><p><span data-ttu-id="26f10-199">说明</span><span class="sxs-lookup"><span data-stu-id="26f10-199">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26f10-200"><strong>adFldOK</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-200"><strong>adFldOK</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-201">0</span><span class="sxs-lookup"><span data-stu-id="26f10-201">0</span></span></p></td>
<td><p><span data-ttu-id="26f10-202">返回非 Null 字段值。</span><span class="sxs-lookup"><span data-stu-id="26f10-202">A non-null field value was returned.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-203"><strong>adFldBadAccessor</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-203"><strong>adFldBadAccessor</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-204">1</span><span class="sxs-lookup"><span data-stu-id="26f10-204">1</span></span></p></td>
<td><p><span data-ttu-id="26f10-205">绑定无效。</span><span class="sxs-lookup"><span data-stu-id="26f10-205">Binding was invalid.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-206"><strong>adFldCantConvertValue</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-206"><strong>adFldCantConvertValue</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-207">2</span><span class="sxs-lookup"><span data-stu-id="26f10-207">2</span></span></p></td>
<td><p><span data-ttu-id="26f10-208">由于符号不匹配或数据溢出之外的原因，值无法转换。</span><span class="sxs-lookup"><span data-stu-id="26f10-208">Value couldn't be converted for reasons other than sign mismatch or data overflow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-209"><strong>adFldNull</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-209"><strong>adFldNull</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-210">3</span><span class="sxs-lookup"><span data-stu-id="26f10-210">3</span></span></p></td>
<td><p><span data-ttu-id="26f10-211">在获取字段时，指示返回空值。
</span><span class="sxs-lookup"><span data-stu-id="26f10-211">When getting a field, indicates a null value was returned.</span></span> <span data-ttu-id="26f10-212">在设置字段时，指示当字段自身无法编码 <strong>NULL</strong>（如一个字符数组或整数）时字段应设置为 <strong>NULL</strong>。</span><span class="sxs-lookup"><span data-stu-id="26f10-212">When setting a field, indicates the field should be set to <strong>NULL</strong> when the field cannot encode <strong>NULL</strong> itself (for example, a character array or an integer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-213"><strong>adFldTruncated</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-213"><strong>adFldTruncated</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-214">4</span><span class="sxs-lookup"><span data-stu-id="26f10-214">4</span></span></p></td>
<td><p><span data-ttu-id="26f10-215">截断可变长度数据或数字。</span><span class="sxs-lookup"><span data-stu-id="26f10-215">Variable-length data or numeric digits were truncated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-216"><strong>adFldSignMismatch</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-216"><strong>adFldSignMismatch</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-217">5</span><span class="sxs-lookup"><span data-stu-id="26f10-217">5</span></span></p></td>
<td><p><span data-ttu-id="26f10-218">值有符号，变量数据类型无符号。</span><span class="sxs-lookup"><span data-stu-id="26f10-218">Value is signed and variable data type is unsigned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-219"><strong>adFldDataOverFlow</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-219"><strong>adFldDataOverFlow</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-220">6</span><span class="sxs-lookup"><span data-stu-id="26f10-220">6</span></span></p></td>
<td><p><span data-ttu-id="26f10-221">值大于变量数据类型中可存储的大小。</span><span class="sxs-lookup"><span data-stu-id="26f10-221">Value is larger than could be stored in the variable data type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-222"><strong>adFldCantCreate</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-222"><strong>adFldCantCreate</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-223">7</span><span class="sxs-lookup"><span data-stu-id="26f10-223">7</span></span></p></td>
<td><p><span data-ttu-id="26f10-224">打开了未知的列类型和字段。</span><span class="sxs-lookup"><span data-stu-id="26f10-224">Unknown column type and field already open.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-225"><strong>adFldUnavailable</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-225"><strong>adFldUnavailable</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-226">8</span><span class="sxs-lookup"><span data-stu-id="26f10-226">8</span></span></p></td>
<td><p><span data-ttu-id="26f10-227">无法确定字段值 - 例如，在一个无默认值的新的未赋值字段上。</span><span class="sxs-lookup"><span data-stu-id="26f10-227">Field value could not be determined — for example, on a new, unassigned field with no default value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-228"><strong>adFldPermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-228"><strong>adFldPermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-229">9</span><span class="sxs-lookup"><span data-stu-id="26f10-229">9</span></span></p></td>
<td><p><span data-ttu-id="26f10-230">更新时，无权写数据。</span><span class="sxs-lookup"><span data-stu-id="26f10-230">When updating, no permission to write data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-231"><strong>adFldIntegrityViolation</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-231"><strong>adFldIntegrityViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-232">10</span><span class="sxs-lookup"><span data-stu-id="26f10-232">10</span></span></p></td>
<td><p><span data-ttu-id="26f10-233">更新时，字段值与列完整性冲突。</span><span class="sxs-lookup"><span data-stu-id="26f10-233">When updating, field value would violate column integrity.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-234"><strong>adFldSchemaViolation</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-234"><strong>adFldSchemaViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-235">11</span><span class="sxs-lookup"><span data-stu-id="26f10-235">11</span></span></p></td>
<td><p><span data-ttu-id="26f10-236">更新时，字段值与列架构冲突。</span><span class="sxs-lookup"><span data-stu-id="26f10-236">When updating, field value would violate column schema.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f10-237"><strong>adFldBadStatus</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-237"><strong>adFldBadStatus</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-238">12</span><span class="sxs-lookup"><span data-stu-id="26f10-238">12</span></span></p></td>
<td><p><span data-ttu-id="26f10-239">更新时，状态参数无效。</span><span class="sxs-lookup"><span data-stu-id="26f10-239">When updating, invalid status parameter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f10-240"><strong>adFldDefault</strong></span><span class="sxs-lookup"><span data-stu-id="26f10-240"><strong>adFldDefault</strong></span></span></p></td>
<td><p><span data-ttu-id="26f10-241">13</span><span class="sxs-lookup"><span data-stu-id="26f10-241">13</span></span></p></td>
<td><p><span data-ttu-id="26f10-242">更新时，使用默认值。</span><span class="sxs-lookup"><span data-stu-id="26f10-242">When updating, a default value was used.</span></span></p></td>
</tr>
</tbody>
</table>

