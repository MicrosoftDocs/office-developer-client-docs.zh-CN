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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721288"
---
# <a name="visual-c-ado-programming"></a><span data-ttu-id="99923-102">Visual C++ ADO 编程</span><span class="sxs-lookup"><span data-stu-id="99923-102">Visual C++ ADO programming</span></span>

<span data-ttu-id="99923-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="99923-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="99923-104">《ADO API 参考》采用类似 Microsoft Visual Basic 的语法来描述 ADO 应用程序编程接口 (API) 的功能。</span><span class="sxs-lookup"><span data-stu-id="99923-104">The ADO API Reference describes the functionality of the ADO application programming interface (API) using a syntax similar to Microsoft Visual Basic.</span></span> <span data-ttu-id="99923-105">ADO 程序员目标的受众为所有用户，但使用不同的语言，例如 Visual Basic 中，Visual c + + (具有和没有**\#导入**指令)，并 Visual J + + （与 ADO/WFC 类封装）。</span><span class="sxs-lookup"><span data-stu-id="99923-105">Though the intended audience is all users, ADO programmers employ diverse languages such as Visual Basic, Visual C++ (with and without the **\#import** directive), and Visual J++ (with the ADO/WFC class package).</span></span>

<span data-ttu-id="99923-106">为照顾这种多样性，[ADO for Visual C++ 语法索引](using-ado-with-microsoft-visual-c.md)中提供了 Visual C++ 语言的专用语法，以及指向《API 参考》中功能、参数、异常行为等内容的一般性说明的链接。</span><span class="sxs-lookup"><span data-stu-id="99923-106">To accommodate this diversity, the [ADO for Visual C++ Syntax Indexes](using-ado-with-microsoft-visual-c.md) provide Visual C++ language-specific syntax with links to common descriptions of functionality, parameters, exceptional behaviors, and so on, in the API Reference.</span></span>

<span data-ttu-id="99923-p102">ADO 采用 COM（组件对象模型）接口来实现。不过，对于程序员而言，在某些编程语言中使用 COM 要比在其他一些语言中更为容易。例如，在 Visual Basic 中，几乎所有使用 COM 的细节均已隐式处理，而在 Visual C++ 中，程序员必须留意这些细节。</span><span class="sxs-lookup"><span data-stu-id="99923-p102">ADO is implemented with COM (Component Object Model) interfaces. However, it is easier for programmers to work with COM in certain programming languages than others. For example, nearly all the details of using COM are handled implicitly for Visual Basic programmers, whereas Visual C++ programmers must attend to those details themselves.</span></span>

<span data-ttu-id="99923-110">以下各节汇总为 C 和 c + + 程序员中使用 ADO 的详细信息和**\#导入**指令。</span><span class="sxs-lookup"><span data-stu-id="99923-110">The following sections summarize details for C and C++ programmers using ADO and the **\#import** directive.</span></span> <span data-ttu-id="99923-111">重点特定于 COM （**Variant**、 **BSTR**和**SafeArray**） 和错误处理的数据类型 (\_com\_错误)。</span><span class="sxs-lookup"><span data-stu-id="99923-111">It focuses on data types specific to COM (**Variant**, **BSTR**, and **SafeArray**), and error handling (\_com\_error).</span></span>

## <a name="using-the-import-compiler-directive"></a><span data-ttu-id="99923-112">使用\#导入编译器指令</span><span class="sxs-lookup"><span data-stu-id="99923-112">Using the \#import compiler directive</span></span>

<span data-ttu-id="99923-113">**\#导入**Visual c + + 编译器指令简化了使用 ADO 方法和属性。</span><span class="sxs-lookup"><span data-stu-id="99923-113">The **\#import** Visual C++ compiler directive simplifies working with the ADO methods and properties.</span></span> <span data-ttu-id="99923-114">该指令获取诸如 ADO .dll (Msado15.dll) 等包含类型库的文件的名称，然后生成包含 typedef 声明、智能接口指针和枚举常量的头文件。</span><span class="sxs-lookup"><span data-stu-id="99923-114">The directive takes the name of a file containing a type library, such as the ADO .dll (Msado15.dll), and generates header files containing typedef declarations, smart pointers for interfaces, and enumerated constants.</span></span> <span data-ttu-id="99923-115">每个接口都被封装或包装在类中。</span><span class="sxs-lookup"><span data-stu-id="99923-115">Each interface is encapsulated, or wrapped, in a class.</span></span>

<span data-ttu-id="99923-p105">对于类中的每个操作（即方法或属性调用），都存在一个声明以直接调用操作（即操作的"原始"形式），还存在另一个声明以调用原始操作并当操作无法成功执行时引发 COM 错误。如果操作为属性，则通常存在一个编译器指令，为具有类似 Visual Basic 语法的操作创建替代语法。</span><span class="sxs-lookup"><span data-stu-id="99923-p105">For each operation within a class (that is, a method or property call), there is a declaration to call the operation directly (that is, the "raw" form of the operation), and a declaration to call the raw operation and throw a COM error if the operation fails to execute successfully. If the operation is a property, there is usually a compiler directive that creates an alternative syntax for the operation that has syntax like Visual Basic.</span></span>

<span data-ttu-id="99923-118">检索属性的值的操作具有名称窗体，\**获取 \*\*\* 属性*。</span><span class="sxs-lookup"><span data-stu-id="99923-118">Operations that retrieve the value of a property have names of the form, \**Get\*\*\*Property*.</span></span> <span data-ttu-id="99923-119">设置属性的值的操作具有名称窗体，\**放置 \*\*\* 属性*。</span><span class="sxs-lookup"><span data-stu-id="99923-119">Operations that set the value of a property have names of the form, \**Put\*\*\*Property*.</span></span> <span data-ttu-id="99923-120">将指针的属性的值设置为 ADO 对象的操作具有名称窗体，\**PutRef \*\*\* 属性*。</span><span class="sxs-lookup"><span data-stu-id="99923-120">Operations that set the value of a property with a pointer to an ADO object have names of the form, \**PutRef\*\*\*Property*.</span></span>

<span data-ttu-id="99923-121">可以用以下形式的调用来获取或设置属性：</span><span class="sxs-lookup"><span data-stu-id="99923-121">You can get or set a property with calls of these forms:</span></span>

```vb 
 
variable = objectPtr->GetProperty(); // get property value 
objectPtr->PutProperty(value); // set property value 
objectPtr->PutRefProperty(&value); // set property with object pointer 
```

## <a name="using-property-directives"></a><span data-ttu-id="99923-122">使用属性指令</span><span class="sxs-lookup"><span data-stu-id="99923-122">Using property directives</span></span>

<span data-ttu-id="99923-123">\*\* \_ \_Declspec(property...)\*\* 编译器指令是声明为属性用于具有替代语法函数的特定的 Microsoft C 语言扩展。</span><span class="sxs-lookup"><span data-stu-id="99923-123">The **\_\_declspec(property...)** compiler directive is a Microsoft-specific C language extension that declares a function used as a property to have an alternative syntax.</span></span> <span data-ttu-id="99923-124">因此，可以采用类似于 Visual Basic 的方式来设置或获取属性值。</span><span class="sxs-lookup"><span data-stu-id="99923-124">As a result, you can set or get values of a property in a way similar to Visual Basic.</span></span> <span data-ttu-id="99923-125">例如，可以按照以下方式设置和获取属性：</span><span class="sxs-lookup"><span data-stu-id="99923-125">For example, you can set and get a property this way:</span></span>

```vb 
 
objectPtr->property = value; // set property value 
variable = objectPtr->property; // get property value 
```

<span data-ttu-id="99923-126">请注意，您无需使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="99923-126">Notice you do not have to code:</span></span>

```vb 
 
objectPtr->PutProperty(value); // set property value 
variable = objectPtr->GetProperty; // get property value 
```

<span data-ttu-id="99923-127">编译器将生成相应 \*\*Get \*\**-*， **Put**-，或 \**PutRef \*\*\* 属性*呼叫基于声明的哪些替代语法以及是否正在属性读取或写入。</span><span class="sxs-lookup"><span data-stu-id="99923-127">The compiler will generate the appropriate \**Get\*\*\*-*, **Put**-, or \**PutRef\*\*\*Property* call based on what alternative syntax is declared and whether the property is being read or written.</span></span>

<span data-ttu-id="99923-128">\*\* \_ \_Declspec(property...)\*\* 编译器指令只能声明**获取**、 **put**，或将函数**获取**并**放置**替代语法。</span><span class="sxs-lookup"><span data-stu-id="99923-128">The **\_\_declspec(property...)** compiler directive can only declare **get**, **put**, or **get** and **put** alternative syntax for a function.</span></span> <span data-ttu-id="99923-129">只读操作只能具有 **get** 声明；只写操作只能具有 **put** 声明；读写操作可以具有 **get** 和 **put** 声明。</span><span class="sxs-lookup"><span data-stu-id="99923-129">Read-only operations only have a **get** declaration; write-only operations only have a **put** declaration; operations that are both read and write have both **get** and **put** declarations.</span></span>

<span data-ttu-id="99923-130">只有两个声明而言，可能有此指令;但是，每个属性可能有三个属性函数: **获取 \*\*\* 属性\*，**放置 \*\*\* 属性\*，和 \**PutRef \*\*\* 属性*。</span><span class="sxs-lookup"><span data-stu-id="99923-130">Only two declarations are possible with this directive; however, each property may have three property functions: \**Get\*\*\*Property*, \**Put\*\*\*Property*, and \**PutRef\*\*\*Property*.</span></span> <span data-ttu-id="99923-131">因此，只有两个属性具有替代语法。</span><span class="sxs-lookup"><span data-stu-id="99923-131">In that case, only two forms of the property have the alternative syntax.</span></span>

<span data-ttu-id="99923-132">例如， **ActiveConnection**属性将**Command**对象用声明的替代语法 \**获取 \*\*\* ActiveConnection*和 \**PutRef \*\*\* ActiveConnection*。</span><span class="sxs-lookup"><span data-stu-id="99923-132">For example, the **Command** object **ActiveConnection** property is declared with an alternative syntax for \**Get\*\*\*ActiveConnection* and \**PutRef\*\*\*ActiveConnection*.</span></span> <span data-ttu-id="99923-133">**PutRef**-语法因为实际上，通常要打开的**Connection**对象 （即，**连接**对象指针） 置于此属性是一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="99923-133">The **PutRef**- syntax is a good choice because in practice, you will typically want to put an open **Connection** object (that is, a **Connection** object pointer) in this property.</span></span> <span data-ttu-id="99923-134">另一方面， **Recordset**对象中的**Get**-、 **Put**-和 \**PutRef \*\*\* ActiveConnection*操作，但没有替代语法。</span><span class="sxs-lookup"><span data-stu-id="99923-134">On the other hand, the **Recordset** object has **Get**-, **Put**-, and \**PutRef\*\*\*ActiveConnection* operations, but no alternative syntax.</span></span>

## <a name="collections-the-getitem-method-and-the-item-property"></a><span data-ttu-id="99923-135">集合、 GetItem 方法和 Item 属性</span><span class="sxs-lookup"><span data-stu-id="99923-135">Collections, the GetItem method, and the Item property</span></span>

<span data-ttu-id="99923-p111">ADO 定义了多个集合，包括 **Fields**、**Parameters**、**Properties** 和 **Errors**。在 Visual C++ 中，**GetItem(***index***)** 方法返回集合的成员。*index* 为 **Variant**，其值可以是集合中成员的数字索引，也可以是包含成员名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="99923-p111">ADO defines several collections, including **Fields**, **Parameters**, **Properties**, and **Errors**. In Visual C++, the **GetItem(***index***)** method returns a member of the collection. *Index* is a **Variant**, the value of which is either a numerical index of the member in the collection, or a string containing the name of the member.</span></span>

<span data-ttu-id="99923-139">\*\* \_ \_Declspec(property...)\*\* 编译器指令声明为每个集合的基本**GetItem()** 方法的可选语法**Item**属性。</span><span class="sxs-lookup"><span data-stu-id="99923-139">The **\_\_declspec(property...)** compiler directive declares the **Item** property as an alternative syntax to each collection's fundamental **GetItem()** method.</span></span> <span data-ttu-id="99923-140">替代语法使用方括号，类似于数组引用。</span><span class="sxs-lookup"><span data-stu-id="99923-140">The alternative syntax uses square brackets and looks similar to an array reference.</span></span> <span data-ttu-id="99923-141">一般情况下，这两种形式如下所示：</span><span class="sxs-lookup"><span data-stu-id="99923-141">In general, the two forms look like the following:</span></span>

```vb
    collectionPtr->GetItem(index); 
    collectionPtr->Item[index]; 
```

<span data-ttu-id="99923-142">例如，将值分配给名为***rs***，派生自**pubs**数据库的**authors**表的**Recordset**对象的字段。</span><span class="sxs-lookup"><span data-stu-id="99923-142">For example, assign a value to a field of a **Recordset** object, named ***rs***, derived from the **authors** table of the **pubs** database.</span></span> <span data-ttu-id="99923-143">使用**了 item （）** 属性访问**Recordset**对象的**Fields**集合的第三个**字段**(集索引从零; 假定第三个字段，命名为***au\_fname***)。</span><span class="sxs-lookup"><span data-stu-id="99923-143">Use the **Item()** property to access the third **Field** of the **Recordset** object **Fields** collection (collections are indexed from zero; assume the third field is named ***au\_fname***).</span></span> <span data-ttu-id="99923-144">对**Field**对象分配一个 string 值，然后调用**使用 value （）** 方法。</span><span class="sxs-lookup"><span data-stu-id="99923-144">Then call the **Value()** method on the **Field** object to assign a string value.</span></span>

<span data-ttu-id="99923-145">在 Visual Basic 中，以上操作可采用以下四种方式表达（后两种方式是 Visual Basic 所独有的；其他语言没有等效的代码）：</span><span class="sxs-lookup"><span data-stu-id="99923-145">This can be expressed in Visual Basic in the following four ways (the last two forms are unique to Visual Basic; other languages do not have equivalents):</span></span>

```vb 
 
rs.Fields.Item(2).Value = "value" 
rs.Fields.Item("au_fname").Value = "value" 
rs(2) = "value" 
rs!au_fname = "value" 
```

<span data-ttu-id="99923-146">在 Visual C++ 中，与以上前两种方式等效的代码如下：</span><span class="sxs-lookup"><span data-stu-id="99923-146">The equivalent in Visual C++ to the first two forms above is:</span></span>

```cpp 
 
rs->Fields->GetItem(long(2))->PutValue("value"); 
rs->Fields->GetItem("au_fname")->PutValue("value"); 
```

<span data-ttu-id="99923-147">\-或-（还显示**Value**属性的替代语法）</span><span class="sxs-lookup"><span data-stu-id="99923-147">\-or- (the alternative syntax for the **Value** property is also shown)</span></span>

```cpp 
 
rs->Fields->Item[long(2)]->Value = "value"; 
rs->Fields->Item["au_fname"]->Value = "value"; 
```

## <a name="com-specific-data-types"></a><span data-ttu-id="99923-148">COM 特有的数据类型</span><span class="sxs-lookup"><span data-stu-id="99923-148">COM-specific data types</span></span>

<span data-ttu-id="99923-p114">一般而言，在《ADO API 参考》中找到的任何 Visual Basic 数据类型在 Visual C++ 中都有对应的类型。其中包括标准的数据类型，如 **无符号字符型** 对应于 Visual Basic 的 **Byte** ， **短型** 对应于 **整型** 以及 **长整型** 对应于 **长整型** 。请查阅"语法索引"，了解特定方法或属性具体需要什么类型的操作数。</span><span class="sxs-lookup"><span data-stu-id="99923-p114">In general, any Visual Basic data type you find in the ADO API Reference has a Visual C++ equivalent. These include standard data types such as **unsigned char** for a Visual Basic **Byte**, **short** for **Integer**, and **long** for **Long**. Look in the Syntax Indexes to see exactly what is required for the operands of a given method or property.</span></span>

<span data-ttu-id="99923-152">此规则的例外之处是 COM 特有的数据类型： **Variant** 、 **BSTR** 和 **SafeArray** 。</span><span class="sxs-lookup"><span data-stu-id="99923-152">The exceptions to this rule are the data types specific to COM: **Variant**, **BSTR**, and **SafeArray**.</span></span>

### <a name="variant"></a><span data-ttu-id="99923-153">Variant</span><span class="sxs-lookup"><span data-stu-id="99923-153">Variant</span></span>

<span data-ttu-id="99923-p115">**Variant** 是一种结构化数据类型，其中包含值成员和数据类型成员。 **Variant** 中可能包含大量其他数据类型，包括另一个 Variant、BSTR、布尔型、IDispatch 或 IUnknown 指针、货币、日期等。COM 还提供了可以轻松地将一种数据类型转换为另一种数据类型的方法。</span><span class="sxs-lookup"><span data-stu-id="99923-p115">A **Variant** is a structured data type that contains a value member and a data type member. A **Variant** may contain a wide range of other data types including another Variant, BSTR, Boolean, IDispatch or IUnknown pointer, currency, date, and so on. COM also provides methods that make it easy to convert one data type to another.</span></span>

<span data-ttu-id="99923-157">\*\* \_Variant\_t**类封装并管理**Variant\*\*数据类型。</span><span class="sxs-lookup"><span data-stu-id="99923-157">The **\_variant\_t** class encapsulates and manages the **Variant** data type.</span></span>

<span data-ttu-id="99923-158">当 ADO API 参考方法或属性操作数采用值时，它通常表示值被传递中**\_variant\_t**。</span><span class="sxs-lookup"><span data-stu-id="99923-158">When the ADO API Reference says a method or property operand takes a value, it usually means the value is passed in a **\_variant\_t**.</span></span>

<span data-ttu-id="99923-159">此规则明确为 true 时 ADO API 参考主题中的**参数**部分显示操作数是**Variant**。</span><span class="sxs-lookup"><span data-stu-id="99923-159">This rule is explicitly true when the **Parameters** section in the topics of the ADO API Reference says an operand is a **Variant**.</span></span> <span data-ttu-id="99923-160">文档明确指出操作数采用标准数据类型，如**Long** 、**字节**或枚举时一个例外。</span><span class="sxs-lookup"><span data-stu-id="99923-160">One exception is when the documentation explicitly says the operand takes a standard data type, such as **Long** or **Byte**, or an enumeration.</span></span> <span data-ttu-id="99923-161">操作数采用**字符串**时，另一个异常。</span><span class="sxs-lookup"><span data-stu-id="99923-161">Another exception is when the operand takes a **String**.</span></span>

### <a name="bstr"></a><span data-ttu-id="99923-162">BSTR</span><span class="sxs-lookup"><span data-stu-id="99923-162">BSTR</span></span>

<span data-ttu-id="99923-163">**BSTR** （**B**asic **STR**来） 是包含字符串和字符串的长度的结构化的数据类型。</span><span class="sxs-lookup"><span data-stu-id="99923-163">A **BSTR** (**B**asic **STR**ing) is a structured data type that contains a character string and the string's length.</span></span> <span data-ttu-id="99923-164">COM 提供用于分配、 操作和忙**BSTR**方法。</span><span class="sxs-lookup"><span data-stu-id="99923-164">COM provides methods to allocate, manipulate, and free a **BSTR**.</span></span>

<span data-ttu-id="99923-165">\*\* \_Bstr\_t**类封装和管理**BSTR\*\*数据类型。</span><span class="sxs-lookup"><span data-stu-id="99923-165">The **\_bstr\_t** class encapsulates and manages the **BSTR** data type.</span></span>

<span data-ttu-id="99923-166">当 ADO API 参考方法或属性采用**字符串**值时，它表示的窗体中的值是**\_bstr\_t**。</span><span class="sxs-lookup"><span data-stu-id="99923-166">When the ADO API Reference says a method or property takes a **String** value, it means the value is in the form of a **\_bstr\_t**.</span></span>

#### <a name="casting-variantt-and-bstrt-classes"></a><span data-ttu-id="99923-167">转换\_variant\_t 和\_bstr\_t 类</span><span class="sxs-lookup"><span data-stu-id="99923-167">Casting \_variant\_t and \_bstr\_t classes</span></span>

<span data-ttu-id="99923-168">通常不需要显式代码为**\_variant\_t**或**\_bstr\_t**操作参数。</span><span class="sxs-lookup"><span data-stu-id="99923-168">Often it is not necessary to explicitly code a **\_variant\_t** or **\_bstr\_t** in an argument to an operation.</span></span> <span data-ttu-id="99923-169">如果**\_variant\_t**或**\_bstr\_t**类具有一个构造函数的参数的数据类型相匹配，则编译器将生成相应**\_variant\_t**或**\_bstr\_t**。</span><span class="sxs-lookup"><span data-stu-id="99923-169">If the **\_variant\_t** or **\_bstr\_t** class has a constructor that matches the data type of the argument, then the compiler will generate the appropriate **\_variant\_t** or **\_bstr\_t**.</span></span>

<span data-ttu-id="99923-170">不过，如果参数不明确，即参数的数据类型与多个构造函数匹配，那么必须用适当的数据类型转换参数，以调用正确的构造函数。</span><span class="sxs-lookup"><span data-stu-id="99923-170">However, if the argument is ambiguous, that is, the argument's data type matches more than one constructor, you must cast the argument with the appropriate data type to invoke the correct constructor.</span></span>

<span data-ttu-id="99923-171">例如， **Recordset::Open** 方法的声明如下：</span><span class="sxs-lookup"><span data-stu-id="99923-171">For example, the declaration for the **Recordset::Open** method is:</span></span>

```vb 
 
 HRESULT Open ( 
 const _variant_t & Source, 
 const _variant_t & ActiveConnection, 
 enum CursorTypeEnum CursorType, 
 enum LockTypeEnum LockType, 
 long Options ); 
```

<span data-ttu-id="99923-172">其中 ActiveConnection 参数采用引用**\_variant\_t**，其中可能编写为一个连接字符串或指向打开的**Connection**对象的指针。</span><span class="sxs-lookup"><span data-stu-id="99923-172">The ActiveConnection argument takes a reference to a **\_variant\_t**, which you may code as a connection string or a pointer to an open **Connection** object.</span></span>

<span data-ttu-id="99923-173">正确**\_variant\_t**将隐式构造，如果您传递一个字符串，如"DSN = pubs; uid = sa; pwd =;"，或如指针"(IDispatch \*) pConn"。</span><span class="sxs-lookup"><span data-stu-id="99923-173">The correct **\_variant\_t** will be constructed implicitly if you pass a string such as "DSN=pubs;uid=sa;pwd=;", or a pointer such as "(IDispatch \*) pConn".</span></span>

<span data-ttu-id="99923-174">显式可能代码或**\_variant\_t**包含一个指针，如"\_variant\_t ((IDispatch \*) pConn，true)"。</span><span class="sxs-lookup"><span data-stu-id="99923-174">Or you may explicitly code a **\_variant\_t** containing a pointer such as "\_variant\_t((IDispatch \*) pConn, true)".</span></span> <span data-ttu-id="99923-175">强制转换，(IDispatch \*)，解析为与另一个构造函数采用的 IUnknown 接口的指针歧义。</span><span class="sxs-lookup"><span data-stu-id="99923-175">The cast, (IDispatch \*), resolves the ambiguity with another constructor that takes a pointer to an IUnknown interface.</span></span>

<span data-ttu-id="99923-p120">ADO 是 IDispatch 接口这一事实虽然很少提及，但这一点极为重要。指向 ADO 对象的指针都必须作为 **Variant** 传递，且该指针必须转换为指向 IDispatch 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="99923-p120">It is a crucial, though seldom mentioned fact, that ADO is an IDispatch interface. Whenever a pointer to an ADO object must be passed as a **Variant**, that pointer must be cast as a pointer to an IDispatch interface.</span></span>

<span data-ttu-id="99923-178">最后一种情况明确编写构造函数的第二个布尔参数，其可选，默认值为 true。</span><span class="sxs-lookup"><span data-stu-id="99923-178">The last case explicitly codes the second boolean argument of the constructor with its optional, default value of true.</span></span> <span data-ttu-id="99923-179">此参数导致**Variant**构造函数调用其**AddRef**（） 方法，ADO 自动调用补偿**\_variant\_t::Release**（） 方法 （ADO 方法或属性调用完成时。</span><span class="sxs-lookup"><span data-stu-id="99923-179">This argument causes the **Variant** constructor to call its **AddRef**() method, which compensates for ADO automatically calling the **\_variant\_t::Release**() method when the ADO method or property call completes.</span></span>

### <a name="safearray"></a><span data-ttu-id="99923-180">SafeArray</span><span class="sxs-lookup"><span data-stu-id="99923-180">SafeArray</span></span>

<span data-ttu-id="99923-181">**SafeArray** 是一种结构化数据类型，其中包含其他数据类型的数组。</span><span class="sxs-lookup"><span data-stu-id="99923-181">A **SafeArray** is a structured data type that contains an array of other data types.</span></span> <span data-ttu-id="99923-182">**SafeArray**称为*安全*，因为它包含的界限每个数组维度和限制访问这些边界内的数组元素的信息。</span><span class="sxs-lookup"><span data-stu-id="99923-182">A **SafeArray** is called *safe* because it contains information about the bounds of each array dimension, and limits access to array elements within those bounds.</span></span>

<span data-ttu-id="99923-183">当《ADO API 参考》中提到方法或属性获取或返回数组时，表示方法或属性获取或返回的是 **SafeArray** ，而不是本机 C/C++ 数组。</span><span class="sxs-lookup"><span data-stu-id="99923-183">When the ADO API Reference says a method or property takes or returns an array, it means the method or property takes or returns a **SafeArray**, not a native C/C++ array.</span></span>

<span data-ttu-id="99923-p123">例如， **Connection** 对象的 **OpenSchema** 方法的第二个参数需要一个 **变量型** 值数组。这些 **变量型** 值必须作为 **SafeArray** 的元素传递，且该 **SafeArray** 必须设置为另一个 **变量型** 值，这便是作为 **OpenSchema** 的第二个参数传递的 **变量型** 。</span><span class="sxs-lookup"><span data-stu-id="99923-p123">For example, the second parameter of the **Connection** object **OpenSchema** method requires an array of **Variant** values. Those **Variant** values must be passed as elements of a **SafeArray**, and that **SafeArray** must be set as the value of another **Variant**. It is that other **Variant** that is passed as the second argument of **OpenSchema**.</span></span>

<span data-ttu-id="99923-187">更进一步，例如， **Find** 方法的第一个参数是值为一维 **SafeArray** 的 **变量型** ； **AddNew** 方法的可选的第一个和第二个参数为一维 **SafeArray** ； **GetRows** 方法的返回值是值为二维 **SafeArray** 的 **变量型** 。</span><span class="sxs-lookup"><span data-stu-id="99923-187">As further examples, the first argument of the **Find** method is a **Variant** whose value is a one-dimensional **SafeArray**; each of the optional first and second arguments of **AddNew** is a one-dimensional **SafeArray**; and the return value of the **GetRows** method is a **Variant** whose value is a two-dimensional **SafeArray**.</span></span>

## <a name="missing-and-default-parameters"></a><span data-ttu-id="99923-188">缺少和默认参数</span><span class="sxs-lookup"><span data-stu-id="99923-188">Missing and default parameters</span></span>

<span data-ttu-id="99923-p124">Visual Basic 允许方法中省略参数。例如， **Recordset** 对象 **Open** 方法具有五个参数，但您可以跳过中间的参数，只留下后面的参数。根据省略的操作数数据类型的不同，将替换为默认的 **BSTR** 或 **变量型** 。</span><span class="sxs-lookup"><span data-stu-id="99923-p124">Visual Basic allows missing parameters in methods. For example, the **Recordset** object **Open** method has five parameters, but you can skip intermediate parameters and leave off trailing parameters. A default **BSTR** or **Variant** will be substituted depending on the data type of the missing operand.</span></span>

<span data-ttu-id="99923-192">在 C/C++ 中，必须指定所有操作数。</span><span class="sxs-lookup"><span data-stu-id="99923-192">In C/C++, all operands must be specified.</span></span> <span data-ttu-id="99923-193">如果您想要指定缺少的参数数据类型是一个字符串，指定**\_bstr\_t**包含空字符串。</span><span class="sxs-lookup"><span data-stu-id="99923-193">If you want to specify a missing parameter whose data type is a string, specify a **\_bstr\_t** containing a null string.</span></span> <span data-ttu-id="99923-194">如果您想要指定缺少的参数数据类型是**variant 类型的值**，指定**\_variant\_t**值显示为\_E\_PARAMNOTFOUND 和 VT 类型\_错误。</span><span class="sxs-lookup"><span data-stu-id="99923-194">If you want to specify a missing parameter whose data type is a **Variant**, specify a **\_variant\_t** with a value of DISP\_E\_PARAMNOTFOUND and a type of VT\_ERROR.</span></span> <span data-ttu-id="99923-195">此外，指定等同**\_variant\_t**常量、 **vtMissing**，后者提供通过**\#导入**指令。</span><span class="sxs-lookup"><span data-stu-id="99923-195">Alternatively, specify the equivalent **\_variant\_t** constant, **vtMissing**, which is supplied by the **\#import** directive.</span></span>

<span data-ttu-id="99923-p126">以下三种方法对于 **vtMissing** 的常见用法是例外： **Connection** 和 **Command** 对象的 **Execute** 方法以及 **Recordset** 对象的 **NextRecordset** 方法。以下是这些方法的签名：</span><span class="sxs-lookup"><span data-stu-id="99923-p126">Three methods are exceptions to the typical use of **vtMissing**. These are the **Execute** methods of the **Connection** and **Command** objects, and the **NextRecordset** method of the **Recordset** object. The following are their signatures:</span></span>

```vb 
 
_RecordsetPtr Invalid DDUE based on source, error:link not allowed in code, link filename:mdmthcnnexecute_HV10294345.xml( _bstr_t CommandText, VARIANT * RecordsAffected, 
 long Options ); // Connection 
_RecordsetPtr Invalid DDUE based on source, error:link not allowed in code, link filename:mdmthcmdexecute_HV10294344.xml( VARIANT * RecordsAffected, VARIANT * Parameters, 
 long Options ); // Command 
_RecordsetPtr Invalid DDUE based on source, error:link not allowed in code, link filename:mdmthnextrec_HV10294541.xml( VARIANT * RecordsAffected ); // Recordset 
```

<span data-ttu-id="99923-p127">其中参数 *RecordsAffected* 和 *Parameters* 是指向**变量型**的指针。*Parameters* 是输入参数，用于指定包含单个参数或参数数组的**变量型**的地址，它将修改要执行的命令。*RecordsAffected* 是输出参数，用于指定**变量型**的地址，其中返回了受方法影响的行的数量。</span><span class="sxs-lookup"><span data-stu-id="99923-p127">The parameters, *RecordsAffected* and *Parameters*, are pointers to a **Variant**. *Parameters* is an input parameter which specifies the address of a **Variant** containing a single parameter, or array of parameters, that will modify the command being executed. *RecordsAffected* is an output parameter that specifies the address of a **Variant**, where the number of rows affected by the method is returned.</span></span>

<span data-ttu-id="99923-202">在**Execute**方法的**Command**对象，指示*参数*设置为以下任意未指定任何参数\&vtMissing （这建议） 或 null 的指针 （即**NULL**或零 (0)）。</span><span class="sxs-lookup"><span data-stu-id="99923-202">In the **Command** object **Execute** method, indicate that no parameters are specified by setting *Parameters* to either \&vtMissing (which is recommended) or to the null pointer (that is, **NULL** or zero (0)).</span></span> <span data-ttu-id="99923-203">如果*参数*设置为 null 的指针，该方法将内部替换**vtMissing**的等效项，然后完成该操作。</span><span class="sxs-lookup"><span data-stu-id="99923-203">If *Parameters* is set to the null pointer, the method internally substitutes the equivalent of **vtMissing**, and then completes the operation.</span></span>

<span data-ttu-id="99923-204">在所有方法，指示影响的记录数不应返回通过将*RecordsAffected*设置为 null 的指针。</span><span class="sxs-lookup"><span data-stu-id="99923-204">In all the methods, indicate that the number of records affected should not be returned by setting *RecordsAffected* to the null pointer.</span></span> <span data-ttu-id="99923-205">此时，空指针不仅仅是省略的参数，还作为一个指示，表明方法应当放弃受影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="99923-205">In this case, the null pointer is not so much a missing parameter as an indication that the method should discard the number of records affected.</span></span>

<span data-ttu-id="99923-206">因此，对于这三种方法而言，如下代码是有效的：</span><span class="sxs-lookup"><span data-stu-id="99923-206">Thus, for these three methods, it is valid to code something such as:</span></span>

```vb 
 
pConnection->Execute("commandText", NULL, adCmdText); 
pCommand->Execute(NULL, NULL, adCmdText); 
pRecordset->NextRecordset(NULL); 
```

## <a name="error-handling"></a><span data-ttu-id="99923-207">错误处理</span><span class="sxs-lookup"><span data-stu-id="99923-207">Error handling</span></span>

<span data-ttu-id="99923-208">在 COM，大多数操作返回 HRESULT 返回代码，指示函数是否已成功完成。</span><span class="sxs-lookup"><span data-stu-id="99923-208">In COM, most operations return an HRESULT return code that indicates whether a function completed successfully.</span></span> <span data-ttu-id="99923-209">**\#导入**指令生成周围每个"原始"方法或属性的包装代码，并检查返回的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="99923-209">The **\#import** directive generates wrapper code around each "raw" method or property and checks the returned HRESULT.</span></span> <span data-ttu-id="99923-210">如果 HRESULT 指示故障，包装代码通过调用引发 COM 错误\_com\_问题\_errorex() hresult 返回作为参数的代码。</span><span class="sxs-lookup"><span data-stu-id="99923-210">If the HRESULT indicates failure, the wrapper code throws a COM error by calling \_com\_issue\_errorex() with the HRESULT return code as an argument.</span></span> <span data-ttu-id="99923-211">可以在**尝试**捕获 COM error 对象-**catch**块。</span><span class="sxs-lookup"><span data-stu-id="99923-211">COM error objects can be caught in a **try**-**catch** block.</span></span> <span data-ttu-id="99923-212">(为效率的起见，捕获对**\_com\_错误**对象。)</span><span class="sxs-lookup"><span data-stu-id="99923-212">(For efficiency's sake, catch a reference to a **\_com\_error** object.)</span></span>

<span data-ttu-id="99923-p131">请记住，这些是 ADO 错误：它们是由于 ADO 操作失败而导致的。基础提供程序返回的错误显示为 **Connection** 对象的 **Errors** 集合中的 **Error** 对象。</span><span class="sxs-lookup"><span data-stu-id="99923-p131">Remember, these are ADO errors: they result from the ADO operation failing. Errors returned by the underlying provider appear as **Error** objects in the **Connection** object **Errors** collection.</span></span>

<span data-ttu-id="99923-215">**\#导入**指令创建唯一的错误处理例程的方法和属性在 ADO.dll 中声明。</span><span class="sxs-lookup"><span data-stu-id="99923-215">The **\#import** directive creates only error handling routines for methods and properties declared in the ADO .dll.</span></span> <span data-ttu-id="99923-216">不过，您可以编写自己的错误检测宏或内嵌函数，以利用同样的错误处理机制。</span><span class="sxs-lookup"><span data-stu-id="99923-216">However, you can take advantage of this same error handling mechanism by writing your own error checking macro or inline function.</span></span> <span data-ttu-id="99923-217">有关示例，请参阅主题 [Visual C++ 扩展](visual-c-extensions-for-ado.md)或下文中的代码。</span><span class="sxs-lookup"><span data-stu-id="99923-217">See the topic, [Visual C++ Extensions](visual-c-extensions-for-ado.md), or the code in the following sections for examples.</span></span>

## <a name="visual-c-equivalents-of-visual-basic-conventions"></a><span data-ttu-id="99923-218">Visual Basic 约定等效的 visual c + + 值</span><span class="sxs-lookup"><span data-stu-id="99923-218">Visual C++ equivalents of Visual Basic conventions</span></span>

<span data-ttu-id="99923-219">以下摘要介绍用 Visual Basic 编写的 ADO 文档中的若干约定，以及等效的 Visual C++ 代码。</span><span class="sxs-lookup"><span data-stu-id="99923-219">The following is a summary of several conventions in the ADO documentation, coded in Visual Basic, as well as their equivalents in Visual C++.</span></span>

### <a name="declaring-an-ado-object"></a><span data-ttu-id="99923-220">声明 ADO 对象</span><span class="sxs-lookup"><span data-stu-id="99923-220">Declaring an ADO object</span></span>

<span data-ttu-id="99923-221">在 Visual Basic 中，ADO 对象变量（此处以 **Recordset** 对象为例）声明如下：</span><span class="sxs-lookup"><span data-stu-id="99923-221">In Visual Basic, an ADO object variable (in this case for a **Recordset** object) is declared as follows:</span></span>

```vb 
 
Dim rst As ADODB.Recordset 
```

<span data-ttu-id="99923-222">子句中，"ADODB。记录集"，是在注册表中定义的 ProgID 的**Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="99923-222">The clause, "ADODB.Recordset", is the ProgID of the **Recordset** object as defined in the Registry.</span></span> <span data-ttu-id="99923-223">**Record** 对象的新实例声明如下：</span><span class="sxs-lookup"><span data-stu-id="99923-223">A new instance of a **Record** object is declared as follows:</span></span>

```vb 
 
Dim rst As New ADODB.Recordset 
```

<span data-ttu-id="99923-224">\-或-</span><span class="sxs-lookup"><span data-stu-id="99923-224">\-or-</span></span>

```vb 
 
Dim rst As ADODB.Recordset 
Set rst = New ADODB.Recordset 
```

<span data-ttu-id="99923-225">Visual c + + 中，在**\#导入**指令将生成的所有 ADO 对象的智能指针类型声明。</span><span class="sxs-lookup"><span data-stu-id="99923-225">In Visual C++, the **\#import** directive generates smart pointer-type declarations for all the ADO objects.</span></span> <span data-ttu-id="99923-226">例如，变量指向**\_Recordset**对象的类型是**\_RecordsetPtr**，和声明，如下所示：</span><span class="sxs-lookup"><span data-stu-id="99923-226">For example, a variable that points to a **\_Recordset** object is of type **\_RecordsetPtr**, and is declared as follows:</span></span>

```cpp 
 
_RecordsetPtr rs; 
```

<span data-ttu-id="99923-227">变量指向的新实例**\_Recordset**对象声明，如下所示：</span><span class="sxs-lookup"><span data-stu-id="99923-227">A variable that points to a new instance of a **\_Recordset** object is declared as follows:</span></span>

```cpp 
 
_RecordsetPtr rs("ADODB.Recordset"); 
```

<span data-ttu-id="99923-228">\-或-</span><span class="sxs-lookup"><span data-stu-id="99923-228">\-or-</span></span>

```cpp 
 
_RecordsetPtr rs; 
rs.CreateInstance("ADODB.Recordset"); 
```

<span data-ttu-id="99923-229">\-或-</span><span class="sxs-lookup"><span data-stu-id="99923-229">\-or-</span></span>

```cpp 
 
_RecordsetPtr rs; 
rs.CreateInstance(__uuidof(_Recordset)); 
```

<span data-ttu-id="99923-230">调用 **CreateInstance** 方法之后，可以按照以下方式使用变量：</span><span class="sxs-lookup"><span data-stu-id="99923-230">After the **CreateInstance** method is called, the variable can be used as follows:</span></span>

```cpp 
 
rs->Open(...); 
```

<span data-ttu-id="99923-231">请注意，在一个情况下，"。"运算符使用变量好像实例的类 (rs。创建实例），并在其他情况下，"-\>"运算符使用变量好像指向接口的指针 (rs-\>打开)。</span><span class="sxs-lookup"><span data-stu-id="99923-231">Notice that in one case, the "." operator is used as if the variable were an instance of a class (rs.CreateInstance), and in another case, the "-\>" operator is used as if the variable were a pointer to an interface (rs-\>Open).</span></span>

<span data-ttu-id="99923-232">可以通过以下两种使用一个变量，因为"-\>"重载运算符允许如同指向接口的类的实例。</span><span class="sxs-lookup"><span data-stu-id="99923-232">One variable can be used in two ways because the "-\>" operator is overloaded to allow an instance of a class to behave like a pointer to an interface.</span></span> <span data-ttu-id="99923-233">私有类成员的实例变量包含一个指向**\_Recordset**接口;"-\>"运算符返回该指针;返回的指针访问的成员和**\_Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="99923-233">A private class member of the instance variable contains a pointer to the **\_Recordset** interface; the "-\>" operator returns that pointer; and the returned pointer accesses the members of the **\_Recordset** object.</span></span>

### <a name="coding-a-missing-parameter"></a><span data-ttu-id="99923-234">缺少参数进行编码</span><span class="sxs-lookup"><span data-stu-id="99923-234">Coding a missing parameter</span></span>

#### <a name="string"></a><span data-ttu-id="99923-235">字符串</span><span class="sxs-lookup"><span data-stu-id="99923-235">String</span></span>

<span data-ttu-id="99923-236">在 Visual Basic 中，如果需要对省略的 **字符串型** 操作数进行编码，只需省略该操作数即可。</span><span class="sxs-lookup"><span data-stu-id="99923-236">When you need to code a missing **String** operand in Visual Basic, you merely omit the operand.</span></span> <span data-ttu-id="99923-237">在 Visual C++ 中，则必须指定操作数。</span><span class="sxs-lookup"><span data-stu-id="99923-237">You must specify the operand in Visual C++.</span></span> <span data-ttu-id="99923-238">代码**\_bstr\_t**具有作为值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="99923-238">Code a **\_bstr\_t** that has an empty string as a value.</span></span>

```cpp 
 
_bstr_t strMissing(L""); 
```

#### <a name="variant"></a><span data-ttu-id="99923-239">Variant</span><span class="sxs-lookup"><span data-stu-id="99923-239">Variant</span></span>

<span data-ttu-id="99923-240">在 Visual Basic 中，如果需要对省略的 **变量型** 操作数进行编码，只需省略该操作数即可。</span><span class="sxs-lookup"><span data-stu-id="99923-240">When you need to code a missing **Variant** operand in Visual Basic, you merely omit the operand.</span></span> <span data-ttu-id="99923-241">在 Visual C++ 中，则必须指定所有操作数。</span><span class="sxs-lookup"><span data-stu-id="99923-241">You must specify all operands in Visual C++.</span></span> <span data-ttu-id="99923-242">代码的缺少**Variant**参数**\_variant\_t**设置特殊值，显示为\_E\_PARAMNOTFOUND 和类型，VT\_错误。</span><span class="sxs-lookup"><span data-stu-id="99923-242">Code a missing **Variant** parameter with a **\_variant\_t** set to the special value, DISP\_E\_PARAMNOTFOUND, and type, VT\_ERROR.</span></span> <span data-ttu-id="99923-243">或者，指定**vtMissing**，即等效由提供的预定义的常数**\#导入**指令。</span><span class="sxs-lookup"><span data-stu-id="99923-243">Alternatively, specify **vtMissing**, which is an equivalent pre-defined constant supplied by the **\#import** directive.</span></span>

```cpp 
 
_variant_t vtMissingYours(DISP_E_PARAMNOTFOUND, VT_ERROR); 
```

<span data-ttu-id="99923-244">\-或使用-</span><span class="sxs-lookup"><span data-stu-id="99923-244">\-or use -</span></span>

```cpp 
 
...vtMissing...; 
```

### <a name="declaring-a-variant"></a><span data-ttu-id="99923-245">声明变量型</span><span class="sxs-lookup"><span data-stu-id="99923-245">Declaring a variant</span></span>

<span data-ttu-id="99923-246">在 Visual Basic 中，用 **Dim** 语句声明 **变量型** ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="99923-246">In Visual Basic, a **Variant** is declared with the **Dim** statement as follows:</span></span>

```vb 
 
Dim VariableName As Variant 
```

<span data-ttu-id="99923-247">在 Visual c + + 中，声明的变量类型为**\_variant\_t**。</span><span class="sxs-lookup"><span data-stu-id="99923-247">In Visual C++, declare a variable as type **\_variant\_t**.</span></span> <span data-ttu-id="99923-248">几示意图**\_variant\_t**声明如下所示。</span><span class="sxs-lookup"><span data-stu-id="99923-248">A few schematic **\_variant\_t** declarations are shown below.</span></span>

> [!NOTE]
> <span data-ttu-id="99923-p139">[!注释] 这些声明仅仅为您在编写自己的程序时提供一个粗略的思路。有关详细信息，请参阅以下示例和 Visual C++ 文档。</span><span class="sxs-lookup"><span data-stu-id="99923-p139">These declarations merely give a rough idea of what you would code in your own program. For more information, see the examples below, and the Visual C++ documentation.</span></span>

```cpp 
 
_variant_t VariableName(value); 
_variant_t VariableName((data type cast) value); 
_variant_t VariableName(value, VT_DATATYPE); 
_variant_t VariableName(interface * value, bool fAddRef = true); 
```

### <a name="using-arrays-of-variants"></a><span data-ttu-id="99923-251">使用变量型数组</span><span class="sxs-lookup"><span data-stu-id="99923-251">Using arrays of variants</span></span>

<span data-ttu-id="99923-252">在 Visual Basic 中，可以用 **Dim** 语句编写 **变量型** 数组，或者也可以使用 **Array** 函数，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="99923-252">In Visual Basic, arrays of **Variants** can be coded with the **Dim** statement, or you may use the **Array** function, as demonstrated in the following example code:</span></span>

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

<span data-ttu-id="99923-253">下面的 Visual c + + 示例展示了如何使用用于**SafeArray** \*\* \_variant\_t\*\*。</span><span class="sxs-lookup"><span data-stu-id="99923-253">The following Visual C++ example demonstrates using a **SafeArray** used with a **\_variant\_t**.</span></span>

> [!NOTE]
> <span data-ttu-id="99923-254">[!注释] 以下注释对应于代码示例中的注释部分。</span><span class="sxs-lookup"><span data-stu-id="99923-254">The following notes correspond to commented sections in the code example.</span></span>

1. <span data-ttu-id="99923-255">TESTHR() 内嵌函数再次被定义为利用现有的错误处理机制。</span><span class="sxs-lookup"><span data-stu-id="99923-255">Once again, the TESTHR() inline function is defined to take advantage of the existing error-handling mechanism.</span></span>

2. <span data-ttu-id="99923-p140">您只需要一个一维数组，因此可以使用 **SafeArrayCreateVector** 取代通用的 **SAFEARRAYBOUND** 声明和 **SafeArrayCreate** 函数。如果使用 **SafeArrayCreate** ，则代码如下所示：</span><span class="sxs-lookup"><span data-stu-id="99923-p140">You only need a one-dimensional array, so you can use **SafeArrayCreateVector**, instead of the general purpose **SAFEARRAYBOUND** declaration and **SafeArrayCreate** function. The following is what that code would look like using **SafeArrayCreate**:</span></span>
    
   ```cpp 
     
     SAFEARRAYBOUND sabound[1]; 
     sabound[0].lLbound = 0; 
     sabound[0].cElements = 4; 
     pSa = SafeArrayCreate(VT_VARIANT, 1, sabound); 
   ```

3. <span data-ttu-id="99923-258">架构枚举的常量， **adSchemaColumns**，由标识相关联四个约束列： 表\_目录、 表\_架构、 表\_名称和列\_名称。</span><span class="sxs-lookup"><span data-stu-id="99923-258">The schema identified by the enumerated constant, **adSchemaColumns**, is associated with four constraint columns: TABLE\_CATALOG, TABLE\_SCHEMA, TABLE\_NAME, and COLUMN\_NAME.</span></span> <span data-ttu-id="99923-259">因此，将创建包含四个元素的 **变量型** 数组。</span><span class="sxs-lookup"><span data-stu-id="99923-259">Therefore, an array of **Variant** values with four elements is created.</span></span> <span data-ttu-id="99923-260">然后约束的值，对应于第三列，表\_名称，指定。</span><span class="sxs-lookup"><span data-stu-id="99923-260">Then a constraint value that corresponds to the third column, TABLE\_NAME, is specified.</span></span> <span data-ttu-id="99923-261">返回的 **Recordset** 包含多列，其子集为约束列。</span><span class="sxs-lookup"><span data-stu-id="99923-261">The **Recordset** that is returned consists of several columns, a subset of which is the constraint columns.</span></span> <span data-ttu-id="99923-262">每个返回行的约束列的值必须等于相应的约束值。</span><span class="sxs-lookup"><span data-stu-id="99923-262">The values of the constraint columns for each returned row must be the same as the corresponding constraint values.</span></span>

4. <span data-ttu-id="99923-263">熟悉**SafeArrays**可能想不到不会在退出之前调用**SafeArrayDestroy**（）。</span><span class="sxs-lookup"><span data-stu-id="99923-263">Those familiar with **SafeArrays** may be surprised that **SafeArrayDestroy**() is not called before the exit.</span></span> <span data-ttu-id="99923-264">实际上，调用**SafeArrayDestroy**（） 在这种情况下将导致运行时异常。</span><span class="sxs-lookup"><span data-stu-id="99923-264">In fact, calling **SafeArrayDestroy**() in this case will cause a run-time exception.</span></span> <span data-ttu-id="99923-265">原因是： vtCriteria 的析构函数将调用**VariantClear**（） 时**\_variant\_t**超出范围，将闲**SafeArray**。</span><span class="sxs-lookup"><span data-stu-id="99923-265">The reason is that the destructor for vtCriteria will call **VariantClear**() when the **\_variant\_t** goes out of scope, which will free the **SafeArray**.</span></span> <span data-ttu-id="99923-266">调用**SafeArrayDestroy**，而不手动清除**\_variant\_t**，会导致对析构函数尝试清除了无效的**SafeArray**指针。</span><span class="sxs-lookup"><span data-stu-id="99923-266">Calling **SafeArrayDestroy**, without manually clearing the **\_variant\_t**, would cause the destructor to try to clear an invalid **SafeArray** pointer.</span></span> <span data-ttu-id="99923-267">如果调用 **SafeArrayDestroy** ，则代码如下所示：</span><span class="sxs-lookup"><span data-stu-id="99923-267">If **SafeArrayDestroy** were called, the code would look like this:</span></span>
    
   ```cpp 
     
     TESTHR(SafeArrayDestroy(pSa)); 
     vtCriteria.vt = VT_EMPTY; 
     vtCriteria.parray = NULL; 
   ```
    
   <span data-ttu-id="99923-268">但是，就要让简单得多**\_variant\_t**管理**SafeArray**。</span><span class="sxs-lookup"><span data-stu-id="99923-268">However, it is much simpler to let the **\_variant\_t** manage the **SafeArray**.</span></span>


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

### <a name="using-property-getputputref"></a><span data-ttu-id="99923-269">使用属性 Get/Put/PutRef</span><span class="sxs-lookup"><span data-stu-id="99923-269">Using property Get/Put/PutRef</span></span>

<span data-ttu-id="99923-270">在 Visual Basic 中，属性的名称并未限定（无论是对它进行检索、赋值还是赋予一个引用）。</span><span class="sxs-lookup"><span data-stu-id="99923-270">In Visual Basic, the name of a property is not qualified by whether it is retrieved, assigned, or assigned a reference.</span></span>

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

<span data-ttu-id="99923-271">以下 Visual c + + 示例演示如何**获取**/**放置**/\**PutRef \*\*\* 属性*。</span><span class="sxs-lookup"><span data-stu-id="99923-271">This Visual C++ example demonstrates the **Get**/**Put**/\**PutRef\*\*\*Property*.</span></span>

> [!NOTE]
> <span data-ttu-id="99923-272">[!注释] 以下注释对应于代码示例中的注释部分。</span><span class="sxs-lookup"><span data-stu-id="99923-272">The following notes correspond to commented sections in the code example.</span></span>

1. <span data-ttu-id="99923-273">此示例使用两种形式的缺少的字符串参数： 显式常量、 **strMissing**和字符串编译器将用于创建一个临时**\_bstr\_t**的**Open**方法的作用域存在。</span><span class="sxs-lookup"><span data-stu-id="99923-273">This example uses two forms of a missing string argument: an explicit constant, **strMissing**, and a string that the compiler will use to create a temporary **\_bstr\_t** that will exist for the scope of the **Open** method.</span></span>

2. <span data-ttu-id="99923-274">不需要的 rs-操作数转换\>PutRefActiveConnection(cn) 为 (IDispatch \*) 由于操作数的类型已经是 (IDispatch \*)。</span><span class="sxs-lookup"><span data-stu-id="99923-274">It isn't necessary to cast the operand of rs-\>PutRefActiveConnection(cn) to (IDispatch \*) because the type of the operand is already (IDispatch \*).</span></span>
    
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

### <a name="using-getitemx-and-itemx"></a><span data-ttu-id="99923-275">使用 getitem （x） 和 Item\[x\]</span><span class="sxs-lookup"><span data-stu-id="99923-275">Using GetItem(x) and Item\[x\]</span></span>

<span data-ttu-id="99923-276">此 Visual Basic 示例展示了 **Item**() 的标准语法和替代语法。</span><span class="sxs-lookup"><span data-stu-id="99923-276">This Visual Basic example demonstrates the standard and alternative syntax for **Item**().</span></span>

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

<span data-ttu-id="99923-277">此 Visual C++ 示例展示了 **Item** 。</span><span class="sxs-lookup"><span data-stu-id="99923-277">This Visual C++ example demonstrates **Item**.</span></span>

> [!NOTE]
> <span data-ttu-id="99923-278">[!注释] 以下注释对应于代码示例中的注释部分。</span><span class="sxs-lookup"><span data-stu-id="99923-278">The following note corresponds to commented sections in the code example.</span></span>

1. <span data-ttu-id="99923-279">当用 **Item** 访问集合时，索引 **2** 必须转换为 **长整型** ，以调用适当的构造函数。</span><span class="sxs-lookup"><span data-stu-id="99923-279">When the collection is accessed with **Item**, the index, **2**, must be cast to **long** so an appropriate constructor will be invoked.</span></span>
    
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

### <a name="casting-ado-object-pointers-with-idispatch-"></a><span data-ttu-id="99923-280">用 (IDispatch \*) 转换 ADO 对象指针</span><span class="sxs-lookup"><span data-stu-id="99923-280">Casting ADO object pointers with (IDispatch \*)</span></span>

<span data-ttu-id="99923-281">以下 Visual C++ 示例展示了如何使用 (IDispatch \*) 转换 ADO 对象指针。</span><span class="sxs-lookup"><span data-stu-id="99923-281">The following Visual C++ example demonstrates using (IDispatch \*) to cast ADO object pointers.</span></span>

> [!NOTE]
> <span data-ttu-id="99923-282">[!注释] 以下注释对应于代码示例中的注释部分。</span><span class="sxs-lookup"><span data-stu-id="99923-282">The following notes correspond to commented sections in the code example.</span></span>

1. <span data-ttu-id="99923-283">在显式编码的 **变量型** 中指定打开的 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="99923-283">Specify an open **Connection** object in an explicitly coded **Variant**.</span></span> <span data-ttu-id="99923-284">将其与强制转换 (IDispatch \*) 以正确的构造函数调用。</span><span class="sxs-lookup"><span data-stu-id="99923-284">Cast it with (IDispatch \*) so the correct constructor will be invoked.</span></span> <span data-ttu-id="99923-285">此外，显式设置第二个**\_variant\_t**参数为默认值为**true**，因此**Recordset::Open**操作结束时，是正确的对象引用计数。</span><span class="sxs-lookup"><span data-stu-id="99923-285">Also, explicitly set the second **\_variant\_t** parameter to the default value of **true**, so the object reference count will be correct when the **Recordset::Open** operation ends.</span></span>

2. <span data-ttu-id="99923-286">表达式，(\_bstr\_t)，不是强制转换，但**\_variant\_t**提取的运算符**\_bstr\_t**从**变量\*\*\*\*值**返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="99923-286">The expression, (\_bstr\_t), is not a cast, but a **\_variant\_t** operator that extracts a **\_bstr\_t** string from the **Variant** returned by **Value**.</span></span> <span data-ttu-id="99923-287">表达式，(char\*)，不是强制转换，但**\_bstr\_t**提取一个指向中封装的字符串的运算符**\_bstr\_t**对象。</span><span class="sxs-lookup"><span data-stu-id="99923-287">The expression, (char\*), is not a cast, but a **\_bstr\_t** operator that extracts a pointer to the encapsulated string in a **\_bstr\_t** object.</span></span> <span data-ttu-id="99923-288">代码的这一节演示一些有用行为**\_variant\_t**和**\_bstr\_t**运算符。</span><span class="sxs-lookup"><span data-stu-id="99923-288">This section of code demonstrates some of the useful behaviors of **\_variant\_t** and **\_bstr\_t** operators.</span></span>
    
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

