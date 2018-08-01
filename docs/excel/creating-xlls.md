---
title: 创建 XLL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
keywords:
- dll [excel 2007]，导入 excel，xlAutoFree 函数 [Excel 2007]，[Excel 2007],xlcall32.lib [Excel 2007]，[Excel 2007],xlcall.cpp [Excel 2007]，xlAutoRemove 函数 [Excel 2007，] xlAddInManagerInfo xlAutoRegister 函数 xlAutoFree12 函数调用函数 [Excel 2007]、 xlAutoAdd 函数 [Excel 2007]、 xlAutoOpen 函数 [Excel 2007]、 xlAutoClose 函数 [Excel 2007，] Dll [Excel 2007] 中，打开到 xll （英文），调用 Excel xlAutoRegister12 函数 [Excel 2007],xlcall.h [Excel Xll [Excel 2007]2007 年]，xlAddInManagerInfo12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 7754998f-4e13-4a37-9724-43b6ee6c919b
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: de347d34768c25adf0d96642b4fade781ae26a9c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773650"
---
# <a name="creating-xlls"></a>创建 XLL

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
如果您的 DLL 是独立或仅依赖其他库，您必须知道如何启用 Microsoft Excel 访问其函数和命令。 有关详细信息，请参阅[在 Excel 中访问 Dll](how-to-access-dlls-in-excel.md)。 
  
但是，如果您的 DLL 需要访问 Excel 功能 （例如，若要获取单元格，调用工作表函数，或询问 Excel 获取工作区信息的内容），您的代码必须能够回调到 Excel。
  
Excel C API 提供了几个启用 Dll 以回调到 Excel 的功能。 若要访问这些，DLL 必须链接静态编译时与 Excel 32 位库，xlcall32.lib。 可下载的 Microsoft Excel 2013 XLL SDK，其中包含 32 位和 64 位版本该库的一部分的 microsoft 静态库。
  
## <a name="enabling-dlls-to-call-back-into-excel"></a>启用呼叫回 Excel Dll

Dll 为能够访问 Excel 中的功能和获取或设置工作区信息，它必须先获得**Excel4**、 **Excel4v**、 **Excel12**和**Excel12v**Excel 回调函数的地址。 最后两个引入 Excel 2007 中，并在以后的版本中可用。 若要访问所有这些，DLL 项目必须包括对以下文件从 Excel 2013 XLL SDK 的引用。 如果您想要访问仅 （中任何版本的 Excel） 的前两个回调，您的项目需要包括仅前两个文件。
  
### <a name="xlcallh"></a>Xlcall.h

Xlcall.h 文件包含以下各项：
  
- 所有的回调函数的函数原型。
    
- 数据类型常量定义和定义回调使用 DLL/XLL 和 Excel 之间交换数据的数据结构。
    
- 定义的工作表、 宏工作表函数和受支持的 Excel 命令的 C API 函数和命令等效。
    
- 定义回调函数的返回值。
    
您应使用 **#include**指令此文件，直接或间接通过的访问 C API 或的处理 C API 使用的数据类型的所有文件中的另一个标头文件。 
  
### <a name="xlcall32lib"></a>Xlcall32.lib

Xlcall32.lib 库将导出的前两个回调时， **Excel4** **Excel4v**，并还**XlCallVer**函数。 不到此库中项目的引用，链接器无法创建 XLL，如果您已在代码中使用任何这些回调。 （您可以获取这些函数的地址的动态链接到复制到您的系统正常 Excel 安装的一部分等效 Xlcall32.dll。） 
  
### <a name="xlcallcpp"></a>Xlcall.cpp

Excel 回调**Excel12**和**Excel12v**不会在 Xlcall32.lib 中导出。 这样可确保您创建从 Excel 2007 XLL 项目还将使用的 Excel 的早期版本。 Xlcall.cpp 模块包含代码的**Excel12**和**Excel12v**函数调用 Excel 条目点开始在 Excel 2007 中，或如果您运行的早期版本的 Excel 返回安全错误值。 如果您想要创建 XLL 启动 Excel 2007 中运行的并且可以使用新的处理较大网格和更长时间的 Unicode 字符串数据类型，应在项目中包括的这一模块。 
  
> [!NOTE]
> 从开始 Excel 2010 SDK，可以为 32 位和 64 位 Xll 编译此文件。 
  
## <a name="turning-dlls-into-xlls-add-in-manager-interface-functions"></a>关闭到 Xll Dll： 加载项管理器界面函数

XLL 是导出多个过程，由 Excel 或 Excel 加载项管理器调用 DLL。 这些过程将此处简要描述和[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)中详细讨论。 所有这些 DLL 回调开始前缀**xlAuto**。 这些命令**xlAutoOpen**中，只有一个是必需的。 调用外接程序激活时，它通常用于将注册 XLL 函数和命令通过 Excel 并执行其他初始化任务。 后面部分中提供的函数签名和示例实现的所有**xlAuto**功能。 
  
即使**xlAutoOpen** ，这些回调只需要的一个加载项可能也需要导出其他人根据其行为。 
  
Excel 2007 中引入的新的数据类型， **XLOPER12**，以容纳更大的网格并支持长 Unicode 字符串。 本主题后面描述**XLOPER12** 。 而**xlAuto**函数执行，或返回旧的数据类型**XLOPER**，这些函数的新版本中引入 Excel 2007 中使用**XLOPER12**数据类型。 除外**xlAutoFree12**，其中您有时必须实现以避免**XLOPER12**内存泄漏，您可以安全地忽略所有版本 12 **xlAuto**功能，在这种情况下，在 Excel 2007 中，Excel 呼叫**XLOPER**启动版本。 
  
### <a name="xlautoopen"></a>xlAutoOpen

每当激活 XLL，Excel 将调用[xlAutoOpen](xlautoopen.md)函数。 外接程序将激活的 Excel 会话的起始处如果它成功，则通常结束的最后一个 Excel 会话中处于活动状态。 外接程序被激活如果 Excel 会话过程中加载。 外接程序可以停用和重新激活 Excel 会话期间，并重新激活调用的函数。 
  
您应使用**xlAutoOpen** XLL 函数和命令注册、 初始化数据结构、 自定义用户界面，等等。 
  
如果加载项实现并将导出[xlAutoRegister](xlautoregister-xlautoregister12.md)函数或[xlAutoRegister12](xlautoregister-xlautoregister12.md)函数，Excel 可能会尝试激活并在不首先调用**xlAutoOpen**函数注册函数或命令。 在这种情况下，您应该确保的加载项已足够初始化函数或命令可以正常运行。 如果不是这样，您应该也会失败尝试注册的函数或命令，或执行必要的初始化。 
  
### <a name="xlautoclose"></a>xlAutoClose

每当在停用 XLL，Excel 将调用[xlAutoClose](xlautoclose.md)函数。 外接程序将被停用时通常 Excel 会话结束。 如果外接程序停用用户 Excel 会话期间，则调用函数。 
  
您应使用**xlAutoClose**注销函数和命令、 释放资源、 撤消自定义项，等等。 
  
> [!NOTE]
> 没有的函数和命令的注销的已知的问题。 有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。 
  
### <a name="xlautoadd"></a>xlAutoAdd

只要用户使用加载项管理器 Excel 会话过程中激活 XLL，Excel 将调用[xlAutoAdd 函数](xlautoadd.md)。 Excel 启动和加载预安装的加载项时，不会调用此函数。 
  
可以使用此函数，以显示自定义对话框中，告知用户的外接程序已被激活，以读取或写入注册表中，或检查许可信息。
  
### <a name="xlautoremove"></a>xlAutoRemove

每当用户将停用 XLL Excel 会话过程中使用加载项管理器，Excel 将调用[xlAutoRemove](xlautoremove.md)函数。 Excel 关闭会话时，通常或异常，与安装的加载项时，不会调用此函数。 
  
您可以使用此函数显示一个自定义的对话框，通知用户外, 接程序已停用，或者从读取或写入到注册表。
  
### <a name="xladdinmanagerinfoxladdinmanagerinfo12"></a>xlAddInManagerInfo/xlAddInManagerInfo12

Excel 会话中第一次调用的加载项管理器时，Excel 将调用[xlAddInManagerInfo](xladdinmanagerinfo-xladdinmanagerinfo12.md)函数。 如果 Excel 将传递参数等于 1，此函数应该返回的字符串 （通常的外接程序的名称）;否则，它应返回 **#VALUE ！**。
  
从 Excel 2007 开始，Excel 调用优先于**xlAddInManagerInfo**函数**xlAddInManagerInfo12**函数的操作，如果它通过 XLL 导出。 **XlAddInManagerInfo12**函数应都以相同的方式为**xlAddInManagerInfo**函数以避免 XLL 的行为的特定于版本的差异。 **XlAddInManagerInfo12**函数应返回**XLOPER12**数据类型，而**xlAddInManagerInfo**函数应返回**XLOPER**数据类型。 
  
### <a name="xlautoregisterxlautoregister12"></a>xlAutoRegister/xlAutoRegister12

Excel 调用[xlAutoRegister](xlautoregister-xlautoregister12.md)函数，只要呼叫已**注册**，XLM 函数或 C API 等效[xlfRegister](xlfregister-form-1.md)函数，返回到和缺少要所注册的函数的参数类型。 使用**xlAutoRegister**功能，XLL 搜索其内部导出的函数和命令来注册功能使用参数并返回指定的类型的列表。 
  
从 Excel 2007 开始，Excel 调用优先于**xlAddInRegister**函数**xlAddInRegister12**函数的操作，如果它通过 XLL 导出。 
  
> [!NOTE]
> 如果**xlAddInRegister**/ **xlAddInRegister12**尝试函数注册无需提供参数和返回类型，调用循环递归发生的最终溢出 call 堆栈并使 Excel 关闭或停止响应。 
  
### <a name="xlautofreexlautofree12"></a>xlAutoFree/xlAutoFree12

Excel XLL 工作表函数返回**XLOPER**后立即调用[xlAutoFree/xlAutoFree12](xlautofree-xlautofree12.md)函数/ **XLOPER12**数据类型设置一个标志来告知 Excel XLL 仍需要释放的内存。 这样，XLL 返回动态分配数组、 字符串和不内存泄漏工作表的外部引用。 从 Excel 2007 开始，支持**XLOPER12**数据类型。 有关详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。
  
> [!NOTE]
> 从 Excel 2007 开始，当 Excel 配置为使用多线程的工作表重新计算， **xlAutoFree**/ **xlAutoFree12**函数调用只用于调用的函数的返回它的同一线程。 调用**xlAutoFree**/ **xlAutoFree12**始终进行更改之前在该线程上进行评估任何后续的工作表的单元格。 这样可简化您 XLL 中的线程安全设计。 有关详细信息，请参阅[在 Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)。 
  
### <a name="creating-64-bit-xlls"></a>创建 64-bit xll （英文）

Excel 和用户定义的函数可以充分利用性能优点 32 位操作系统上的 64 位操作系统上运行。 Excel 中包含的数据的类型信息的**XLOPER12**结构传递值。 **XLOPER12**结构中的值与本机类型，如**int**或指针以保留中更大的类型的值之间进行转换时应谨慎。 
  
## <a name="see-also"></a>另请参阅



[从函数向导或替换对话框调用 XLL 函数](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
  
[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)
  
[Developing Excel XLLs](developing-excel-xlls.md)

