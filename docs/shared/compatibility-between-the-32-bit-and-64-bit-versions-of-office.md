---
title: 32 位版 Office 与 64 位版 Office 的兼容性
ms.date: 04/27/2016
ms.audience: ITPro
ms.assetid: ff49dc9e-daf8-43cf-8802-51c2537ed561
description: 了解 32 位版 Office 如何与 64 位版 Office 保持兼容。
localization_priority: Priority
ms.openlocfilehash: b03323b37b242c9992c47cd737ae54f3f9bbf2ca
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712013"
---
# <a name="compatibility-between-the-32-bit-and-64-bit-versions-of-office"></a>32 位版 Office 与 64 位版 Office 的兼容性

了解 32 位版 Office 如何与 64 位版 Office 保持兼容。
  
Office 应用程序分为 32 位版和 64 位版。 
  
使用 64 位版 Office，可以移动更多数据，从而提升功能性，例如在 Microsoft Excel 2010 中处理大量数据时。 编写 32 位代码时，可使用 64 位版 Office，无需进行任何更改。 然而，在编写 64 位代码时，应确保代码包含特定关键字和条件编译常量，以确保代码与旧版 Office 保持向后兼容性，且执行的是正确代码（如果混用 32 位和 64 位代码的话）。
  
Visual Basic for Applications 7.0 (VBA 7) 是在 64 位版 Office 中发布，可用于 32 位和 64 位应用程序。 本文所述的更改仅适用于 64 位版 Office。 使用 32 位版 Microsoft Office，可使用在旧版 Office 中生成的解决方案，无需进一步修改。
  
> [!NOTE]
> 默认情况下，在你安装 64 位版 Office 后，32 位版本也与 64 位系统一起安装了。 必须显式选择 Microsoft Office 64 位版本安装选项。 
  
在 VBA 7 中，必须更新现有 Windows API 语句（**Declare** 语句），才能支持 64 位版本。 此外，还必须在这些语句使用的用户定义类型中更新地址指针和显示窗口句柄。 本文更详细地介绍了这一点，以及 32 位版和 64 位版之间的兼容性问题和建议解决方案。 
  
## <a name="comparing-32-bit-and-64-bit-systems"></a>比较 32 位和 64 位系统
<a name="odc_office_Compatibility32bit64bit_Comparing32BitSystemsto64BitSystems"> </a>

与 32 位版相比，使用 64 位版 Office 生成的应用程序可以引用更大地址空间。 也就是说，可以对数据使用比以往更多的物理内存，这样可能会减少在物理内存中移入和移出数据所需的开销
  
除了能够引用物理内存中的特定位置（称为“指针”）之外，还可以使用地址来引用显示窗口标识符（称为“句柄”）。 指针或句柄的大小（以字节为单位）取决于使用的是 32 位系统，还是 64 位系统。 
  
若要使用 64 位版 Office 运行现有解决方案，请注意以下几点：
  
- Office 中的本机 64 位进程无法加载 32 位二进制文件。 这应该是在现有 Microsoft ActiveX 控件和加载项时的常见问题。
    
- VBA 以前没有指针数据类型，因此必须使用 32 位变量来存储指针和句柄。 这些变量现在会截断在使用 **Declare** 语句时由 API 调用返回的 64 位值。 
    
## <a name="vba-7-code-base"></a>VBA 7 基准代码
<a name="odc_office_Compatibility32bit64bit_IntroducingVBA7CodeBase"> </a>

VBA 7 替换 Office 2007 及更低版本中的 VBA 基准代码。 VBA 7 可用于 32 位版和 64 位版 Office。 它提供以下两个条件编译常量： 
  
- **VBA7** - 通过测试应用程序使用的是 VBA 7 还是旧版 VBA，有助于确保代码的向后兼容性。 
    
- **Win64** - 测试代码是运行为 32 位代码，还是运行为 64 位代码。 
    
除一些例外，如果文档中的宏可用于 32 位版应用程序，也可用于 64 位版应用程序。
  
## <a name="activex-control-and-com-add-in-compatibility"></a>ActiveX 控件和 COM 加载项兼容性
<a name="odc_office_Compatibility32bit64bit_ActiveXControlCOMAddinCompatibility"> </a>

现有 32 位 ActiveX 控件与 64 位版 Office 不兼容。 对于 ActiveX 控件和 COM 对象：
  
- 若有源代码，请自行生成 64 位版本。
- 若无源代码，请联系供应商，以获得更新后的版本。
    
Office 中的本机 64 位进程无法加载 32 位二进制文件。 这包括 **MSComCtl** 的常见控件（TabStrip、Toolbar、StatusBar、ProgressBar、TreeView、ListViews、ImageList、Slider、ImageComboBox）和 **MSComCt2** 的控件（Animation、UpDown、MonthView、DateTimePicker、FlatScrollBar）。 这些控件是由低于 Office 2010 的 32 位版 Office 进行安装。 将代码迁移到 64 位版 Office 时，必须寻找使用这些控件的现有 VBA 解决方案的替代方案。 
  
## <a name="api-compatibility"></a>API 兼容性
<a name="odc_office_Compatibility32bit64bit_ApplicationProgrammingInterfaceCompatibility"> </a>

通过结合使用 VBA 和类型库，可以使用许多功能来创建 Office 应用程序。 不过，有时必须直接与计算机操作系统及其他组件通信，如在管理内存或进程时、在处理窗口和控件等 UI 元素时或在修改 Windows 注册表时。 在这些情况下，最佳选择是使用 DLL 文件中嵌入的外部函数之一。 为此，在 VBA 中，可使用 **Declare** 语句执行 API 调用。 
  
> [!NOTE]
> Microsoft 提供了包含 1,500 条 Declare 语句的 Win32API.txt 文件，以及用于将所需 **Declare** 语句复制到代码中的工具。 不过，这些语句适用于 32 位系统，必须根据本文稍后介绍的信息转换为 64 位。 只有在使用 **PtrSafe** 属性将现有 **Declare** 语句标记为 64 位安全后，才能在 64 位 VBA 中编译这些语句。 有关此类转换的示例，可以访问 Excel MVP Jan Karel Pieterse 的网站 ([https://www.jkp-ads.com/articles/apideclarations.asp](https://www.jkp-ads.com/articles/apideclarations.asp))。 [Office 代码兼容性检查器用户指南](https://technet.microsoft.com/zh-CN/library/ee833946%28office.14%29.aspx)是一款实用工具，可用于检查 API **Declare** 语句的语法中是否有 **PtrSafe** 属性，以及相应的返回类型（如果需要）。 
  
**Declare** 语句类似于以下代码之一，具体取决于调用的是子例程（没有返回值）还是函数（有返回值）。 
  
```vb
Public/Private Declare Sub SubName Lib "LibName" Alias "AliasName" (argument list)
Public/Private Declare Function FunctionName Lib "Libname" alias "aliasname" (argument list) As Type

```

**SubName** 函数或 **FunctionName** 函数替换为 DLL 文件中过程的实际名称，并表示通过 VBA 代码调用过程时使用的名称。 还可以对过程名称指定 **AliasName** 参数。 包含正在调用过程的 DLL 文件的名称跟在 **Lib** 关键字后面。 最后，参数列表包含必须传递给过程的参数和数据类型。 
  
下面的 **Declare** 语句打开 Windows 注册表中的*子项*，并替换它的值。 
  
```vb
Declare Function RegOpenKeyA Lib "advapi32.dll" (ByVal Key As Long, ByVal SubKey As String, NewKey As Long) As Long
```

**RegOpenKeyA** 函数的 Windows.h（窗口句柄）条目如下所示： 
  
```vb
LONG RegOpenKeyA ( HKEY hKey, LPCSTR lpSubKey, HKEY *phkResult );
```

在 Visual C 和 Microsoft Visual C++ 中，上一示例针对 32 位和 64 位进行了正确编译。 这是因为 HKEY 被定义为指针，它的大小反映了代码编译平台的内存大小。
  
在旧版 VBA 中，由于没有具体指针数据类型，因此使用了 **Long** 数据类型。 由于 **Long** 数据类型始终是 32 位，因此在使用 64 位内存的系统中使用它时就会中断，因为上面的 32 位可能会被截断或覆盖其他内存地址。 这两种情况都可能会导致不可预测行为发生或系统故障。 
  
为了解决此问题，VBA 添加了真正的*指针*数据类型：**LongPtr**。 使用这一新数据类型，可以将原始 **Declare** 语句正确编写为： 
  
```vb
Declare PtrSafe Function RegOpenKeyA Lib "advapire32.dll" (ByVal hKey as LongPtr, ByVal lpSubKey As String, phkResult As LongPtr) As Long
```

结合使用这一数据类型和新 **PtrSafe** 属性，可以在 32 位或 64 位系统上使用此 **Declare** 语句。 **PtrSafe**属性向 VBA 编译器指明，**Declare** 语句针对的是 64 位版 Office。 如果没有这一属性，在 64 位系统中使用 **Declare** 语句会生成编译时错误。 在 32 位版 Office 中，**PtrSafe** 是可选属性。 这样一来，现有 **Declare** 语句就可以像往常一样正常运行了。 
  
下表详细介绍了新限定符和数据类型以及另一种数据类型、两个转换运算符和三个函数。
  
|类型|Item|说明|
|:-----|:-----|:-----|
|限定符  <br/> |**PtrSafe** <br/> |指明 **Declare** 语句与 64 位兼容。此属性是 64 位系统中的必需属性。<br/> |
|数据类型  <br/> |**LongPtr** <br/> |可变数据类型，在 32 位版 Microsoft Office 上为 4 字节数据类型，在 64 位版 Microsoft Office 上为 8 字节数据类型。 这是为新代码声明指针或句柄的推荐方法，也是为旧代码声明指针或句柄的推荐方法（如果必须在 64 位版 Office 中运行的话）。 只在 32 位和 64 位的 VBA 7 运行时中才受支持。 请注意，可以向它分配数值，但不能分配数值类型。  <br/> |
|数据类型  <br/> |**LongLong** <br/> |这是 8 字节数据类型，仅在 64 位版 Microsoft Office 中可用。 可以指定数值，但不能指定数值类型（以免发生截断）。  <br/> |
|转换运算符  <br/> |**CLngPtr** <br/> |将简单表达式转换为 **LongPtr** 数据类型。  <br/> |
|转换运算符  <br/> |**CLngLng** <br/> |将简单表达式转换为 **LongLong** 数据类型。  <br/> |
|函数  <br/> |**VarPtr** <br/> |变体转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本（4 字节）上返回 **Long**。<br/> |
|函数  <br/> |**ObjPtr** <br/> |对象转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本（4 字节）上返回 **Long**。<br/> |
|函数  <br/> |**StrPtr** <br/> |字符串转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本（4 字节）上返回 **Long**。<br/> |
   
下面的示例展示了如何在 **Declare** 语句中使用其中部分项。 
  
```vb
Declare PtrSafe Function RegOpenKeyA Lib "advapi32.dll" (ByVal Key As LongPtr, ByVal SubKey As String, NewKey As LongPtr) As Long
```

请注意，没有 **PtrSafe** 属性的 **Declare** 语句被认定为与 64 位版 Office 不兼容。 
  
有以下两个条件编译常量：**VBA7** 和 **Win64**。 为了确保与旧版 Microsoft Office 保持向后兼容性，可使用 **VBA7** 常量（这是更典型的情况），以防在旧版 Office 中使用 64 位代码。 对于因 32 位版本和 64 位版本而异的代码（如调用的数学 API 对 64 位版本使用 **LongLong**，而对 32 位版本使用 **Long**），可使用 **Win64** 常量。 下面的代码展示了如何使用这两个常量。 
  
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

总而言之，如果编写 64 位代码并打算在旧版 Office 中使用它，不妨使用 **VBA7** 条件编译常量。 不过，如果你在 Office 中编写 32 位代码，此代码的工作方式与在旧版 Office 中相同，无需编译常量。 若要确保对 32 位版本使用 32 位语句，并对 64 位版本使用 64 位语句，最佳选择是使用 **Win64** 条件编译常量。 
  
## <a name="using-conditional-compilation-attributes"></a>使用条件编译属性
<a name="odc_office_Compatibility32bit64bit_UsingConditionalCompilationAttributes"> </a>

下面的示例展示了为 32 位版本编写的 VBA 代码（需要更新）。 请注意，旧代码中的数据类型更新为使用 **LongPtr**，因为它们引用句柄或指针。 
  
### <a name="vba-code-written-for-32-bit-versions"></a>为 32 位版本编写的 VBA 代码
  
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

### <a name="vba-code-rewritten-for-64-bit-versions"></a>为 64 位版本重写的 VBA 代码
  
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

## <a name="frequently-asked-questions"></a>常见问题解答

#### <a name="when-should-i-use-the-64-bit-version-of-office"></a>何时应使用 64 位版 Office？
  
这个问题更像是要使用哪个主机应用程序（Excel、Word 等）。 例如，如果使用 64 位版 Microsoft Office，Excel 可以处理更大的工作表。
  
#### <a name="can-i-install-64-bit-and-32-bit-versions-of-office-side-by-side"></a>能否并行安装 64 位版和 32 位版 Office？
  
否。
  
#### <a name="when-should-i-convert-long-parameters-to-longptr"></a>何时应将 Long 参数转换为 LongPtr？
  
需要查看要调用函数在 Microsoft Developer Network 上的 Windows API 文档。 必须将句柄和指针转换为 **LongPtr**。 例如，[RegOpenKeyA](https://msdn.microsoft.com/library/c8a590f2-3249-437f-a320-c7443d42b792.aspx) 的文档提供以下签名： 
  
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
|hKey [in]  <br/> |打开注册表项的*句柄*。  <br/> |
|lpSubKey [in, optional]  <br/> |要打开的注册表子项的名称。  <br/> |
|ulOptions  <br/> |此为保留参数，且必须为零。  <br/> |
|samDesired [in]  <br/> |指定所需密钥访问权限的掩码。  <br/> |
|phkResult [out]  <br/> |指向接收已打开密钥的句柄的变量的*指针*。  <br/> |
   
在 [Win32API_PtrSafe.txt](https://www.microsoft.com/downloads/details.aspx?displaylang=en&amp;FamilyID=035b72a5-eef9-4baf-8dbc-63fbd2dd982b) 中，**Declare** 语句的定义如下： 
  
```vb
Declare PtrSafe Function RegOpenKeyEx Lib "advapi32.dll" Alias "RegOpenKeyExA" (ByVal hKey As LongPtr , ByVal lpSubKey As String, ByVal ulOptions As Long, ByVal samDesired As Long, phkResult As LongPtr ) As Long
```

#### <a name="should-i-convert-pointers-and-handles-in-structures"></a>是否应在结构中转换指针和句柄？
  
是。 请参阅 Win32API_PtrSafe.txt 中的 **MSG** 类型： 
  
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

#### <a name="when-should-i-use-strptr-varpt-and-objptr"></a>何时应使用 strptr、varpt 和 objptr？
  
应使用这些函数来分别检索指向字符串、变量和对象的指针。 在 64 位版 Office 上，这些函数返回可以传递给 **Declare** 语句的 64 位 **LongPtr**。 与旧版 VBA 相比，这些函数的用法没有改变。 唯一区别是，它们现在返回 **LongPtr**。
  
## <a name="see-also"></a>另请参阅
<a name="odc_office_Compatibility32bit64bit_AdditionalResources"> </a>

- [Declare 语句剖析](https://msdn.microsoft.com/library/office/aa671659.aspx)
    

