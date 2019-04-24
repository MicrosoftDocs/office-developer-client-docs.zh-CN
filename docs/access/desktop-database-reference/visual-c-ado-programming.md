---
title: Visual C++ ADO 编程
TOCTitle: Visual C++ ADO programming
ms:assetid: 117c4fad-8c11-5e3a-ea0c-18811e87475f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248878(v=office.15)
ms:contentKeyID: 48543319
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2a890b4906fb9f207f12ff17ef0d3ccf1a97a44d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302770"
---
# <a name="visual-c-ado-programming"></a>Visual C++ ADO 编程

**适用于**：Access 2013、Office 2013

《ADO API 参考》采用类似 Microsoft Visual Basic 的语法来描述 ADO 应用程序编程接口 (API) 的功能。 虽然目标受众是所有用户, 但 ado 程序员采用各种语言, 如 visual Basic、visual c + + (带有和不带** \#import**指令) 和 Visual j + + (使用 ADO/WFC 类包)。

为照顾这种多样性，[ADO for Visual C++ 语法索引](using-ado-with-microsoft-visual-c.md)中提供了 Visual C++ 语言的专用语法，以及指向《API 参考》中功能、参数、异常行为等内容的一般性说明的链接。

ADO 采用 COM（组件对象模型）接口来实现。不过，对于程序员而言，在某些编程语言中使用 COM 要比在其他一些语言中更为容易。例如，在 Visual Basic 中，几乎所有使用 COM 的细节均已隐式处理，而在 Visual C++ 中，程序员必须留意这些细节。

以下各节概述了使用 ADO 和** \#import**指令的 C 和 c + + 程序员的详细信息。 它侧重于特定于 COM 的数据类型 (**Variant**、 **BSTR**和**SafeArray**) 和错误处理 (\_COM\_错误)。

## <a name="using-the-import-compiler-directive"></a>使用\#导入编译器指令

导入 Visual c + + 编译器指令简化了 ADO 方法和属性的使用。 ** \#** 该指令获取诸如 ADO .dll (Msado15.dll) 等包含类型库的文件的名称，然后生成包含 typedef 声明、智能接口指针和枚举常量的头文件。 每个接口都被封装或包装在类中。

对于类中的每个操作（即方法或属性调用），都存在一个声明以直接调用操作（即操作的“原始”形式），还存在另一个声明以调用原始操作并当操作无法成功执行时引发 COM 错误。如果操作为属性，则通常存在一个编译器指令，为具有类似 Visual Basic 语法的操作创建替代语法。

检索属性值的操作具有窗体的名称, **Get * *** * 属性。 设置属性值的操作具有 form、**Put * * * 属性*的名称。 使用指向 ADO 对象的指针设置属性值的操作具有 form 的名称, **PutRef * * * 属性*。

可以用以下形式的调用来获取或设置属性：

```vb 
 
variable = objectPtr->GetProperty(); // get property value 
objectPtr->PutProperty(value); // set property value 
objectPtr->PutRefProperty(&value); // set property with object pointer 
```

## <a name="using-property-directives"></a>使用属性指令

**declspec (property ...) 编译器指令是一种特定于 Microsoft 的 C 语言的扩展, 用于声明用作属性的函数, 以具有替代语法。 \_ \_** 因此，可以采用类似于 Visual Basic 的方式来设置或获取属性值。 例如，可以按照以下方式设置和获取属性：

```vb 
 
objectPtr->property = value; // set property value 
variable = objectPtr->property; // get property value 
```

请注意，您无需使用以下代码：

```vb 
 
objectPtr->PutProperty(value); // set property value 
variable = objectPtr->GetProperty; // get property value 
```

编译器将根据声明的替代语法以及是否正在读取或写入属性, 生成相应的 **Get * * *-*、 **Put**或 **PutRef * * 属性*调用。

**** **** **** **** ** \_declspec (属性 ...) 编译器指令只能声明 get、put 或 get 和\_** put 函数的替代语法。 只读操作只能具有 **get** 声明；只写操作只能具有 **put** 声明；读写操作可以具有 **get** 和 **put** 声明。

此指令只能有两个声明;但是, 每个属性可能具有三个属性函数: **Get * * * * 属性*、**Put * * * 属性*和 **PutRef * * * 属性*。 因此，只有两个属性具有替代语法。

例如, **Command**对象**ActiveConnection**属性声明为 **Get * * * * ActiveConnection*和 **PutRef * * * ActiveConnection*的替代语法。 因为在实践中通常希望将打开的 **Connection** 对象（即 **Connection** 对象指针）放在此属性中，因此 **PutRef**- 语法是较好的选择。 另一方面, **Recordset**对象具有**Get**、 **Put**和 **PutRef * * * ActiveConnection*操作, 但没有其他语法。

## <a name="collections-the-getitem-method-and-the-item-property"></a>集合、GetItem 方法和 Item 属性

ADO 定义了多个集合，包括 **Fields**、**Parameters**、**Properties** 和 **Errors**。 在 Visual c + + 中, **GetItem (***index***)** 方法返回集合的一个成员。 *index* 为 **Variant**，其值可以是集合中成员的数字索引，也可以是包含成员名称的字符串。

declspec ( **** **property ...) 编译器指令将 Item 属性声明为每个集合的基本 GetItem () 方法的替代\_ \_** 语法。 **** 替代语法使用方括号，类似于数组引用。 一般情况下，这两种形式如下所示：

```vb
    collectionPtr->GetItem(index); 
    collectionPtr->Item[index]; 
```

例如，若要给名为 **rs** 的 ***Recordset*** 对象的字段赋值，该对象派生自 **pubs** 数据库的 **authors** 表。 使用**Item ()** 属性可访问**Recordset**对象**字段**集合的第三个**字段**(集合从零开始索引; 假定第三个字段名为 ***"\_au fname***")。 然后，对 **Field** 对象调用 **Value()** 方法，并赋予字符串值。

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

\-或者-(也显示了**Value**属性的替代语法)

```cpp 
 
rs->Fields->Item[long(2)]->Value = "value"; 
rs->Fields->Item["au_fname"]->Value = "value"; 
```

## <a name="com-specific-data-types"></a>特定于 COM 的数据类型

一般而言，在《ADO API 参考》中找到的任何 Visual Basic 数据类型在 Visual C++ 中都有对应的类型。其中包括标准的数据类型，如 **无符号字符型** 对应于 Visual Basic 的 **Byte** ， **短型** 对应于 **整型** 以及 **长整型** 对应于 **长整型** 。请查阅"语法索引"，了解特定方法或属性具体需要什么类型的操作数。

此规则的例外之处是 COM 特有的数据类型：**Variant**、**BSTR** 和 **SafeArray**。

### <a name="variant"></a>Variant

**Variant** 是一种结构化数据类型，其中包含值成员和数据类型成员。**Variant** 中可能包含大量其他数据类型，包括另一个 Variant、BSTR、布尔型、IDispatch 或 IUnknown 指针、货币、日期等。COM 还提供了可以轻松地将一种数据类型转换为另一种数据类型的方法。

** \_variant\_t**类封装并管理**variant**数据类型。

当 ADO API 引用指示方法或属性操作数采用值时, 通常表示值是在** \_variant\_t**中传递的。

当《ADO API 参考》主题中的“参数”**** 部分提到操作数为 **Variant** 时，以上规则显然成立。一个例外是：当文档明确指出操作数采用标准数据类型，如 **Long**、**Byte** 或枚举型时。另一个例外是：当操作数采用 **String** 时。

### <a name="bstr"></a>BSTR

**BSTR**（基本字符串********）是一种结构化数据类型，其中包含字符串和字符串的长度。COM 提供了可分配、操作和释放 **BSTR** 的方法。

** \_bstr\_t**类封装和管理**bstr**数据类型。

当 ADO API 引用指出某个方法或属性采用**字符串**值时, 它表示值的格式为** \_bstr\_t**。

#### <a name="casting-variantt-and-bstrt-classes"></a>转换\_variant\_t 和\_bstr\_t 类

通常无需将参数中的** \_variant\_t**或** \_bstr\_t**显式编码为操作。 如果** \_\_variant t**或** \_bstr\_t**类具有与参数的数据类型相匹配的构造函数, 则编译器将生成相应** \_的 variant\_t**或** \_bstr\_t**。

不过，如果参数不明确，即参数的数据类型与多个构造函数匹配，那么必须用适当的数据类型转换参数，以调用正确的构造函数。

例如，**Recordset::Open** 方法的声明如下：

```vb 
 
 HRESULT Open ( 
 const _variant_t & Source, 
 const _variant_t & ActiveConnection, 
 enum CursorTypeEnum CursorType, 
 enum LockTypeEnum LockType, 
 long Options ); 
```

ActiveConnection 参数获取对** \_\_variant t**的引用, 您可以将其作为连接字符串或指向打开的**connection**对象的指针进行编码。

如果传递的是诸如 "DSN = pubs; uid = sa; pwd =;" 的字符串或诸如 "(IDispatch \*) pConn" 的指针, 则将隐式构造正确** \_的 variant\_t** 。

或者, 您可以显式地将\_\_ \* ** \_\_** 包含指针的 variant t 编码为 "variant t ((IDispatch) pConn, true)"。 cast (IDispatch \*) 使用另一个构造函数解析多义性, 该构造函数采用指向 IUnknown 接口的指针。

ADO 是 IDispatch 接口这一事实虽然很少提及，但这一点极为重要。指向 ADO 对象的指针都必须作为 **Variant** 传递，且该指针必须转换为指向 IDispatch 接口的指针。

最后一种情况是，显式地编写构造函数的第二个布尔型参数，其可选的默认值为 true。 此参数使**Variant**构造函数调用其**AddRef**() 方法, 在 ado 方法或属性调用完成时, 该方法会对 ado 进行补偿以自动调用** \_Variant\_t:: Release**() 方法。

### <a name="safearray"></a>SafeArray

**SafeArray** 是一种结构化数据类型，其中包含其他数据类型的数组。**SafeArray** 之所以被称为是 *“安全的”*，是由于它包含每个数组维度的界限信息，并限制对这些界限内数组元素的访问。

当《ADO API 参考》中提到方法或属性获取或返回数组时，表示方法或属性获取或返回的是 **SafeArray**，而不是本机 C/C++ 数组。

例如，**Connection** 对象的 **OpenSchema** 方法的第二个参数需要一个**变量型**值数组。这些**变量型**值必须作为 **SafeArray** 的元素传递，且该 **SafeArray** 必须设置为另一个**变量型**值，这便是作为 **OpenSchema** 的第二个参数传递的**变量型**。

更进一步，例如，**Find** 方法的第一个参数是值为一维 **SafeArray** 的**变量型**；**AddNew** 方法的可选的第一个和第二个参数为一维 **SafeArray**；**GetRows** 方法的返回值是值为二维 **SafeArray** 的**变量型**。

## <a name="missing-and-default-parameters"></a>缺少参数和默认参数

Visual Basic 允许方法中省略参数。例如，**Recordset** 对象 **Open** 方法具有五个参数，但您可以跳过中间的参数，只留下后面的参数。根据省略的操作数数据类型的不同，将替换为默认的 **BSTR** 或**变量型**。

在 C/C++ 中，必须指定所有操作数。 如果要指定的缺少的参数的数据类型为 string, 请指定包含空字符串的** \_bstr\_t** 。 如果要指定的缺少的参数的数据类型为**Variant**, 请指定一个\_\_\_ ** \_\_** 值为 "PARAMNOTFOUND E" 和一种 VT 错误的 variant t。 或者, 指定等效** \_的 variant\_t**常量, 即由** \#import**指令提供的**vtMissing**。

以下三种方法对于 **vtMissing** 的常见用法是例外：**Connection** 和 **Command** 对象的 **Execute** 方法以及 **Recordset** 对象的 **NextRecordset** 方法。以下是这些方法的签名：

```vb 
 
_RecordsetPtr Invalid DDUE based on source, error:link not allowed in code, link filename:mdmthcnnexecute_HV10294345.xml( _bstr_t CommandText, VARIANT * RecordsAffected, 
 long Options ); // Connection 
_RecordsetPtr Invalid DDUE based on source, error:link not allowed in code, link filename:mdmthcmdexecute_HV10294344.xml( VARIANT * RecordsAffected, VARIANT * Parameters, 
 long Options ); // Command 
_RecordsetPtr Invalid DDUE based on source, error:link not allowed in code, link filename:mdmthnextrec_HV10294541.xml( VARIANT * RecordsAffected ); // Recordset 
```

其中参数 *RecordsAffected* 和 *Parameters* 是指向**变量型**的指针。*Parameters* 是输入参数，用于指定包含单个参数或参数数组的**变量型**的地址，它将修改要执行的命令。*RecordsAffected* 是输出参数，用于指定**变量型**的地址，其中返回了受方法影响的行的数量。

在**Command**对象的**Execute**方法中, 通过将*参数*设置为\&vtMissing (推荐) 或 null 指针 (即**null**或零 (0)) 来指示未指定任何参数。 如果将 *Parameters* 设置为空指针，则方法将在内部替换等效的 **vtMissing**，然后完成操作。

在所有方法中，可以将 *RecordsAffected* 设置为空指针，以指示不应当返回受影响的记录数。此时，空指针不仅仅是省略的参数，还作为一个指示，表明方法应当放弃受影响的记录数。

因此，对于这三种方法而言，如下代码是有效的：

```vb 
 
pConnection->Execute("commandText", NULL, adCmdText); 
pCommand->Execute(NULL, NULL, adCmdText); 
pRecordset->NextRecordset(NULL); 
```

## <a name="error-handling"></a>错误处理

在 COM 中, 大多数操作返回一个 HRESULT 返回代码, 该代码指示函数是否已成功完成。 ** \#import**指令在每个 "raw" 方法或属性的周围生成包装代码, 并检查返回的 HRESULT。 如果 HRESULT 指示失败, 则包装代码会通过调用\_com\_问题\_errorex (), 并将 HRESULT 返回代码作为参数来引发 com 错误。 可以在**try**-**catch**块中捕获 COM error 对象。 (为了提高效率, 请捕获对** \_com\_error**对象的引用。)

请记住，这些是 ADO 错误：它们是由于 ADO 操作失败而导致的。基础提供程序返回的错误显示为 **Connection** 对象的 **Errors** 集合中的 **Error** 对象。

导入指令仅为在 ADO 中声明的方法和属性创建错误处理例程。 ** \#** 不过，您可以编写自己的错误检测宏或内嵌函数，以利用同样的错误处理机制。 有关示例，请参阅主题 [Visual C++ 扩展](visual-c-extensions-for-ado.md)或下文中的代码。

## <a name="visual-c-equivalents-of-visual-basic-conventions"></a>visual c + + 等效的 visual Basic 约定

以下摘要介绍用 Visual Basic 编写的 ADO 文档中的若干约定，以及等效的 Visual C++ 代码。

### <a name="declaring-an-ado-object"></a>声明 ADO 对象

在 Visual Basic 中，ADO 对象变量（此处以 **Recordset** 对象为例）声明如下：

```vb 
 
Dim rst As ADODB.Recordset 
```

子句 "ADODB。recordset ", 是注册表中定义的**recordset**对象的 ProgID。 **Record** 对象的新实例声明如下：

```vb 
 
Dim rst As New ADODB.Recordset 
```

\-和

```vb 
 
Dim rst As ADODB.Recordset 
Set rst = New ADODB.Recordset 
```

在 Visual c + + 中, ** \#导入**指令为所有 ADO 对象生成智能指针类型声明。 例如, 指向** \_Recordset**对象的变量的类型** \_为 RecordsetPtr**, 并声明如下:

```cpp 
 
_RecordsetPtr rs; 
```

指向** \_Recordset**对象的新实例的变量声明如下:

```cpp 
 
_RecordsetPtr rs("ADODB.Recordset"); 
```

\-和

```cpp 
 
_RecordsetPtr rs; 
rs.CreateInstance("ADODB.Recordset"); 
```

\-和

```cpp 
 
_RecordsetPtr rs; 
rs.CreateInstance(__uuidof(_Recordset)); 
```

调用 **CreateInstance** 方法之后，可以按照以下方式使用变量：

```cpp 
 
rs->Open(...); 
```

请注意, 在一种情况下, "." 运算符的使用方式就好像变量是类的实例 (rs。CreateInstance), 在另一种情况下, 将\>使用 "-" 运算符, 如同该变量是一个指向接口的指针 (rs\>-Open)。

可以通过两种方式使用一个变量, 这是因为\>重载了 "-" 运算符以允许类的实例像指向接口的指针一样正常工作。 实例变量的私有类成员包含指向** \_Recordset**接口的指针;"-\>" 运算符返回该指针;而返回的指针将访问** \_Recordset**对象的成员。

### <a name="coding-a-missing-parameter"></a>对缺少的参数进行编码

#### <a name="string"></a>字符串

在 Visual Basic 中，如果需要对省略的**字符串型**操作数进行编码，只需省略该操作数即可。 在 Visual C++ 中，则必须指定操作数。 代码将** \_空\_** 字符串作为值的 bstr t。

```cpp 
 
_bstr_t strMissing(L""); 
```

#### <a name="variant"></a>Variant

在 Visual Basic 中，如果需要对省略的**变量型**操作数进行编码，只需省略该操作数即可。 在 Visual C++ 中，则必须指定所有操作数。 代码缺少 variant **** 参数, 其** \_variant\_t**设置为特殊值, 指示\_E\_PARAMNOTFOUND, type, VT\_错误。 或者, 指定**vtMissing**, 它是由** \#import**指令提供的等效预定义常量。

```cpp 
 
_variant_t vtMissingYours(DISP_E_PARAMNOTFOUND, VT_ERROR); 
```

\-或使用-

```cpp 
 
...vtMissing...; 
```

### <a name="declaring-a-variant"></a>声明 variant

在 Visual Basic 中，用 **Dim** 语句声明**变量型**，如下所示：

```vb 
 
Dim VariableName As Variant 
```

在 Visual c + + 中, 将变量声明为** \_variant\_t**类型。 下面显示了几个示意性** \_的变量\_t**声明。

> [!NOTE]
> 这些声明仅仅为您在编写自己的程序时提供一个粗略的思路。有关详细信息，请参阅以下示例和 Visual C++ 文档。

```cpp 
 
_variant_t VariableName(value); 
_variant_t VariableName((data type cast) value); 
_variant_t VariableName(value, VT_DATATYPE); 
_variant_t VariableName(interface * value, bool fAddRef = true); 
```

### <a name="using-arrays-of-variants"></a>使用变量型数组

在 Visual Basic 中，可以用 **Dim** 语句编写**变量型**数组，或者也可以使用 **Array** 函数，如以下代码所示：

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

下面的 Visual c + + 示例演示了如何使用用于** \_variant\_t**的**SafeArray** 。

> [!NOTE]
> 以下注释对应于代码示例中的注释部分。

1. TESTHR() 内嵌函数再次被定义为利用现有的错误处理机制。

2. 您只需要一个一维数组，因此可以使用 **SafeArrayCreateVector** 取代通用的 **SAFEARRAYBOUND** 声明和 **SafeArrayCreate** 函数。如果使用 **SafeArrayCreate** ，则代码如下所示：
    
   ```cpp 
     
     SAFEARRAYBOUND sabound[1]; 
     sabound[0].lLbound = 0; 
     sabound[0].cElements = 4; 
     pSa = SafeArrayCreate(VT_VARIANT, 1, sabound); 
   ```

3. 由枚举常量**adSchemaColumns**标识的架构与四个约束列相关联:\_表目录、表\_架构、表\_名称和列\_名称。 因此，将创建包含四个元素的**变量型**数组。 然后, 指定与第三列 (表\_名称) 对应的约束值。 返回的 **Recordset** 包含多列，其子集为约束列。 每个返回行的约束列的值必须等于相应的约束值。

4. 熟悉 **SafeArrays** 的人可能会对退出前未调用 **SafeArrayDestroy**() 感到惊奇。 事实上，在此例中调用 **SafeArrayDestroy**() 会引发运行时异常。 原因是, 当** \_variant\_t**超出范围时, vtCriteria 的析构函数将调用**VariantClear**(), 这将释放**SafeArray**。 如果不手动清除** \_variant\_t**, 调用**SafeArrayDestroy**将导致析构函数尝试清除无效的**SafeArray**指针。 如果调用 **SafeArrayDestroy**，则代码如下所示：
    
   ```cpp 
     
     TESTHR(SafeArrayDestroy(pSa)); 
     vtCriteria.vt = VT_EMPTY; 
     vtCriteria.parray = NULL; 
   ```
    
   但是, 让** \_\_variant t**管理该**SafeArray**要简单得多。


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

### <a name="using-property-getputputref"></a>使用属性 Get/Put/PutRef

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

此 Visual c + + 示例展示了**Get**/**Put**/**PutRef * *** * 属性。

> [!NOTE]
> 以下注释对应于代码示例中的注释部分。

1. 此示例使用两种形式的缺少字符串参数: 一个显式常量、 **strMissing**和一个字符串, 编译器将使用该字符串创建**Open**方法范围内存在的临时** \_bstr\_t** 。

2. 不需要将 rs-\>PutRefActiveConnection (cn) 的操作数转换为 (idispatch \*), 因为操作数的类型已为 (idispatch \*)。
    
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

### <a name="using-getitemx-and-itemx"></a>使用 GetItem (x) 和 Item\[x\]

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

此 Visual C++ 示例展示了 **Item**。

> [!NOTE]
> [!注释] 以下注释对应于代码示例中的注释部分。

1. 当用 **Item** 访问集合时，索引 **2** 必须转换为 **长整型** ，以调用适当的构造函数。
    
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

### <a name="casting-ado-object-pointers-with-idispatch-"></a>使用 (IDispatch \*) 转换 ADO 对象指针

以下 Visual C++ 示例展示了如何使用 (IDispatch \*) 转换 ADO 对象指针。

> [!NOTE]
> [!注释] 以下注释对应于代码示例中的注释部分。

1. 在显式编码的 **变量型** 中指定打开的 **Connection** 对象。 将其转换为 ( \*IDispatch), 以便调用正确的构造函数。 此外, 将第二个** \_variant\_t**参数显式设置为默认值**true**, 以便在**Recordset:: Open**操作结束时, 对象引用计数将正确。

2. \_表达式 (bstr\_t) 不是强制转换, 而是一个** \_variant\_t**运算符, 它从**值**返回的**变量**中提取** \_bstr\_t**字符串。 表达式 (char\*) 不是一个强制转换, 而是一个** \_bstr\_t**运算符, 用于将指向** \_bstr\_t**对象中的封装字符串的指针提取出来。 此代码段演示了** \_variant\_t**和** \_bstr\_t**运算符的一些有用行为。
    
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

