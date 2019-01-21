---
title: 创建 XLL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
keywords:
- dlls [excel 2007], 调用 excel, xlAutoFree 函数 [Excel 2007], xlAutoFree12 函数 [Excel 2007], xlcall32.lib [Excel 2007], xlAutoRegister 函数 [Excel 2007], xlcall.cpp [Excel 2007], xlAutoRemove 函数 [Excel 2007], xlAddInManagerInfo 函数 [Excel 2007], xlAutoAdd 函数 [Excel 2007], xlAutoOpen 函数 [Excel 2007], xlAutoClose 函数 [Excel 2007], DLLs [Excel 2007], 转换为 XLLs, XLLs [Excel 2007], 调用 Excel, xlAutoRegister12 函数 [Excel 2007], xlcall.h [Excel 2007], xlAddInManagerInfo12 函数 [Excel 2007]
ms.assetid: 7754998f-4e13-4a37-9724-43b6ee6c919b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: 886b8e74f00f2e724785d43475ee0ffa3c922710
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706742"
---
# <a name="creating-xlls"></a>创建 XLL

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
如果 DLL 是独立的或者依赖于其他库，则必须知道如何支持 Microsoft Excel 访问其函数和命令。 有关详细信息，请参阅 [在 Excel 中的访问 DLL](how-to-access-dlls-in-excel.md)。 
  
但是，如果 DLL 需要访问 Excel 功能（例如，获取单元格的内容、调用工作表函数或询问 Excel 以获取工作区信息），则代码必须能够回调至 Excel。
  
Excel C API 提供了多个支持 DLL 回调至 Excel 的函数。 若要访问这些函数，必须在编译时将 DLL 静态链接至 Excel 32 位库 xlcall32.lib。 静态库可作为 Microsoft Excel 2013 XLL SDK 的一部分从 Microsoft 下载，其中包括 32 位和 64 位版本的静态库。
  
## <a name="enabling-dlls-to-call-back-into-excel"></a>支持 DLL 回调至 Excel

若要使 DLL 能够访问 Excel 中的功能并获取或设置工作区信息，必须先获取 Excel 回调函数 **Excel4**、**Excel4v**、**Excel12** 和 **Excel12v** 的地址。 最后两个回调函数是在 Excel 2007 中引入的，可用于后续版本中。 若要访问所有这些函数，DLL 项目必须包括对 Excel 2013 XLL SDK 中的以下文件的引用。 如果想要仅访问前两个回调函数（在任何版本的 Excel 中），则项目必须仅包括前两个文件。
  
### <a name="xlcallh"></a>Xlcall.h

Xlcall.h 文件包含以下项：
  
- 所有回调函数的函数属性。
    
- 回调函数用于交换 DLL/XLL 与 Excel 之间的数据的数据结构定义，以及数据类型常量定义。
    
- 工作表的 C API 函数和命令等效项、宏工作表函数和受支持的 Excel 命令的定义。
    
- 回调函数返回值的定义。
    
应直接或间接通过用于访问 C API 或处理 C API 所使用数据类型的所有文件中的其他头文件，使用此文件的 **#include** 指令。 
  
### <a name="xlcall32lib"></a>Xlcall32.lib

Xlcall32.lib 库将导出前两个回调函数 **Excel4** 和 **Excel4v** 以及 **XlCallVer** 函数。 如果项目没有至此库的引用，当已在代码中使用任意上述回调函数时，链接器无法创建 XLL。 （可以获取这些函数的地址，方法是动态链接至等效 Xlcall32.dll，后者已作为正常 Excel 安装的一部分复制到系统。） 
  
### <a name="xlcallcpp"></a>Xlcall.cpp

Excel 回调函数 **Excel12** 和 **Excel12v** 不会在 Xlcall32.lib 中导出。 这可确保自 Excel 2007 起创建的 XLL 项目同样也适用于更早版本的 Excel。 Xlcall.cpp 模块包含 **Excel12** 和 **Excel12v** 函数代码，这些函数将调用至 Excel 入口点（从 Excel 2007 起），或者在运行更早版本的 Excel 时返回安全错误值。 如果想要创建的 XLL 能够在 Excel 2007 及之后的 Excel 版本中运行并且能够使用可处理较大网格和更长 Unicode 字符串的新数据类型，应在项目中包含此模块。 
  
> [!NOTE]
> 从 Excel 2010 SDK 起，可以针对 32 位和 64 位 XLL 编译此文件。 
  
## <a name="turning-dlls-into-xlls-add-in-manager-interface-functions"></a>将 DLL 转换为 XLL：加载项管理器接口函数

XLL 是一种可导出多个程序的 DLL，这些程序供 Excel 或 Excel 加载项管理器调用。 此处简要介绍了这些程序，[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)中将会对它们进行详细介绍。 所有这些 DLL 回调函数均以前缀 **xlAuto** 开头。 只有其中一种需要命令 **xlAutoOpen**。 在激活加载项时将会调用此命令，它通常用于使用 Excel 注册 XLL 函数和命令以及执行其他初始化任务。 后面的章节中提供了所有 **xlAuto** 函数的函数签名和示例实施。 
  
即便只有其中一种回调函数需要 **xlAutoOpen** 命令，加载项也可能需要基于其行为导出其他项。 
  
Excel 2007 中引入了新的数据类型 **XLOPER12**，以适应更大的网格和支持 Unicode 长字符串。 本主题后面介绍了 **XLOPER12**。 尽管 **xlAuto** 函数采用或返回旧数据类型 **XLOPER**，在 Excel 2007 中引入的新版函数将使用 **XLOPER12** 数据类型。 除了 **xlAutoFree12** 外（有时必须使用它来避免 **XLOPER12** 内存泄漏），你可以放心地省略所有版本 12 **xlAuto** 函数，因为在此情况下，Excel 2007 及以后版本的 Excel 将会调用 **XLOPER** 版本。 
  
### <a name="xlautoopen"></a>xlAutoOpen

激活 XLL 时，Excel 将会调用 [xlAutoOpen](xlautoopen.md) 函数。 如果加载项在正常结束的最后一个 Excel 会话中处于活动状态，则会在 Excel 会话开始时激活该加载项。 在 Excel 会话期间加载加载项也会将其加载。 可以在 Excel 会话期间停用和重新激活加载项，并且将在重新激活时调用函数。 
  
应使用 **xlAutoOpen** 注册 XLL 函数和命令，初始化数据结构，自定义用户界面等等。 
  
如果加载项实施和导出 [xlAutoRegister](xlautoregister-xlautoregister12.md) 函数或 [xlAutoRegister12](xlautoregister-xlautoregister12.md) 函数，则 Excel 可能会尝试激活和注册函数和命令，而不先调用 **xlAutoOpen** 函数。 在此情况下，应确保充分初始化加载项，以便函数或命令正常运行。 如果未充分初始化，则尝试注册函数或命令或者执行必要初始化将会失败。 
  
### <a name="xlautoclose"></a>xlAutoClose

停用 XLL 时，Excel 将调用 [xlAutoClose](xlautoclose.md) 函数。 当 Excel 会话正常结束时，将会停用加载项。 如果用户在 Excel 会话期间停用加载项，则会调用函数。 
  
应使用 **xlAutoClose** 注销函数和命令，发布资源，撤销自定义项等等。 
  
> [!NOTE]
> 注销函数和命令时存在一个已知问题。 有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。 
  
### <a name="xlautoadd"></a>xlAutoAdd

在 Excel 会话期间，如果用户使用加载项管理器激活 XLL，则 Excel 将调用 [xlAutoAdd](xlautoadd.md) 函数。 当 Excel 启动并加载预安装的加载项时，不会调用此函数。 
  
可以使用此函数来显示用于通知用户加载项已激活的自定义对话框、读取或写入注册表或者检查许可信息。
  
### <a name="xlautoremove"></a>xlAutoRemove

在 Excel 会话期间，如果用户使用加载项管理器停用 XLL，则 Excel 将调用 [xlAutoRemove](xlautoremove.md) 函数。 如果在已安装加载项的情况下 Excel 会话正常或异常关闭，则不会调用此函数。 
  
可以使用此函数来显示用于通知用户加载项已停用的自定义对话框，或者读取或写入注册表。
  
### <a name="xladdinmanagerinfoxladdinmanagerinfo12"></a>xlAddInManagerInfo/xlAddInManagerInfo12

在 Excel 会话中首次调用加载项管理器时，Excel 将调用 [xlAddInManagerInfo](xladdinmanagerinfo-xladdinmanagerinfo12.md) 函数。 如果 Excel 传递一个等于 1 的参数，则此函数应返回一个字符串（通常为加载项的名称）；否则，它将返回 **#VALUE!**。
  
从 Excel 2007 起，如果 Excel 是通过 XLL 导出，则它将优先调用 **xlAddInManagerInfo12** 函数，而不是 **xlAddInManagerInfo** 函数。 **xlAddInManagerInfo12** 函数的工作方式应与 **xlAddInManagerInfo** 函数相同，以免在 XLL 行为中出现特定于版本的差异。 **xlAddInManagerInfo12** 函数应返回 **XLOPER12** 数据类型，而 **xlAddInManagerInfo** 函数应返回 **XLOPER** 数据类型。 
  
### <a name="xlautoregisterxlautoregister12"></a>xlAutoRegister/xlAutoRegister12

如果已调用 XLM 函数 **REGISTER** 或 C API [xlfRegister](xlfregister-form-1.md) 等效函数，且注册的函数中缺少返回值和参数类型，则 Excel 将调用 [xlAutoRegister](xlautoregister-xlautoregister12.md) 函数。 **xlAutoRegister** 函数允许 XLL 搜索其内部的已导出函数和命令列表，以注册带有参数的函数和返回指定类型。 
  
从 Excel 2007 起，如果 Excel 是通过 XLL 导出，则它将优先调用 **xlAddInRegister12** 函数，而不是 **xlAddInRegister** 函数。 
  
> [!NOTE]
> 如果 **xlAddInRegister**/ **xlAddInRegister12** 尝试注册函数而不提供参数和返回值类型，则会发生递归调用循环，这最终会溢出调用堆栈并导致 Excel 关闭或停止响应。 
  
### <a name="xlautofreexlautofree12"></a>xlAutoFree/xlAutoFree12

在 XLL 工作表函数返回 **XLOPER**/ **XLOPER12** 数据类型后，如果显示了通知 Excel XLL 仍需释放内存的标志集时，则 Excel 将调用 [xlAutoFree/xlAutoFree12](xlautofree-xlautofree12.md) 函数。 这将会使 XLL 动态返回已分配的数组、字符串以及没有内部泄漏的工作表的外部引用。 从 Excel 2007 起，**XLOPER12** 数据类型受支持。 有关详细信息，请参阅 [Excel 中的内存管理](memory-management-in-excel.md)。
  
> [!NOTE]
> 从 Excel 2007 起，如果 Excel 已配置为使用多线程工作表重新计算，则会在刚用于调用所返回函数的函数的相同线程上调用 **xlAutoFree**/ **xlAutoFree12** 函数。 在对该线程上的任何后续工作表单元格进行求值之前，始终调用 **xlAutoFree**/ **xlAutoFree12**。 这可以简化 XLL 中的线程安全设计。 有关详细信息，请参阅 [Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)。 
  
### <a name="creating-64-bit-xlls"></a>创建 64 位 XLL

Excel 和用户定义的函数可在 64 位操作系统上运行，以充分利用 32 位操作系统所没有的性能优势。 Excel 将传递其中包含有关数据类型信息的 **XLOPER12** 结构中的值。 转换 **XLOPER12** 结构与本机类型（如 **int** 或指针）之间的值以保留更大类型的值时，请务必谨慎。 
  
## <a name="see-also"></a>另请参阅



[从“函数向导”或“替换”对话框调用 XLL 函数](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
  
[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)
  
[开发 Excel XLL](developing-excel-xlls.md)

