---
title: 32 位和 64 位版本的 Office 之间的兼容性
ms.date: 04/27/2016
ms.audience: ITPro
localization_priority: Normal
ms.assetid: ff49dc9e-daf8-43cf-8802-51c2537ed561
description: 找出与 64 位版本的 Office 兼容 32 位版本的 Office 的方式。
ms.openlocfilehash: eeff11f11d4f2595b7111c0233703d09b1c46651
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390938"
---
# <a name="compatibility-between-the-32-bit-and-64-bit-versions-of-office"></a>32 位和 64 位版本的 Office 之间的兼容性

找出与 64 位版本的 Office 兼容 32 位版本的 Office 的方式。
  
Office 应用程序有 32 位和 64 位版本。 
  
64 位版本的 Office，您可以增加功能，例如，当您使用 Microsoft Excel 2010 中的大量移动多个数据。 编写 32 位代码时，您可以使用 64 位版本的 Office 作任何更改。 但是，当您编写 64 位代码，您应该确保您的代码包含特定关键词和条件编译常量，以确保了与早期版本的 Office，向后兼容的代码和正确的代码正在执行，如果您混合使用 32 位和 64 位的代码。
  
Office、 释放的 64 位版本中的 Visual Basic for Applications (VBA 7) 7.0 时，它适用于 32 位和 64 位应用程序。 本文中介绍的更改仅应用于 Office 的 64 位版本。 您可以使用解决方案使用 32 位版本的 Microsoft Office 启用内置的早期版本的 Office 不进一步进行修改。
  
> [!NOTE]
> 默认情况下，当您安装 64 位版本的 Office，您还安装 32 位版本和 64 位系统安装。 您必须明确选择 Microsoft Office 64 位版本安装选项。 
  
在 VBA 7 中，则必须更新现有 Windows API 语句 （**Declare**语句） 以使用 64 位版本。 此外，必须更新地址指针，并显示在使用这些语句的用户定义类型的窗口句柄。 更多详细信息以及在本文中的 32 位和 64 位版本和建议的解决方案之间的兼容性问题如下所述。 
  
## <a name="comparing-32-bit-and-64-bit-systems"></a>将 32 位和 64 位系统进行比较
<a name="odc_office_Compatibility32bit64bit_Comparing32BitSystemsto64BitSystems"> </a>

构建与 64 位版本的 Office 的应用程序可以引用比 32 位版本的较大地址空间。 这意味着，您可以使用更多物理内存数据比之前，可能会降低的开销花费注销物理内存的移动数据
  
除了在物理内存中引用特定的位置 （称为指针），您可以使用地址引用 （称为句柄） 的显示窗口标识符。 （以字节为单位） 的指针或句柄的大小取决于您是否使用 32 位或 64 位系统。 
  
如果您想要使用 64 位版本的 Office 中运行的现有解决方案，请注意下列选项：
  
- 在 Office 中的本机 64 位进程中无法加载 32 位二进制文件。 此举有望时您具有现有的 Microsoft ActiveX 控件和现有外接程序是一个常见的问题。
    
- VBA 以前没有指针数据类型，因此您必须使用 32 位变量来存储指针和句柄。 现在，这些变量截断使用**Declare**语句时 API 调用返回的 64 位值。 
    
## <a name="vba-7-code-base"></a>VBA 7 基本代码
<a name="odc_office_Compatibility32bit64bit_IntroducingVBA7CodeBase"> </a>

VBA 7 替换基本 Office 2007 和早期版本中的 VBA 代码。 VBA 7 是 32 位和 64 位 Office 版本中可用。 它提供了两个条件编译常量： 
  
- **VBA7** -有助于确保通过测试您的应用程序使用 VBA 7 或 VBA 的早期版本是否在您的代码的向后兼容性。 
    
- **Win64**测试是否为 32 位或 64 位运行代码。 
    
某些例外情况外，32 位版本的应用程序中的文档中的宏也可在 64 位版本。
  
## <a name="activex-control-and-com-add-in-compatibility"></a>ActiveX 控件和 COM 加载项兼容性
<a name="odc_office_Compatibility32bit64bit_ActiveXControlCOMAddinCompatibility"> </a>

现有的 32 位 ActiveX 控件，不与 64 位版本的 Office 兼容。 ActiveX 控件和 COM 对象：
  
- 如果您有自己生成的 64 位版本的源代码。
- 如果您没有源代码，请将供应商联系以获取更新版本。
    
在 Office 中的本机 64 位进程中无法加载 32 位二进制文件。 这包括**MSComCtl** （TabStrip、 工具栏、 状态栏、 进度栏、 TreeView、 列表视图、 ImageList、 滑块、 ImageComboBox） 的公共控件和控件的**MSComCt2** （动画、 上下、 MonthView、 DateTimePicker，FlatScrollBar)。 这些控件安装 32 位版本的 Office 早于 Office 2010。 您需要查找现有 VBA 解决方案迁移到 64 位版本的 Office 代码时使用这些控件的替代项。 
  
## <a name="api-compatibility"></a>API 兼容性
<a name="odc_office_Compatibility32bit64bit_ApplicationProgrammingInterfaceCompatibility"> </a>

VBA 和类型库的组合为您提供了大量功能来创建 Office 应用程序。 但是，有时必须与您通信直接计算机的操作系统和其他组件，如管理时内存或过程，使用用户界面元素 linke windows 和控件，或修改 Windows 注册表时。 在这些情况下，最好的选择是使用 DLL 文件中嵌入外部函数之一。 执行此操作的 API 调用使用**Declare**语句在 VBA 中。 
  
> [!NOTE]
> Microsoft 提供的 Win32API.txt 文件包含 1,500 Declare 语句和用于复制到您的代码所需的**Declare**语句的工具。 但是，这些语句的 32 位系统，并且必须转换为 64 位使用下文中讨论的信息。 现有**Declare**语句不会在 64 位 VBA 中编译，直到将它们标记为可安全执行 64-bit 使用**PtrSafe**属性。 您可以在 Excel MVP Jan Karel Pieterse 网站，找到此类型的转换的示例[https://www.jkp-ads.com/articles/apideclarations.asp](https://www.jkp-ads.com/articles/apideclarations.asp)。 [Office 代码兼容性检查器用户指南](https://technet.microsoft.com/en-us/library/ee833946%28office.14%29.aspx)是一个非常有用的工具，如果需要请检查**PtrSafe**属性的 API **Declare**语句的语法和相应的返回类型。 
  
**Declare**语句类似于以下内容，具体取决于您调用的子例程 （没有返回值） 或函数 （有返回值） 之一。 
  
```vb
Public/Private Declare Sub SubName Lib "LibName" Alias "AliasName" (argument list)
Public/Private Declare Function FunctionName Lib "Libname" alias "aliasname" (argument list) As Type

```

**SubName**函数或**FunctionName**函数替换为实际的 DLL 文件中的过程的名称和表示从 VBA 代码调用该过程时使用的名称。 您还可以指定**AliasName**参数的过程的名称。 包含要调用的过程的 DLL 文件的名称都遵循**Lib**关键字。 和最后，参数列表包含的参数和必须要传递给过程的数据类型。 
  
下面的**Declare**语句将在 Windows 注册表中打开一个*子项*并替换其值。 
  
```vb
Declare Function RegOpenKeyA Lib "advapi32.dll" (ByVal Key As Long, ByVal SubKey As String, NewKey As Long) As Long
```

**RegOpenKeyA** 函数的 Windows.h（窗口句柄）条目如下所示： 
  
```vb
LONG RegOpenKeyA ( HKEY hKey, LPCSTR lpSubKey, HKEY *phkResult );
```

在 Visual C 和 Microsoft Visual c + + 中，上面的示例将编译正确的 32 位和 64 位。 这是因为 HKEY 被定义为的指针，其大小反映代码在编译平台的内存大小。
  
在早期版本的 VBA，没有任何特定指针数据类型，以便使用已**Long**数据类型。 因为**长**数据类型始终是 32 位，因为高 32 位可能被截断，或者可能覆盖其他内存地址在使用 64 位系统上使用时此分隔符。 任何一种情况会导致不可预测的行为或系统崩溃。 
  
若要解决此问题，VBA，包括 true*指针*数据类型： **LongPtr**。 此新的数据类型，您可以编写原始**Declare**语句正确为： 
  
```vb
Declare PtrSafe Function RegOpenKeyA Lib "advapire32.dll" (ByVal hKey as LongPtr, ByVal lpSubKey As String, phkResult As LongPtr) As Long
```

此数据类型和新**PtrSafe**属性，可以使用此**Declare**语句在 32 位或 64 位系统上。 **PtrSafe**属性指示 VBA 编译器**Declare**语句面向于 Office 的 64 位版本。 如果没有此属性，在 64 位系统使用**Declare**语句将导致编译时错误。 在 32 位版本的 Office 可选**PtrSafe**属性。 这使现有的**Declare**语句，以便他们始终需要具有。 
  
下表提供了有关新限定符和数据 typeas 以及另一种数据类型、 两个转换运算符和三个函数的详细信息。
  
|类型|项|说明|
|:-----|:-----|:-----|
|限定符  <br/> |**PtrSafe** <br/> |指示 **Declare** 语句与 64 位兼容。此属性在 64 位系统上是必需的。<br/> |
|数据类型  <br/> |**LongPtr** <br/> |变量数据类型，这是在 32 位版本和 64 位版本的 Microsoft Office 8 字节数据类型的 4 个字节数据类型。 这是 office 的声明指针或新代码还可以旧版代码句柄，如果它具有要在 64 位版本中运行的推荐的方法。 它只是支持在 VBA 7 运行时在 32 位和 64 位。 请注意，可以将数字值分配给它，但不是数值类型。  <br/> |
|数据类型  <br/> |**LongLong** <br/> |这是 8 字节数据类型，这是仅在 64 位版本的 Microsoft Office 中可用。 您可以分配数值，但不是数字类型 （以避免被截断）。  <br/> |
|转换运算符  <br/> |**CLngPtr** <br/> |将简单表达式转换为 **LongPtr** 数据类型。  <br/> |
|转换运算符  <br/> |**CLngLng** <br/> |将简单表达式转换为 **LongLong** 数据类型。  <br/> |
|函数  <br/> |**VarPtr** <br/> |变量转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本上返回 **Long**（4 字节）。<br/> |
|函数  <br/> |**ObjPtr** <br/> |对象转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本上返回 **Long**（4 字节）。<br/> |
|函数  <br/> |**StrPtr** <br/> |字符串转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本上返回 **Long**（4 字节）。<br/> |
   
下面的示例演示如何在 **Declare** 语句中使用其中某些项。 
  
```vb
Declare PtrSafe Function RegOpenKeyA Lib "advapi32.dll" (ByVal Key As LongPtr, ByVal SubKey As String, NewKey As LongPtr) As Long
```

请注意，没有**PtrSafe**属性的**Declare**语句被假定不为与 64 位版本的 Office 兼容。 
  
有两个条件编译常量： **VBA7**和**Win64**。 若要确保与 Microsoft Office 早期版本向后的兼容，您使用**VBA7**常量 （这是多个典型大小写） 阻止 64 位代码在早期版本的 Office 中使用。 对于不同的 32 位版本和 64 位版本，如调用其 32 位版本，使用其 64 位版本的**LongLong**的 API 和**长**数学的代码中，您将使用**Win64**常量。 下面的代码演示如何使用这两个常量。 
  
```vb
#if Win64 then
   Declare PtrSafe Function MyMathFunc Lib "User32" (ByVal N As LongLong) As LongLong
#else
   Declare Function MyMathFunc Lib "User32" (ByVal N As Long) As Long
#end if
#if VBA7 then
   Declare PtrSafe Sub MessageBeep Lib "User32" (ByVal N AS Long)
#else
   Declare Sub MessageBeep Lib "User32" (ByVal N AS Long)
#end if
```

总之，如果您编写 64-bit 代码和打算在早期版本的 Office 中使用它，您需要使用**VBA7**条件编译常量。 但是，如果您在 Office 中编写 32 位代码，该代码将运行在早期版本的 Office，而无需编译常数原样。 如果您想要确保您使用的 32 位语句为 32 位版本和 64 位版本的 64 位语句，最好的选择是使用**Win64**条件编译常量。 
  
## <a name="using-conditional-compilation-attributes"></a>使用条件编译属性
<a name="odc_office_Compatibility32bit64bit_UsingConditionalCompilationAttributes"> </a>

下面的示例演示为需要更新的 32 位编写 VBA 代码。 请注意进行了更新以使用**LongPtr** ，因为它们引用的句柄或指针在旧的代码中的数据类型。 
  
### <a name="vba-code-written-for-32-bit-versions"></a>VBA 代码编写的 32 位版本
  
```vb
Declare Function SHBrowseForFolder Lib "shell32.dll" _
  Alias "SHBrowseForFolderA" (lpBrowseInfo As BROWSEINFO) As Long
  
Public Type BROWSEINFO
  hOwner As Long
  pidlRoot As Long
  pszDisplayName As String
  lpszTitle As String
  ulFlags As Long
  lpfn As Long
  lParam As Long
  iImage As Long
End Type
```

### <a name="vba-code-rewritten-for-64-bit-versions"></a>重写的 64 位版本的 VBA 代码
  
```vb
#if VBA7 then    ' VBA7 
Declare PtrSafe Function SHBrowseForFolder Lib "shell32.dll" _
  Alias "SHBrowseForFolderA" (lpBrowseInfo As BROWSEINFO) As Long
Public Type BROWSEINFO
  hOwner As LongPtr
  pidlRoot As Long
  pszDisplayName As String
  lpszTitle As String
  ulFlags As Long
  lpfn As LongPtr
  lParam As LongPtr
  iImage As Long
End Type
 
#else    ' Downlevel when using previous version of VBA7
Declare Function SHBrowseForFolder Lib "shell32.dll" _
  Alias "SHBrowseForFolderA" (lpBrowseInfo As BROWSEINFO) As Long
Public Type BROWSEINFO
  hOwner As Long
  pidlRoot As Long
  pszDisplayName As String
  lpszTitle As String
  ulFlags As Long
  lpfn As Long
  lParam As Long
  iImage As Long
End Type
 
#end if
Sub TestSHBrowseForFolder ()
    Dim bInfo As BROWSEINFO
    Dim pidList As Long
    bInfo.pidlRoot = 0&amp;
    bInfo.ulFlags = &amp;H1
    pidList = SHBrowseForFolder(bInfo)
End Sub
```

<a name="odc_office_Compatibility32bit64bit_FrequentlyAskedQuestions"> </a>

## <a name="frequently-asked-questions"></a>常见问题

#### <a name="when-should-i-use-the-64-bit-version-of-office"></a>何时应使用 64 位版本的 Office？
  
这是您使用空格 （Excel、 Word 等） 的主机应用程序的详细信息。 例如，Excel 就能够处理与 64 位版本的 Microsoft Office 量较大的工作表。
  
#### <a name="can-i-install-64-bit-and-32-bit-versions-of-office-side-by-side"></a>可以安装 64 位和 32 位版本的 Office 并行？
  
否。
  
#### <a name="when-should-i-convert-long-parameters-to-longptr"></a>何时应将长的参数为 LongPtr？
  
您需要检查您要呼叫的函数 Microsoft 开发人员网络上的 Windows API 文档。 控点和指针需要转换为**LongPtr**。 例如，文档的[RegOpenKeyA](https://msdn.microsoft.com/library/c8a590f2-3249-437f-a320-c7443d42b792.aspx)提供了以下签名： 
  
```cs
LONG WINAPI RegOpenKeyEx(
  __in        HKEY hKey,
  __in_opt    LPCTSTR lpSubKey,
  __reserved  DWORD ulOptions,
  __in        REGSAM samDesired,
  __out       PHKEY phkResult
);
```

参数的定义如下：
  
|参数|说明|
|:-----|:-----|
|[in] hKey  <br/> |*处理*打开注册表项。  <br/> |
|lpSubKey [中，可选]  <br/> |要打开注册表子项的名称。  <br/> |
|ulOptions  <br/> |此参数是保留，且必须为零。  <br/> |
|[in] samDesired  <br/> |指定到项的所需的访问权限掩码。  <br/> |
|phkResult [out]  <br/> |指向一个变量来接收打开密钥的句柄的*指针*。  <br/> |
   
在[Win32API_PtrSafe.txt](https://www.microsoft.com/downloads/details.aspx?displaylang=en&amp;FamilyID=035b72a5-eef9-4baf-8dbc-63fbd2dd982b)， **Declare**语句被定义为： 
  
```vb
Declare PtrSafe Function RegOpenKeyEx Lib "advapi32.dll" Alias "RegOpenKeyExA" (ByVal hKey As LongPtr , ByVal lpSubKey As String, ByVal ulOptions As Long, ByVal samDesired As Long, phkResult As LongPtr ) As Long
```

#### <a name="should-i-convert-pointers-and-handles-in-structures"></a>应将转换指针和结构中的句柄？
  
能。 请参阅 Win32API_PtrSafe.txt 中的**MSG**类型： 
  
```vb
Type MSG
    hwnd As LongPtr 
    message As Long
    wParam As LongPtr 
    lParam As LongPtr 
    time As Long
    pt As POINTAPI
End TypeF
```

#### <a name="when-should-i-use-strptr-varpt-and-objptr"></a>何时应使用 strptr、 varpt 和 objptr？
  
应使用这些函数可以分别检索到字符串、 变量和对象的指针。 在 64 位版本的 Office，这些函数将返回 64-bit **LongPtr**，其中可以传递给**Declare**语句。 未从早期版本的 VBA 更改这些函数的用法。 唯一的区别是，他们现在返回为**LongPtr**。
  
## <a name="see-also"></a>另请参阅
<a name="odc_office_Compatibility32bit64bit_AdditionalResources"> </a>

- [解析 Declare 语句](https://msdn.microsoft.com/library/office/aa671659.aspx)
    

