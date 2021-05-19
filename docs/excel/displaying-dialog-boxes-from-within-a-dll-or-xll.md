---
title: 显示 DLL 或 XLL 中的对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xlls [excel 2007]， displaying dialog boxes from，dialog boxes [Excel 2007]， displaying from a DLL or XLL，DLL [Excel 2007]， displaying dialog boxes from
localization_priority: Normal
ms.assetid: e77ac555-331d-41c8-a000-7b178959754d
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7b00430b047fe792afef701d210ccde06dd16216
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417866"
---
# <a name="displaying-dialog-boxes-from-within-a-dll-or-xll"></a><span data-ttu-id="a09a6-104">显示 DLL 或 XLL 中的对话框</span><span class="sxs-lookup"><span data-stu-id="a09a6-104">Displaying Dialog Boxes from Within a DLL or XLL</span></span>

 <span data-ttu-id="a09a6-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a09a6-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a09a6-106">若要使用例如 Windows SDK 函数 **DialogBox** 显示 Win32 对话框，必须先获取 Excel 的完整 32 位实例和主窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="a09a6-106">To display a Win32 dialog box using, for example, the Windows SDK function **DialogBox**, you must first obtain the full 32-bit instance and main window handles for Excel.</span></span> <span data-ttu-id="a09a6-107">有关详细信息，请参阅访问 [Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)。</span><span class="sxs-lookup"><span data-stu-id="a09a6-107">For more information, see [Access Excel Instance and Main Window Handles](how-to-access-excel-instance-and-main-window-handles.md).</span></span> 
  
<span data-ttu-id="a09a6-108">假定您的项目包含对话框资源，则必须执行几个步骤，将消息处理例程设置为新显示的对话框的例程，以及当对话框关闭时还原 Excel 邮件处理例程。</span><span class="sxs-lookup"><span data-stu-id="a09a6-108">Assuming your project contains the dialog box resource, you must take several steps to set the message-handling routine to that of the newly displayed dialog box and to restore the Excel message handling routine when the dialog box is closed.</span></span> <span data-ttu-id="a09a6-109">Generic 项目中 [的示例命令 fShowDialog](fshowdialog.md) 演示了如何使用 Windows 函数正确完成此操作。</span><span class="sxs-lookup"><span data-stu-id="a09a6-109">The example command [fShowDialog](fshowdialog.md) in the Generic project demonstrates the use of the Windows functions to do this correctly.</span></span> 
  
<span data-ttu-id="a09a6-110">您还可以使用 C API 显示对话框，而无需使用 Windows SDK 函数。</span><span class="sxs-lookup"><span data-stu-id="a09a6-110">You can also display dialog boxes using the C API without having to use Windows SDK functions.</span></span> <span data-ttu-id="a09a6-111">但是，与 Windows、Visual Basic for Applications (VBA) 或 Microsoft Foundation Classes (MFC) 相比，C API 的对话框功能非常有限。</span><span class="sxs-lookup"><span data-stu-id="a09a6-111">However, the dialog box capabilities of the C API are very limited compared with those of Windows, Visual Basic for Applications (VBA), or the Microsoft Foundation Classes (MFC).</span></span> <span data-ttu-id="a09a6-112"> (例如，C API 对话框始终是模式) 。</span><span class="sxs-lookup"><span data-stu-id="a09a6-112">(For example, C API dialog boxes are always modal).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a09a6-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a09a6-113">See also</span></span>



[<span data-ttu-id="a09a6-114">创建 XLL</span><span class="sxs-lookup"><span data-stu-id="a09a6-114">Creating XLLs</span></span>](creating-xlls.md)
  
[<span data-ttu-id="a09a6-115">开发 DLL</span><span class="sxs-lookup"><span data-stu-id="a09a6-115">Developing DLLs</span></span>](developing-dlls.md)
  
[<span data-ttu-id="a09a6-116">访问 Excel 实例和主窗口句柄</span><span class="sxs-lookup"><span data-stu-id="a09a6-116">Access Excel Instance and Main Window Handles</span></span>](how-to-access-excel-instance-and-main-window-handles.md)
  
[<span data-ttu-id="a09a6-117">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="a09a6-117">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

