---
title: Visual C++ ADO 编程
TOCTitle: Visual C++ ADO Programming
ms:assetid: 117c4fad-8c11-5e3a-ea0c-18811e87475f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248878(v=office.15)
ms:contentKeyID: 48543319
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 55e4bf1476112cc950b72e8bfd1659226704f991
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25890006"
---
# <a name="visual-c-ado-programming"></a>Visual C++ ADO 编程


**适用于**： Access 2013、 Office 2013

《ADO API 参考》采用类似 Microsoft Visual Basic 的语法来描述 ADO 应用程序编程接口 (API) 的功能。 ADO 程序员目标的受众为所有用户，但使用不同的语言，例如 Visual Basic 中，Visual c + + (具有和没有**\#导入**指令)，并 Visual J + + （与 ADO/WFC 类封装）。

为照顾这种多样性，[ADO for Visual C++ 语法索引](using-ado-with-microsoft-visual-c.md)中提供了 Visual C++ 语言的专用语法，以及指向《API 参考》中功能、参数、异常行为等内容的一般性说明的链接。

ADO 采用 COM（组件对象模型）接口来实现。不过，对于程序员而言，在某些编程语言中使用 COM 要比在其他一些语言中更为容易。例如，在 Visual Basic 中，几乎所有使用 COM 的细节均已隐式处理，而在 Visual C++ 中，程序员必须留意这些细节。

以下各节汇总为 C 和 c + + 程序员中使用 ADO 的详细信息和**\#导入**指令。 重点特定于 COM （**Variant**、 **BSTR**和**SafeArray**） 和错误处理的数据类型 (\_com\_错误)。

## <a name="using-the-import-compiler-directive"></a>使用\#导入编译器指令

**\#导入**Visual c + + 编译器指令简化了使用 ADO 方法和属性。 该指令获取诸如 ADO .dll (Msado15.dll) 等包含类型库的文件的名称，然后生成包含 typedef 声明、智能接口指针和枚举常量的头文件。 每个接口都被封装或包装在类中。

对于类中的每个操作（即方法或属性调用），都存在一个声明以直接调用操作（即操作的"原始"形式），还存在另一个声明以调用原始操作并当操作无法成功执行时引发 COM 错误。如果操作为属性，则通常存在一个编译器指令，为具有类似 Visual Basic 语法的操作创建替代语法。

检索属性的值的操作具有名称窗体，**获取 *** 属性*。 设置属性的值的操作具有名称窗体，**放置 *** 属性*。 将指针的属性的值设置为 ADO 对象的操作具有名称窗体，**PutRef *** 属性*。

可以用以下形式的调用来获取或设置属性：

```vb 
 
variable = objectPtr->GetProperty(); // get property value 
objectPtr->PutProperty(value); // set property value 
objectPtr->PutRefProperty(&value); // set property with object pointer 
```

## <a name="using-property-directives"></a>使用属性指令

** \_ \_Declspec(property...)** 编译器指令是声明为属性用于具有替代语法函数的特定的 Microsoft C 语言扩展。 因此，可以采用类似于 Visual Basic 的方式来设置或获取属性值。 例如，可以按照以下方式设置和获取属性：

```vb 
 
objectPtr->property = value; // set property value 
variable = objectPtr->property; // get property value 
```

请注意，您无需使用以下代码：

```vb 
 
objectPtr->PutProperty(value); // set property value 
variable = objectPtr->GetProperty; // get property value 
```

编译器将生成相应 **Get ***-*， **Put**-，或 **PutRef *** 属性*呼叫基于声明的哪些替代语法以及是否正在属性读取或写入。

** \_ \_Declspec(property...)** 编译器指令只能声明**获取**、 **put**，或将函数**获取**并**放置**替代语法。 只读操作只能具有 **get** 声明；只写操作只能具有 **put** 声明；读写操作可以具有 **get** 和 **put** 声明。

只有两个声明而言，可能有此指令;但是，每个属性可能有三个属性函数: **获取 *** 属性*，**放置 *** 属性*，和 **PutRef *** 属性*。 因此，只有两个属性具有替代语法。

例如， **ActiveConnection**属性将**Command**对象用声明的替代语法 **获取 *** ActiveConnection*和 **PutRef *** ActiveConnection*。 **PutRef**-语法因为实际上，通常要打开的**Connection**对象 （即，**连接**对象指针） 置于此属性是一个不错的选择。 另一方面， **Recordset**对象中的**Get**-、 **Put**-和 **PutRef *** ActiveConnection*操作，但没有替代语法。

## <a name="collections-the-getitem-method-and-the-item-property"></a>集合、GetItem 方法和 Item 属性

ADO 定义了多个集合，包括 **Fields**、**Parameters**、**Properties** 和 **Errors**。在 Visual C++ 中，**GetItem(***index***)** 方法返回集合的成员。*index* 为 **Variant**，其值可以是集合中成员的数字索引，也可以是包含成员名称的字符串。

** \_ \_Declspec(property...)** 编译器指令声明为每个集合的基本**GetItem()** 方法的可选语法**Item**属性。 替代语法使用方括号，类似于数组引用。 一般情况下，这两种形式如下所示：

```vb
    collectionPtr->GetItem(index); 
    collectionPtr->Item[index]; 
```

例如，将值分配给名为***rs***，派生自**pubs**数据库的**authors**表的**Recordset**对象的字段。 使用**了 item （）** 属性访问**Recordset**对象的**Fields**集合的第三个**字段**(集索引从零; 假定第三个字段，命名为***au\_fname***)。 对**Field**对象分配一个 string 值，然后调用**使用 value （）** 方法。

在 Visual Basic 中，以上操作可采用以下四种方式表达（后两种方式是 Visual Basic 所独有的；其他语言没有等效的代码）：

```vb 
 
rs.Fields.Item(2).Value = "value" 
rs.Fields.Item("au_fname").Value = "value" 
rs(2) = "value" 
rs!au_fname = "value" 
```

在 Visual C++ 中，与以上前两种方式等效的代码如下：

```cpp 
 
rs->Fields->GetItem(long(2))->PutValue("value"); 
rs->Fields->GetItem("au_fname")->PutValue("value"); 
```

\-或-（还显示**Value**属性的替代语法）

```cpp 
 
rs->Fields->Item[long(2)]->Value = "value"; 
rs->Fields->Item["au_fname"]->Value = "value"; 
```

## <a name="com-specific-data-types"></a>COM 特有的数据类型

一般而言，在《ADO API 参考》中找到的任何 Visual Basic 数据类型在 Visual C++ 中都有对应的类型。其中包括标准的数据类型，如 **无符号字符型** 对应于 Visual Basic 的 **Byte** ， **短型** 对应于 **整型** 以及 **长整型** 对应于 **长整型** 。请查阅"语法索引"，了解特定方法或属性具体需要什么类型的操作数。

此规则的例外之处是 COM 特有的数据类型： **Variant** 、 **BSTR** 和 **SafeArray** 。

## <a name="variant"></a>Variant

**Variant** 是一种结构化数据类型，其中包含值成员和数据类型成员。 **Variant** 中可能包含大量其他数据类型，包括另一个 Variant、BSTR、布尔型、IDispatch 或 IUnknown 指针、货币、日期等。COM 还提供了可以轻松地将一种数据类型转换为另一种数据类型的方法。

** \_Variant\_t**类封装并管理**Variant**数据类型。

当 ADO API 参考方法或属性操作数采用值时，它通常表示值被传递中**\_variant\_t**。

此规则明确为 true 时 ADO API 参考主题中的**参数**部分显示操作数是**Variant**。 文档明确指出操作数采用标准数据类型，如**Long** 、**字节**或枚举时一个例外。 操作数采用**字符串**时，另一个异常。

## <a name="bstr"></a>BSTR

**BSTR** （**B**asic **STR**来） 是包含字符串和字符串的长度的结构化的数据类型。 COM 提供用于分配、 操作和忙**BSTR**方法。

** \_Bstr\_t**类封装和管理**BSTR**数据类型。

当 ADO API 参考方法或属性采用**字符串**值时，它表示的窗体中的值是**\_bstr\_t**。

## <a name="casting-variantt-and-bstrt-classes"></a>转换\_variant\_t 和\_bstr\_t 类

通常不需要显式代码为**\_variant\_t**或**\_bstr\_t**操作参数。 如果**\_variant\_t**或**\_bstr\_t**类具有一个构造函数的参数的数据类型相匹配，则编译器将生成相应**\_variant\_t**或**\_bstr\_t**。

不过，如果参数不明确，即参数的数据类型与多个构造函数匹配，那么必须用适当的数据类型转换参数，以调用正确的构造函数。

例如， **Recordset::Open** 方法的声明如下：

```vb 
 
 HRESULT Open ( 
 const _variant_t & Source, 
 const _variant_t & ActiveConnection, 
 enum CursorTypeEnum CursorType, 
 enum LockTypeEnum LockType, 
 long Options ); 
```

其中 ActiveConnection 参数采用引用**\_variant\_t**，其中可能编写为一个连接字符串或指向打开的**Connection**对象的指针。

正确**\_variant\_t**将隐式构造，如果您传递一个字符串，如"DSN = pubs; uid = sa; pwd =;"，或如指针"(IDispatch \*) pConn"。

显式可能代码或**\_variant\_t**包含一个指针，如"\_variant\_t ((IDispatch \*) pConn，true)"。 强制转换，(IDispatch \*)，解析为与另一个构造函数采用的 IUnknown 接口的指针歧义。

ADO 是 IDispatch 接口这一事实虽然很少提及，但这一点极为重要。指向 ADO 对象的指针都必须作为 **Variant** 传递，且该指针必须转换为指向 IDispatch 接口的指针。

最后一种情况明确编写构造函数的第二个布尔参数，其可选，默认值为 true。 此参数导致**Variant**构造函数调用其**AddRef**（） 方法，ADO 自动调用补偿**\_variant\_t::Release**（） 方法 （ADO 方法或属性调用完成时。

## <a name="safearray"></a>SafeArray

**SafeArray** 是一种结构化数据类型，其中包含其他数据类型的数组。 **SafeArray**称为*安全*，因为它包含的界限每个数组维度和限制访问这些边界内的数组元素的信息。

当《ADO API 参考》中提到方法或属性获取或返回数组时，表示方法或属性获取或返回的是 **SafeArray** ，而不是本机 C/C++ 数组。

例如， **Connection** 对象的 **OpenSchema** 方法的第二个参数需要一个 **变量型** 值数组。这些 **变量型** 值必须作为 **SafeArray** 的元素传递，且该 **SafeArray** 必须设置为另一个 **变量型** 值，这便是作为 **OpenSchema** 的第二个参数传递的 **变量型** 。

更进一步，例如， **Find** 方法的第一个参数是值为一维 **SafeArray** 的 **变量型** ； **AddNew** 方法的可选的第一个和第二个参数为一维 **SafeArray** ； **GetRows** 方法的返回值是值为二维 **SafeArray** 的 **变量型** 。

## <a name="missing-and-default-parameters"></a>省略参数和默认参数

Visual Basic 允许方法中省略参数。例如， **Recordset** 对象 **Open** 方法具有五个参数，但您可以跳过中间的参数，只留下后面的参数。根据省略的操作数数据类型的不同，将替换为默认的 **BSTR** 或 **变量型** 。

在 C/C++ 中，必须指定所有操作数。 如果您想要指定缺少的参数数据类型是一个字符串，指定**\_bstr\_t**包含空字符串。 如果您想要指定缺少的参数数据类型是**variant 类型的值**，指定**\_variant\_t**值显示为\_E\_PARAMNOTFOUND 和 VT 类型\_错误。 此外，指定等同**\_variant\_t**常量、 **vtMissing**，后者提供通过**\#导入**指令。

以下三种方法对于 **vtMissing** 的常见用法是例外： **Connection** 和 **Command** 对象的 **Execute** 方法以及 **Recordset** 对象的 **NextRecordset** 方法。以下是这些方法的签名：

```vb 
 
_RecordsetPtr Invalid DDUE based on source, error:link not allowed in code, link filename:mdmthcnnexecute_HV10294345.xml( _bstr_t CommandText, VARIANT * RecordsAffected, 
 long Options ); // Connection 
_RecordsetPtr Invalid DDUE based on source, error:link not allowed in code, link filename:mdmthcmdexecute_HV10294344.xml( VARIANT * RecordsAffected, VARIANT * Parameters, 
 long Options ); // Command 
_RecordsetPtr Invalid DDUE based on source, error:link not allowed in code, link filename:mdmthnextrec_HV10294541.xml( VARIANT * RecordsAffected ); // Recordset 
```

其中参数 *RecordsAffected* 和 *Parameters* 是指向**变量型**的指针。*Parameters* 是输入参数，用于指定包含单个参数或参数数组的**变量型**的地址，它将修改要执行的命令。*RecordsAffected* 是输出参数，用于指定**变量型**的地址，其中返回了受方法影响的行的数量。

在**Execute**方法的**Command**对象，指示*参数*设置为以下任意未指定任何参数\&vtMissing （这建议） 或 null 的指针 （即**NULL**或零 (0)）。 如果*参数*设置为 null 的指针，该方法将内部替换**vtMissing**的等效项，然后完成该操作。

在所有方法，指示影响的记录数不应返回通过将*RecordsAffected*设置为 null 的指针。 此时，空指针不仅仅是省略的参数，还作为一个指示，表明方法应当放弃受影响的记录数。

因此，对于这三种方法而言，如下代码是有效的：

```vb 
 
pConnection->Execute("commandText", NULL, adCmdText); 
pCommand->Execute(NULL, NULL, adCmdText); 
pRecordset->NextRecordset(NULL); 
```

## <a name="error-handling"></a>出错处理

在 COM，大多数操作返回 HRESULT 返回代码，指示函数是否已成功完成。 **\#导入**指令生成周围每个"原始"方法或属性的包装代码，并检查返回的 HRESULT。 如果 HRESULT 指示故障，包装代码通过调用引发 COM 错误\_com\_问题\_errorex() hresult 返回作为参数的代码。 可以在**尝试**捕获 COM error 对象-**catch**块。 (为效率的起见，捕获对**\_com\_错误**对象。)

请记住，这些是 ADO 错误：它们是由于 ADO 操作失败而导致的。基础提供程序返回的错误显示为 **Connection** 对象的 **Errors** 集合中的 **Error** 对象。

**\#导入**指令创建唯一的错误处理例程的方法和属性在 ADO.dll 中声明。 不过，您可以编写自己的错误检测宏或内嵌函数，以利用同样的错误处理机制。 有关示例，请参阅主题 [Visual C++ 扩展](visual-c-extensions-for-ado.md)或下文中的代码。

## <a name="visual-c-equivalents-of-visual-basic-conventions"></a>与 Visual Basic 约定等效的 Visual C++ 代码

以下摘要介绍用 Visual Basic 编写的 ADO 文档中的若干约定，以及等效的 Visual C++ 代码。

## <a name="declaring-an-ado-object"></a>声明 ADO 对象

在 Visual Basic 中，ADO 对象变量（此处以 **Recordset** 对象为例）声明如下：

```vb 
 
Dim rst As ADODB.Recordset 
```

子句中，"ADODB。记录集"，是在注册表中定义的 ProgID 的**Recordset**对象。 **Record** 对象的新实例声明如下：

```vb 
 
Dim rst As New ADODB.Recordset 
```

\-或-

```vb 
 
Dim rst As ADODB.Recordset 
Set rst = New ADODB.Recordset 
```

Visual c + + 中，在**\#导入**指令将生成的所有 ADO 对象的智能指针类型声明。 例如，变量指向**\_Recordset**对象的类型是**\_RecordsetPtr**，和声明，如下所示：

```cpp 
 
_RecordsetPtr rs; 
```

变量指向的新实例**\_Recordset**对象声明，如下所示：

```cpp 
 
_RecordsetPtr rs("ADODB.Recordset"); 
```

\-或-

```cpp 
 
_RecordsetPtr rs; 
rs.CreateInstance("ADODB.Recordset"); 
```

\-或-

```cpp 
 
_RecordsetPtr rs; 
rs.CreateInstance(__uuidof(_Recordset)); 
```

调用 **CreateInstance** 方法之后，可以按照以下方式使用变量：

```cpp 
 
rs->Open(...); 
```

请注意，在一个情况下，"。"运算符使用变量好像实例的类 (rs。创建实例），并在其他情况下，"-\>"运算符使用变量好像指向接口的指针 (rs-\>打开)。

可以通过以下两种使用一个变量，因为"-\>"重载运算符允许如同指向接口的类的实例。 私有类成员的实例变量包含一个指向**\_Recordset**接口;"-\>"运算符返回该指针;返回的指针访问的成员和**\_Recordset**对象。

## <a name="coding-a-missing-parameter"></a>对省略的变量型参数进行编码

在 Visual Basic 中，如果需要对省略的 **字符串型** 操作数进行编码，只需省略该操作数即可。 在 Visual C++ 中，则必须指定操作数。 代码**\_bstr\_t**具有作为值为空字符串。

```cpp 
 
_bstr_t strMissing(L""); 
```

## <a name="coding-a-missing-parameter"></a>对省略的变量型参数进行编码

在 Visual Basic 中，如果需要对省略的 **变量型** 操作数进行编码，只需省略该操作数即可。 在 Visual C++ 中，则必须指定所有操作数。 代码的缺少**Variant**参数**\_variant\_t**设置特殊值，显示为\_E\_PARAMNOTFOUND 和类型，VT\_错误。 或者，指定**vtMissing**，即等效由提供的预定义的常数**\#导入**指令。

```cpp 
 
_variant_t vtMissingYours(DISP_E_PARAMNOTFOUND, VT_ERROR); 
```

\-或使用-

```cpp 
 
...vtMissing...; 
```

## <a name="declaring-a-variant"></a>声明变量型

在 Visual Basic 中，用 **Dim** 语句声明 **变量型** ，如下所示：

```vb 
 
Dim VariableName As Variant 
```

在 Visual c + + 中，声明的变量类型为**\_variant\_t**。 几示意图**\_variant\_t**声明如下所示。


> [!NOTE]
> <P>[!注释] 这些声明仅仅为您在编写自己的程序时提供一个粗略的思路。有关详细信息，请参阅以下示例和 Visual C++ 文档。</P>



```cpp 
 
_variant_t VariableName(value); 
_variant_t VariableName((data type cast) value); 
_variant_t VariableName(value, VT_DATATYPE); 
_variant_t VariableName(interface * value, bool fAddRef = true); 
```

## <a name="using-arrays-of-variants"></a>使用变量型数组

在 Visual Basic 中，可以用 **Dim** 语句编写 **变量型** 数组，或者也可以使用 **Array** 函数，如以下代码所示：

```vb 
 
Public Sub ArrayOfVariants 
Dim cn As ADODB.Connection 
Dim rs As ADODB.Recordset 
Dim fld As ADODB.Field 
 
cn.Open "DSN=pubs", "sa", "" 
rs = cn.OpenSchema(adSchemaColumns, _ 
 Array(Empty, Empty, "authors", Empty)) 
For Each fld in rs.Fields 
 Debug.Print "Name = "; fld.Name 
Next fld 
rs.Close 
cn.Close 
End Sub 
```

下面的 Visual c + + 示例展示了如何使用用于**SafeArray** ** \_variant\_t**。


> [!NOTE]
> <P>[!注释] 以下注释对应于代码示例中的注释部分。</P>



1.  TESTHR() 内嵌函数再次被定义为利用现有的错误处理机制。

2.  您只需要一个一维数组，因此可以使用 **SafeArrayCreateVector** 取代通用的 **SAFEARRAYBOUND** 声明和 **SafeArrayCreate** 函数。如果使用 **SafeArrayCreate** ，则代码如下所示：
    
    ```cpp 
     
     SAFEARRAYBOUND sabound[1]; 
     sabound[0].lLbound = 0; 
     sabound[0].cElements = 4; 
     pSa = SafeArrayCreate(VT_VARIANT, 1, sabound); 
    ```

3.  架构枚举的常量， **adSchemaColumns**，由标识相关联四个约束列： 表\_目录、 表\_架构、 表\_名称和列\_名称。 因此，将创建包含四个元素的 **变量型** 数组。 然后约束的值，对应于第三列，表\_名称，指定。 返回的 **Recordset** 包含多列，其子集为约束列。 每个返回行的约束列的值必须等于相应的约束值。

4.  熟悉**SafeArrays**可能想不到不会在退出之前调用**SafeArrayDestroy**（）。 实际上，调用**SafeArrayDestroy**（） 在这种情况下将导致运行时异常。 原因是： vtCriteria 的析构函数将调用**VariantClear**（） 时**\_variant\_t**超出范围，将闲**SafeArray**。 调用**SafeArrayDestroy**，而不手动清除**\_variant\_t**，会导致对析构函数尝试清除了无效的**SafeArray**指针。 如果调用 **SafeArrayDestroy** ，则代码如下所示：
    
    ```cpp 
     
     TESTHR(SafeArrayDestroy(pSa)); 
     vtCriteria.vt = VT_EMPTY; 
     vtCriteria.parray = NULL; 
    ```
    
    但是，就要让简单得多**\_variant\_t**管理**SafeArray**。

<!-- end list -->

```cpp 
 
#import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
#include <stdio.h> 
 
// Note 1 
inline void TESTHR( HRESULT _hr ) 
 { if FAILED(_hr) _com_issue_error(_hr); } 
 
void main(void) 
{ 
 CoInitialize(NULL); 
 try 
 { 
 _RecordsetPtr pRs("ADODB.Recordset"); 
 _ConnectionPtr pCn("ADODB.Connection"); 
 _variant_t vtTableName("authors"), 
 vtCriteria; 
 long ix[1]; 
 SAFEARRAY *pSa = NULL; 
 
 pCn->Open("DSN=pubs;User ID=MyUserId;pwd=MyPassword;Provider=MSDASQL;", "", "", 
 adConnectUnspecified); 
// Note 2, Note 3 
 pSa = SafeArrayCreateVector(VT_VARIANT, 1, 4); 
 if (!pSa) _com_issue_error(E_OUTOFMEMORY); 
 
// Specify TABLE_NAME in the third array element (index of 2). 
 
 ix[0] = 2; 
 TESTHR(SafeArrayPutElement(pSa, ix, &vtTableName)); 
 
// There is no Variant constructor for a SafeArray, so manually set the 
// type (SafeArray of Variant) and value (pointer to a SafeArray). 
 
 vtCriteria.vt = VT_ARRAY | VT_VARIANT; 
 vtCriteria.parray = pSa; 
 
 pRs = pCn->OpenSchema(adSchemaColumns, vtCriteria, vtMissing); 
 
 long limit = pRs->GetFields()->Count; 
 for (long x = 0; x < limit; x++) 
 printf("%d: %s\n", x+1, 
 ((char*) pRs->GetFields()->Item[x]->Name)); 
// Note 4 
 pRs->Close(); 
 pCn->Close(); 
 } 
 catch (_com_error &e) 
 { 
 printf("Error:\n"); 
 printf("Code = %08lx\n", e.Error()); 
 printf("Code meaning = %s\n", (char*) e.ErrorMessage()); 
 printf("Source = %s\n", (char*) e.Source()); 
 printf("Description = %s\n", (char*) e.Description()); 
 } 
 CoUninitialize(); 
} 
```

## <a name="using-property-getputputref"></a>使用属性 Get/Put/PutRef

在 Visual Basic 中，属性的名称并未限定（无论是对它进行检索、赋值还是赋予一个引用）。

```vb
    Public Sub GetPutPutRef 
    Dim rs As New ADODB.Recordset 
    Dim cn As New ADODB.Connection 
    Dim sz as Integer 
    cn.Open "Provider=sqloledb;Data Source=yourserver;" & _ 
     "Initial Catalog=pubs;Integrated Security=SSPI;" 
    rs.PageSize = 10 
    sz = rs.PageSize 
    rs.ActiveConnection = cn 
    rs.Open "authors",,adOpenStatic 
    ' ... 
    rs.Close 
    cn.Close 
    End Sub
```

以下 Visual c + + 示例演示如何**获取**/**放置**/**PutRef *** 属性*。


> [!NOTE]
> <P>[!注释] 以下注释对应于代码示例中的注释部分。</P>



1.  此示例使用两种形式的缺少的字符串参数： 显式常量、 **strMissing**和字符串编译器将用于创建一个临时**\_bstr\_t**的**Open**方法的作用域存在。

2.  不需要的 rs-操作数转换\>PutRefActiveConnection(cn) 为 (IDispatch \*) 由于操作数的类型已经是 (IDispatch \*)。
    
    ```cpp 
     
    #import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
    #include <stdio.h> 
     
    void main(void) 
    { 
     CoInitialize(NULL); 
     try 
     { 
     _ConnectionPtr cn("ADODB.Connection"); 
     _RecordsetPtr rs("ADODB.Recordset"); 
     _bstr_t strMissing(L""); 
     long oldPgSz = 0, 
     newPgSz = 5; 
     
    // Note 1 
     cn->Open("Provider=sqloledb;Data Source=MyServer;" 
     "Initial Catalog=pubs;Integrated Security=SSPI;", 
     strMissing, "", 
     adConnectUnspecified); 
     
     oldPgSz = rs->GetPageSize(); 
     // -or- 
     oldPgSz = rs->PageSize; 
     
     rs->PutPageSize(newPgSz); 
     // -or- 
     rs->PageSize = newPgSz; 
     
    // Note 2 
     rs->PutRefActiveConnection( cn ); 
     rs->Open("authors", vtMissing, adOpenStatic, adLockReadOnly, 
     adCmdTable); 
     printf("Original pagesize = %d, new pagesize = %d\n", oldPgSz, 
     rs->GetPageSize()); 
     rs->Close(); 
     cn->Close(); 
     } 
     catch (_com_error &e) 
     { 
     printf("Description = %s\n", (char*) e.Description()); 
     } 
     ::CoUninitialize(); 
    } 
    ```

## <a name="using-getitemx-and-itemx"></a>使用 getitem （x） 和 Item\[x\]

此 Visual Basic 示例展示了 **Item**() 的标准语法和替代语法。

```vb 
 
Public Sub GetItemItem 
Dim rs As New ADODB.Recordset 
Dim name as String 
rs = rs.Open "authors", "DSN=pubs;", adOpenDynamic, _ 
 adLockBatchOptimistic, adTable 
name = rs(0) 
' -or- 
name = rs.Fields.Item(0) 
rs(0) = "Test" 
rs.UpdateBatch 
' Restore name 
rs(0) = name 
rs.UpdateBatch 
rs.Close 
End Sub 
```

此 Visual C++ 示例展示了 **Item** 。


> [!NOTE]
> <P>[!注释] 以下注释对应于代码示例中的注释部分。</P>



1.  当用 **Item** 访问集合时，索引 **2** 必须转换为 **长整型** ，以调用适当的构造函数。
    
    ```cpp 
     
    #import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
    #include <stdio.h> 
     
    void main(void) 
    { 
     CoInitialize(NULL); 
     try { 
     _RecordsetPtr rs("ADODB.Recordset"); 
     _variant_t vtFirstName; 
     
     rs->Open("authors", 
     "Provider=sqloledb;Data Source=MyServer;" 
     "Initial Catalog=pubs;Integrated Security=SSPI;", 
     adOpenStatic, adLockOptimistic, adCmdTable); 
     rs->MoveFirst(); 
     
    // Note 1. Get a field. 
     vtFirstName = rs->Fields->GetItem((long)2)->GetValue(); 
     // -or- 
     vtFirstName = rs->Fields->Item[(long)2]->Value; 
     
     printf( "First name = '%s'\n", (char*) ((_bstr_t) vtFirstName)); 
     
     rs->Fields->GetItem((long)2)->Value = L"TEST"; 
     rs->Update(vtMissing, vtMissing); 
     
     // Restore name 
     rs->Fields->GetItem((long)2)->PutValue(vtFirstName); 
     // -or- 
     rs->Fields->GetItem((long)2)->Value = vtFirstName; 
     rs->Update(vtMissing, vtMissing); 
     rs->Close(); 
     } 
     catch (_com_error &e) 
     { 
     printf("Description = '%s'\n", (char*) e.Description()); 
     } 
     ::CoUninitialize(); 
    } 
    ```

## <a name="casting-ado-object-pointers-with-idispatch-"></a>用 (IDispatch \*) 转换 ADO 对象指针

以下 Visual C++ 示例展示了如何使用 (IDispatch \*) 转换 ADO 对象指针。


> [!NOTE]
> <P>[!注释] 以下注释对应于代码示例中的注释部分。</P>



1.  在显式编码的 **变量型** 中指定打开的 **Connection** 对象。 将其与强制转换 (IDispatch \*) 以正确的构造函数调用。 此外，显式设置第二个**\_variant\_t**参数为默认值为**true**，因此**Recordset::Open**操作结束时，是正确的对象引用计数。

2.  表达式，(\_bstr\_t)，不是强制转换，但**\_variant\_t**提取的运算符**\_bstr\_t**从**变量****值**返回的字符串。 表达式，(char\*)，不是强制转换，但**\_bstr\_t**提取一个指向中封装的字符串的运算符**\_bstr\_t**对象。 代码的这一节演示一些有用行为**\_variant\_t**和**\_bstr\_t**运算符。
    
    ```cpp 
     
    #import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
     
    #include <stdio.h> 
     
    void main(void) 
    { 
     CoInitialize(NULL); 
     try 
     { 
     _ConnectionPtr pConn("ADODB.Connection"); 
     _RecordsetPtr pRst("ADODB.Recordset"); 
     
     pConn->Open("Provider=sqloledb;Data Source=MyServer;" 
     "Initial Catalog=pubs;Integrated Security=SSPI;", 
     "", "", adConnectUnspecified); 
    // Note 1. 
     pRst->Open( 
     "authors", 
     _variant_t((IDispatch *) pConn, true), 
     adOpenStatic, 
     adLockReadOnly, 
     adCmdTable); 
     pRst->MoveLast(); 
    // Note 2. 
     printf("Last name is '%s %s'\n", 
     (char*) ((_bstr_t) pRst->GetFields()->GetItem("au_fname")->GetValue()), 
     (char*) ((_bstr_t) pRst->Fields->Item["au_lname"]->Value)); 
     
     pRst->Close(); 
     pConn->Close(); 
     } 
     catch (_com_error &e) 
     { 
     printf("Description = '%s'\n", (char*) e.Description()); 
     } 
    ::CoUninitialize(); 
    } 
    ```

